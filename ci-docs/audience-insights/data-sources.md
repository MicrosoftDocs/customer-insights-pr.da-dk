---
title: Brug datakilder til at indsætte data
description: Få mere at vide om, hvordan du importerer data fra forskellige kilder.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304689"
---
# <a name="data-sources-overview"></a>Oversigt over datakilder

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Målgruppeindsigt-muligheden for Dynamics 365 Customer Insights opretter forbindelse til data fra et bredt udvalg af kilder. Oprettelse af forbindelse til en datakilde kaldes ofte processen for *dataindtagelse*. Når du har indtaget dataene, kan du [samle](data-unification.md) og udføre handlinger på dem.

## <a name="add-a-data-source"></a>Tilføj en datakilde

Se de detaljerede artikler om, hvordan du kan tilføje en datakilde, afhængigt af den indstilling, du vælger.

Du kan tilføje en datakilde på tre primære måder:

- [Via dusinvis af Power Query-connectorer](connect-power-query.md)
- [Fra en Common Data Model-mappe](connect-common-data-model.md)
- [Fra din egen Microsoft Dataverse-sø](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Tilføje data fra de lokale datakilder

Data fra de lokale datakilder i målgruppeindsigt understøttes på basis af Microsoft Power Platform-dataflows. Dataflows kan aktiveres i Customer Insights ved at [angive Microsoft Dataverse URL-adressen til miljøet](manage-environments.md#create-an-environment-in-an-existing-organization) under konfiguration af miljøet.

Datakilder, der er oprettet, når et Dataverse-miljø er blevet associeret med Customer Insights, bruger som standard [Power Platform-dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Dataflows understøtter forbindelser i det lokale miljø ved hjælp af datagateway. Fjern og genskab datakilder, der fandtes, før et Dataverse-miljø blev knyttet til at [bruge de lokale datagateways](/data-integration/gateway/service-gateway-app.md).

Datagateways fra et eksisterende Power BI- eller Power Apps-miljø er synlige, og du kan genbruge dem i Customer Insights. På siden med datakilder vises links til at gå til det Microsoft Power Platform-miljø, hvor du kan få vist og konfigurere det lokale miljøs datagateways.

## <a name="review-ingested-data"></a>Gennemgå indtagede data

Du får vist navnet på hver indtagne datakilde, dens status, og hvornår dataene sidst blev opdateret for den pågældende kilde. Du kan sortere listen over datakilder efter alle kolonner.

> [!div class="mx-imgBorder"]
> ![Tilføjet datakilde](media/configure-data-datasource-added.png "Tilføjet datakilde")

|Status  |Beskrivelse  |
|---------|---------|
|Fuldført   |Datakilde blev indregistreret, hvis der er angivet et tidspunkt i den **Opdaterede** kolonne.
|Ikke startet   |Datakilde har ingen data, der er indsat endnu, eller er stadig i kladdetilstand.         |
|Opdaterer    |Dataindtagelse er i gang. Du kan annullere denne handling ved at vælge **Stop opdatering** i kolonnen **Handlinger**. Hvis du stopper opdateringen af en datakilde, gendannes den til den seneste opdateringstilstand.       |
|Mislykket     |Der opstod fejl under indtagelse af data.         |

Vælg værdien i kolonnen **Status** i en hvilken som helst datakilde du vil gennemse for flere detaljer. Udvid **Datakilder** i ruden **Statusdetaljer**. Vælg **Se detaljer** for at få vist flere oplysninger om opdateringsstatus, herunder fejldetaljer og downstream-procesopdateringer.

Det kan tage tid at indlæse data. Når opdateringen er gennemført, kan de indtagne data gennemses fra siden **Objekter**. Du kan finde flere oplysninger under [Objekter](entities.md).

## <a name="refresh-a-data-source"></a>Opdater en datakilde

Datakilder kan opdateres automatisk i en automatisk planlægning eller opdateres manuelt efter behov. 

Gå til **Administrator** > **System** > [**Tidsplan**](system.md#schedule-tab) for at konfigurere planlagte opdateringer af alle dine påtagede datakilder.

Benyt følgende fremgangsmåde for at opdatere en datakilde efter behov:

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

2. Vælg den lodrette ellipse ud for den datakilde, du vil opdatere, og vælg **Opdatér** i rullemenuen.

3. Datakilden er nu udløst for at få en manuel opdatering. Hvis du opdaterer en datakilde, opdateres både objektskemaet og dataene for alle de objekter, der er angivet i datakilden.

4. Vælg **Stop opdatering**, hvis du vil annullere en eksisterende opdatering, og datakilden nulstilles til seneste opdateringsstatus.

## <a name="delete-a-data-source"></a>Slette en datakilde

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

2. Vælg den lodrette ellipse ud for den datakilde, du vil fjerne, og vælg **Slet** i rullemenuen.

3. Bekræft sletningen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
