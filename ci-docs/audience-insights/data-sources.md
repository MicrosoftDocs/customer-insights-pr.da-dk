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
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643946"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="585ae-103">Oversigt over datakilder</span><span class="sxs-lookup"><span data-stu-id="585ae-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="585ae-104">Målgruppeindsigt-muligheden for Dynamics 365 Customer Insights opretter forbindelse til data fra et bredt udvalg af kilder.</span><span class="sxs-lookup"><span data-stu-id="585ae-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="585ae-105">Oprettelse af forbindelse til en datakilde kaldes ofte processen for *dataindtagelse*.</span><span class="sxs-lookup"><span data-stu-id="585ae-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="585ae-106">Når du har indtaget dataene, kan du [samle](data-unification.md) og udføre handlinger på dem.</span><span class="sxs-lookup"><span data-stu-id="585ae-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="585ae-107">Tilføj en datakilde</span><span class="sxs-lookup"><span data-stu-id="585ae-107">Add a data source</span></span>

<span data-ttu-id="585ae-108">Se de detaljerede artikler om, hvordan du kan tilføje en datakilde, afhængigt af den indstilling, du vælger.</span><span class="sxs-lookup"><span data-stu-id="585ae-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="585ae-109">Du kan tilføje en datakilde på tre primære måder:</span><span class="sxs-lookup"><span data-stu-id="585ae-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="585ae-110">Via dusinvis af Power Query-connectorer</span><span class="sxs-lookup"><span data-stu-id="585ae-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="585ae-111">Fra en Common Data Model-mappe</span><span class="sxs-lookup"><span data-stu-id="585ae-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="585ae-112">Fra din egen Common Data Service-sø</span><span class="sxs-lookup"><span data-stu-id="585ae-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="585ae-113">Du kan ikke tilføje data fra datakilder i det lokale miljø endnu.</span><span class="sxs-lookup"><span data-stu-id="585ae-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="585ae-114">Gennemgå indtagede data</span><span class="sxs-lookup"><span data-stu-id="585ae-114">Review ingested data</span></span>

<span data-ttu-id="585ae-115">Du får vist navnet på hver indtagne datakilde, dens status, og hvornår dataene sidst blev opdateret for den pågældende kilde.</span><span class="sxs-lookup"><span data-stu-id="585ae-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="585ae-116">Du kan sortere listen over datakilder efter alle kolonner.</span><span class="sxs-lookup"><span data-stu-id="585ae-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="585ae-117">![Tilføjet datakilde](media/configure-data-datasource-added.png "Tilføjet datakilde")</span><span class="sxs-lookup"><span data-stu-id="585ae-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="585ae-118">Status</span><span class="sxs-lookup"><span data-stu-id="585ae-118">Status</span></span>  |<span data-ttu-id="585ae-119">Beskrivelse</span><span class="sxs-lookup"><span data-stu-id="585ae-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="585ae-120">Fuldført</span><span class="sxs-lookup"><span data-stu-id="585ae-120">Successful</span></span>   |<span data-ttu-id="585ae-121">Datakilde blev indregistreret, hvis der er angivet et tidspunkt i den **Opdaterede** kolonne.</span><span class="sxs-lookup"><span data-stu-id="585ae-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="585ae-122">Ikke startet</span><span class="sxs-lookup"><span data-stu-id="585ae-122">Not started</span></span>   |<span data-ttu-id="585ae-123">Datakilde har ingen data, der er indsat endnu, eller er stadig i kladdetilstand.</span><span class="sxs-lookup"><span data-stu-id="585ae-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="585ae-124">Opdaterer</span><span class="sxs-lookup"><span data-stu-id="585ae-124">Refreshing</span></span>    |<span data-ttu-id="585ae-125">Dataindtagelse er i gang.</span><span class="sxs-lookup"><span data-stu-id="585ae-125">Data ingestion is in progress.</span></span> <span data-ttu-id="585ae-126">Du kan annullere denne handling ved at vælge **Stop opdatering** i kolonnen **Handlinger**.</span><span class="sxs-lookup"><span data-stu-id="585ae-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="585ae-127">Hvis du stopper opdateringen af en datakilde, gendannes den til den seneste opdateringstilstand.</span><span class="sxs-lookup"><span data-stu-id="585ae-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="585ae-128">Mislykket</span><span class="sxs-lookup"><span data-stu-id="585ae-128">Failed</span></span>     |<span data-ttu-id="585ae-129">Der opstod fejl under indtagelse af data.</span><span class="sxs-lookup"><span data-stu-id="585ae-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="585ae-130">Vælg **Opdateringsstatus** for at få vist flere detaljer om opdateringsstatus, herunder fejldetaljer og downstream-procesopdateringer.</span><span class="sxs-lookup"><span data-stu-id="585ae-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="585ae-131">Indlæsning af tage kan tage et stykke tid.</span><span class="sxs-lookup"><span data-stu-id="585ae-131">Loading data can take some time.</span></span> <span data-ttu-id="585ae-132">Når opdateringen er gennemført, kan de indtagne data gennemses fra siden **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="585ae-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="585ae-133">Du kan finde flere oplysninger under [Objekter](entities.md).</span><span class="sxs-lookup"><span data-stu-id="585ae-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="585ae-134">Opdater en datakilde</span><span class="sxs-lookup"><span data-stu-id="585ae-134">Refresh a data source</span></span>

<span data-ttu-id="585ae-135">Datakilder kan opdateres automatisk i en automatisk planlægning eller opdateres manuelt efter behov.</span><span class="sxs-lookup"><span data-stu-id="585ae-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="585ae-136">Gå til **Administrator** > **System** > [**Tidsplan**](system.md#schedule-tab) for at konfigurere planlagte opdateringer af alle dine påtagede datakilder.</span><span class="sxs-lookup"><span data-stu-id="585ae-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="585ae-137">Benyt følgende fremgangsmåde for at opdatere en datakilde efter behov:</span><span class="sxs-lookup"><span data-stu-id="585ae-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="585ae-138">Gå til **Data** > **Datakilder** i målgruppen Insights</span><span class="sxs-lookup"><span data-stu-id="585ae-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="585ae-139">Vælg den lodrette ellipse ud for den datakilde, du vil opdatere, og vælg **Opdater** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="585ae-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="585ae-140">Datakilden er nu udløst for at få en manuel opdatering.</span><span class="sxs-lookup"><span data-stu-id="585ae-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="585ae-141">Hvis du opdaterer en datakilde, opdateres både objektskemaer og data for alle de objekter, der er angivet i datakilden.</span><span class="sxs-lookup"><span data-stu-id="585ae-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="585ae-142">Vælg **Stop opdatering**, hvis du vil annullere en eksisterende opdatering, og datakilden nulstilles til seneste opdateringsstatus.</span><span class="sxs-lookup"><span data-stu-id="585ae-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="585ae-143">Slette en datakilde</span><span class="sxs-lookup"><span data-stu-id="585ae-143">Delete a data source</span></span>

1. <span data-ttu-id="585ae-144">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="585ae-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="585ae-145">Vælg den lodrette ellipse ud for den datakilde, du vil fjerne, og vælg **Slet** i rullemenuen.</span><span class="sxs-lookup"><span data-stu-id="585ae-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="585ae-146">Bekræft sletningen.</span><span class="sxs-lookup"><span data-stu-id="585ae-146">Confirm your deletion.</span></span>
