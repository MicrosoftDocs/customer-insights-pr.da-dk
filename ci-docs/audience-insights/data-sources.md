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
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085523"
---
# <a name="data-sources-overview"></a><span data-ttu-id="f6739-103">Oversigt over datakilder</span><span class="sxs-lookup"><span data-stu-id="f6739-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f6739-104">Målgruppeindsigt-muligheden for Dynamics 365 Customer Insights opretter forbindelse til data fra et bredt udvalg af kilder.</span><span class="sxs-lookup"><span data-stu-id="f6739-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="f6739-105">Oprettelse af forbindelse til en datakilde kaldes ofte processen for *dataindtagelse*.</span><span class="sxs-lookup"><span data-stu-id="f6739-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="f6739-106">Når du har indtaget dataene, kan du [samle](data-unification.md) og udføre handlinger på dem.</span><span class="sxs-lookup"><span data-stu-id="f6739-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="f6739-107">Tilføj en datakilde</span><span class="sxs-lookup"><span data-stu-id="f6739-107">Add a data source</span></span>

<span data-ttu-id="f6739-108">Se de detaljerede artikler om, hvordan du kan tilføje en datakilde, afhængigt af den indstilling, du vælger.</span><span class="sxs-lookup"><span data-stu-id="f6739-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="f6739-109">Du kan tilføje en datakilde på tre primære måder:</span><span class="sxs-lookup"><span data-stu-id="f6739-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="f6739-110">Via dusinvis af Power Query-connectorer</span><span class="sxs-lookup"><span data-stu-id="f6739-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="f6739-111">Fra en Common Data Model-mappe</span><span class="sxs-lookup"><span data-stu-id="f6739-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="f6739-112">Fra din egen Common Data Service-sø</span><span class="sxs-lookup"><span data-stu-id="f6739-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="f6739-113">Tilføje data fra de lokale datakilder</span><span class="sxs-lookup"><span data-stu-id="f6739-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="f6739-114">Data fra de lokale datakilder i målgruppeindsigt understøttes på basis af Power Platform-dataflows.</span><span class="sxs-lookup"><span data-stu-id="f6739-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="f6739-115">Dataflows kan aktiveres i Customer Insights ved at [angive Microsoft Dataverse URL-adressen til miljøet](manage-environments.md#create-an-environment-in-an-existing-organization) under konfiguration af miljøet.</span><span class="sxs-lookup"><span data-stu-id="f6739-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="f6739-116">Datakilder, der er oprettet, når et Dataverse-miljø er blevet associeret med Customer Insights, bruger som standard [Power Platform-dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="f6739-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="f6739-117">Dataflows understøtter forbindelser i det lokale miljø ved hjælp af datagateway.</span><span class="sxs-lookup"><span data-stu-id="f6739-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="f6739-118">Fjern og genskab datakilder, der fandtes, før et Dataverse-miljø blev knyttet til at [bruge de lokale datagateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="f6739-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="f6739-119">Datagateways fra et eksisterende Power BI- eller Power Apps-miljø er synlige, og du kan genbruge dem i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f6739-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="f6739-120">På siden med datakilder vises links til at gå Power Platform-miljøet, hvor du kan få vist og konfigurere de lokale datagateways.</span><span class="sxs-lookup"><span data-stu-id="f6739-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="f6739-121">Gennemgå indtagede data</span><span class="sxs-lookup"><span data-stu-id="f6739-121">Review ingested data</span></span>

<span data-ttu-id="f6739-122">Du får vist navnet på hver indtagne datakilde, dens status, og hvornår dataene sidst blev opdateret for den pågældende kilde.</span><span class="sxs-lookup"><span data-stu-id="f6739-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="f6739-123">Du kan sortere listen over datakilder efter alle kolonner.</span><span class="sxs-lookup"><span data-stu-id="f6739-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f6739-124">![Tilføjet datakilde](media/configure-data-datasource-added.png "Tilføjet datakilde")</span><span class="sxs-lookup"><span data-stu-id="f6739-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="f6739-125">Status</span><span class="sxs-lookup"><span data-stu-id="f6739-125">Status</span></span>  |<span data-ttu-id="f6739-126">Beskrivelse</span><span class="sxs-lookup"><span data-stu-id="f6739-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="f6739-127">Fuldført</span><span class="sxs-lookup"><span data-stu-id="f6739-127">Successful</span></span>   |<span data-ttu-id="f6739-128">Datakilde blev indregistreret, hvis der er angivet et tidspunkt i den **Opdaterede** kolonne.</span><span class="sxs-lookup"><span data-stu-id="f6739-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="f6739-129">Ikke startet</span><span class="sxs-lookup"><span data-stu-id="f6739-129">Not started</span></span>   |<span data-ttu-id="f6739-130">Datakilde har ingen data, der er indsat endnu, eller er stadig i kladdetilstand.</span><span class="sxs-lookup"><span data-stu-id="f6739-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="f6739-131">Opdaterer</span><span class="sxs-lookup"><span data-stu-id="f6739-131">Refreshing</span></span>    |<span data-ttu-id="f6739-132">Dataindtagelse er i gang.</span><span class="sxs-lookup"><span data-stu-id="f6739-132">Data ingestion is in progress.</span></span> <span data-ttu-id="f6739-133">Du kan annullere denne handling ved at vælge **Stop opdatering** i kolonnen **Handlinger**.</span><span class="sxs-lookup"><span data-stu-id="f6739-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="f6739-134">Hvis du stopper opdateringen af en datakilde, gendannes den til den seneste opdateringstilstand.</span><span class="sxs-lookup"><span data-stu-id="f6739-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="f6739-135">Mislykket</span><span class="sxs-lookup"><span data-stu-id="f6739-135">Failed</span></span>     |<span data-ttu-id="f6739-136">Der opstod fejl under indtagelse af data.</span><span class="sxs-lookup"><span data-stu-id="f6739-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="f6739-137">Vælg værdien i kolonnen **Status** i en hvilken som helst datakilde du vil gennemse for flere detaljer.</span><span class="sxs-lookup"><span data-stu-id="f6739-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="f6739-138">Udvid **Datakilder** i ruden **Statusdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="f6739-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="f6739-139">Vælg **Se detaljer** for at få vist flere oplysninger om opdateringsstatus, herunder fejldetaljer og downstream-procesopdateringer.</span><span class="sxs-lookup"><span data-stu-id="f6739-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="f6739-140">Indlæsning af tage kan tage et stykke tid.</span><span class="sxs-lookup"><span data-stu-id="f6739-140">Loading data can take some time.</span></span> <span data-ttu-id="f6739-141">Når opdateringen er gennemført, kan de indtagne data gennemses fra siden **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="f6739-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="f6739-142">Du kan finde flere oplysninger under [Objekter](entities.md).</span><span class="sxs-lookup"><span data-stu-id="f6739-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="f6739-143">Opdater en datakilde</span><span class="sxs-lookup"><span data-stu-id="f6739-143">Refresh a data source</span></span>

<span data-ttu-id="f6739-144">Datakilder kan opdateres automatisk i en automatisk planlægning eller opdateres manuelt efter behov.</span><span class="sxs-lookup"><span data-stu-id="f6739-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="f6739-145">Gå til **Administrator** > **System** > [**Tidsplan**](system.md#schedule-tab) for at konfigurere planlagte opdateringer af alle dine påtagede datakilder.</span><span class="sxs-lookup"><span data-stu-id="f6739-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="f6739-146">Benyt følgende fremgangsmåde for at opdatere en datakilde efter behov:</span><span class="sxs-lookup"><span data-stu-id="f6739-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="f6739-147">Gå til **Data** > **Datakilder** i målgruppen Insights</span><span class="sxs-lookup"><span data-stu-id="f6739-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="f6739-148">Vælg den lodrette ellipse ud for den datakilde, du vil opdatere, og vælg **Opdater** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="f6739-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="f6739-149">Datakilden er nu udløst for at få en manuel opdatering.</span><span class="sxs-lookup"><span data-stu-id="f6739-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="f6739-150">Hvis du opdaterer en datakilde, opdateres både objektskemaet og dataene for alle de objekter, der er angivet i datakilden.</span><span class="sxs-lookup"><span data-stu-id="f6739-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="f6739-151">Vælg **Stop opdatering**, hvis du vil annullere en eksisterende opdatering, og datakilden nulstilles til seneste opdateringsstatus.</span><span class="sxs-lookup"><span data-stu-id="f6739-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="f6739-152">Slette en datakilde</span><span class="sxs-lookup"><span data-stu-id="f6739-152">Delete a data source</span></span>

1. <span data-ttu-id="f6739-153">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="f6739-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="f6739-154">Vælg den lodrette ellipse ud for den datakilde, du vil fjerne, og vælg **Slet** i rullemenuen.</span><span class="sxs-lookup"><span data-stu-id="f6739-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="f6739-155">Bekræft sletningen.</span><span class="sxs-lookup"><span data-stu-id="f6739-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
