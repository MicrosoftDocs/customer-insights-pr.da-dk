---
title: Eksempler på OData-forespørgsler til API'er for Customer Insights
description: Almindeligt anvendte eksempler på OData (Open Data Protocol) til at forespørge om Customer Insights-API'er til gennemgang af data.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387195"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Eksempler på OData-forespørgsler til API'er for Customer Insights

OData (Open Data Protocol) er en dataadgangsprotokol, der er baseret på kerneprotokoller som HTTP. Der bruges almindeligt accepterede metoder, f.eks. REST til internettet. Der findes forskellige typer biblioteker og værktøjer, der kan bruges til at forbruge OData-tjenester.

Du kan se nogle ofte anmodede eksempler på forespørgsler, der kan hjælpe dig med at oprette dine egne implementeringer baseret på [Customer Insights-API'er](apis.md).

Du skal ændre forespørgselseksemplerne, så de fungerer i destinationsmiljøerne:

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` hvor {instanceId} er GUID'et for det Customer Insights-miljø, du vil forespørge om. Du kan bruge handlingen [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) til at finde {InstanceId}, du har adgang til.
- {CID}: GUID for en ensartet kundepost. Eksempel: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Id for den primære nøgle for en kundepost i en datakilde. Eksempel: `CNTID_1002`
- {DSname}: Streng med objektnavnet på en datakilde, der får adgang til Customer Insights. Eksempel: `Website_contacts`.
- {SegmentName}: Streng med navnet på outputobjektet for et segment i Customer Insights. Eksempel: `Male_under_40`.

## <a name="customer"></a>Kunde

Eksempelforespørgsler for objektet *Kunde*.

|Forespørgselstype |Eksempel  | Bemærk  |
|---------|---------|---------|
|Enkelt kunde-id     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Alternativ nøgle    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternative nøgler bliver ved med at være i objektet Samlet kunde       |
|Markér   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Om    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternativ nøgle + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Søge  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Returnerer de 10 bedste resultater for en søgestreng      |
|Segmentmedlemskab  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Returnerer et antal rækker fra segmenteringsobjektet.      |
|Medlemskab af et segment for en kunde | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Returnerer kundeprofilen, hvis kunden er medlem af det givne segment     |

## <a name="unified-activity"></a>Samlet aktivitet

Eksempelforespørgsler for objektet *UnifiedActivity*.

|Forespørgselstype |Eksempel  | Bemærk  |
|---------|---------|---------|
|CID for aktivitet     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Viser aktiviteter for en bestemt kundeprofil |
|Tidsramme for aktivitet    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktiviteter for en kundeprofil i en tidsramme       |
|Aktivitetstype    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktivitet efter visningsnavn     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Aktivitetssortering    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Sortér aktiviteter stigende eller faldende       |
|Aktiviteten er udvidet fra at være medlem af et segment  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Andre eksempler

Eksempelforespørgsler for andre objekter.

|Forespørgselstype |Eksempel  | Bemærk  |
|---------|---------|---------|
|Målinger af CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Forbedrede mærker til CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Forbedring af interesser til CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|In-Clause + Udvid     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Understøttede OData-forespørgsler

Følgende forespørgsler understøttes ikke af Customer Insights:

- `$filter` for indtagede kildeobjekter. Du kan kun køre $filter-forespørgsler på systemobjekter, der er oprettet af Customer Insights.
- `$expand` fra en `$search`-forespørgsel. Eksempel: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` fra `$select`, hvis der kun er valgt et delsæt af attributter. Eksempel: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` forbedret mærke eller interessetilhørsforhold for en bestemt kunde. Eksempel: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Outputobjekter for forespørgselsforudsigelsesmodeller via alternativ nøgle. Eksempel: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
