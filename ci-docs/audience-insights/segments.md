---
title: Segmenter i målgruppeindsigt
description: Oversigt over segmenter, og hvordan de oprettes og administreres.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111380"
---
# <a name="segments-overview"></a><span data-ttu-id="c4e24-103">Oversigter over segmenter</span><span class="sxs-lookup"><span data-stu-id="c4e24-103">Segments overview</span></span>

<span data-ttu-id="c4e24-104">Med segmenter kan du gruppere dine kunder baseret på demografiske, transaktionsrelaterede eller adfærdsattributter.</span><span class="sxs-lookup"><span data-stu-id="c4e24-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="c4e24-105">Du kan bruge segmenter til at målrette kampagnefremstød, salgsaktiviteter og kundesupporthandlinger for at nå dine forretningsmæssige mål.</span><span class="sxs-lookup"><span data-stu-id="c4e24-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="c4e24-106">Kundeprofiler, der matcher filtrene i en segmentdefinition, kaldes *medlemmer* af et segment.</span><span class="sxs-lookup"><span data-stu-id="c4e24-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="c4e24-107">Der gælder nogle [tjenestebegrænsninger](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="c4e24-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="c4e24-108">Oprette et nyt segment</span><span class="sxs-lookup"><span data-stu-id="c4e24-108">Create a new segment</span></span>

<span data-ttu-id="c4e24-109">Der er flere måder, du kan oprette et nyt segment på:</span><span class="sxs-lookup"><span data-stu-id="c4e24-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="c4e24-110">Komplekst segment med segmentgenerator: [Tomt segment](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="c4e24-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="c4e24-111">Simple segmenter med én operator: [Hurtigt segment](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="c4e24-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="c4e24-112">AI-baserede måder at finde lignende kunder på: [Lignende kunder](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="c4e24-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="c4e24-113">AI-baserede forslag ud fra målinger eller attributter: [Foreslåede segmenter til forbedring af målingerne](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="c4e24-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="c4e24-114">Forslag baseret på aktiviteter: [Foreslåede segmenter baseret på kundeaktivitet](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="c4e24-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="c4e24-115">Administrere eksisterende segmenter</span><span class="sxs-lookup"><span data-stu-id="c4e24-115">Manage existing segments</span></span>

<span data-ttu-id="c4e24-116">Gå til siden **Segmenter** for at få vist alle dine gemte segmenter og administrere dem.</span><span class="sxs-lookup"><span data-stu-id="c4e24-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="c4e24-117">De enkelte segmenter repræsenteres af en række, der indeholder yderligere oplysninger om segmentet.</span><span class="sxs-lookup"><span data-stu-id="c4e24-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Markeret segment med rulleliste med indstillinger og tilgængelige indstillinger.":::

<span data-ttu-id="c4e24-119">Følgende handlinger er tilgængelige, når du vælger et segment:</span><span class="sxs-lookup"><span data-stu-id="c4e24-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="c4e24-120">**Vis** segmentoplysningerne, herunder tendensen for antal medlemmer, et eksempel på segmentmedlemmer.</span><span class="sxs-lookup"><span data-stu-id="c4e24-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="c4e24-121">**Rediger** segmentet for at ændre dets egenskaber.</span><span class="sxs-lookup"><span data-stu-id="c4e24-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="c4e24-122">**Opret en dublet** af et segment.</span><span class="sxs-lookup"><span data-stu-id="c4e24-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="c4e24-123">Du kan vælge at redigere egenskaberne med det samme eller ganske enkelt gemme dubletten.</span><span class="sxs-lookup"><span data-stu-id="c4e24-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="c4e24-124">**Opdater** segmentet, så det indeholder de seneste data.</span><span class="sxs-lookup"><span data-stu-id="c4e24-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="c4e24-125">**Aktivér** eller **Deaktiver** segmentet.</span><span class="sxs-lookup"><span data-stu-id="c4e24-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="c4e24-126">Segmenter har to mulige tilstande - aktiv og inaktiv.</span><span class="sxs-lookup"><span data-stu-id="c4e24-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="c4e24-127">Disse tilstande er praktiske, når du redigerer et segment.</span><span class="sxs-lookup"><span data-stu-id="c4e24-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="c4e24-128">I forbindelse med inaktive segmenter findes der en definition af segmentet, men den indeholder ikke nogen kunder endnu.</span><span class="sxs-lookup"><span data-stu-id="c4e24-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="c4e24-129">Når du aktiverer et segment, ændres dets tilstand fra 'inaktiv' til "aktiv", og der starter en søgning efter de kunder, der opfylder segmentdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="c4e24-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="c4e24-130">Hvis der er konfigureret en [planlagt opdatering](system.md#schedule-tab), har vises **Status** for inaktive segmenter som **Sprunget over** som tegn på, at en opdatering ikke er forsøgt udført.</span><span class="sxs-lookup"><span data-stu-id="c4e24-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="c4e24-131">Når et inaktivt segment aktiveres, opdateres det og inkluderes i de planlagte opdateringer.</span><span class="sxs-lookup"><span data-stu-id="c4e24-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="c4e24-132">Du kan også bruge **Planlæg senere** i rullemenuen **Aktivér/deaktiver** til at angive fremtidig dato og klokkeslæt for aktivering og deaktivering af et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="c4e24-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="c4e24-133">**Omdøb** segmentet.</span><span class="sxs-lookup"><span data-stu-id="c4e24-133">**Rename** the segment.</span></span>
- <span data-ttu-id="c4e24-134">**Hent** listen over medlemmer som en .CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="c4e24-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="c4e24-135">**Administrer eksport** for at få vist eksportrelaterede segmenter og administrere dem.</span><span class="sxs-lookup"><span data-stu-id="c4e24-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="c4e24-136">Få mere at vide om eksporter</span><span class="sxs-lookup"><span data-stu-id="c4e24-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="c4e24-137">**Slet** segmentet.</span><span class="sxs-lookup"><span data-stu-id="c4e24-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="c4e24-138">Opdatere segmenter</span><span class="sxs-lookup"><span data-stu-id="c4e24-138">Refresh segments</span></span>

<span data-ttu-id="c4e24-139">Du kan opdatere alle segmenter på én gang ved at vælge **Opdater alle** på siden **Segmenter**, eller du kan opdatere et eller flere segmenter, når du vælger dem, og vælge **Opdater** fra indstillingerne.</span><span class="sxs-lookup"><span data-stu-id="c4e24-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="c4e24-140">Du kan også konfigurere en tilbagevendende opdatering i **Admin** > **System** > **Planlæg**.</span><span class="sxs-lookup"><span data-stu-id="c4e24-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="c4e24-141">Opgaver og processer indeholder [seks typer status](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="c4e24-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c4e24-142">De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c4e24-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c4e24-143">Du kan vælge status for en proces for at se statusdetaljer for hele jobbet.</span><span class="sxs-lookup"><span data-stu-id="c4e24-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c4e24-144">Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.</span><span class="sxs-lookup"><span data-stu-id="c4e24-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="c4e24-145">Eksportere segmenter</span><span class="sxs-lookup"><span data-stu-id="c4e24-145">Export segments</span></span>

<span data-ttu-id="c4e24-146">Du kan eksportere et segment fra segmentsiden eller [eksportsiden](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c4e24-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="c4e24-147">Gå til siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="c4e24-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="c4e24-148">Vælg **Vis mere [...]** for det segment, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="c4e24-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="c4e24-149">Vælg **Administrer eksporter** på rullelisten med handlinger.</span><span class="sxs-lookup"><span data-stu-id="c4e24-149">Select **Manage exports** from the actions drop-down list.</span></span>

1. <span data-ttu-id="c4e24-150">Siden **Eksporter (forhåndsversion) for segment** åbnes.</span><span class="sxs-lookup"><span data-stu-id="c4e24-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="c4e24-151">Alle konfigurerede eksporter vises grupperet efter eksporter, der indeholder det aktuelle segment eller ikke indeholder det.</span><span class="sxs-lookup"><span data-stu-id="c4e24-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="c4e24-152">Hvis du vil føje det valgte segment til en eksport, skal du markere eksporten på listen og vælge **Tilføj segment**.</span><span class="sxs-lookup"><span data-stu-id="c4e24-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="c4e24-153">Hvis du vil oprette en ny eksport med det valgte segment, skal du vælge **Tilføj eksport**.</span><span class="sxs-lookup"><span data-stu-id="c4e24-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="c4e24-154">Du kan finde flere oplysninger om oprettelse af eksport i [Konfigurere en ny eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c4e24-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c4e24-155">Vælg **Tilbage** for at vende tilbage til hovedsiden for segmenter.</span><span class="sxs-lookup"><span data-stu-id="c4e24-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="c4e24-156">Se behandlingshistorik og segmentmedlemmer</span><span class="sxs-lookup"><span data-stu-id="c4e24-156">View processing history and segment members</span></span>

<span data-ttu-id="c4e24-157">Du kan se konsoliderede data om et segment ved at gennemgå dets detaljer.</span><span class="sxs-lookup"><span data-stu-id="c4e24-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="c4e24-158">Vælg det segment, du vil gennemgå, på siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="c4e24-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="c4e24-159">Den øverste del af siden indeholder en tendensgraf, der viser ændringer i medlemsantal.</span><span class="sxs-lookup"><span data-stu-id="c4e24-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="c4e24-160">Peg på datapunkter for at få vist medlemsantallet på en bestemt dato.</span><span class="sxs-lookup"><span data-stu-id="c4e24-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="c4e24-161">Du kan opdatere tidsrammen i visualiseringen.</span><span class="sxs-lookup"><span data-stu-id="c4e24-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4e24-162">![Tidsinterval for segment](media/segment-time-range.png "Tidsinterval for segment")</span><span class="sxs-lookup"><span data-stu-id="c4e24-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="c4e24-163">Den nederste del indeholder en liste over segmentmedlemmerne.</span><span class="sxs-lookup"><span data-stu-id="c4e24-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="c4e24-164">Felter, der vises på denne liste, er baseret på attributterne for objekterne i dit segment.</span><span class="sxs-lookup"><span data-stu-id="c4e24-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="c4e24-165">Listen er et eksempel på de matchende segmentmedlemmer og viser de første 100 poster i dit segment, så du hurtigt kan evaluere det og gennemgå dets definitioner, hvis det er nødvendigt.</span><span class="sxs-lookup"><span data-stu-id="c4e24-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="c4e24-166">Hvis du vil se alle matchende poster, skal du [eksportere segmentet](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c4e24-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
