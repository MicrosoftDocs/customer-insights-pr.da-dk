---
title: Eksportdestinationer
description: Eksportér data, og administrer eksportdestinationer.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643856"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="80652-103">Eksportdestinationer (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="80652-103">Export destinations (preview)</span></span>

<span data-ttu-id="80652-104">Siden **Eksportdestinationer** viser alle de placeringer, du har konfigureret til at eksportere data til.</span><span class="sxs-lookup"><span data-stu-id="80652-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="80652-105">Du kan også tilføje nye destinationer til eksport.</span><span class="sxs-lookup"><span data-stu-id="80652-105">You can also add new destinations for export.</span></span> <span data-ttu-id="80652-106">Derudover vises de eksportindstillinger, der er tilgængelige i øjeblikket.</span><span class="sxs-lookup"><span data-stu-id="80652-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="80652-107">Få en hurtig oversigt og beskrivelse, og find ud af, hvad du kan gøre med de enkelte udvidelsesmuligheder.</span><span class="sxs-lookup"><span data-stu-id="80652-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="80652-108">Eksportér ensartede profiler, målpunkter og segmenter til understøttede apps, som er relevante for din virksomhed.</span><span class="sxs-lookup"><span data-stu-id="80652-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="80652-109">Gå til **Admin** > **Exportdestinationer** for at finde følgende udvidelsesmuligheder:</span><span class="sxs-lookup"><span data-stu-id="80652-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="80652-110">Dynamics 365 Customer Kundekort</span><span class="sxs-lookup"><span data-stu-id="80652-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="80652-111">Facebook Annonceadministrator-connector</span><span class="sxs-lookup"><span data-stu-id="80652-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="80652-112">Power AutomateConnector</span><span class="sxs-lookup"><span data-stu-id="80652-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="80652-113">Power AppsConnector</span><span class="sxs-lookup"><span data-stu-id="80652-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="80652-114">Power BIConnector</span><span class="sxs-lookup"><span data-stu-id="80652-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="80652-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="80652-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="80652-116">Dynamics 365-salg</span><span class="sxs-lookup"><span data-stu-id="80652-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="80652-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="80652-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="80652-118">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="80652-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="80652-119">LiveRamp&reg;-connector</span><span class="sxs-lookup"><span data-stu-id="80652-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="80652-120">Bot til Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="80652-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="80652-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="80652-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="80652-122">Customer Insights API</span><span class="sxs-lookup"><span data-stu-id="80652-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="80652-123">Tilføje en ny eksportdestination</span><span class="sxs-lookup"><span data-stu-id="80652-123">Add a new export destination</span></span>

<span data-ttu-id="80652-124">Hvis du vil tilføje eksportdestinationer, har du [administratortilladelser](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="80652-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="80652-125">Hvis du eksporterer til Microsoft-tjenester, antages det, at begge servicer er i den samme organisation.</span><span class="sxs-lookup"><span data-stu-id="80652-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="80652-126">Gå til **Adminstration** > **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="80652-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="80652-127">Skift til fanen **Mine eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="80652-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="80652-128">Vælg **Tilføj destination** for at oprette en ny eksportdestination.</span><span class="sxs-lookup"><span data-stu-id="80652-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="80652-129">På ruden **Tilføj destination** vælg **Type** for eksportdestination fra rullelisten.</span><span class="sxs-lookup"><span data-stu-id="80652-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="80652-130">Angiv de nødvendige oplysninger, og vælg **Næste** for at oprette eksportdestinationen.</span><span class="sxs-lookup"><span data-stu-id="80652-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="80652-131">Du kan også vælge **Konfigurer** i et område på fanen **Udforsk**.</span><span class="sxs-lookup"><span data-stu-id="80652-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="80652-132">Vise Eksportdestinationer</span><span class="sxs-lookup"><span data-stu-id="80652-132">View Export destinations</span></span>

<span data-ttu-id="80652-133">Når du har oprettet eksportdestinationer, kan du finde dem i en tabel under fanen **Mine eksportdestinationer**. Denne tabel indeholder tre kolonner:</span><span class="sxs-lookup"><span data-stu-id="80652-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="80652-134">**Vist navn**: Det navn, du angav under oprettelsen af destinationen.</span><span class="sxs-lookup"><span data-stu-id="80652-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="80652-135">**Type**: Den eksportdestinationstype, du angav, da du oprettede destinationen.</span><span class="sxs-lookup"><span data-stu-id="80652-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="80652-136">**Oprettet den**: Den dato, hvor du oprettede destinationen.</span><span class="sxs-lookup"><span data-stu-id="80652-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="80652-137">Rediger en eksportdestination</span><span class="sxs-lookup"><span data-stu-id="80652-137">Edit an export destination</span></span>

1. <span data-ttu-id="80652-138">Vælg den lodrette ellipse for den eksportdestination, du vil redigere.</span><span class="sxs-lookup"><span data-stu-id="80652-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80652-139">![Lodret ellipse](media/export-destinations-page-ellipsis.png "Lodret ellipse")</span><span class="sxs-lookup"><span data-stu-id="80652-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="80652-140">Vælg **Rediger** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="80652-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="80652-141">Rediger de værdier, der skal opdateres, og vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="80652-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="80652-142">Eksporter data efter behov</span><span class="sxs-lookup"><span data-stu-id="80652-142">Export data on demand</span></span>

<span data-ttu-id="80652-143">Når en connector er konfigureret til en eksportdestination, køres eksporter med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="80652-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="80652-144">Hvis du vil eksportere data uden at vente på en planlagt opdatering, så gå til fanen **Mine eksportdestinationer** i **Administrator** > **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="80652-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="80652-145">![Lodret ellipse](media/export-destinations-page-ellipsis.png "Lodret ellipse")</span><span class="sxs-lookup"><span data-stu-id="80652-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="80652-146">Vælg **Eksport** over listen for at køre eksporten til alle eksportdestinationer på samme tid.</span><span class="sxs-lookup"><span data-stu-id="80652-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="80652-147">Vælg ellipsen (...) efter et listeelement, og vælg derefter indstillingen **Eksport** for at køre eksporten for en enkelt eksportdestination.</span><span class="sxs-lookup"><span data-stu-id="80652-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="80652-148">Fjerne en eksportdestination</span><span class="sxs-lookup"><span data-stu-id="80652-148">Remove an Export destination</span></span>

<span data-ttu-id="80652-149">Hvis du vil fjerne en eksportdestination, skal du begynde på siden med primære **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="80652-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="80652-150">Vælg den lodrette ellipse for den eksportdestination, du vil fjerne.</span><span class="sxs-lookup"><span data-stu-id="80652-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80652-151">![Lodret ellipse](media/export-destinations-page-ellipsis.png "Lodret ellipse")</span><span class="sxs-lookup"><span data-stu-id="80652-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="80652-152">Vælg **Fjern** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="80652-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="80652-153">Bekræft fjernelsen ved at vælge **Fjern** på bekræftelsesskærmen.</span><span class="sxs-lookup"><span data-stu-id="80652-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
