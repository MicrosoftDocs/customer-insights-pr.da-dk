---
title: Indsættelse af data via en Power Query forbindelse
description: Connectorer til datakilder, der er baseret på Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405432"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="21e35-103">Oprette forbindelse til en Power Query-datakilde</span><span class="sxs-lookup"><span data-stu-id="21e35-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="21e35-104">Power Query tilbyder en lang række connectorer til indtagelse af data.</span><span class="sxs-lookup"><span data-stu-id="21e35-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="21e35-105">De fleste af disse connectorer understøttes af Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="21e35-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="21e35-106">Hvis du tilføjer datakilder, der er baseret på Power Query-connectorer, følger normalt de trin, der beskrives i næste afsnit.</span><span class="sxs-lookup"><span data-stu-id="21e35-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="21e35-107">Men afhængigt af den connector, du bruger, er der brug for forskellige oplysninger.</span><span class="sxs-lookup"><span data-stu-id="21e35-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="21e35-108">Du kan finde flere oplysninger i dokumentationen om de enkelte connectorer i [Power Query-connector-referencen](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="21e35-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="21e35-109">Oprette en ny datakilde</span><span class="sxs-lookup"><span data-stu-id="21e35-109">Create a new data source</span></span>

1. <span data-ttu-id="21e35-110">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="21e35-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="21e35-111">Vælg **Tilføj datakilde**.</span><span class="sxs-lookup"><span data-stu-id="21e35-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="21e35-112">Vælg metoden **Importér data**, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="21e35-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="21e35-113">Angiv et **Navn** til datakilde, og vælg **Næste** for at oprette datakilden.</span><span class="sxs-lookup"><span data-stu-id="21e35-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="21e35-114">Vælg en af de [tilgængelige connectorer](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="21e35-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="21e35-115">I dette eksempel skal du vælge **Text/CSV** som connector.</span><span class="sxs-lookup"><span data-stu-id="21e35-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="21e35-116">Angiv de nødvendige detaljer i **Forbindelsesindstillinger** for den valgte connector, og vælg **Næste** for at få vist en prøveversion af dataene.</span><span class="sxs-lookup"><span data-stu-id="21e35-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="21e35-117">Vælg **Transformer data**.</span><span class="sxs-lookup"><span data-stu-id="21e35-117">Select **Transform data**.</span></span> <span data-ttu-id="21e35-118">I dette trin skal du føje objekter til din datakilde.</span><span class="sxs-lookup"><span data-stu-id="21e35-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="21e35-119">Objekter er datasæt.</span><span class="sxs-lookup"><span data-stu-id="21e35-119">Entities are datasets.</span></span> <span data-ttu-id="21e35-120">Hvis du har en database, der indeholder flere datasæt, er de enkelte datasæt sit eget objekt.</span><span class="sxs-lookup"><span data-stu-id="21e35-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="21e35-121">Dialogboksen **Power Query - rediger forespørgsler** giver dig mulighed for at gennemse og finpudse dataene.</span><span class="sxs-lookup"><span data-stu-id="21e35-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="21e35-122">De objekter, som systemerne har identificeret i den valgte datakilde, vises i venstre rude.</span><span class="sxs-lookup"><span data-stu-id="21e35-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="21e35-123">![Dialogboksen Rediger forespørgsler](media/data-manager-configure-edit-queries.png "Dialogboksen Rediger forespørgsler")</span><span class="sxs-lookup"><span data-stu-id="21e35-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="21e35-124">Du kan også transformere dine data.</span><span class="sxs-lookup"><span data-stu-id="21e35-124">You can also transform your data.</span></span> <span data-ttu-id="21e35-125">Vælg et objekt, der skal redigeres eller transformeres.</span><span class="sxs-lookup"><span data-stu-id="21e35-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="21e35-126">Brug indstillingerne i Power Query-vinduet til at anvende transformationer.</span><span class="sxs-lookup"><span data-stu-id="21e35-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="21e35-127">Hver transformation er vist under **Anvendte trin**.</span><span class="sxs-lookup"><span data-stu-id="21e35-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="21e35-128">Power Query indeholder mange standardindstillinger for transformation.</span><span class="sxs-lookup"><span data-stu-id="21e35-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="21e35-129">Du kan finde flere oplysninger i [Power Query-transformationer](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="21e35-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="21e35-130">Du kan føje flere objekter til datakilden ved at vælge **Hent data** i dialogboksen **Rediger forespørgsler**.</span><span class="sxs-lookup"><span data-stu-id="21e35-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="21e35-131">Disse transformeringer anbefales på det kraftigste:</span><span class="sxs-lookup"><span data-stu-id="21e35-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="21e35-132">Hvis du indtager data fra en CSV-fil, indeholder den første række ofte overskrifter.</span><span class="sxs-lookup"><span data-stu-id="21e35-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="21e35-133">Gå til **Transformer tabel**, og vælg **Brug overskrifter som første række**.</span><span class="sxs-lookup"><span data-stu-id="21e35-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="21e35-134">Kontrollér, at datatypen er angivet korrekt.</span><span class="sxs-lookup"><span data-stu-id="21e35-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="21e35-135">Vælg **Gem** nederst i Power Query-vinduet for at gemme transformationerne.</span><span class="sxs-lookup"><span data-stu-id="21e35-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="21e35-136">Når du har gemt, kan du finde din datakilde i **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="21e35-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="21e35-137">På siden **Datakilder** skal du bemærke, at den nye datakilde har **Opdatering**-status.</span><span class="sxs-lookup"><span data-stu-id="21e35-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="21e35-138">Tilgængelige Power Query-datakilder</span><span class="sxs-lookup"><span data-stu-id="21e35-138">Available Power Query data sources</span></span>

<span data-ttu-id="21e35-139">Se [Power Query-connector-referencen](https://docs.microsoft.com/power-query/connectors/) for at få en opdateret liste over connectorer, som du kan vælge for at importere data til Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="21e35-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="21e35-140">Connectorer med markering i kolonnen **Customer Insights (dataflows)** er tilgængelige for oprettelse af nye datakilder, der er baseret på Power Query.</span><span class="sxs-lookup"><span data-stu-id="21e35-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="21e35-141">Gennemgå dokumentationen til en bestemt connector for at lære mere om dens forudsætninger, begrænsninger og andre detaljer.</span><span class="sxs-lookup"><span data-stu-id="21e35-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="21e35-142">Redigere Power Query-datakilder</span><span class="sxs-lookup"><span data-stu-id="21e35-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="21e35-143">Det er måske ikke muligt at foretage ændringer af datakilder, der i øjeblikket bruges i en af appens processer (f.eks *segmentering*, *match* eller *fletning*).</span><span class="sxs-lookup"><span data-stu-id="21e35-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="21e35-144">På siden **Indstillinger** kan du spore status for hver af de aktive processer.</span><span class="sxs-lookup"><span data-stu-id="21e35-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="21e35-145">Når en proces er fuldført, kan du vende tilbage til siden **Datakilder** og foretage ændringerne.</span><span class="sxs-lookup"><span data-stu-id="21e35-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="21e35-146">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="21e35-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="21e35-147">Vælg den lodrette ellipse ud for den datakilde, du vil ændre, og vælg **Rediger** i rullemenuen.</span><span class="sxs-lookup"><span data-stu-id="21e35-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="21e35-148">![Indstillingen Rediger](media/edit-option-data-sources.png "Indstillingen Rediger")</span><span class="sxs-lookup"><span data-stu-id="21e35-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="21e35-149">Anvend ændringerne og transformationerne i dialogboksen **Power Query – rediger forespørgsler** som beskrevet i afsnittet [Oprette en ny datakilde](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="21e35-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="21e35-150">Vælg **Gem** i Power Query, når du har fuldført redigeringen, for at gemme ændringerne.</span><span class="sxs-lookup"><span data-stu-id="21e35-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
