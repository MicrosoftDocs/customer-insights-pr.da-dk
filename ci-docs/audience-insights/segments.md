---
title: Oprette og administrere segmenter
description: Opret segmenter med kunder for at gruppere dem på baggrund af forskellige attributter.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405460"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="43db3-103">Oprette og administrere segmenter</span><span class="sxs-lookup"><span data-stu-id="43db3-103">Create and manage segments</span></span>

<span data-ttu-id="43db3-104">Med segmenter kan du gruppere dine kunder baseret på demografiske, transaktionsrelaterede eller adfærdsattributter.</span><span class="sxs-lookup"><span data-stu-id="43db3-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="43db3-105">Du kan bruge segmenter til at målrette kampagnefremstød, salgsaktiviteter og kundesupporthandlinger for at nå dine forretningsmæssige mål.</span><span class="sxs-lookup"><span data-stu-id="43db3-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="43db3-106">Du kan definere komplekse filtre for objektet Kundeprofil og dets relaterede objekter.</span><span class="sxs-lookup"><span data-stu-id="43db3-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="43db3-107">Hvert enkelt segment vil efter behandling oprette et sæt kundeposter, som du kan eksportere og udføre handlinger på.</span><span class="sxs-lookup"><span data-stu-id="43db3-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="43db3-108">Der gælder nogle [tjenestebegrænsninger](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="43db3-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="43db3-109">Medmindre andet er angivet, er alle segmenter **Dynamic-segmenter**, som opdateres med en tilbagevendende plan.</span><span class="sxs-lookup"><span data-stu-id="43db3-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="43db3-110">I følgende eksempel vises segmenteringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="43db3-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="43db3-111">Vi har defineret et segment for kunder, der har bestilt mindst $500 varer over de seneste 90 dage, *og* som har været en del af et kundeserviceopkald, der blev eskaleret.</span><span class="sxs-lookup"><span data-stu-id="43db3-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43db3-112">![Flere grupper](media/segmentation-group1-2.png "Flere grupper")</span><span class="sxs-lookup"><span data-stu-id="43db3-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="43db3-113">Oprette et nyt segment</span><span class="sxs-lookup"><span data-stu-id="43db3-113">Create a new segment</span></span>

<span data-ttu-id="43db3-114">Segmenter administreres på siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="43db3-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="43db3-115">Gå siden **Segmenter** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="43db3-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="43db3-116">Vælg **Ny** > **Tomt segment**.</span><span class="sxs-lookup"><span data-stu-id="43db3-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="43db3-117">Vælg en segmenttype i ruden **Nyt segment**, og angiv et **Navn**.</span><span class="sxs-lookup"><span data-stu-id="43db3-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="43db3-118">Du kan også angive et vist navn og en beskrivelse, der hjælper med at identificere segmentet.</span><span class="sxs-lookup"><span data-stu-id="43db3-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="43db3-119">Vælg **Næste** for at gå til siden **Segmentgenerator**, hvor du definerer en gruppe.</span><span class="sxs-lookup"><span data-stu-id="43db3-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="43db3-120">En gruppe er et sæt kunder.</span><span class="sxs-lookup"><span data-stu-id="43db3-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="43db3-121">Vælg det objekt, der indeholder den attribut, du vil segmentere efter.</span><span class="sxs-lookup"><span data-stu-id="43db3-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="43db3-122">Vælg den attribut, der skal segmenteres efter.</span><span class="sxs-lookup"><span data-stu-id="43db3-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="43db3-123">Denne attribut kan have en af fire værdityper: numerisk, streng, dato eller boolesk.</span><span class="sxs-lookup"><span data-stu-id="43db3-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="43db3-124">Vælg en operator og en værdi for den valgte attribut.</span><span class="sxs-lookup"><span data-stu-id="43db3-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="43db3-125">![Brugerdefineret gruppefilter](media/customer-group-numbers.png "Kundegruppefilter")</span><span class="sxs-lookup"><span data-stu-id="43db3-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="43db3-126">Antal</span><span class="sxs-lookup"><span data-stu-id="43db3-126">Number</span></span> |<span data-ttu-id="43db3-127">Definition</span><span class="sxs-lookup"><span data-stu-id="43db3-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="43db3-128">1</span><span class="sxs-lookup"><span data-stu-id="43db3-128">1</span></span>     |<span data-ttu-id="43db3-129">Entity</span><span class="sxs-lookup"><span data-stu-id="43db3-129">Entity</span></span>          |
   |<span data-ttu-id="43db3-130">2</span><span class="sxs-lookup"><span data-stu-id="43db3-130">2</span></span>     |<span data-ttu-id="43db3-131">Attribut</span><span class="sxs-lookup"><span data-stu-id="43db3-131">Attribute</span></span>          |
   |<span data-ttu-id="43db3-132">3</span><span class="sxs-lookup"><span data-stu-id="43db3-132">3</span></span>    |<span data-ttu-id="43db3-133">Operatør</span><span class="sxs-lookup"><span data-stu-id="43db3-133">Operator</span></span>         |
   |<span data-ttu-id="43db3-134">4</span><span class="sxs-lookup"><span data-stu-id="43db3-134">4</span></span>    |<span data-ttu-id="43db3-135">Værdi</span><span class="sxs-lookup"><span data-stu-id="43db3-135">Value</span></span>         |

8. <span data-ttu-id="43db3-136">Hvis objektet er knyttet til det samlede kundeobjekt via [Relationer](relationships.md), skal du definere relationsstien for at oprette et gyldigt segment.</span><span class="sxs-lookup"><span data-stu-id="43db3-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="43db3-137">Tilføj objekterne fra relationsstien, indtil du kan vælge objektet **Kunde: CustomerInsights** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="43db3-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="43db3-138">Vælg derefter **Alle poster** for hver betingelse.</span><span class="sxs-lookup"><span data-stu-id="43db3-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="43db3-139">![Relationsstien under oprettelse af segmenter](media/segments-multiple-relationships.png "Relationsstien under oprettelse af segmenter")</span><span class="sxs-lookup"><span data-stu-id="43db3-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="43db3-140">Vælg **Gem** for at gemme dit segment.</span><span class="sxs-lookup"><span data-stu-id="43db3-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="43db3-141">Dit segment gemmes og behandles, hvis alle krav valideres.</span><span class="sxs-lookup"><span data-stu-id="43db3-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="43db3-142">Ellers gemmes det som en kladde.</span><span class="sxs-lookup"><span data-stu-id="43db3-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="43db3-143">Vælg **Tilbage til segmenter** for at gå tilbage til siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="43db3-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="43db3-144">Administrere eksisterende segmenter</span><span class="sxs-lookup"><span data-stu-id="43db3-144">Manage existing segments</span></span>

<span data-ttu-id="43db3-145">På siden **Segmenter** kan du få vist alle gemte segmenter og administrere dem.</span><span class="sxs-lookup"><span data-stu-id="43db3-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="43db3-146">De enkelte segmenter repræsenteres af en række, der indeholder yderligere oplysninger om segmentet.</span><span class="sxs-lookup"><span data-stu-id="43db3-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="43db3-147">Du kan sortere segmenterne i en kolonne ved at markere kolonneoverskriften.</span><span class="sxs-lookup"><span data-stu-id="43db3-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="43db3-148">Brug feltet **Søg** i øverste højre hjørne til at filtrere segmenterne.</span><span class="sxs-lookup"><span data-stu-id="43db3-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43db3-149">![Indstillinger til administration af et eksisterende segment](media/segments-selected-segment.png "Indstillinger til administration af et eksisterende segment")</span><span class="sxs-lookup"><span data-stu-id="43db3-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="43db3-150">Følgende handlinger er tilgængelige, når du vælger et segment:</span><span class="sxs-lookup"><span data-stu-id="43db3-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="43db3-151">**Vis** segmentoplysningerne, herunder tendensen for antal medlemmer, et eksempel på segmentmedlemmer.</span><span class="sxs-lookup"><span data-stu-id="43db3-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="43db3-152">**Rediger** segmentet for at ændre dets egenskaber.</span><span class="sxs-lookup"><span data-stu-id="43db3-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="43db3-153">**Opdater** segmentet, så det indeholder de seneste data.</span><span class="sxs-lookup"><span data-stu-id="43db3-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="43db3-154">**Aktivér** eller **Deaktiver** segmentet.</span><span class="sxs-lookup"><span data-stu-id="43db3-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="43db3-155">Segmenter har to mulige tilstande - aktiv og inaktiv.</span><span class="sxs-lookup"><span data-stu-id="43db3-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="43db3-156">Disse tilstande er praktiske, når du redigerer et segment.</span><span class="sxs-lookup"><span data-stu-id="43db3-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="43db3-157">I forbindelse med inaktive segmenter findes der en definition af segmentet, men den indeholder ikke nogen kunder endnu.</span><span class="sxs-lookup"><span data-stu-id="43db3-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="43db3-158">Når du aktiverer et segment, ændres dets tilstand fra 'inaktiv' til "aktiv", og der starter en søgning efter de kunder, der opfylder segmentdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="43db3-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="43db3-159">Hvis der er konfigureret en [planlagt opdatering](system.md#schedule-tab), har vises **Status** for inaktive segmenter som **Sprunget over** som tegn på, at en opdatering ikke er forsøgt udført.</span><span class="sxs-lookup"><span data-stu-id="43db3-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="43db3-160">Når et inaktivt segment aktiveres, opdateres det og inkluderes i de planlagte opdateringer.</span><span class="sxs-lookup"><span data-stu-id="43db3-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="43db3-161">Du kan også bruge **Planlæg senere** i rullemenuen **Aktivér/deaktiver** til at angive fremtidig dato og klokkeslæt for aktivering og deaktivering af et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="43db3-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="43db3-162">**Omdøb** segmentet.</span><span class="sxs-lookup"><span data-stu-id="43db3-162">**Rename** the segment.</span></span>
- <span data-ttu-id="43db3-163">**Hent** listen over medlemmer som en .CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="43db3-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="43db3-164">**Føj til**-indstillingen sender listen over kunde-id'er i segmentet til behandling i et andet program.</span><span class="sxs-lookup"><span data-stu-id="43db3-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="43db3-165">**Slet** segmentet.</span><span class="sxs-lookup"><span data-stu-id="43db3-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="43db3-166">Opdatere segmenter</span><span class="sxs-lookup"><span data-stu-id="43db3-166">Refresh segments</span></span>

<span data-ttu-id="43db3-167">Du kan opdatere alle segmenter på én gang ved at vælge **Opdater alle** på siden **Segmenter**, eller du kan opdatere et eller flere segmenter, når du vælger dem, og vælge **Opdater** fra indstillingerne.</span><span class="sxs-lookup"><span data-stu-id="43db3-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="43db3-168">Du kan også konfigurere en tilbagevendende opdatering i **Admin** > **System** > **Planlæg**.</span><span class="sxs-lookup"><span data-stu-id="43db3-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="43db3-169">Opgaver og processer indeholder [seks typer status](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="43db3-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="43db3-170">De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="43db3-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="43db3-171">Du kan vælge status for en proces for at se statusdetaljer for hele jobbet.</span><span class="sxs-lookup"><span data-stu-id="43db3-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="43db3-172">Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.</span><span class="sxs-lookup"><span data-stu-id="43db3-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="43db3-173">Hente og eksportere segmenter</span><span class="sxs-lookup"><span data-stu-id="43db3-173">Download and export segments</span></span>

<span data-ttu-id="43db3-174">Du kan hente dine segmenter i en CSV-fil eller eksportere dem til Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="43db3-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="43db3-175">Overføre segmenter til en CSV-fil</span><span class="sxs-lookup"><span data-stu-id="43db3-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="43db3-176">Gå siden **Segmenter** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="43db3-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="43db3-177">Vælg ellipsen i et specifikt segments felt.</span><span class="sxs-lookup"><span data-stu-id="43db3-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="43db3-178">Vælg **Download som CSV** på rullelisten med handlinger.</span><span class="sxs-lookup"><span data-stu-id="43db3-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="43db3-179">Eksportér segmenter til Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="43db3-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="43db3-180">Før du eksporterer segmenter til Dynamics 365 Sales, skal en administrator [oprette eksportdestinationen](export-destinations.md) til Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="43db3-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="43db3-181">Gå siden **Segmenter** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="43db3-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="43db3-182">Vælg ellipsen i et specifikt segments felt.</span><span class="sxs-lookup"><span data-stu-id="43db3-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="43db3-183">Vælg **Føj til** på rullelisten over handlinger, og vælg den eksportdestination, som du vil sende dataene til.</span><span class="sxs-lookup"><span data-stu-id="43db3-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="43db3-184">Kladdetilstand for segmenter</span><span class="sxs-lookup"><span data-stu-id="43db3-184">Draft mode for segments</span></span>

<span data-ttu-id="43db3-185">Hvis ikke alle krav til behandling af et segment er opfyldt, kan du gemme segmentet som en kladde og få adgang til det fra siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="43db3-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="43db3-186">Dataene gemmes som et inaktivt segment og kan ikke aktiveres, før det er gyldigt.</span><span class="sxs-lookup"><span data-stu-id="43db3-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="43db3-187">Føje flere betingelser til en gruppe</span><span class="sxs-lookup"><span data-stu-id="43db3-187">Add more conditions to a group</span></span>

<span data-ttu-id="43db3-188">Hvis du vil føje flere betingelser til en gruppe, kan du bruge to logiske operatorer:</span><span class="sxs-lookup"><span data-stu-id="43db3-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="43db3-189">**OG**-operator: Begge betingelser skal overholdes som en del af segmenteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="43db3-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="43db3-190">Denne indstilling er mest nyttig, når du definerer betingelser på tværs af forskellige objekter.</span><span class="sxs-lookup"><span data-stu-id="43db3-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="43db3-191">**ELLER**-operator: Den ene eller anden betingelse skal overholdes som en del af segmenteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="43db3-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="43db3-192">Denne indstilling er mest nyttig, når du definerer flere betingelser for det samme objekt.</span><span class="sxs-lookup"><span data-stu-id="43db3-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="43db3-193">![ELLER-operator, hvor en af betingelserne skal overholdes](media/segmentation-either-condition.png "ELLER-operator, hvor en af betingelserne skal overholdes")</span><span class="sxs-lookup"><span data-stu-id="43db3-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="43db3-194">Det er aktuelt muligt at indlejre en **ELLER**-operator under en **OG**-operator, men ikke den anden vej rundt.</span><span class="sxs-lookup"><span data-stu-id="43db3-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="43db3-195">Kombinere flere grupper</span><span class="sxs-lookup"><span data-stu-id="43db3-195">Combine multiple groups</span></span>

<span data-ttu-id="43db3-196">Hver gruppe producerer et bestemt sæt kunder.</span><span class="sxs-lookup"><span data-stu-id="43db3-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="43db3-197">Du kan kombinere disse grupper, så de inkluderer de kunder, der er nødvendige for din virksomhedscase.</span><span class="sxs-lookup"><span data-stu-id="43db3-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="43db3-198">Gå til siden **Segmenter**, og vælg et segment i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="43db3-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="43db3-199">Vælg **Tilføj gruppe**.</span><span class="sxs-lookup"><span data-stu-id="43db3-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="43db3-200">![Tilføje kundegruppe](media/customer-group-add-group.png "Tilføje kundegruppe")</span><span class="sxs-lookup"><span data-stu-id="43db3-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="43db3-201">Vælg en af følgende sæt operatorer: **Foreningsmængde**, **Overlapning** eller **Undtagen**.</span><span class="sxs-lookup"><span data-stu-id="43db3-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="43db3-202">![Tilføje foreningsmængde af kundegruppe](media/customer-group-union.png "Tilføje foreningsmængde af kundegruppe")</span><span class="sxs-lookup"><span data-stu-id="43db3-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="43db3-203">Vælg en sætoperator for at definere en ny gruppe.</span><span class="sxs-lookup"><span data-stu-id="43db3-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="43db3-204">Gem forskellige grupper for at bestemme, hvilke data der bliver bevaret:</span><span class="sxs-lookup"><span data-stu-id="43db3-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="43db3-205">**Foreningsmængde** forener de to grupper.</span><span class="sxs-lookup"><span data-stu-id="43db3-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="43db3-206">**Overlapning** overlapper de to grupper.</span><span class="sxs-lookup"><span data-stu-id="43db3-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="43db3-207">Kun data, der *er fælles* for begge grupper, bevares i den samlede gruppe.</span><span class="sxs-lookup"><span data-stu-id="43db3-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="43db3-208">**Undtagen** kombinerer de to grupper.</span><span class="sxs-lookup"><span data-stu-id="43db3-208">**Except** combines the two groups.</span></span> <span data-ttu-id="43db3-209">Kun data i gruppe A, der *ikke er fælles* med data i gruppe B, bevares.</span><span class="sxs-lookup"><span data-stu-id="43db3-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="43db3-210">Se behandlingshistorik og segmentmedlemmer</span><span class="sxs-lookup"><span data-stu-id="43db3-210">View processing history and segment members</span></span>

<span data-ttu-id="43db3-211">Du kan se konsoliderede data om et segment ved at gennemgå dets detaljer.</span><span class="sxs-lookup"><span data-stu-id="43db3-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="43db3-212">Vælg det segment, du vil gennemgå, på siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="43db3-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="43db3-213">Den øverste del af siden indeholder en tendensgraf, der viser ændringer i medlemsantal.</span><span class="sxs-lookup"><span data-stu-id="43db3-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="43db3-214">Peg på datapunkter for at få vist medlemsantallet på en bestemt dato.</span><span class="sxs-lookup"><span data-stu-id="43db3-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="43db3-215">Du kan opdatere tidsrammen i visualiseringen.</span><span class="sxs-lookup"><span data-stu-id="43db3-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="43db3-216">![Tidsinterval for segment](media/segment-time-range.png "Tidsinterval for segment")</span><span class="sxs-lookup"><span data-stu-id="43db3-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="43db3-217">Den nederste del indeholder en liste over segmentmedlemmerne.</span><span class="sxs-lookup"><span data-stu-id="43db3-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="43db3-218">Felter, der vises på denne liste, er baseret på attributterne for objekterne i dit segment.</span><span class="sxs-lookup"><span data-stu-id="43db3-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="43db3-219">Listen er et eksempel på de matchende segmentmedlemmer og viser de første 100 poster i dit segment, så du hurtigt kan evaluere det og gennemgå dets definitioner, hvis det er nødvendigt.</span><span class="sxs-lookup"><span data-stu-id="43db3-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="43db3-220">Hvis du vil se alle matchende poster, skal du [eksportere segmentet](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="43db3-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="43db3-221">Hurtige segmenter</span><span class="sxs-lookup"><span data-stu-id="43db3-221">Quick segments</span></span>

<span data-ttu-id="43db3-222">Ud over segmentbyggeren er der en anden vej til at oprette segmenter.</span><span class="sxs-lookup"><span data-stu-id="43db3-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="43db3-223">Hurtige segmenter giver dig mulighed for hurtigt at opbygge simple segmenter med en enkelt operator og med øjeblikkelig indsigt.</span><span class="sxs-lookup"><span data-stu-id="43db3-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="43db3-224">På siden **Segmenter** skal du vælge **Nyt** > **Opret hurtigt fra**.</span><span class="sxs-lookup"><span data-stu-id="43db3-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="43db3-225">Vælg indstillingen **Profiler** for at oprette et segment, der er baseret på det samlede kundeobjekt.</span><span class="sxs-lookup"><span data-stu-id="43db3-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="43db3-226">Vælg indstillingen **Målinger** for at oprette et segment omkring de enkelte kundeattributtyper af målinger, du tidligere har oprettet på siden **Målinger**.</span><span class="sxs-lookup"><span data-stu-id="43db3-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="43db3-227">Vælg indstillingen **Intelligens** for at oprette en segment omkring en af de outputenheder, du har oprettet ved hjælp af funktionerne **Forudsigelser** eller **Brugerdefinerede modeller**.</span><span class="sxs-lookup"><span data-stu-id="43db3-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="43db3-228">Vælg en attribut på rullelisten **Felt** i dialogboksen **Nyt hurtigt segment**.</span><span class="sxs-lookup"><span data-stu-id="43db3-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="43db3-229">Der gives yderligere indsigt i systemet, som kan hjælpe dig med at oprette bedre segmenter af dine kunder.</span><span class="sxs-lookup"><span data-stu-id="43db3-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="43db3-230">I forbindelse med kategoriske felter vises de 10 bedste kundeantal.</span><span class="sxs-lookup"><span data-stu-id="43db3-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="43db3-231">Vælg en **Værdi**, og vælg **Gennemse**.</span><span class="sxs-lookup"><span data-stu-id="43db3-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="43db3-232">I forbindelse med en numerisk attribut viser systemet, hvilken attributværdi der er omfattet af hver enkelt kundes percentil.</span><span class="sxs-lookup"><span data-stu-id="43db3-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="43db3-233">Vælg en **Operator** og en **Værdi**, og vælg derefter **Gennemse**.</span><span class="sxs-lookup"><span data-stu-id="43db3-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="43db3-234">Systemet vil give dig en **Anslået segmentstørrelse**.</span><span class="sxs-lookup"><span data-stu-id="43db3-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="43db3-235">Du kan vælge, om du vil oprette det segment, du har defineret, eller først vil gå til det igen for at få en anden segmentstørrelse.</span><span class="sxs-lookup"><span data-stu-id="43db3-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="43db3-236">![Navn og estimering for et hurtigt segment](media/quick-segment-name.png "Navn og estimering for et hurtigt segment")</span><span class="sxs-lookup"><span data-stu-id="43db3-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="43db3-237">Angiv et **Navn** til dit segment.</span><span class="sxs-lookup"><span data-stu-id="43db3-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="43db3-238">Angiv eventuelt et **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="43db3-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="43db3-239">Vælg **Gem** for at oprette dit segment.</span><span class="sxs-lookup"><span data-stu-id="43db3-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="43db3-240">Når segmentet er færdigbehandlet, kan du se det på samme måde som andre segmenter, du har oprettet.</span><span class="sxs-lookup"><span data-stu-id="43db3-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="43db3-241">I forbindelse med følgende situationer anbefaler vi, at du bruger segmentgeneratoren i stedet for de anbefalede segmentfunktioner:</span><span class="sxs-lookup"><span data-stu-id="43db3-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="43db3-242">Oprette segmenter med filtre på kategoriske felter, hvor operatoren er anderledes end operatoren **Er**</span><span class="sxs-lookup"><span data-stu-id="43db3-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="43db3-243">Oprette segmenter med filtre på numeriske felter, hvor operatoren er forskellig fra operatorerne **Mellem**, **Større end** og **Mindre end**</span><span class="sxs-lookup"><span data-stu-id="43db3-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="43db3-244">Oprette segmenter med filtre i datotypefelter</span><span class="sxs-lookup"><span data-stu-id="43db3-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="43db3-245">Næste trin</span><span class="sxs-lookup"><span data-stu-id="43db3-245">Next steps</span></span>

<span data-ttu-id="43db3-246">[Eksportere et segment](export-destinations.md) og udforske [kundekort](customer-card-add-in.md) og [connectorer](export-power-bi.md) for at få indsigt i kundeniveauet.</span><span class="sxs-lookup"><span data-stu-id="43db3-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
