---
title: Oprette og administrere segmenter
description: Opret segmenter med kunder for at gruppere dem på baggrund af forskellige attributter.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597044"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="187d5-103">Oprette og administrere segmenter</span><span class="sxs-lookup"><span data-stu-id="187d5-103">Create and manage segments</span></span>

<span data-ttu-id="187d5-104">Med segmenter kan du gruppere dine kunder baseret på demografiske, transaktionsrelaterede eller adfærdsattributter.</span><span class="sxs-lookup"><span data-stu-id="187d5-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="187d5-105">Du kan bruge segmenter til at målrette kampagnefremstød, salgsaktiviteter og kundesupporthandlinger for at nå dine forretningsmæssige mål.</span><span class="sxs-lookup"><span data-stu-id="187d5-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="187d5-106">Du kan definere komplekse filtre for objektet Kundeprofil og dets relaterede objekter.</span><span class="sxs-lookup"><span data-stu-id="187d5-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="187d5-107">Hvert enkelt segment vil efter behandling oprette et sæt kundeposter, som du kan eksportere og udføre handlinger på.</span><span class="sxs-lookup"><span data-stu-id="187d5-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="187d5-108">Der gælder nogle [tjenestebegrænsninger](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="187d5-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="187d5-109">Medmindre andet er angivet, er alle segmenter **Dynamic-segmenter**, som opdateres med en tilbagevendende plan.</span><span class="sxs-lookup"><span data-stu-id="187d5-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="187d5-110">I følgende eksempel vises segmenteringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="187d5-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="187d5-111">Vi har defineret et segment for kunder, der har bestilt mindst $500 varer over de seneste 90 dage, *og* som har været en del af et kundeserviceopkald, der blev eskaleret.</span><span class="sxs-lookup"><span data-stu-id="187d5-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="187d5-112">![Flere grupper](media/segmentation-group1-2.png "Flere grupper")</span><span class="sxs-lookup"><span data-stu-id="187d5-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="187d5-113">Oprette et nyt segment</span><span class="sxs-lookup"><span data-stu-id="187d5-113">Create a new segment</span></span>

<span data-ttu-id="187d5-114">Segmenter administreres på siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="187d5-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="187d5-115">Gå siden **Segmenter** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="187d5-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="187d5-116">Vælg **Ny** > **Tomt segment**.</span><span class="sxs-lookup"><span data-stu-id="187d5-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="187d5-117">Vælg en segmenttype i ruden **Nyt segment**, og angiv et **Navn**.</span><span class="sxs-lookup"><span data-stu-id="187d5-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="187d5-118">Du kan også angive et vist navn og en beskrivelse, der hjælper med at identificere segmentet.</span><span class="sxs-lookup"><span data-stu-id="187d5-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="187d5-119">Vælg **Næste** for at gå til siden **Segmentgenerator**, hvor du definerer en gruppe.</span><span class="sxs-lookup"><span data-stu-id="187d5-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="187d5-120">En gruppe er et sæt kunder.</span><span class="sxs-lookup"><span data-stu-id="187d5-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="187d5-121">Vælg det objekt, der indeholder den attribut, du vil segmentere efter.</span><span class="sxs-lookup"><span data-stu-id="187d5-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="187d5-122">Vælg den attribut, der skal segmenteres efter.</span><span class="sxs-lookup"><span data-stu-id="187d5-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="187d5-123">Denne attribut kan have en af fire værdityper: numerisk, streng, dato eller boolesk.</span><span class="sxs-lookup"><span data-stu-id="187d5-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="187d5-124">Vælg en operator og en værdi for den valgte attribut.</span><span class="sxs-lookup"><span data-stu-id="187d5-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="187d5-125">![Brugerdefineret gruppefilter](media/customer-group-numbers.png "Kundegruppefilter")</span><span class="sxs-lookup"><span data-stu-id="187d5-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="187d5-126">Antal</span><span class="sxs-lookup"><span data-stu-id="187d5-126">Number</span></span> |<span data-ttu-id="187d5-127">Definition</span><span class="sxs-lookup"><span data-stu-id="187d5-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="187d5-128">1</span><span class="sxs-lookup"><span data-stu-id="187d5-128">1</span></span>     |<span data-ttu-id="187d5-129">Entity</span><span class="sxs-lookup"><span data-stu-id="187d5-129">Entity</span></span>          |
   |<span data-ttu-id="187d5-130">2</span><span class="sxs-lookup"><span data-stu-id="187d5-130">2</span></span>     |<span data-ttu-id="187d5-131">Attribut</span><span class="sxs-lookup"><span data-stu-id="187d5-131">Attribute</span></span>          |
   |<span data-ttu-id="187d5-132">3</span><span class="sxs-lookup"><span data-stu-id="187d5-132">3</span></span>    |<span data-ttu-id="187d5-133">Operatør</span><span class="sxs-lookup"><span data-stu-id="187d5-133">Operator</span></span>         |
   |<span data-ttu-id="187d5-134">4</span><span class="sxs-lookup"><span data-stu-id="187d5-134">4</span></span>    |<span data-ttu-id="187d5-135">Værdi</span><span class="sxs-lookup"><span data-stu-id="187d5-135">Value</span></span>         |

8. <span data-ttu-id="187d5-136">Hvis objektet er knyttet til det samlede kundeobjekt via [Relationer](relationships.md), skal du definere relationsstien for at oprette et gyldigt segment.</span><span class="sxs-lookup"><span data-stu-id="187d5-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="187d5-137">Tilføj objekterne fra relationsstien, indtil du kan vælge objektet **Kunde: CustomerInsights** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="187d5-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="187d5-138">Vælg derefter **Alle poster** for hver betingelse.</span><span class="sxs-lookup"><span data-stu-id="187d5-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="187d5-139">![Relationsstien under oprettelse af segmenter](media/segments-multiple-relationships.png "Relationsstien under oprettelse af segmenter")</span><span class="sxs-lookup"><span data-stu-id="187d5-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="187d5-140">Som standard opretter segmenter et outputobjekt, der indeholder alle attributter af kundeprofiler, som stemmer overens med de definerede filtre.</span><span class="sxs-lookup"><span data-stu-id="187d5-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="187d5-141">Hvis et segment er baseret på andre objekter end *Kunde*-objektet, kan du føje flere attributter fra disse objekter til outputobjektet.</span><span class="sxs-lookup"><span data-stu-id="187d5-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="187d5-142">Vælg **Projektattributter** for at vælge de attributter, der skal føjes til outputobjektet.</span><span class="sxs-lookup"><span data-stu-id="187d5-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="187d5-143">Eksempel: Et segment er baseret på et objekt, der indeholder kundeaktivitetsdata, som er relateret til objektet *Kunde*.</span><span class="sxs-lookup"><span data-stu-id="187d5-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="187d5-144">Segmentet søger efter alle kunder, der har ringet til Helpdesk inden for de seneste 60 dage.</span><span class="sxs-lookup"><span data-stu-id="187d5-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="187d5-145">Du kan vælge at føje varigheden af opkaldet og antallet af opkald til alle tilsvarende kundeposter i outputobjektet.</span><span class="sxs-lookup"><span data-stu-id="187d5-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="187d5-146">Disse oplysninger kan være nyttige, hvis du vil sende en mail med nyttige links til artikler i onlinehjælp og ofte stillede spørgsmål til kunder, der ofte har ringet.</span><span class="sxs-lookup"><span data-stu-id="187d5-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="187d5-147">Vælg **Gem** for at gemme dit segment.</span><span class="sxs-lookup"><span data-stu-id="187d5-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="187d5-148">Dit segment gemmes og behandles, hvis alle krav valideres.</span><span class="sxs-lookup"><span data-stu-id="187d5-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="187d5-149">Ellers gemmes det som en kladde.</span><span class="sxs-lookup"><span data-stu-id="187d5-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="187d5-150">Vælg **Tilbage til segmenter** for at gå tilbage til siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="187d5-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="187d5-151">Administrere eksisterende segmenter</span><span class="sxs-lookup"><span data-stu-id="187d5-151">Manage existing segments</span></span>

<span data-ttu-id="187d5-152">På siden **Segmenter** kan du få vist alle gemte segmenter og administrere dem.</span><span class="sxs-lookup"><span data-stu-id="187d5-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="187d5-153">De enkelte segmenter repræsenteres af en række, der indeholder yderligere oplysninger om segmentet.</span><span class="sxs-lookup"><span data-stu-id="187d5-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="187d5-154">Du kan sortere segmenterne i en kolonne ved at markere kolonneoverskriften.</span><span class="sxs-lookup"><span data-stu-id="187d5-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="187d5-155">Brug feltet **Søg** i øverste højre hjørne til at filtrere segmenterne.</span><span class="sxs-lookup"><span data-stu-id="187d5-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="187d5-156">![Indstillinger til administration af et eksisterende segment](media/segments-selected-segment.png "Indstillinger til administration af et eksisterende segment")</span><span class="sxs-lookup"><span data-stu-id="187d5-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="187d5-157">Følgende handlinger er tilgængelige, når du vælger et segment:</span><span class="sxs-lookup"><span data-stu-id="187d5-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="187d5-158">**Vis** segmentoplysningerne, herunder tendensen for antal medlemmer, et eksempel på segmentmedlemmer.</span><span class="sxs-lookup"><span data-stu-id="187d5-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="187d5-159">**Rediger** segmentet for at ændre dets egenskaber.</span><span class="sxs-lookup"><span data-stu-id="187d5-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="187d5-160">**Opret en dublet** af et segment.</span><span class="sxs-lookup"><span data-stu-id="187d5-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="187d5-161">Du kan vælge at redigere egenskaberne med det samme eller ganske enkelt gemme dubletten.</span><span class="sxs-lookup"><span data-stu-id="187d5-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="187d5-162">**Opdater** segmentet, så det indeholder de seneste data.</span><span class="sxs-lookup"><span data-stu-id="187d5-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="187d5-163">**Aktivér** eller **Deaktiver** segmentet.</span><span class="sxs-lookup"><span data-stu-id="187d5-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="187d5-164">Segmenter har to mulige tilstande - aktiv og inaktiv.</span><span class="sxs-lookup"><span data-stu-id="187d5-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="187d5-165">Disse tilstande er praktiske, når du redigerer et segment.</span><span class="sxs-lookup"><span data-stu-id="187d5-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="187d5-166">I forbindelse med inaktive segmenter findes der en definition af segmentet, men den indeholder ikke nogen kunder endnu.</span><span class="sxs-lookup"><span data-stu-id="187d5-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="187d5-167">Når du aktiverer et segment, ændres dets tilstand fra 'inaktiv' til "aktiv", og der starter en søgning efter de kunder, der opfylder segmentdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="187d5-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="187d5-168">Hvis der er konfigureret en [planlagt opdatering](system.md#schedule-tab), har vises **Status** for inaktive segmenter som **Sprunget over** som tegn på, at en opdatering ikke er forsøgt udført.</span><span class="sxs-lookup"><span data-stu-id="187d5-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="187d5-169">Når et inaktivt segment aktiveres, opdateres det og inkluderes i de planlagte opdateringer.</span><span class="sxs-lookup"><span data-stu-id="187d5-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="187d5-170">Du kan også bruge **Planlæg senere** i rullemenuen **Aktivér/deaktiver** til at angive fremtidig dato og klokkeslæt for aktivering og deaktivering af et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="187d5-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="187d5-171">**Omdøb** segmentet.</span><span class="sxs-lookup"><span data-stu-id="187d5-171">**Rename** the segment.</span></span>
- <span data-ttu-id="187d5-172">**Hent** listen over medlemmer som en .CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="187d5-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="187d5-173">**Føj til**-indstillingen sender listen over kunde-id'er i segmentet til behandling i et andet program.</span><span class="sxs-lookup"><span data-stu-id="187d5-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="187d5-174">**Slet** segmentet.</span><span class="sxs-lookup"><span data-stu-id="187d5-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="187d5-175">Opdatere segmenter</span><span class="sxs-lookup"><span data-stu-id="187d5-175">Refresh segments</span></span>

<span data-ttu-id="187d5-176">Du kan opdatere alle segmenter på én gang ved at vælge **Opdater alle** på siden **Segmenter**, eller du kan opdatere et eller flere segmenter, når du vælger dem, og vælge **Opdater** fra indstillingerne.</span><span class="sxs-lookup"><span data-stu-id="187d5-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="187d5-177">Du kan også konfigurere en tilbagevendende opdatering i **Admin** > **System** > **Planlæg**.</span><span class="sxs-lookup"><span data-stu-id="187d5-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="187d5-178">Opgaver og processer indeholder [seks typer status](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="187d5-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="187d5-179">De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="187d5-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="187d5-180">Du kan vælge status for en proces for at se statusdetaljer for hele jobbet.</span><span class="sxs-lookup"><span data-stu-id="187d5-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="187d5-181">Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.</span><span class="sxs-lookup"><span data-stu-id="187d5-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="187d5-182">Hente og eksportere segmenter</span><span class="sxs-lookup"><span data-stu-id="187d5-182">Download and export segments</span></span>

<span data-ttu-id="187d5-183">Du kan hente dine segmenter i en CSV-fil eller eksportere dem til Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="187d5-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="187d5-184">Overføre segmenter til en CSV-fil</span><span class="sxs-lookup"><span data-stu-id="187d5-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="187d5-185">Gå siden **Segmenter** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="187d5-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="187d5-186">Vælg ellipsen i et specifikt segments felt.</span><span class="sxs-lookup"><span data-stu-id="187d5-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="187d5-187">Vælg **Download som CSV** på rullelisten med handlinger.</span><span class="sxs-lookup"><span data-stu-id="187d5-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="187d5-188">Eksportér segmenter til Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="187d5-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="187d5-189">Før du eksporterer segmenter til Dynamics 365 Sales, skal en administrator [oprette eksportdestinationen](export-destinations.md) til Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="187d5-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="187d5-190">Gå siden **Segmenter** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="187d5-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="187d5-191">Vælg ellipsen i et specifikt segments felt.</span><span class="sxs-lookup"><span data-stu-id="187d5-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="187d5-192">Vælg **Føj til** på rullelisten over handlinger, og vælg den eksportdestination, som du vil sende dataene til.</span><span class="sxs-lookup"><span data-stu-id="187d5-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="187d5-193">Kladdetilstand for segmenter</span><span class="sxs-lookup"><span data-stu-id="187d5-193">Draft mode for segments</span></span>

<span data-ttu-id="187d5-194">Hvis ikke alle krav til behandling af et segment er opfyldt, kan du gemme segmentet som en kladde og få adgang til det fra siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="187d5-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="187d5-195">Dataene gemmes som et inaktivt segment og kan ikke aktiveres, før det er gyldigt.</span><span class="sxs-lookup"><span data-stu-id="187d5-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="187d5-196">Føje flere betingelser til en gruppe</span><span class="sxs-lookup"><span data-stu-id="187d5-196">Add more conditions to a group</span></span>

<span data-ttu-id="187d5-197">Hvis du vil føje flere betingelser til en gruppe, kan du bruge to logiske operatorer:</span><span class="sxs-lookup"><span data-stu-id="187d5-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="187d5-198">**OG**-operator: Begge betingelser skal overholdes som en del af segmenteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="187d5-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="187d5-199">Denne indstilling er mest nyttig, når du definerer betingelser på tværs af forskellige objekter.</span><span class="sxs-lookup"><span data-stu-id="187d5-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="187d5-200">**ELLER**-operator: Den ene eller anden betingelse skal overholdes som en del af segmenteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="187d5-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="187d5-201">Denne indstilling er mest nyttig, når du definerer flere betingelser for det samme objekt.</span><span class="sxs-lookup"><span data-stu-id="187d5-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="187d5-202">![ELLER-operator, hvor en af betingelserne skal overholdes](media/segmentation-either-condition.png "ELLER-operator, hvor en af betingelserne skal overholdes")</span><span class="sxs-lookup"><span data-stu-id="187d5-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="187d5-203">Det er aktuelt muligt at indlejre en **ELLER**-operator under en **OG**-operator, men ikke den anden vej rundt.</span><span class="sxs-lookup"><span data-stu-id="187d5-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="187d5-204">Kombinere flere grupper</span><span class="sxs-lookup"><span data-stu-id="187d5-204">Combine multiple groups</span></span>

<span data-ttu-id="187d5-205">Hver gruppe producerer et bestemt sæt kunder.</span><span class="sxs-lookup"><span data-stu-id="187d5-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="187d5-206">Du kan kombinere disse grupper, så de inkluderer de kunder, der er nødvendige for din virksomhedscase.</span><span class="sxs-lookup"><span data-stu-id="187d5-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="187d5-207">Gå til siden **Segmenter**, og vælg et segment i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="187d5-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="187d5-208">Vælg **Tilføj gruppe**.</span><span class="sxs-lookup"><span data-stu-id="187d5-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="187d5-209">![Tilføje kundegruppe](media/customer-group-add-group.png "Tilføje kundegruppe")</span><span class="sxs-lookup"><span data-stu-id="187d5-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="187d5-210">Vælg en af følgende sæt operatorer: **Foreningsmængde**, **Overlapning** eller **Undtagen**.</span><span class="sxs-lookup"><span data-stu-id="187d5-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="187d5-211">![Tilføje foreningsmængde af kundegruppe](media/customer-group-union.png "Tilføje foreningsmængde af kundegruppe")</span><span class="sxs-lookup"><span data-stu-id="187d5-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="187d5-212">Vælg en sætoperator for at definere en ny gruppe.</span><span class="sxs-lookup"><span data-stu-id="187d5-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="187d5-213">Gem forskellige grupper for at bestemme, hvilke data der bliver bevaret:</span><span class="sxs-lookup"><span data-stu-id="187d5-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="187d5-214">**Foreningsmængde** forener de to grupper.</span><span class="sxs-lookup"><span data-stu-id="187d5-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="187d5-215">**Overlapning** overlapper de to grupper.</span><span class="sxs-lookup"><span data-stu-id="187d5-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="187d5-216">Kun data, der *er fælles* for begge grupper, bevares i den samlede gruppe.</span><span class="sxs-lookup"><span data-stu-id="187d5-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="187d5-217">**Undtagen** kombinerer de to grupper.</span><span class="sxs-lookup"><span data-stu-id="187d5-217">**Except** combines the two groups.</span></span> <span data-ttu-id="187d5-218">Kun data i gruppe A, der *ikke er fælles* med data i gruppe B, bevares.</span><span class="sxs-lookup"><span data-stu-id="187d5-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="187d5-219">Se behandlingshistorik og segmentmedlemmer</span><span class="sxs-lookup"><span data-stu-id="187d5-219">View processing history and segment members</span></span>

<span data-ttu-id="187d5-220">Du kan se konsoliderede data om et segment ved at gennemgå dets detaljer.</span><span class="sxs-lookup"><span data-stu-id="187d5-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="187d5-221">Vælg det segment, du vil gennemgå, på siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="187d5-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="187d5-222">Den øverste del af siden indeholder en tendensgraf, der viser ændringer i medlemsantal.</span><span class="sxs-lookup"><span data-stu-id="187d5-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="187d5-223">Peg på datapunkter for at få vist medlemsantallet på en bestemt dato.</span><span class="sxs-lookup"><span data-stu-id="187d5-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="187d5-224">Du kan opdatere tidsrammen i visualiseringen.</span><span class="sxs-lookup"><span data-stu-id="187d5-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="187d5-225">![Tidsinterval for segment](media/segment-time-range.png "Tidsinterval for segment")</span><span class="sxs-lookup"><span data-stu-id="187d5-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="187d5-226">Den nederste del indeholder en liste over segmentmedlemmerne.</span><span class="sxs-lookup"><span data-stu-id="187d5-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="187d5-227">Felter, der vises på denne liste, er baseret på attributterne for objekterne i dit segment.</span><span class="sxs-lookup"><span data-stu-id="187d5-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="187d5-228">Listen er et eksempel på de matchende segmentmedlemmer og viser de første 100 poster i dit segment, så du hurtigt kan evaluere det og gennemgå dets definitioner, hvis det er nødvendigt.</span><span class="sxs-lookup"><span data-stu-id="187d5-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="187d5-229">Hvis du vil se alle matchende poster, skal du [eksportere segmentet](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="187d5-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="187d5-230">Hurtige segmenter</span><span class="sxs-lookup"><span data-stu-id="187d5-230">Quick segments</span></span>

<span data-ttu-id="187d5-231">Ud over segmentbyggeren er der en anden vej til at oprette segmenter.</span><span class="sxs-lookup"><span data-stu-id="187d5-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="187d5-232">Hurtige segmenter giver dig mulighed for hurtigt at opbygge simple segmenter med en enkelt operator og med øjeblikkelig indsigt.</span><span class="sxs-lookup"><span data-stu-id="187d5-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="187d5-233">På siden **Segmenter** skal du vælge **Nyt** > **Opret hurtigt fra**.</span><span class="sxs-lookup"><span data-stu-id="187d5-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="187d5-234">Vælg indstillingen **Profiler** for at oprette et segment, der er baseret på det samlede kundeobjekt.</span><span class="sxs-lookup"><span data-stu-id="187d5-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="187d5-235">Vælg indstillingen **Målinger** for at oprette et segment omkring de enkelte kundeattributtyper af målinger, du tidligere har oprettet på siden **Målinger**.</span><span class="sxs-lookup"><span data-stu-id="187d5-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="187d5-236">Vælg indstillingen **Intelligens** for at oprette en segment omkring en af de outputenheder, du har oprettet ved hjælp af funktionerne **Forudsigelser** eller **Brugerdefinerede modeller**.</span><span class="sxs-lookup"><span data-stu-id="187d5-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="187d5-237">Vælg en attribut på rullelisten **Felt** i dialogboksen **Nyt hurtigt segment**.</span><span class="sxs-lookup"><span data-stu-id="187d5-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="187d5-238">Der gives yderligere indsigt i systemet, som kan hjælpe dig med at oprette bedre segmenter af dine kunder.</span><span class="sxs-lookup"><span data-stu-id="187d5-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="187d5-239">I forbindelse med kategoriske felter vises de 10 bedste kundeantal.</span><span class="sxs-lookup"><span data-stu-id="187d5-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="187d5-240">Vælg en **Værdi**, og vælg **Gennemse**.</span><span class="sxs-lookup"><span data-stu-id="187d5-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="187d5-241">I forbindelse med en numerisk attribut viser systemet, hvilken attributværdi der er omfattet af hver enkelt kundes percentil.</span><span class="sxs-lookup"><span data-stu-id="187d5-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="187d5-242">Vælg en **Operator** og en **Værdi**, og vælg derefter **Gennemse**.</span><span class="sxs-lookup"><span data-stu-id="187d5-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="187d5-243">Systemet vil give dig en **Anslået segmentstørrelse**.</span><span class="sxs-lookup"><span data-stu-id="187d5-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="187d5-244">Du kan vælge, om du vil oprette det segment, du har defineret, eller først vil gå til det igen for at få en anden segmentstørrelse.</span><span class="sxs-lookup"><span data-stu-id="187d5-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="187d5-245">![Navn og estimering for et hurtigt segment](media/quick-segment-name.png "Navn og estimering for et hurtigt segment")</span><span class="sxs-lookup"><span data-stu-id="187d5-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="187d5-246">Angiv et **Navn** til dit segment.</span><span class="sxs-lookup"><span data-stu-id="187d5-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="187d5-247">Angiv eventuelt et **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="187d5-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="187d5-248">Vælg **Gem** for at oprette dit segment.</span><span class="sxs-lookup"><span data-stu-id="187d5-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="187d5-249">Når segmentet er færdigbehandlet, kan du se det på samme måde som andre segmenter, du har oprettet.</span><span class="sxs-lookup"><span data-stu-id="187d5-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="187d5-250">I forbindelse med følgende situationer anbefaler vi, at du bruger segmentgeneratoren i stedet for de anbefalede segmentfunktioner:</span><span class="sxs-lookup"><span data-stu-id="187d5-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="187d5-251">Oprette segmenter med filtre på kategoriske felter, hvor operatoren er anderledes end operatoren **Er**</span><span class="sxs-lookup"><span data-stu-id="187d5-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="187d5-252">Oprette segmenter med filtre på numeriske felter, hvor operatoren er forskellig fra operatorerne **Mellem**, **Større end** og **Mindre end**</span><span class="sxs-lookup"><span data-stu-id="187d5-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="187d5-253">Oprette segmenter med filtre i datotypefelter</span><span class="sxs-lookup"><span data-stu-id="187d5-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="187d5-254">Næste trin</span><span class="sxs-lookup"><span data-stu-id="187d5-254">Next steps</span></span>

<span data-ttu-id="187d5-255">[Eksportere et segment](export-destinations.md) og udforske [kundekort](customer-card-add-in.md) og [connectorer](export-power-bi.md) for at få indsigt i kundeniveauet.</span><span class="sxs-lookup"><span data-stu-id="187d5-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]