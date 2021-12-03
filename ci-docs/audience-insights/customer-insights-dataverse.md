---
title: Customer Insights-data i Microsoft Dataverse
description: Brug Customer Insights-objekter som tabeller i Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866927"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Arbejde med Customer Insights-data i Microsoft Dataverse

Customer Insights giver mulighed for at gøre outputobjekter tilgængelige i [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Denne integration muliggør nem datadeling og brugerdefineret udvikling gennem en tilgang med næste ingen kode/ingen kode. Outputobjekterne vil være tilgængelige som tabeller i Dataverse. Disse tabeller muliggør scenarier som [automatiserede arbejdsprocesser via Power Automate](/power-automate/getting-started), [modelbaserede apps](/powerapps/maker/model-driven-apps/) og [lærredapps](/powerapps/maker/canvas-apps/) via Power Apps. Du kan bruge dataene til alle andre applikationer, der er baseret på Dataverse-tabeller. Den aktuelle implementering understøtter hovedsageligt opslag, hvor data fra de tilgængelige målgruppeindsigtsobjekter kan hentes for et givet kunde-id.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Knytte et Dataverse-miljø til Customer Insights

**Organisationer med eksisterende Dataverse-miljøer**

Organisationer, der allerede bruger Dataverse, kan bruge et af deres [eksisterende Dataverse-miljøer](create-environment.md), når en administrator konfigurerer målgruppeindsigt. Når du angiver URL-adressen til Dataverse-miljøet, knyttes den til deres nye målgruppeindsigtsmiljø. Customer Insights- og Dataverse-miljøer skal hostes i samme område for at sikre den bedst mulige ydeevne.

**Ny organisation**

Hvis du opretter en ny organisation, når du konfigurerer Customer Insights, får du automatisk et nyt Dataverse-miljø.

> [!NOTE]
> Hvis dine organisationer allerede bruger Dataverse i deres lejer, er det vigtigt at huske, at [oprettelsen af Dataverse-miljøet styres af en administrator](/power-platform/admin/control-environment-creation.md). Hvis du f.eks. konfigurerer et nyt målgruppeindsigtsmiljø med din organisationskonto, og administratoren har deaktiveret oprettelsen af Dataverse-prøvemiljøer for alle undtagen administratorer, kan du ikke oprette et nyt prøvemiljø.
> 
> De Dataverse-prøvemiljøer, der er oprettet i Customer Insights, har 3 GB lagerplads, som ikke tæller med i den samlede kapacitet, der er berettiget til lejeren. Betalte abonnementer får Dataverse-berettigelse til 15 GB til database og 20 GB til fillagring.

## <a name="output-entities"></a>Outputobjekter

Nogle outputobjekter fra målgruppeindsigt er tilgængelige som tabeller i Dataverse. Afsnittene nedenfor beskriver det forventede skema for disse tabeller.

- [Kundeprofil](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Forbedring](#enrichment)
- [Forudsigelse](#prediction)
- [Segmentmedlemskab](#segment-membership)


### <a name="customerprofile"></a>Kundeprofil

Denne tabel indeholder den samlede kundeprofil fra Customer Insights. Skemaet for en samlet kundeprofil afhænger af de objekter og attributter, der bruges i fletteprocessen. Et kundeprofilskema indeholder normalt et undersæt af attributterne fra [Common Data Model-definitionen i CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabellen AlternateKey indeholder nøgler til de objekter, der deltog i den samlende proces.

|Column  |Skriv  |Beskrivelse  |
|---------|---------|---------|
|DataSourceName    |String         | Navnet på datakilden. Eksempel: `datasource5`        |
|EntityName        | String        | Navnet på objektet i målgruppeindsigt. Eksempel: `contact1`        |
|AlternateValue    |String         |Alternativt id, der er knyttet til kunde-id'et. Eksempel: `cntid_1078`         |
|KeyRing           | Tekst med flere linjer        | JSON-værdi  </br> Eksempel: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | Id for den samlede kundeprofil.         |
|AlternateKeyId     | GUID         |  Deterministisk AlternateKey-GUID baseret på msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Eksempel: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Denne tabel indeholder aktiviteter udført af brugere, der er tilgængelige i Customer Insights.

| Column            | Skriv        | Beskrivelse                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Kundeprofil-id                                                                      |
| ActivityId        | String      | Internt id for kundeaktiviteten (primær nøgle)                                       |
| SourceEntityName  | String      | Navn på kildeobjektet                                                                |
| SourceActivityId  | String      | Primær nøgle fra kildeobjektet                                                       |
| ActivityType      | String      | Semantisk aktivitetstype eller navnet på brugerdefineret aktivitet                                        |
| ActivityTimeStamp | DATETIME    | Tidsstempel for aktivitet                                                                      |
| Titel             | String      | Aktivitetens titel eller navn                                                               |
| Beskrivelse       | String      | Beskrivelse af aktivitet                                                                     |
| URL-adresse               | String      | Link til en ekstern URL-adresse, der er specifik for aktiviteten                                         |
| SemanticData      | JSON-streng | Indeholder en liste over nøgleværdipar for semantiske tilknytningsfelter, der er specifikke for aktivitetstypen |
| RangeIndex        | String      | Unix-tidsstempel, der bruges til sortering af aktivitetstidslinjer og forespørgsler med effektive områder |
| mydynci_unifiedactivityid   | GUID | Internt id for kundeaktiviteten (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Denne tabel indeholder outputdata for kundeattributbaserede målpunkter.

| Column             | Skriv             | Beskrivelse                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Kundeprofil-id        |
| Målinger           | JSON-streng      | Indeholder en liste over nøgleværdipar for målpunktsnavn og værdier for den givne kunde | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Kundeprofil-id |


### <a name="enrichment"></a>Forbedring

Denne tabel indeholder resultatet af forbedringsprocessen.

| Column               | Skriv             |  Beskrivelse                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Kundeprofil-id                                 |
| EnrichmentProvider   | String           | Navnet på udbyderen af forbedringen                                  |
| EnrichmentType       | String           | Type af forbedring                                      |
| Værdier               | JSON-streng      | Liste over attributter, der er produceret af forbedringsprocessen |
| msdynci_enrichmentid | GUID             | Deterministisk GUID genereret fra msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Forudsigelse

Denne tabel indeholder resultatet af modelforudsigelserne.

| Column               | Skriv        | Beskrivelse                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Kundeprofil-id                                  |
| ModelProvider        | String      | Navnet på udbyderen af modellen                                      |
| Model                | String      | Modelnavn                                                |
| Værdier               | JSON-streng | Liste over attributter, der er produceret af modellen |
| msdynci_predictionid | GUID        | Deterministisk GUID genereret fra msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmentmedlemskab

Denne tabel indeholder oplysninger om kundeprofilerne vedrørende segmentmedlemskaber.

| Column        | Skriv | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Kundeprofil-id        |
| SegmentProvider      | String       | App, der udgiver segmenterne. Standard: Målgruppeindsigt         |
| SegmentMembershipType | String       | Kundetype for denne segmentmedlemspost. Understøtter flere typer, f.eks. Kunde, Kontakt eller Firma. Standard: Kunde  |
| Segmenter       | JSON-streng  | Liste over entydige segmenter, som kundeprofilen er medlem af      |
| msdynci_identifier  | String   | Entydigt id for segmentmedlemspost. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministisk GUID, der er genereret fra `msdynci_identifier`          |
