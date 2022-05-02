---
title: Brug datakilder til at indsætte data
description: Få mere at vide om, hvordan du importerer data fra forskellige kilder.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: bcc50c6fa8f8e2a66ef6164bfa9022e068c0e374
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646016"
---
# <a name="data-sources-overview"></a>Oversigt over datakilder



Dynamics 365 Customer Insights opretter forbindelse til data fra et bredt sæt kilder. Oprettelse af forbindelse til en datakilde kaldes ofte processen for *dataindtagelse*. Når du har indtaget dataene, kan du [samle](data-unification.md) og udføre handlinger på dem.

## <a name="add-a-data-source"></a>Tilføj en datakilde

Se de detaljerede artikler om, hvordan du tilføjer en datakilde afhængigt af den indstilling, du vælger.

Du kan tilføje følgende datakilder:

- [Gennem mange forbindelser til Power Query](connect-power-query.md)
- [Fra en Common Data Model-mappe](connect-common-data-model.md)
- [Fra din egen Microsoft Dataverse-sø](connect-dataverse-managed-lake.md)
- [Fra en Azure Synapse Analytics-database](connect-synapse.md)

> [!NOTE]
> Hvis du bruger prøveversionen, indeholder afsnittet importmetoder et **Customer Insights-databibliotek**. Vælg denne indstilling for at vælge en datasæt tilgængelig for forskellige brancher. Du kan finde flere oplysninger under [Dynamics 365 Customer Insights-prøveversion](trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Tilføje data fra de lokale datakilder

Indtagelse af data fra det lokale miljø understøttes på baggrund af Microsoft Power Platform-dataflows. Du kan aktivere dataflow i Customer Insights ved at [angive URL Microsoft Dataverse-miljøet](create-environment.md), når du konfigurerer miljøet.

Datakilder, der er oprettet, når et Dataverse-miljø er blevet associeret med Customer Insights, bruger [Power Platform-dataflow](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) som standard. Dataflows understøtter forbindelser i det lokale miljø ved hjælp af datagateway. Du kan fjerne og genoprette datakilder, der fandtes, før et Dataverse-miljø blev tilknyttet, [ved hjælp af datagateways i det lokale miljø](/data-integration/gateway/service-gateway-app).

Datagateways fra et eksisterende Power BI- eller Power Apps-miljø er synlige, og du kan genbruge dem i Customer Insights. På siden med datakilder vises links til at gå til det Microsoft Power Platform-miljø, hvor du kan få vist og konfigurere det lokale miljøs datagateways.

> [!IMPORTANT]
> Kontrollér, at dine gateways er opdateret til den nyeste version. Du kan installere en opdatering og omkonfigurere en gateway fra en prompt, der vises direkte på gatewayskærmbilledet, eller [hente den nyeste version](https://powerapps.microsoft.com/downloads/). Hvis du ikke bruger den nyeste gatewayversion, lykkes opdateringen af dataflowet ikke, og fejlmeddelelser som **Nøgleordet understøttes ikke: konfigurationsegenskaber. Parameternavn: nøgleord**.

## <a name="review-ingested-data"></a>Gennemgå indtagne data
Hvis miljøet indeholder Power Platform-dataflow, vises der tre sektioner på siden **Datakilder**: 
- **Delt**: Datakilder, der kan administreres af alle Customer Insights-administratorer. Power BI-dataflows, din egen lagerkonto og din vedhæftede fil til en Dataverse-administreret datasø er eksempler på delte datakilder.
- **Administreres af mig**: Power Platform-dataflow, der er oprettet og kun kan administreres af dig. Andre Customer Insights-administratorer kan kun få vist disse dataflows, men de kan ikke redigere, opdatere eller slette dem.
- **Administreret af andre**: Power Platform-dataflows, der er oprettet af andre administratorer. Du kan kun se dem. Ejeren af det dataflow, der skal kontaktes, vises for at få hjælp.
> [!NOTE]
> Alle objekter kan ses og bruges af andre brugere. Kontekstafhængige brugere gælder kun for datakilder og ikke for de objekter, der er resultatet af disse dataflows.

Hvis der ikke bruges Power Platform-dataflows, kan du ikke se grupper eller sektioner. Siden **Datakilder** indeholder kun en liste over alle datakilder.

Du får vist navnet på hver indtagne datakilde, dens status, og hvornår dataene sidst blev opdateret for den pågældende kilde. Du kan sortere listen over datakilder efter alle kolonner.

> [!div class="mx-imgBorder"]
> ![Datakilde er tilføjet.](media/configure-data-datasource-added.png "Tilføjet datakilde")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan tage tid at indlæse data. Når opdateringen er gennemført, kan de indtagne data gennemses fra siden **Objekter**. Du kan finde flere oplysninger under [Objekter](entities.md).

## <a name="refresh-a-data-source"></a>Opdater en datakilde

Datakilder kan opdateres automatisk i en automatisk planlægning eller opdateres manuelt efter behov. 

Gå til **Administrator** > **System** > [**Tidsplan**](system.md#schedule-tab) for at konfigurere planlagte opdateringer af alle dine påtagede datakilder.

Benyt følgende fremgangsmåde for at opdatere en datakilde efter behov:

1. Gå til **Data** > **Datakilder**.

2. Vælg den lodrette ellipse ud for den datakilde, du vil opdatere, og vælg **Opdatér** i rullemenuen.

3. Datakilden er nu udløst for at få en manuel opdatering. Hvis du opdaterer en datakilde, opdateres både objektskemaet og dataene for alle de objekter, der er angivet i datakilden.

4. Vælg **Stop opdatering**, hvis du vil annullere en eksisterende opdatering, og datakilden nulstilles til seneste opdateringsstatus.

## <a name="delete-a-data-source"></a>Slette en datakilde

1. Gå til **Data** > **Datakilder**.

2. Vælg den lodrette ellipse ud for den datakilde, du vil fjerne, og vælg **Slet** i rullemenuen.

3. Bekræft sletningen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
