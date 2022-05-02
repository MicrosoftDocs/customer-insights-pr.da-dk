---
title: Customer Insights-data i Microsoft Dataverse
description: Brug Customer Insights-objekter som tabeller i Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 85995cbd7f797810bfb6ecdc8a24d56542f0b5a9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646026"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Arbejde med Customer Insights-data i Microsoft Dataverse

Customer Insights giver mulighed for at gøre outputobjekter tilgængelige i [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Denne integration muliggør nem datadeling og brugerdefineret udvikling gennem en tilgang med næste ingen kode/ingen kode. [Outputobjekterne](#output-entities) er tilgængelige som tabeller i et Dataverse-miljø. Du kan bruge dataene til et hvilket som helst andet program baseret på Dataverse-tabeller. Disse tabeller muliggør scenarier som automatiserede arbejdsprocesser via Power Automate eller opbygning af apps med Power Apps. Den aktuelle implementering understøtter primært opslag, hvor data fra de tilgængelige Customer Insights-objekter kan hentes til et bestemt kunde-id.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Knytte et Dataverse-miljø til Customer Insights

**Eksisterende organisation**

Administratorer kan konfigurere Customer Insights til at [bruge et eksisterende Dataverse-miljø](create-environment.md), når de opretter et Customer Insights-miljø. Når du angiver webadressen til Dataverse-miljøet, knyttes den til deres nye Customer Insights-miljø. Customer Insights og Dataverse-miljøer skal hostes i det samme område. 

Hvis du ikke vil bruge et eksisterende Dataverse-miljø, oprettes der et nyt miljø for Customer Insights-dataene i din lejer. 

> [!NOTE]
> Hvis organisationerne allerede bruger Dataverse i deres lejer, er det vigtigt at huske på, at [Dataverse-miljøoprettelse styres af en administrator](/power-platform/admin/control-environment-creation). Hvis du f.eks. konfigurerer et nyt Customer Insights-miljø med din organisationskonto, og administratoren har deaktiveret oprettelsen af Dataverse-prøvemiljøer for alle undtagen administratorer, kan du ikke oprette et nyt prøvemiljø.
> 
> De Dataverse-prøvemiljøer, der er oprettet i Customer Insights, har 3 GB lagerplads, som ikke tæller med i den samlede kapacitet, der er berettiget til lejeren. Betalte abonnementer får Dataverse-berettigelse til 15 GB til database og 20 GB til fillagring.

**Ny organisation**

Hvis du opretter en ny organisation, når du konfigurerer Customer Insights, oprettes der automatisk et nyt Dataverse-miljø i organisationen for dig.

## <a name="output-entities"></a>Outputobjekter

Nogle outputobjekter fra Customer Insights er tilgængelige som tabeller i Dataverse. Afsnittene nedenfor beskriver det forventede skema for disse tabeller.

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
|EntityName        | String        | Navnet på objektet i Customer Insights. Eksempel: `contact1`        |
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
| SegmentProvider      | String       | App, der udgiver segmenterne.      |
| SegmentMembershipType | String       | Kundetype for denne segmentmedlemspost. Understøtter flere typer, f.eks. Kunde, Kontakt eller Firma. Standard: Kunde  |
| Segmenter       | JSON-streng  | Liste over entydige segmenter, som kundeprofilen er medlem af      |
| msdynci_identifier  | String   | Entydigt id for segmentmedlemspost. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministisk GUID, der er genereret fra `msdynci_identifier`          |
