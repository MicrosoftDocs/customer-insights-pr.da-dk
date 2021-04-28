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
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887887"
---
# <a name="data-sources-overview"></a><span data-ttu-id="46b76-103">Oversigt over datakilder</span><span class="sxs-lookup"><span data-stu-id="46b76-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="46b76-104">Målgruppeindsigt-muligheden for Dynamics 365 Customer Insights opretter forbindelse til data fra et bredt udvalg af kilder.</span><span class="sxs-lookup"><span data-stu-id="46b76-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="46b76-105">Oprettelse af forbindelse til en datakilde kaldes ofte processen for *dataindtagelse*.</span><span class="sxs-lookup"><span data-stu-id="46b76-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="46b76-106">Når du har indtaget dataene, kan du [samle](data-unification.md) og udføre handlinger på dem.</span><span class="sxs-lookup"><span data-stu-id="46b76-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="46b76-107">Tilføj en datakilde</span><span class="sxs-lookup"><span data-stu-id="46b76-107">Add a data source</span></span>

<span data-ttu-id="46b76-108">Se de detaljerede artikler om, hvordan du kan tilføje en datakilde, afhængigt af den indstilling, du vælger.</span><span class="sxs-lookup"><span data-stu-id="46b76-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="46b76-109">Du kan tilføje en datakilde på tre primære måder:</span><span class="sxs-lookup"><span data-stu-id="46b76-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="46b76-110">Via dusinvis af Power Query-connectorer</span><span class="sxs-lookup"><span data-stu-id="46b76-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="46b76-111">Fra en Common Data Model-mappe</span><span class="sxs-lookup"><span data-stu-id="46b76-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="46b76-112">Fra din egen Common Data Service-sø</span><span class="sxs-lookup"><span data-stu-id="46b76-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="46b76-113">Tilføje data fra de lokale datakilder</span><span class="sxs-lookup"><span data-stu-id="46b76-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="46b76-114">Data fra de lokale datakilder i målgruppeindsigt understøttes på basis af Power Platform-dataflows.</span><span class="sxs-lookup"><span data-stu-id="46b76-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="46b76-115">Dataflows kan aktiveres i Customer Insights ved at [angive Microsoft Dataverse URL-adressen til miljøet](manage-environments.md#create-an-environment-in-an-existing-organization) under konfiguration af miljøet.</span><span class="sxs-lookup"><span data-stu-id="46b76-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="46b76-116">Datakilder, der er oprettet, når et Dataverse-miljø er blevet associeret med Customer Insights, bruger som standard [Power Platform-dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="46b76-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="46b76-117">Dataflows understøtter forbindelse forud for brug ved hjælp af data gateways.</span><span class="sxs-lookup"><span data-stu-id="46b76-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="46b76-118">Fjern og genskab datakilder, der fandtes, før et Dataverse-miljø blev knyttet til at bruge de lokale datagateways.</span><span class="sxs-lookup"><span data-stu-id="46b76-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="46b76-119">Datagateways fra et eksisterende Power BI- eller Power Apps-miljø er synlige, og du kan genbruge dem i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="46b76-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="46b76-120">På siden med datakilder vises links til at gå Power Platform-miljøet, hvor du kan få vist og konfigurere de lokale datagateways.</span><span class="sxs-lookup"><span data-stu-id="46b76-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Skærmbillede af siden med datakilder, der viser links, der peger på Power Platform-miljøet.":::

## <a name="review-ingested-data"></a><span data-ttu-id="46b76-122">Gennemgå indtagede data</span><span class="sxs-lookup"><span data-stu-id="46b76-122">Review ingested data</span></span>

<span data-ttu-id="46b76-123">Du får vist navnet på hver indtagne datakilde, dens status, og hvornår dataene sidst blev opdateret for den pågældende kilde.</span><span class="sxs-lookup"><span data-stu-id="46b76-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="46b76-124">Du kan sortere listen over datakilder efter alle kolonner.</span><span class="sxs-lookup"><span data-stu-id="46b76-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="46b76-125">![Tilføjet datakilde](media/configure-data-datasource-added.png "Tilføjet datakilde")</span><span class="sxs-lookup"><span data-stu-id="46b76-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="46b76-126">Status</span><span class="sxs-lookup"><span data-stu-id="46b76-126">Status</span></span>  |<span data-ttu-id="46b76-127">Beskrivelse</span><span class="sxs-lookup"><span data-stu-id="46b76-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="46b76-128">Fuldført</span><span class="sxs-lookup"><span data-stu-id="46b76-128">Successful</span></span>   |<span data-ttu-id="46b76-129">Datakilde blev indregistreret, hvis der er angivet et tidspunkt i den **Opdaterede** kolonne.</span><span class="sxs-lookup"><span data-stu-id="46b76-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="46b76-130">Ikke startet</span><span class="sxs-lookup"><span data-stu-id="46b76-130">Not started</span></span>   |<span data-ttu-id="46b76-131">Datakilde har ingen data, der er indsat endnu, eller er stadig i kladdetilstand.</span><span class="sxs-lookup"><span data-stu-id="46b76-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="46b76-132">Opdaterer</span><span class="sxs-lookup"><span data-stu-id="46b76-132">Refreshing</span></span>    |<span data-ttu-id="46b76-133">Dataindtagelse er i gang.</span><span class="sxs-lookup"><span data-stu-id="46b76-133">Data ingestion is in progress.</span></span> <span data-ttu-id="46b76-134">Du kan annullere denne handling ved at vælge **Stop opdatering** i kolonnen **Handlinger**.</span><span class="sxs-lookup"><span data-stu-id="46b76-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="46b76-135">Hvis du stopper opdateringen af en datakilde, gendannes den til den seneste opdateringstilstand.</span><span class="sxs-lookup"><span data-stu-id="46b76-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="46b76-136">Mislykket</span><span class="sxs-lookup"><span data-stu-id="46b76-136">Failed</span></span>     |<span data-ttu-id="46b76-137">Der opstod fejl under indtagelse af data.</span><span class="sxs-lookup"><span data-stu-id="46b76-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="46b76-138">Vælg værdien i kolonnen **Status** i en hvilken som helst datakilde du vil gennemse for flere detaljer.</span><span class="sxs-lookup"><span data-stu-id="46b76-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="46b76-139">Udvid **Datakilder** i ruden **Statusdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="46b76-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="46b76-140">Vælg **Se detaljer** for at få vist flere oplysninger om opdateringsstatus, herunder fejldetaljer og downstream-procesopdateringer.</span><span class="sxs-lookup"><span data-stu-id="46b76-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="46b76-141">Indlæsning af tage kan tage et stykke tid.</span><span class="sxs-lookup"><span data-stu-id="46b76-141">Loading data can take some time.</span></span> <span data-ttu-id="46b76-142">Når opdateringen er gennemført, kan de indtagne data gennemses fra siden **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="46b76-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="46b76-143">Du kan finde flere oplysninger under [Objekter](entities.md).</span><span class="sxs-lookup"><span data-stu-id="46b76-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="46b76-144">Opdater en datakilde</span><span class="sxs-lookup"><span data-stu-id="46b76-144">Refresh a data source</span></span>

<span data-ttu-id="46b76-145">Datakilder kan opdateres automatisk i en automatisk planlægning eller opdateres manuelt efter behov.</span><span class="sxs-lookup"><span data-stu-id="46b76-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="46b76-146">Gå til **Administrator** > **System** > [**Tidsplan**](system.md#schedule-tab) for at konfigurere planlagte opdateringer af alle dine påtagede datakilder.</span><span class="sxs-lookup"><span data-stu-id="46b76-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="46b76-147">Benyt følgende fremgangsmåde for at opdatere en datakilde efter behov:</span><span class="sxs-lookup"><span data-stu-id="46b76-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="46b76-148">Gå til **Data** > **Datakilder** i målgruppen Insights</span><span class="sxs-lookup"><span data-stu-id="46b76-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="46b76-149">Vælg den lodrette ellipse ud for den datakilde, du vil opdatere, og vælg **Opdater** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="46b76-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="46b76-150">Datakilden er nu udløst for at få en manuel opdatering.</span><span class="sxs-lookup"><span data-stu-id="46b76-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="46b76-151">Hvis du opdaterer en datakilde, opdateres både objektskemaet og dataene for alle de objekter, der er angivet i datakilden.</span><span class="sxs-lookup"><span data-stu-id="46b76-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="46b76-152">Vælg **Stop opdatering**, hvis du vil annullere en eksisterende opdatering, og datakilden nulstilles til seneste opdateringsstatus.</span><span class="sxs-lookup"><span data-stu-id="46b76-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="46b76-153">Slette en datakilde</span><span class="sxs-lookup"><span data-stu-id="46b76-153">Delete a data source</span></span>

1. <span data-ttu-id="46b76-154">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="46b76-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="46b76-155">Vælg den lodrette ellipse ud for den datakilde, du vil fjerne, og vælg **Slet** i rullemenuen.</span><span class="sxs-lookup"><span data-stu-id="46b76-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="46b76-156">Bekræft sletningen.</span><span class="sxs-lookup"><span data-stu-id="46b76-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
