---
title: Brug datakilder til at indsætte data
description: Få mere at vide om, hvordan du importerer data fra forskellige kilder.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269691"
---
# <a name="data-sources-overview"></a><span data-ttu-id="902de-103">Oversigt over datakilder</span><span class="sxs-lookup"><span data-stu-id="902de-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="902de-104">Målgruppeindsigt-muligheden for Dynamics 365 Customer Insights opretter forbindelse til data fra et bredt udvalg af kilder.</span><span class="sxs-lookup"><span data-stu-id="902de-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="902de-105">Oprettelse af forbindelse til en datakilde kaldes ofte processen for *dataindtagelse*.</span><span class="sxs-lookup"><span data-stu-id="902de-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="902de-106">Når du har indtaget dataene, kan du [samle](data-unification.md) og udføre handlinger på dem.</span><span class="sxs-lookup"><span data-stu-id="902de-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="902de-107">Tilføj en datakilde</span><span class="sxs-lookup"><span data-stu-id="902de-107">Add a data source</span></span>

<span data-ttu-id="902de-108">Se de detaljerede artikler om, hvordan du kan tilføje en datakilde, afhængigt af den indstilling, du vælger.</span><span class="sxs-lookup"><span data-stu-id="902de-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="902de-109">Du kan tilføje en datakilde på tre primære måder:</span><span class="sxs-lookup"><span data-stu-id="902de-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="902de-110">Via dusinvis af Power Query-connectorer</span><span class="sxs-lookup"><span data-stu-id="902de-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="902de-111">Fra en Common Data Model-mappe</span><span class="sxs-lookup"><span data-stu-id="902de-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="902de-112">Fra din egen Common Data Service-sø</span><span class="sxs-lookup"><span data-stu-id="902de-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="902de-113">Du kan ikke tilføje data fra datakilder i det lokale miljø endnu.</span><span class="sxs-lookup"><span data-stu-id="902de-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="902de-114">Gennemgå indtagede data</span><span class="sxs-lookup"><span data-stu-id="902de-114">Review ingested data</span></span>

<span data-ttu-id="902de-115">Du får vist navnet på hver indtagne datakilde, dens status, og hvornår dataene sidst blev opdateret for den pågældende kilde.</span><span class="sxs-lookup"><span data-stu-id="902de-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="902de-116">Du kan sortere listen over datakilder efter alle kolonner.</span><span class="sxs-lookup"><span data-stu-id="902de-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="902de-117">![Tilføjet datakilde](media/configure-data-datasource-added.png "Tilføjet datakilde")</span><span class="sxs-lookup"><span data-stu-id="902de-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="902de-118">Status</span><span class="sxs-lookup"><span data-stu-id="902de-118">Status</span></span>  |<span data-ttu-id="902de-119">Beskrivelse</span><span class="sxs-lookup"><span data-stu-id="902de-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="902de-120">Fuldført</span><span class="sxs-lookup"><span data-stu-id="902de-120">Successful</span></span>   |<span data-ttu-id="902de-121">Datakilde blev indregistreret, hvis der er angivet et tidspunkt i den **Opdaterede** kolonne.</span><span class="sxs-lookup"><span data-stu-id="902de-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="902de-122">Ikke startet</span><span class="sxs-lookup"><span data-stu-id="902de-122">Not started</span></span>   |<span data-ttu-id="902de-123">Datakilde har ingen data, der er indsat endnu, eller er stadig i kladdetilstand.</span><span class="sxs-lookup"><span data-stu-id="902de-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="902de-124">Opdaterer</span><span class="sxs-lookup"><span data-stu-id="902de-124">Refreshing</span></span>    |<span data-ttu-id="902de-125">Dataindtagelse er i gang.</span><span class="sxs-lookup"><span data-stu-id="902de-125">Data ingestion is in progress.</span></span> <span data-ttu-id="902de-126">Du kan annullere denne handling ved at vælge **Stop opdatering** i kolonnen **Handlinger**.</span><span class="sxs-lookup"><span data-stu-id="902de-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="902de-127">Hvis du stopper opdateringen af en datakilde, gendannes den til den seneste opdateringstilstand.</span><span class="sxs-lookup"><span data-stu-id="902de-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="902de-128">Mislykket</span><span class="sxs-lookup"><span data-stu-id="902de-128">Failed</span></span>     |<span data-ttu-id="902de-129">Der opstod fejl under indtagelse af data.</span><span class="sxs-lookup"><span data-stu-id="902de-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="902de-130">Vælg værdien i kolonnen **Status** i en hvilken som helst datakilde du vil gennemse for flere detaljer.</span><span class="sxs-lookup"><span data-stu-id="902de-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="902de-131">Udvid **Datakilder** i ruden **Statusdetaljer**.</span><span class="sxs-lookup"><span data-stu-id="902de-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="902de-132">Vælg **Se detaljer** for at få vist flere oplysninger om opdateringsstatus, herunder fejldetaljer og downstream-procesopdateringer.</span><span class="sxs-lookup"><span data-stu-id="902de-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="902de-133">Indlæsning af tage kan tage et stykke tid.</span><span class="sxs-lookup"><span data-stu-id="902de-133">Loading data can take some time.</span></span> <span data-ttu-id="902de-134">Når opdateringen er gennemført, kan de indtagne data gennemses fra siden **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="902de-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="902de-135">Du kan finde flere oplysninger under [Objekter](entities.md).</span><span class="sxs-lookup"><span data-stu-id="902de-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="902de-136">Opdater en datakilde</span><span class="sxs-lookup"><span data-stu-id="902de-136">Refresh a data source</span></span>

<span data-ttu-id="902de-137">Datakilder kan opdateres automatisk i en automatisk planlægning eller opdateres manuelt efter behov.</span><span class="sxs-lookup"><span data-stu-id="902de-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="902de-138">Gå til **Administrator** > **System** > [**Tidsplan**](system.md#schedule-tab) for at konfigurere planlagte opdateringer af alle dine påtagede datakilder.</span><span class="sxs-lookup"><span data-stu-id="902de-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="902de-139">Benyt følgende fremgangsmåde for at opdatere en datakilde efter behov:</span><span class="sxs-lookup"><span data-stu-id="902de-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="902de-140">Gå til **Data** > **Datakilder** i målgruppen Insights</span><span class="sxs-lookup"><span data-stu-id="902de-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="902de-141">Vælg den lodrette ellipse ud for den datakilde, du vil opdatere, og vælg **Opdater** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="902de-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="902de-142">Datakilden er nu udløst for at få en manuel opdatering.</span><span class="sxs-lookup"><span data-stu-id="902de-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="902de-143">Hvis du opdaterer en datakilde, opdateres både objektskemaer og data for alle de objekter, der er angivet i datakilden.</span><span class="sxs-lookup"><span data-stu-id="902de-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="902de-144">Vælg **Stop opdatering**, hvis du vil annullere en eksisterende opdatering, og datakilden nulstilles til seneste opdateringsstatus.</span><span class="sxs-lookup"><span data-stu-id="902de-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="902de-145">Slette en datakilde</span><span class="sxs-lookup"><span data-stu-id="902de-145">Delete a data source</span></span>

1. <span data-ttu-id="902de-146">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="902de-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="902de-147">Vælg den lodrette ellipse ud for den datakilde, du vil fjerne, og vælg **Slet** i rullemenuen.</span><span class="sxs-lookup"><span data-stu-id="902de-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="902de-148">Bekræft sletningen.</span><span class="sxs-lookup"><span data-stu-id="902de-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]