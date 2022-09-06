---
title: Eksport af diagnosticeringslogfiler (forhåndsversion)
description: Få mere at vide om, hvordan du sender logge til Microsoft Azure-overvågning.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: c573c46fda895d36d29712e75fe28b261c9b399a
ms.sourcegitcommit: 0b5bfe0145dbd325fa518df4561d6a0a9a352264
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/25/2022
ms.locfileid: "9352794"
---
# <a name="export-diagnostic-logs-preview"></a>Eksport af diagnosticeringslogfiler (forhåndsversion)

Videresende logfiler fra Customer Insights ved hjælp af Azure Monitor. Med Azure Monitor-ressourcelogfiler kan du overvåge og sende logge til [Azure-datalager](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview) eller streame dem til [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

Customer Insights sender følgende hændelseslogfiler:

- **Overvågningshændelser**
  - **APIEvent** - aktiverer sporing af ændringer via Dynamics 365 Customer Insights-brugergrænsefladen.
- **Driftshændelser**
  - **WorkflowEvent** - gør det muligt at konfigurere [datakilder](data-sources.md), [samle](data-unification.md) og [forbedre](enrichment-hub.md) og til sidst [eksportere](export-destinations.md) data til andre systemer. Disse trin kan udføres individuelt (f.eks. udløse en enkelt eksport). De kan også køres orkestreret (f.eks. dataopdatering fra datakilder, der udløser den enhedsproces, der trækker oplysninger ind, og når dataene er eksporteret til et andet system). Du kan finde flere oplysninger i [WorkflowEvent-skema](#workflow-event-schema).
  - **APIEvent** - sender alle API-opkald til kundernes forekomst til Dynamics 365 Customer Insights. Du kan finde flere oplysninger i [APIEvent-skema](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Konfigurer diagnosticeringsindstillinger

### <a name="prerequisites"></a>Forudsætninger

- Et aktivt [Azure-abonnement](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Administrator](permissions.md#admin)-tilladelser i Customer Insights.
- En gyldig ressource på Azure, der følger [destinationskravene](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) til Azure Storage, Azure-hændelseshub eller Azure Log Analytics.
- [Rollen som bidragyder og brugeradgangsadministrator](/azure/role-based-access-control/role-assignments-portal) for destinationsressourcen på Azure. Ressourcen kan være en Azure Data Lake Storage-konto, en Azure-hændelseshub eller et Azure Log Analytics-arbejdsområde. Denne tilladelse er nødvendig, når du konfigurerer diagnosticeringsindstillinger i Customer Insights, men den kan ændres, når installationen er fuldført.
- Du har som minimum rollen **Læser** i den ressourcegruppe, som ressourcen tilhører.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Konfigurere diagnosticeringsværktøjet med Azure Monitor

1. Gå i Customer Insights til **Administration** > **System**, og vælg fanen **Diagnosticering**.

1. Vælg **Tilføj destination**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Diagnosticeringsforbindelse.":::

1. Angiv et navn i feltet **Navn til diagnosticering af destination**.

1. Vælg **Ressourcetypen** (lagerkonto, hændelseshub eller loganalyser).

1. Vælg **Abonnement**, **Ressourcegruppe** og **Ressource** for destinationsressourcen. Se [Konfiguration på destinationsressourcen](#configuration-on-the-destination-resource) for at få tilladelse og logoplysninger.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse til systemet** for at oprette forbindelse til destinationsressourcen. Loggene begynder at blive vist på destinationen efter 15 minutter, hvis API'en er i brug og genererer hændelser.

## <a name="configuration-on-the-destination-resource"></a>Konfiguration på destinationsressourcen

Afhængigt af dit valg af ressourcetype indtræffer følgende ændringer automatisk:

### <a name="storage-account"></a>Storage account

Customer Insights-servicestyringskontoen får tilladelsen **Lagerkontobidragyder** den valgte ressource, og der oprettes to objektbeholdere under det valgte navneområde:

- `insight-logs-audit` indeholder **overvågningshændelser**
- `insight-logs-operational` indeholder **driftshændelser**

### <a name="event-hub"></a>Hændelses hub

Customer Insights-servicestyringskontoen får tilladelsen **Ejeren af Azure Event Hubs-data** den valgte ressource, og der oprettes to hændelseshubs under det valgte navneområde:

- `insight-logs-audit` indeholder **overvågningshændelser**
- `insight-logs-operational` indeholder **driftshændelser**

### <a name="log-analytics"></a>Log Analytics

Customer Insights-servicechefen får tilladelsen **Loganalyse bidragyder** på ressourcen. Logfilerne bliver tilgængelige under **Logfiler** > **Tabeller** > **Logfilstyring** i det valgte arbejdsområde loganalyser. Udvid løsningen **Logstyring**, og find `CIEventsAudit` og `CIEventsOperational`-tabellerne.

- `CIEventsAudit` indeholder **overvågningshændelser**
- `CIEventsOperational` indeholder **driftshændelser**

Udvid **overvågningsløsning** i vinduet **Forespørgsler**, og find de eksempelforespørgsler, der findes ved at søge efter `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Fjern en destination for diagnosticering

1. Gå til **Administration** > **System**, og vælg fanen **Diagnosticering**.

1. Vælg diagnosticeringsdestinationen på listen.

   > [!TIP]
   > Når destinationen fjernes, stoppes videresendelsen af logfilen, men ressourcen slettes ikke i Azure-abonnementet. Du kan slette ressourcen i Azure, vælge linket i kolonnen **Handlinger** for at åbne Azure-portalen for den valgte ressource og slette den der. Slet derefter diagnosticeringsdestinationen.

1. I kolonnen **Handlinger** vælges ikonet **Slet**.

1. Bekræft sletningen for at fjerne destinationen og stoppe videresendelse af loggen.

## <a name="log-categories-and-event-schemas"></a>Logkategorier og hændelsesskemaer

Aktuelt understøttes [API-hændelser](apis.md) og arbejdsproceshændelser, og følgende kategorier og skemaer gælder.
Logskemaet følger det [almindelige Azure Monitor-skema](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorier

Customer Insights indeholder to kategorier:

- **Overvågningshændelser**: [API-hændelser](#api-event-schema), der sporer konfigurationsændringerne i tjenesten. `POST|PUT|DELETE|PATCH`-handlinger i denne kategori.
- **Driftsmæssige hændelser**: [API-hændelser](#api-event-schema) eller [arbejdsproceshændelser](#workflow-event-schema), der oprettes under brug af tjenesten.  F.eks. `GET`-forespørgsler eller udførelseshændelser for en arbejdsproces.

## <a name="event-schemas"></a>Hændelsesskemaer

API-hændelser og arbejdsproceshændelser har en fælles struktur, men med nogle få forskelle. Du kan finde flere oplysninger i [API-hændelsesskema](#api-event-schema) eller [Workflow-hændelsesskema](#workflow-event-schema).

### <a name="api-event-schema"></a>API-hændelsesskema

| Felt             | DataType  | Påkrævet/valgfrit | Beskrivelse       | Eksempel        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Tidsstempel | Obligatorisk          | Tidsstempel for hændelsen (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Obligatorisk          | ResourceId for den forekomst, der har sendt hændelsen         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Obligatorisk          | Navnet på den handling, der repræsenteres ved denne hændelse.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Obligatorisk          | Logkategori for hændelsen. Enten `Operational` eller `Audit`. Alle POST/PUT/PATCH/DELETE HTTP-forespørgsler er markeret med `Audit`, alt andet med `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Obligatorisk          | Status for hændelsen. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Valgfrit          | Resultatstatus for hændelsen. Hvis handlingen svarer til et REST API, er det HTTP-statuskoden.        | `200`             |
| `durationMs`      | Long      | Valgfrit          | Varigheden af handlingen i millisekunder.     | `133`     |
| `callerIpAddress` | String    | Valgfrit          | Opkalders IP-adresse, hvis handlingen svarer til et API-opkald, der kommer fra en offentligt tilgængelig IP-adresse.                                                 | `144.318.99.233`         |
| `identity`        | String    | Valgfrit          | JSON-objekt, der beskriver identiteten på den bruger eller det program, der har udført handlingen.       | Se [Identitet](#identity-schema)-sektion.     |  
| `properties`      | String    | Valgfrit          | JSON-objekt med flere egenskaber til en bestemt kategori af hændelser.      | Se [Egenskaber for](#api-properties-schema)-sektion.    |
| `level`           | String    | Obligatorisk          | Begivenhedens forskellige niveauer.    | `Informational`, `Warning`, `Error` eller `Critical`.           |
| `uri`             | String    | Valgfrit          | URI'er til absolutte anmodninger.    |               |

#### <a name="identity-schema"></a>Identitetsskema

`identity` JSON-objektet har følgende struktur

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Felt                         | Beskrivelse                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Tildelt rolle for brugeren eller appen. Du kan finde flere oplysninger i [brugertilladelser](permissions.md).                                     |
| `Authorization.RequiredRoles` | Nødvendige roller for at udføre handlingen. `Admin`-rollen er tillades til alle handlinger.                                                    |
| `Claims`                      | Krav fra bruger- eller app-JSON-webtoken (JWT). Egenskaber for krav varierer, afhængigt af organisation og Azure Active Directory-konfiguration. |

#### <a name="api-properties-schema"></a>Skema over API-egenskaber

[API-hændelser](apis.md) har følgende egenskaber.

| Felt                        | Beskrivelse                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Altid `ApiEvent`-markering af loghændelsen som API-hændelse.                                                                 |
| `properties.userAgent`       | Browseragent, der sender anmodningen eller `unknown`.                                                                        |
| `properties.method`          | HTTP-metode: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Relativ sti til anmodningen.                                                                                          |
| `properties.origin`          | URI'er, der angiver, hvor en Fetch kommer fra, eller `unknown`.                                                                  |
| `properties.operationStatus` | `Success` Status HTTP-kode < 400 <br> `ClientError` Status HTTP-kode < 500 <br> `Error` til HTTP-status >= 500 |
| `properties.tenantId`        | Organisations-id                                                                                                        |
| `properties.tenantName`      | Navn på organisationen.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId for den kaldende.                                                                         |
| `properties.instanceId`      | Customer Insights `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Skema over arbejdsproceshændelse

Arbejdsprocessen indeholder flere trin. [Indtage datakilder](data-sources.md), [samle](data-unification.md), [forbedre](enrichment-hub.md) og [eksportere](export-destinations.md) data. Alle disse trin kan køres individuelt eller orkestreret med følgende processer.

#### <a name="operation-types"></a>Handlingstyper

| Handlingstype     | Gruppe                                     |
| ----------------- | ----------------------------------------- |
| Indtagelse         | [Datakilder](data-sources.md)           |
| DataPreparation   | [Datakilder](data-sources.md)           |
| Tilknytning               | [Datasamling](data-unification.md)   |
| Resultat             | [Datasamling](data-unification.md)   |
| Fletning             | [Datasamling](data-unification.md)   |
| ProfileStore      | [Kundeprofiler](customer-profiles.md) |
| Søge            | [Kundeprofiler](customer-profiles.md) |
| Aktivitet          | [Aktiviteter](activities.md)                  |
| AttributeMeasures | [Segmenter og målinger](segments.md)      |
| EntityMeasures    | [Segmenter og målinger](segments.md)      |
| Målinger          | [Segmenter og målinger](segments.md)      |
| Segmentering      | [Segmenter og målinger](segments.md)      |
| Forbedring        | [Forbedring](enrichment-hub.md)                                          |
| Intelligens      | [Forudsigelser](predictions-overview.md)                                          |
| AiBuilder         | [Forudsigelser](predictions-overview.md)                                          |
| Indsigt          | [Forudsigelser](predictions-overview.md)                                          |
| Export            | [Eksport](export-destinations.md)                                          |
| ModelManagement   | [Forudsigelser](custom-models.md)                                           |
| Relation      | [Datasamling](relationships.md)                                           |

#### <a name="field-description"></a>Feltbeskrivelse

| Felt           | DataType  | Påkrævet/valgfrit | Beskrivelse                                                                                                                                                   | Eksempel                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Tidsstempel | Obligatorisk          | Tidsstempel for hændelsen (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Obligatorisk          | ResourceId for den forekomst, der har sendt hændelsen.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Obligatorisk          | Navnet på den handling, der repræsenteres ved denne hændelse. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Se [operationstyper](#operation-types), der kan henvises til. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Obligatorisk          | Logkategori for hændelsen. Altid `Operational` for arbejdsproceshændelser                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Obligatorisk          | Status for hændelsen. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | Valgfrit          | Varigheden af handlingen i millisekunder.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Valgfrit          | JSON-objekt med flere egenskaber til en bestemt kategori af hændelser.                                                                                        | Se underafsnit [Arbejdsprocesegenskaber](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Obligatorisk          | Begivenhedens forskellige niveauer.                                                                                                                                  | `Informational`, `Warning` eller `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Skema for arbejdsprocesegenskaber

Arbejdsproceshændelser har følgende egenskaber.

| Felt              | Workflow | Opgave | Beskrivelse            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ja      | Ja  | Altid `WorkflowEvent`-markering af loghændelsen som arbejdsproceshændelse.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ja      | Ja  | Id for kørslen af arbejdsprocessen. Alle arbejdsproces- og opgavehændelser i arbejdsproceskørslen har samme `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ja      | Ja  | Id for handlingen findes i [Handlingstyper](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Ja      | Nr.   | Kun arbejdsproces. Antallet af opgaver, der er udløst af arbejdsprocessen.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ja      | Nr.   | Valgfrit. Kun arbejdsproceshændelser. Det Azure Active Directory [objectId for den bruger](/azure/marketplace/find-tenant-object-id#find-user-object-id), der udløste arbejdsprocessen, skal også se `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ja      | Nr.   | `full` eller `incremental` opdatere.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ja      | Nr.   | `OnDemand` eller `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ja      | Nr.   | `Running` eller  `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ja      | Ja  | UTC-tidsstempel `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ja      | Ja  | UTC-tidsstempel `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ja      | Ja  | UTC-tidsstempel `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ja      | Ja  | Customer Insights `instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | Nr.       | Ja  | - For OperationType = `Export`er id-guid for eksportkonfigurationen. <br> - For OperationType = `Enrichment` er det guid for forbedringen <br> - I forbindelse med OperationType er `Measures` og `Segmentation` id'et objektnavnet. |
| `properties.friendlyName`                    | Nr.       | Ja  | Brugervenligt navn på eksporten eller det objekt, der behandles.                                                                                                                                                                                           |
| `properties.error`                           | Nr.       | Ja  | Valgfrit. Fejlmeddelelse med flere detaljer.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | Nr.       | Ja  | Valgfrit. Kun for `Export`-OperationType. Identificerer eksporttypen. Du kan finde flere oplysninger i [oversigt over eksportdestinationer](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | Nr.       | Ja  | Valgfrit. Kun for `Export`-OperationType. Indeholder en liste over konfigurerede objekter i eksporten.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | Nr.       | Ja  | Valgfrit. Kun for `Export`-OperationType. Detaljeret meddelelse om eksporten.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | Nr.       | Ja  | Valgfrit. Kun for `Segmentation`-OperationType. Angiver det samlede antal medlemmer, som segmentet har.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
