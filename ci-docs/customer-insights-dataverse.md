---
title: Arbejde med Customer Insights-data i Microsoft Dataverse
description: Få mere at vide om, hvordan du opretter forbindelse mellem Customer Insights og Microsoft Dataverse, og forstå de outputobjekter, der eksporteres til Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833669"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Arbejde med Customer Insights-data i Microsoft Dataverse

Customer Insights giver dig mulighed for at gøre outputobjekter tilgængelige som [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Denne integration muliggør nem datadeling og brugerdefineret udvikling gennem en tilgang med næste ingen kode/ingen kode. [Outputobjekterne](#output-entities) er tilgængelige som tabeller i et Dataverse-miljø. Du kan bruge dataene til et hvilket som helst andet program baseret på Dataverse-tabeller. Disse tabeller muliggør scenarier som automatiserede arbejdsprocesser via Power Automate eller opbygning af apps med Power Apps.

Hvis du opretter forbindelse til Dataverse-miljøet, kan du også [indtage data fra det lokale miljø datakilder ved hjælp af Power Platform-dataflow og gateways](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Forudsætninger

- Customer Insights og Dataverse-miljøer skal hostes i det samme område.
- Du skal have en global administratorrolle i Dataverse-miljøet. Kontrollér, om dette [Dataverse-miljø er knyttet](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) til visse sikkerhedsgrupper, og kontrollér, at du er føjet til de pågældende sikkerhedsgrupper.
- Der er ikke allerede knyttet andre Customer Insights-miljø til det Dataverse-miljø, du vil oprette forbindelse til. Få mere at vide om , hvordan du [fjerner en eksisterende forbindelse til et Dataverse-miljø](#remove-an-existing-connection-to-a-dataverse-environment).
- Et Microsoft Dataverse-miljø kan kun oprette forbindelse til en enkelt lagerkonto. Det gælder kun, hvis du konfigurerer miljøet til at [bruge Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Oprette forbindelse mellem et Dataverse-miljø og Customer Insights

I **Microsoft Dataverse**-trinnet kan du knytte Customer Insights til dit Dataverse-miljø, mens du [opretter et Customer Insights-miljø](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="datadeling med Microsoft Dataverse er automatisk aktiveret for nye miljøer.":::

Administratorer kan konfigurere Customer Insights til at oprette forbindelse til et eksisterende Dataverse-miljø. Når du angiver webadressen til Dataverse-miljøet, knyttes den til deres nye Customer Insights-miljø.

Hvis du ikke vil bruge et eksisterende Dataverse-miljø, oprettes der et nyt miljø for Customer Insights-dataene i din lejer. [Power Platform-administratorer kan styre, hvem der kan oprette miljøer](/power-platform/admin/control-environment-creation) Når du konfigurerer et nyt Customer Insights-miljø, og administratoren har deaktiveret oprettelse af Dataverse-miljøer for alle undtagen administratorer, kan du muligvis ikke oprette et nyt miljø.

**Aktivér datadeling** med Dataverse ved at markere afkrydsningsfeltet for datadeling.

Hvis du bruger din egen Data Lake Storage-konto, skal du også bruge **tilladelses-id'et**. Du kan finde flere oplysninger om, hvordan du henter tilladelses-id'et, i følgende afsnit.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Aktivere datadeling med Dataverse fra dit eget Azure Data Lake Storage (forhåndsversion)

Hvis du aktiverer datadeling med Microsoft Dataverse, når dit miljø [bruger din egen Azure Data Lake Storage-konto](own-data-lake-storage.md), skal der udføres ekstra konfiguration. Den bruger, der konfigurerer Customer Insights-miljøet, skal som minimum have **Læser af Blob Data-lager**-tilladelser til *CustomerInsights*-objektbeholderen i Azure Data Lake Storage-kontoen.

1. Opret to sikkerhedsgrupper i dit Azure-abonnement – en **Læser**-sikkerhedsgruppe og en **bidragyder**-sikkerhedsgruppe, og angiv Microsoft Dataverse-tjenesten som ejer for begge sikkerhedsgrupper.
2. Administrer ACL (Access Control List) på CustomerInsights-beholderen på din lagerkonto via disse sikkerhedsgrupper. Tilføj tjenesten Microsoft Dataverse og alle Dataverse-baserede virksomhedsprogrammer, f.eks. Dynamics 365 Marketing til **Læser**-sikkerhedsgruppen med **skrivebeskyttede** tilladelser. Tilføj *kun* programmet Customers Insights til sikkerhedsgruppen **Bidragyder** for at give både **læse- og skrivetilladelser** til at skrive profiler og indsigt.

### <a name="limitations"></a>Begrænsninger

Der er to begrænsninger, når du bruger Dataverse med din egen Azure Data Lake Storage-konto:

- Der findes en til en-tilknytning mellem en Dataverse-organisation og en Azure Data Lake Storage-konto. Når en Dataverse-organisation er knyttet til en lagerkonto, kan den ikke oprette forbindelse til en anden lagerkonto. Denne begrænsning forhindrer, at Dataverse ikke udfylder flere lagerkonti.
- Datadeling fungerer ikke, hvis en konfiguration af Azure Private Link er nødvendig for at få adgang til din Azure Data Lake Storage-konto, da den er bag en firewall. Dataverse understøtter i øjeblikket ikke forbindelsen til private slutpunkter via Private Link.

### <a name="set-up-powershell"></a>Konfigurere PowerShell

Hvis du vil køre PowerShell-scripts, skal du først konfigurere PowerShell til det.

1. Installer den nyeste version af [Azure Active Directory PowerShell til Graph](/powershell/azure/active-directory/install-adv2).
   1. På din pc skal du vælge Windows-tasten på tastaturet og søge efter **Windows PowerShell** og vælge **Kør som administrator**.
   1. I det PowerShell-vindue, der åbnes, skal du skrive `Install-Module AzureAD`.
2. Importér tre moduler.
    1. Skriv `Install-Module -Name Az.Accounts` i PowerShell-vinduet, og følg trinnene.
    1. Gentag for `Install-Module -Name Az.Resources` og `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Konfigurationstrin

1. Hent de to PowerShell-scripts, du skal bruge for at køre fra vores udviklers [GitHub-repo](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Du skal bruge *lejer-admin*-tilladelser til at køre dette PowerShell-script.
       - Med dette PowerShell-script oprettes der to sikkerhedsgrupper i dit Azure-abonnement. Et for Læsergruppen og et andet for gruppen Bidragyder og Microsoft Dataverse-tjenesten gøres til ejer af begge disse sikkerhedsgrupper.
       - Udfør dette PowerShell-script i Windows PowerShell ved at angive det Azure-abonnements-id, der indeholder dit Azure Data Lake Storage. Åbn PowerShell-scriptet i en editor for at gennemse flere oplysninger og den implementerede logik.
       - Gem begge id-værdier for sikkerhedsgrupper, der er genereret med dette script, da vi bruger dem i `ByolSetup.ps1`-scriptet.

        > [!NOTE]
        > Oprettelse af sikkerhedsgrupper kan deaktiveres for lejeren. I det tilfælde skal du konfigurere manuelt, og din Azure AD-administrator skal aktivere[ oprettelse af sikkerhedsgruppe](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Du skal have tilladelser som *Lager Blob-dataejer* på lagerkonto/beholderniveau for at køre dette script, ellers oprettes der en for dig i dette script. Rolletildelingen kan fjernes manuelt, når scriptet er kørt korrekt.
        - Dette PowerShell-script tilføjer det påkrævede rollebaserede adgangskontrolelement (RBAC) for Microsoft Dataverse-tjenesten og alle Dataverse-baserede virksomhedsprogrammer. Den opdaterer også ACL (Access Control List) i CustomerInsights-beholderen for de sikkerhedsgrupper, der er oprettet med `CreateSecurityGroups.ps1`-scriptet. Gruppen bidragyder har kun *rwx*-tilladelsen, og gruppen Læsere har kun *r-x*-tilladelsen.
        - Kør dette PowerShell-script i Windows PowerShell ved at angive det Azure-abonnements-id, der indeholder dit Azure Data Lake Storage, navnet på din lagerkonto, navnet på ressourcegruppen og id for Læser- og Bidragyder-sikkerhedsgruppen. Åbn PowerShell-scriptet i en editor for at gennemse flere oplysninger og den implementerede logik.
        - Kopiér outputstrengen, når scriptet er kørt. Outputstrengen ser således ud: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Angiv den outputstreng, der er kopieret ovenfra, til feltet **Tilladelser-id** i trinnet til miljøkonfiguration for Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurationsindstillinger, der gør det muligt at dele data direkte fra det eget Azure Data Lake Storage med Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Fjern en eksisterende forbindelse til et Dataverse-miljø

Når der oprettes forbindelse til et Dataverse-miljø, betyder fejlmeddelelsen **Denne CDS-organisation er allerede knyttet til en anden forekomst af Customer Insights**, at Dataverse-miljøet allerede er brugt i et Customer Insights-miljø. Du kan fjerne den eksisterende forbindelse som en global administrator i Dataverse-miljøet. Det kan tage et par timer at udfylde ændringerne.

1. Gå til [Power Apps](https://make.powerapps.com).
1. Vælg miljøet på miljøvælgeren.
1. Gå til **Løsninger**
1. Fjern eller slet løsningen med navnet **Dynamics 365 Customer Insights Kundekort-tilføjelsesprogrammet (forhåndsversion)**.

ELLER

1. Åbn dit Dataverse-miljø.
1. Gå til **Avancerede indstillinger** > **Løsninger**.
1. Fjern løsningen **CustomerInsightsCustomerCard**.

Hvis det ikke lykkes at fjerne forbindelsen på grund af afhængigheder, skal du også fjerne afhængighederne. Du kan finde flere oplysninger under [Fjernelse af afhængigheder](/power-platform/alm/removing-dependencies).

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

Denne tabel indeholder den samlede kundeprofil fra Customer Insights. Skemaet for en unified customer profile afhænger af de objekter og attributter, der bruges i data samlingsprocessen. Et kundeprofilskema indeholder normalt et undersæt af attributterne fra [Common Data Model-definitionen i CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

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

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
