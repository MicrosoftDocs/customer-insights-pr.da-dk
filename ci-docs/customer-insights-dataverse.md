---
title: Arbejde med Customer Insights-data i Microsoft Dataverse
description: Få mere at vide om, hvordan du opretter forbindelse mellem Customer Insights og Microsoft Dataverse, og forstå de outputobjekter, der eksporteres til Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424302"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Arbejde med Customer Insights-data i Microsoft Dataverse

Customer Insights giver mulighed for at gøre outputobjekter tilgængelige i [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Denne integration muliggør nem datadeling og brugerdefineret udvikling gennem en tilgang med næste ingen kode/ingen kode. [Outputobjekterne](#output-entities) er tilgængelige som tabeller i et Dataverse-miljø. Du kan bruge dataene til et hvilket som helst andet program baseret på Dataverse-tabeller. Disse tabeller muliggør scenarier som automatiserede arbejdsprocesser via Power Automate eller opbygning af apps med Power Apps.

Hvis du opretter forbindelse til Dataverse-miljøet, kan du også [indtage data fra det lokale miljø datakilder ved hjælp af Power Platform-dataflow og gateways](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Forudsætninger

- Customer Insights og Dataverse-miljøer skal hostes i det samme område.
- En opsætning af en global administratorrolle i Dataverse-miljøet. Kontrollér, om dette [Dataverse-miljø er knyttet](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) til visse sikkerhedsgrupper, og kontrollér, at du er føjet til de pågældende sikkerhedsgrupper.
- Der er ikke allerede knyttet andre Customer Insights-miljøer til det Dataverse-miljø, du vil oprette forbindelse til. Få mere at vide om , hvordan du [fjerner en eksisterende forbindelse til et Dataverse-miljø](#remove-an-existing-connection-to-a-dataverse-environment).
- Et Microsoft Dataverse,miljø, der er knyttet til en enkelt lagerkonto, hvis du konfigurerer miljøet til at [bruge dit Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse-lagerkapacitetsberettigelse

Et Customer Insights-abonnement giver dig mulighed for ekstra kapacitet til organisationens eksisterende [Dataverse-lagerkapacitet](/power-platform/admin/capacity-storage). Den tilføjede kapacitet afhænger af antallet af profiler, som bruges i abonnementet.

**Eksempel:**

Hvis du får 15 GB databaselager og 20 GB fillager pr. 100.000 kundeprofiler. Hvis dit abonnement omfatter 300.000 kundeprofiler, er din samlede lagerkapacitet 45 GB (3 x 15 GB) databaselager og 60 GB fillager (3 x 20 GB). Hvis du har et B-til-B-abonnement med 30.000 konti, er din samlede lagerkapacitet på 45 GB (3 x 15 GB) databaselager og 60 GB fillager (3 x 20 GB).

Logkapaciteten er ikke trinvis og fast for organisationen.

Du kan finde flere oplysninger om detaljerede kapacitetsberettigelser i [Licensguide til Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Oprette forbindelse mellem et Dataverse-miljø og Customer Insights

I **Microsoft Dataverse**-trinnet kan du knytte Customer Insights til dit Dataverse-miljø, mens du [opretter et Customer Insights-miljø](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="-datadeling med Microsoft Dataverse er automatisk aktiveret for nye miljøer.":::

1. Angiv URL-adressen til dit Dataverse-miljø, eller lad den være tom, så der oprettes en adresse til dig.

   > [!NOTE]
   > Når du har etableret forbindelsen mellem Customer Insights og Dataverse, skal du ikke ændre organisationsnavnet for Dataverse-miljøet. Navnet på organisationen bruges i Dataverse URL-adressen, og et ændret navn ødelægger forbindelsen til Customer Insights.

   [Power Platform-administratorer kan styre, hvem der kan oprette nye Dataverse-miljøer](/power-platform/admin/control-environment-creation). Når du forgæves forsøger at konfigurere et nyt Customer Insights-miljø, kan administratoren have deaktiveret oprettelse af Dataverse-miljøer for alle undtagen administratorer.

1. Hvis du bruger din egen Data Lake Storage-konto:
   1. Vælg **Aktivér datadeling** med Dataverse.
   1. Angiv **Tilladelses-id**. Du kan få tilladelses-id ved at [aktivere datadeling med Dataverse fra dit eget Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Aktivere datadeling med Dataverse fra dit eget Azure Data Lake Storage (forhåndsversion)

I [din egen Azure Data Lake Storage-konto](own-data-lake-storage.md), skal du få bekræftet, at den bruger, der konfigurerer Customer Insights-miljøet, som minimum har **Læser af Blob Data-lager**-tilladelser til `customerinsights`-objektbeholderen i lagerkontoen.

### <a name="limitations"></a>Begrænsninger

- Kun en til en-tilknytning mellem en Dataverse-organisation og en Azure Data Lake Storage-konto. Når en Dataverse-organisation er knyttet til en lagerkonto, kan den ikke oprette forbindelse til en anden lagerkonto. Denne begrænsning forhindrer Dataverse i at udfylde flere lagerkonti.
- Datadeling fungerer ikke, hvis en konfiguration af Azure Private Link er nødvendig for at få adgang til din Azure Data Lake Storage-konto, da den er bag en firewall. Dataverse understøtter i øjeblikket ikke forbindelsen til private slutpunkter via Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Konfigurere sikkerhedsgrupper på din egen Azure Data Lake Storage

1. Opret to sikkerhedsgrupper i dit Azure-abonnement – en **Læser**-sikkerhedsgruppe og en **bidragyder**-sikkerhedsgruppe, og angiv Microsoft Dataverse-tjenesten som ejer for begge sikkerhedsgrupper.

1. Administrer ACL (Access Control List) på `customerinsights`-beholderen på din lagerkonto via disse sikkerhedsgrupper.
   1. Tilføj tjenesten Microsoft Dataverse og alle Dataverse-baserede virksomhedsprogrammer, f.eks. Dynamics 365 Marketing til **Læser**-sikkerhedsgruppen med **skrivebeskyttede** tilladelser.
   1. Tilføj *kun* programmet Customers Insights til sikkerhedsgruppen **Bidragyder** for at give både **læse- og skrivetilladelser** til at skrive profiler og indsigt.

### <a name="set-up-powershell"></a>Konfigurere PowerShell

Konfigurer PowerShell til at udføre PowerShell-scripts.

1. Installer den nyeste version af [Azure Active Directory PowerShell til Graph](/powershell/azure/active-directory/install-adv2).
   1. På din pc skal du vælge Windows-tasten på tastaturet og søge efter **Windows PowerShell** og vælge **Kør som administrator**.
   1. I det PowerShell-vindue, der åbnes, skal du skrive `Install-Module AzureAD`.

1. Importér tre moduler.
   1. Skriv `Install-Module -Name Az.Accounts` i PowerShell-vinduet, og følg trinnene.
   1. Gentag for `Install-Module -Name Az.Resources` og `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Udfør PowerShell-scripts, og hent tilladelses-id'et

1. Hent de to PowerShell-scripts, du skal bruge for at køre fra vores udviklers [GitHub-repo](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Kræver lejeradministratortilladelser.
   - `ByolSetup.ps1`: Kræver tilladelser som Ejer af Blob Data-lager på lagerkonto/beholderniveau. Du kan bruge dette script til at oprette tilladelsen for dig. Rolletildelingen kan fjernes manuelt, når scriptet er kørt korrekt.

1. Udfør `CreateSecurityGroups.ps1` i Windows PowerShell ved at angive det Azure-abonnements-id, der indeholder dit Azure Data Lake Storage. Åbn PowerShell-scriptet i en editor for at gennemse flere oplysninger og den implementerede logik.

   Med dette script oprettes der to sikkerhedsgrupper i dit Azure-abonnement: én for Læser-gruppen og en anden for Bidragyder-gruppen. Microsoft Dataverse-tjenesten er ejer af begge disse sikkerhedsgrupper.

1. Gem begge id-værdier for sikkerhedsgrupper, der er genereret med dette script, for at bruge dem i `ByolSetup.ps1`-scriptet.

   > [!NOTE]
   > Oprettelse af sikkerhedsgrupper kan deaktiveres for lejeren. I det tilfælde skal du konfigurere manuelt, og din Azure AD-administrator skal aktivere[ oprettelse af sikkerhedsgruppe](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Kør `ByolSetup.ps1` i Windows PowerShell ved at angive det Azure-abonnements-id, der indeholder dit Azure Data Lake Storage, navnet på din lagerkonto, navnet på ressourcegruppen og id for Læser- og Bidragyder-sikkerhedsgruppen. Åbn PowerShell-scriptet i en editor for at gennemse flere oplysninger og den implementerede logik.

   Dette script tilføjer det påkrævede rollebaserede adgangskontrolelement for Microsoft Dataverse-tjenesten og alle Dataverse-baserede virksomhedsprogrammer. Den opdaterer også ACL (Access Control List) i `customerinsights`-beholderen for de sikkerhedsgrupper, der er oprettet med scriptet `CreateSecurityGroups.ps1`. Gruppen Bidragyder har kun *rwx*-tilladelsen, og gruppen Læsere har kun *r-x*-tilladelsen.

1. Kopiér outputstrengen, der ser således ud: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Angiv den kopierede outputstreng i feltet **Tilladelser-id** i trinnet til miljøkonfiguration for Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurationsindstillinger, der gør det muligt at dele data direkte fra det eget Azure Data Lake Storage med Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Fjern en eksisterende forbindelse til et Dataverse-miljø

Når der oprettes forbindelse til et Dataverse-miljø, betyder fejlmeddelelsen **Denne CDS-organisation er allerede knyttet til en anden forekomst af Customer Insights**, at Dataverse-miljøet allerede er brugt i et Customer Insights-miljø. Du kan fjerne den eksisterende forbindelse som en global administrator i Dataverse-miljøet. Det kan tage et par timer at udfylde ændringerne.

1. Gå til [Power Apps](https://make.powerapps.com).
1. Vælg miljøet på miljøvælgeren.
1. Gå til **Løsninger**.
1. Fjern eller slet løsningen med navnet **Dynamics 365 Customer Insights Kundekort-tilføjelsesprogrammet (forhåndsversion)**.

ELLER

1. Åbn dit Dataverse-miljø.
1. Gå til **Avancerede indstillinger** > **Løsninger**.
1. Fjern løsningen **CustomerInsightsCustomerCard**.

Hvis det ikke lykkes at fjerne forbindelsen på grund af afhængigheder, skal du også fjerne afhængighederne. Du kan finde flere oplysninger under [Fjernelse af afhængigheder](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Outputobjekter

Nogle outputobjekter fra Customer Insights er tilgængelige som tabeller i Dataverse. Afsnittene nedenfor beskriver det forventede skema for disse tabeller.

- [Kundeprofil](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Forbedring](#enrichment)
- [Forudsigelse](#prediction)
- [Segmentmedlemskab](#segment-membership)

### <a name="customerprofile"></a>Kundeprofil

Denne tabel indeholder unified customer profile fra Customer Insights. Skemaet for en unified customer profile afhænger af de objekter og attributter, der bruges i data samlingsprocessen. Et kundeprofilskema indeholder normalt et undersæt af attributterne fra [Common Data Model-definitionen i CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). I B-til-B-scenariet indeholder kundeprofilen samlede konti, og skemaet indeholder som regel et delsæt af attributterne fra [definitionen af Common Data Model-konto](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

En ContactProfile indeholder samlede oplysninger om en kontakt. Kontakter er [enkeltpersoner, der er knyttet til en firmakonto](data-unification-contacts.md) i et B-til-B-scenario.

| Kolonne                       | Type                | Beskrivelse     |
| ---------------------------- | ------------------- | --------------- |
|  BirthDate            | DateTime       |  Kontaktens fødselsdato               |
|  City                 | Tekst |  Kontaktadressens by               |
|  ContactId            | Tekst |  Id for kontaktprofilen               |
|  ContactProfileId     | Entydigt id   |  GUID for kontakten               |
|  CountryOrRegion      | Tekst |  Land/område for kontaktadressen               |
|  CustomerId           | Tekst |  Id'et for den firmakonto, kontakten er knyttet til               |
|  EntityName           | Tekst |  Det objekt, som data kommer fra                |
|  FirstName            | Tekst |  Kontaktens fornavn               |
|  Gender               | Tekst |  Kontaktpersonens køn               |
|  Id                   | Tekst |  Deterministisk GUID baseret på `Identifier`               |
|  Identifier           | Tekst |  Internt id for kontaktprofilen: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Tekst |  Kontaktens stilling               |
|  LastName             | Tekst |  Kontaktens efternavn               |
|  PostalCode           | Tekst |  Kontaktadressens postnummer               |
|  PrimaryEmail         | Tekst |  Kontaktens mailadresse               |
|  PrimaryPhone         | Tekst |  Telefonnummer til kontakten               |
|  StateOrProvince      | Tekst |  Delstat eller provins i kontaktadressen               |
|  StreetAddress        | Tekst |  Kontaktadressens gade               |

### <a name="alternatekey"></a>AlternateKey

Tabellen AlternateKey indeholder nøgler til de objekter, der deltog i den samlende proces.

|Column  |Type  |Beskrivelse  |
|---------|---------|---------|
|DataSourceName    |Tekst         | Navnet på datakilden. Eksempel: `datasource5`        |
|EntityName        | Tekst        | Navnet på objektet i Customer Insights. Eksempel: `contact1`        |
|AlternateValue    |Tekst         |Alternativt id, der er knyttet til kunde-id'et. Eksempel: `cntid_1078`         |
|KeyRing           | Tekst        | JSON-værdi  </br> Eksempel: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Tekst        | Id for den samlede kundeprofil.         |
|AlternateKeyId     | Entydigt id        |  AlternateKey-deterministisk GUID baseret på `Identifier`      |
|Identifier |   Tekst      |   `DataSourceName|EntityName|AlternateValue`  </br> Eksempel: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Denne tabel indeholder aktiviteter udført af brugere, der er tilgængelige i Customer Insights.

| Column            | Type        | Beskrivelse                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Tekst      | Kundeprofil-id                                                                      |
| ActivityId        | Tekst      | Internt id for kundeaktiviteten (primær nøgle)                                       |
| SourceEntityName  | Tekst      | Navn på kildeobjektet                                                                |
| SourceActivityId  | Tekst      | Primær nøgle fra kildeobjektet                                                       |
| ActivityType      | Tekst      | Semantisk aktivitetstype eller navnet på brugerdefineret aktivitet                                        |
| ActivityTimeStamp | Datetime    | Tidsstempel for aktivitet                                                                      |
| titel             | Tekst      | Aktivitetens titel eller navn                                                               |
| Beskrivelse       | Tekst      | Beskrivelse af aktivitet                                                                     |
| URL               | Tekst      | Link til en ekstern URL-adresse, der er specifik for aktiviteten                                         |
| SemanticData      | Tekst | Indeholder en liste over nøgleværdipar for semantiske tilknytningsfelter, der er specifikke for aktivitetstypen |
| RangeIndex        | Tekst      | Unix-tidsstempel, der bruges til sortering af aktivitetstidslinjer og forespørgsler med effektive områder |
| UnifiedActivityId   | Entydigt id | Internt id for kundeaktiviteten (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Denne tabel indeholder outputdata for kundeattributbaserede målpunkter.

| Column             | Type             | Beskrivelse                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Tekst           | Kundeprofil-id        |
| Målinger           | Tekst      | Indeholder en liste over nøgleværdipar for målpunktsnavn og værdier for den givne kunde |
| Identifier | Tekst           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Entydigt id     | Kundeprofil-id |

### <a name="enrichment"></a>Forbedring

Denne tabel indeholder resultatet af forbedringsprocessen.

| Column               | Type             |  Beskrivelse                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Tekst           | Kundeprofil-id                                 |
| EnrichmentProvider   | Tekst           | Navnet på udbyderen af forbedringen                                  |
| EnrichmentType       | Tekst           | Type af forbedring                                      |
| Værdier               | Tekst      | Liste over attributter, der er produceret af forbedringsprocessen |
| EnrichmentId | Entydigt id            | Deterministisk GUID, der er genereret fra `Identifier` |
| Identifier   | Tekst           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Forudsigelse

Denne tabel indeholder resultatet af modelforudsigelserne.

| Column               | Type        | Beskrivelse                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Tekst      | Kundeprofil-id                                  |
| ModelProvider        | Tekst      | Navnet på udbyderen af modellen                                      |
| Model                | Tekst      | Modelnavn                                                |
| Værdier               | Tekst | Liste over attributter, der er produceret af modellen |
| PredictionId | Entydigt id       | Deterministisk GUID, der er genereret fra `Identifier` |
| Identifier   | Tekst      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmentmedlemskab

Denne tabel indeholder oplysninger om kundeprofilerne vedrørende segmentmedlemskaber.

| Column        | Type | Beskrivelse                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Tekst       | Kundeprofil-id        |
| SegmentProvider      | Tekst       | App, der udgiver segmenterne.      |
| SegmentMembershipType | Tekst       | Kundetype for denne segmentmedlemspost. Understøtter flere typer, f.eks. Kunde, Kontakt eller Firma. Standard: Kunde  |
| Segmenter       | Tekst  | Liste over entydige segmenter, som kundeprofilen er medlem af      |
| Identifier  | Tekst   | Entydigt id for segmentmedlemspost. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Entydigt id      | Deterministisk GUID, der er genereret fra `Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
