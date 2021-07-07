---
title: Indsættelse af data via en Power Query forbindelse
description: Connectorer til datakilder, der er baseret på Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305884"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="4ccf9-103">Oprette forbindelse til en Power Query-datakilde</span><span class="sxs-lookup"><span data-stu-id="4ccf9-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="4ccf9-104">Power Query tilbyder en lang række connectorer til indtagelse af data.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="4ccf9-105">De fleste af disse connectorer understøttes af Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="4ccf9-106">Hvis du tilføjer datakilder, der er baseret på Power Query-connectorer, følger normalt de trin, der beskrives i næste afsnit.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="4ccf9-107">Men afhængigt af den connector, du bruger, er der brug for forskellige oplysninger.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="4ccf9-108">Du kan finde flere oplysninger i dokumentationen om de enkelte connectorer i [Power Query-connector-referencen](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="4ccf9-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="4ccf9-109">Oprette en ny datakilde</span><span class="sxs-lookup"><span data-stu-id="4ccf9-109">Create a new data source</span></span>

1. <span data-ttu-id="4ccf9-110">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="4ccf9-111">Vælg **Tilføj datakilde**.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="4ccf9-112">Vælg metoden **Importér data**, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="4ccf9-113">Angiv et **Navn** til datakilde, og vælg **Næste** for at oprette datakilden.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="4ccf9-114">Navneretningslinjer:</span><span class="sxs-lookup"><span data-stu-id="4ccf9-114">Name guidelines:</span></span> 
   - <span data-ttu-id="4ccf9-115">Start med et bogstav.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-115">Start with a letter.</span></span>
   - <span data-ttu-id="4ccf9-116">Brug kun bogstaver og tal.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-116">Use letters and numbers only.</span></span> <span data-ttu-id="4ccf9-117">Specialtegn og mellemrum er ikke tilladt.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="4ccf9-118">Brug mellem 3 og 64 tegn.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="4ccf9-119">Vælg en af de [tilgængelige connectorer](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="4ccf9-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="4ccf9-120">I dette eksempel skal du vælge **Text/CSV** som connector.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4ccf9-121">Angiv de nødvendige detaljer i **Forbindelsesindstillinger** for den valgte connector, og vælg **Næste** for at få vist en prøveversion af dataene.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="4ccf9-122">Vælg **Transformer data**.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-122">Select **Transform data**.</span></span> <span data-ttu-id="4ccf9-123">I dette trin skal du føje objekter til din datakilde.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="4ccf9-124">Objekter er datasæt.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-124">Entities are datasets.</span></span> <span data-ttu-id="4ccf9-125">Hvis du har en database, der indeholder flere datasæt, er de enkelte datasæt sit eget objekt.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="4ccf9-126">Dialogboksen **Power Query - rediger forespørgsler** giver dig mulighed for at gennemse og finpudse dataene.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="4ccf9-127">De objekter, som systemerne har identificeret i den valgte datakilde, vises i venstre rude.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4ccf9-128">![Dialogboksen Rediger forespørgsler](media/data-manager-configure-edit-queries.png "Dialogboksen Rediger forespørgsler")</span><span class="sxs-lookup"><span data-stu-id="4ccf9-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="4ccf9-129">Du kan også transformere dine data.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-129">You can also transform your data.</span></span> <span data-ttu-id="4ccf9-130">Vælg et objekt, der skal redigeres eller transformeres.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="4ccf9-131">Brug indstillingerne i Power Query-vinduet til at anvende transformationer.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="4ccf9-132">Hver transformation er vist under **Anvendte trin**.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="4ccf9-133">Power Query indeholder mange standardindstillinger for transformation.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="4ccf9-134">Du kan finde flere oplysninger i [Power Query-transformationer](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="4ccf9-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="4ccf9-135">Du kan føje flere objekter til datakilden ved at vælge **Hent data** i dialogboksen **Rediger forespørgsler**.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="4ccf9-136">Disse transformeringer anbefales på det kraftigste:</span><span class="sxs-lookup"><span data-stu-id="4ccf9-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="4ccf9-137">Hvis du indtager data fra en CSV-fil, indeholder den første række ofte overskrifter.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="4ccf9-138">Gå til **Transformer tabel**, og vælg **Brug overskrifter som første række**.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="4ccf9-139">Kontrollér, at datatypen er angivet korrekt.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="4ccf9-140">Vælg **Gem** nederst i Power Query-vinduet for at gemme transformationerne.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="4ccf9-141">Når du har gemt, kan du finde din datakilde i **Data** > **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="4ccf9-142">På siden **Datakilder** skal du bemærke, at den nye datakilde har **Opdatering**-status.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="4ccf9-143">Tilgængelige Power Query-datakilder</span><span class="sxs-lookup"><span data-stu-id="4ccf9-143">Available Power Query data sources</span></span>

<span data-ttu-id="4ccf9-144">Se [Power Query-connector-referencen](/power-query/connectors/) for at få en opdateret liste over connectorer, som du kan vælge for at importere data til Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="4ccf9-145">Connectorer med markering i kolonnen **Customer Insights (dataflows)** er tilgængelige for oprettelse af nye datakilder, der er baseret på Power Query.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="4ccf9-146">Gennemgå dokumentationen til en bestemt connector for at lære mere om dens forudsætninger, begrænsninger og andre detaljer.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="4ccf9-147">Redigere Power Query-datakilder</span><span class="sxs-lookup"><span data-stu-id="4ccf9-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="4ccf9-148">Det er måske ikke muligt at foretage ændringer af datakilder, der i øjeblikket bruges i en af appens processer (f.eks *segmentering*, *match* eller *fletning*).</span><span class="sxs-lookup"><span data-stu-id="4ccf9-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="4ccf9-149">På siden **Indstillinger** kan du spore status for hver af de aktive processer.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="4ccf9-150">Når en proces er fuldført, kan du vende tilbage til siden **Datakilder** og foretage ændringerne.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="4ccf9-151">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="4ccf9-152">Vælg den lodrette ellipse ud for den datakilde, du vil ændre, og vælg **Rediger** i rullemenuen.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the dropdown menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4ccf9-153">![Indstillingen Rediger](media/edit-option-data-sources.png "Indstillingen Rediger")</span><span class="sxs-lookup"><span data-stu-id="4ccf9-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="4ccf9-154">Anvend ændringerne og transformationerne i dialogboksen **Power Query – rediger forespørgsler** som beskrevet i afsnittet [Oprette en ny datakilde](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="4ccf9-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="4ccf9-155">Vælg **Gem** i Power Query, når du har fuldført redigeringen, for at gemme ændringerne.</span><span class="sxs-lookup"><span data-stu-id="4ccf9-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]