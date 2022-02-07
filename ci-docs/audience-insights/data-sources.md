---
title: Brug datakilder til at indsætte data
description: 'Få mere at vide om, hvordan du importerer data fra forskellige kilder.'
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
---

# <a name="data-sources-overview"></a>Oversigt over datakilder



Målgruppeindsigt-muligheden for Dynamics 365 Customer Insights opretter forbindelse til data fra et bredt udvalg af kilder. Oprettelse af forbindelse til en datakilde kaldes ofte processen for *dataindtagelse*. Når du har indtaget dataene, kan du [samle](data-unification.md) og udføre handlinger på dem.

## <a name="add-a-data-source"></a>Tilføj en datakilde

Se de detaljerede artikler om, hvordan du tilføjer en datakilde afhængigt af den indstilling, du vælger.

Du kan tilføje følgende datakilder:

- [Power Query-connectorer](connect-power-query.md)
- [Fælles datamodel](connect-common-data-model.md)
- [Microsoft Dataverse-sø](connect-dataverse-managed-lake.md)

> [!NOTE]
> Hvis du bruger prøveversionen, indeholder afsnittet importmetoder et **Customer Insights-databibliotek**. Vælg denne indstilling for at vælge en datasæt tilgængelig for forskellige brancher. Du kan finde flere oplysninger under [Dynamics 365 Customer Insights-prøveversion](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Tilføje data fra de lokale datakilder

Data fra de lokale datakilder i målgruppeindsigt understøttes på basis af Microsoft Power Platform-dataflows. Du kan aktivere dataflow i Customer Insights ved at [angive URL Microsoft Dataverse-miljøet](create-environment.md), når du konfigurerer miljøet.

Datakilder, der er oprettet, når et Dataverse-miljø er blevet associeret med Customer Insights, bruger [Power Platform-dataflow](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) som standard. Dataflows understøtter forbindelser i det lokale miljø ved hjælp af datagateway. Du kan fjerne og genoprette datakilder, der fandtes, før et Dataverse-miljø blev tilknyttet, [ved hjælp af datagateways i det lokale miljø](/data-integration/gateway/service-gateway-app).

Datagateways fra et eksisterende Power BI- eller Power Apps-miljø er synlige, og du kan genbruge dem i Customer Insights. På siden med datakilder vises links til at gå til det Microsoft Power Platform-miljø, hvor du kan få vist og konfigurere det lokale miljøs datagateways.

## <a name="review-ingested-data"></a>Gennemgå indtagne data

Du får vist navnet på hver indtagne datakilde, dens status, og hvornår dataene sidst blev opdateret for den pågældende kilde. Du kan sortere listen over datakilder efter alle kolonner.

> [!div class="mx-imgBorder"]
> ![Datakilde er tilføjet.](media/configure-data-datasource-added.png "Tilføjet datakilde")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

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
