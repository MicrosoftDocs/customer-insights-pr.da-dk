---
title: Oprette og administrere segmenter
description: Opret segmenter med kunder for at gruppere dem på baggrund af forskellige attributter.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064930"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="a609c-103">Oprette og administrere segmenter</span><span class="sxs-lookup"><span data-stu-id="a609c-103">Create and manage segments</span></span>

<span data-ttu-id="a609c-104">Definer komplekse filtre omkring det samlede kundeobjekt og dets tilknyttede objekter.</span><span class="sxs-lookup"><span data-stu-id="a609c-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="a609c-105">Hvert enkelt segment vil efter behandling oprette et sæt kundeposter, som du kan eksportere og udføre handlinger på.</span><span class="sxs-lookup"><span data-stu-id="a609c-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="a609c-106">Segmenter administreres på siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="a609c-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="a609c-107">I følgende eksempel vises segmenteringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="a609c-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="a609c-108">Vi har defineret et segment for kunder, der har bestilt mindst $500 varer over de seneste 90 dage, *og* som har været en del af et kundeserviceopkald, der blev eskaleret.</span><span class="sxs-lookup"><span data-stu-id="a609c-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Skærmbillede af brugergrænsefladen til segmentgenerator med to grupper, der angiver et kundesegment.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="a609c-110">Oprette et nyt segment</span><span class="sxs-lookup"><span data-stu-id="a609c-110">Create a new segment</span></span>

<span data-ttu-id="a609c-111">Der er flere måder, du kan oprette et nyt segment på.</span><span class="sxs-lookup"><span data-stu-id="a609c-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="a609c-112">I dette afsnit beskrives, hvordan du opretter *et tomt segment* fra bunden.</span><span class="sxs-lookup"><span data-stu-id="a609c-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="a609c-113">Du kan også oprette et *hurtigt segment*, der er baseret på eksisterende objekter, eller gøre brug af modeller til maskinel indlæring for at få *forslag til segmenter*.</span><span class="sxs-lookup"><span data-stu-id="a609c-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="a609c-114">Flere oplysninger: [Oversigt over segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a609c-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="a609c-115">Når du opretter et segment, kan du gemme en kladde.</span><span class="sxs-lookup"><span data-stu-id="a609c-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="a609c-116">Den gemmes som et inaktivt segment og kan ikke aktiveres, før den er fuldført med en gyldig konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a609c-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="a609c-117">Gå til siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="a609c-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="a609c-118">Vælg **Ny** > **Tomt segment**.</span><span class="sxs-lookup"><span data-stu-id="a609c-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="a609c-119">Vælg en segmenttype i ruden **Nyt segment**:</span><span class="sxs-lookup"><span data-stu-id="a609c-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="a609c-120">**Dynamiske segmenter** [opdateres](segments.md#refresh-segments) efter en tilbagevendende tidsplan.</span><span class="sxs-lookup"><span data-stu-id="a609c-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="a609c-121">**Statiske segmenter** køres én gang, når du opretter dem.</span><span class="sxs-lookup"><span data-stu-id="a609c-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="a609c-122">Angiv **Navn på outputobjekt** for segmentet.</span><span class="sxs-lookup"><span data-stu-id="a609c-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="a609c-123">Du kan også angive et vist navn og en beskrivelse, der hjælper med at identificere segmentet.</span><span class="sxs-lookup"><span data-stu-id="a609c-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="a609c-124">Vælg **Næste** for at gå til siden **Segmentgenerator**, hvor du definerer en gruppe.</span><span class="sxs-lookup"><span data-stu-id="a609c-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="a609c-125">En gruppe er et sæt kunder.</span><span class="sxs-lookup"><span data-stu-id="a609c-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="a609c-126">Vælg det objekt, der indeholder den attribut, du vil segmentere efter.</span><span class="sxs-lookup"><span data-stu-id="a609c-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="a609c-127">Vælg den attribut, der skal segmenteres efter.</span><span class="sxs-lookup"><span data-stu-id="a609c-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="a609c-128">Denne attribut kan have en af fire værdityper: numerisk, streng, dato eller boolesk.</span><span class="sxs-lookup"><span data-stu-id="a609c-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="a609c-129">Vælg en operator og en værdi for den valgte attribut.</span><span class="sxs-lookup"><span data-stu-id="a609c-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a609c-130">![Brugerdefineret gruppefilter](media/customer-group-numbers.png "Kundegruppefilter")</span><span class="sxs-lookup"><span data-stu-id="a609c-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="a609c-131">Antal</span><span class="sxs-lookup"><span data-stu-id="a609c-131">Number</span></span> |<span data-ttu-id="a609c-132">Definition</span><span class="sxs-lookup"><span data-stu-id="a609c-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="a609c-133">0</span><span class="sxs-lookup"><span data-stu-id="a609c-133">1</span></span>     |<span data-ttu-id="a609c-134">Enhed</span><span class="sxs-lookup"><span data-stu-id="a609c-134">Entity</span></span>          |
   |<span data-ttu-id="a609c-135">2</span><span class="sxs-lookup"><span data-stu-id="a609c-135">2</span></span>     |<span data-ttu-id="a609c-136">Attribut</span><span class="sxs-lookup"><span data-stu-id="a609c-136">Attribute</span></span>          |
   |<span data-ttu-id="a609c-137">3</span><span class="sxs-lookup"><span data-stu-id="a609c-137">3</span></span>    |<span data-ttu-id="a609c-138">Operatør</span><span class="sxs-lookup"><span data-stu-id="a609c-138">Operator</span></span>         |
   |<span data-ttu-id="a609c-139">4</span><span class="sxs-lookup"><span data-stu-id="a609c-139">4</span></span>    |<span data-ttu-id="a609c-140">Værdi</span><span class="sxs-lookup"><span data-stu-id="a609c-140">Value</span></span>         |

   1. <span data-ttu-id="a609c-141">Hvis du vil føje flere betingelser til en gruppe, kan du bruge to logiske operatorer:</span><span class="sxs-lookup"><span data-stu-id="a609c-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="a609c-142">**OG**-operator: Begge betingelser skal overholdes som en del af segmenteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="a609c-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="a609c-143">Denne indstilling er mest nyttig, når du definerer betingelser på tværs af forskellige objekter.</span><span class="sxs-lookup"><span data-stu-id="a609c-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="a609c-144">**ELLER**-operator: Den ene eller anden betingelse skal overholdes som en del af segmenteringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="a609c-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="a609c-145">Denne indstilling er mest nyttig, når du definerer flere betingelser for det samme objekt.</span><span class="sxs-lookup"><span data-stu-id="a609c-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="a609c-146">![ELLER-operator, hvor en af betingelserne skal overholdes](media/segmentation-either-condition.png "ELLER-operator, hvor en af betingelserne skal overholdes")</span><span class="sxs-lookup"><span data-stu-id="a609c-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="a609c-147">Det er aktuelt muligt at indlejre en **ELLER**-operator under en **OG**-operator, men ikke den anden vej rundt.</span><span class="sxs-lookup"><span data-stu-id="a609c-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="a609c-148">Hver gruppe matcher sæt af kundegrupper.</span><span class="sxs-lookup"><span data-stu-id="a609c-148">Each group matches set of customers.</span></span> <span data-ttu-id="a609c-149">Du kan kombinere grupper for at medtage de kunder, der kræves til din sag.</span><span class="sxs-lookup"><span data-stu-id="a609c-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="a609c-150">Vælg **Tilføj gruppe**.</span><span class="sxs-lookup"><span data-stu-id="a609c-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="a609c-151">![Tilføje kundegruppe](media/customer-group-add-group.png "Tilføje kundegruppe")</span><span class="sxs-lookup"><span data-stu-id="a609c-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="a609c-152">Vælg en af de indstillede operatorer: **Foreningsmængde**, **Overlapning** eller **Undtagen**.</span><span class="sxs-lookup"><span data-stu-id="a609c-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a609c-153">![Tilføje foreningsmængde af kundegruppe](media/customer-group-union.png "Tilføje foreningsmængde af kundegruppe")</span><span class="sxs-lookup"><span data-stu-id="a609c-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="a609c-154">**Foreningsmængde** forener de to grupper.</span><span class="sxs-lookup"><span data-stu-id="a609c-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="a609c-155">**Overlapning** overlapper de to grupper.</span><span class="sxs-lookup"><span data-stu-id="a609c-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="a609c-156">Kun data, der *er fælles* for begge grupper, bevares i den samlede gruppe.</span><span class="sxs-lookup"><span data-stu-id="a609c-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="a609c-157">**Undtagen** kombinerer de to grupper.</span><span class="sxs-lookup"><span data-stu-id="a609c-157">**Except** combines the two groups.</span></span> <span data-ttu-id="a609c-158">Kun data i gruppe A, der *ikke er fælles* med data i gruppe B, bevares.</span><span class="sxs-lookup"><span data-stu-id="a609c-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="a609c-159">Hvis objektet er knyttet til det samlede kundeobjekt via [Relationer](relationships.md), skal du definere relationsstien for at oprette et gyldigt segment.</span><span class="sxs-lookup"><span data-stu-id="a609c-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="a609c-160">Tilføj objekterne fra relationsstien, indtil du kan vælge objektet **Kunde: CustomerInsights** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="a609c-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="a609c-161">Vælg derefter **Alle poster** for hvert trin.</span><span class="sxs-lookup"><span data-stu-id="a609c-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a609c-162">![Relationsstien under oprettelse af segmenter](media/segments-multiple-relationships.png "Relationsstien under oprettelse af segmenter")</span><span class="sxs-lookup"><span data-stu-id="a609c-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="a609c-163">Som standard opretter segmenter et outputobjekt, der indeholder alle attributter af kundeprofiler, som stemmer overens med de definerede filtre.</span><span class="sxs-lookup"><span data-stu-id="a609c-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="a609c-164">Hvis et segment er baseret på andre objekter end *Kunde*-objektet, kan du føje flere attributter fra disse objekter til outputobjektet.</span><span class="sxs-lookup"><span data-stu-id="a609c-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="a609c-165">Vælg **Projektattributter** for at vælge de attributter, der skal føjes til outputobjektet.</span><span class="sxs-lookup"><span data-stu-id="a609c-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="a609c-166">Eksempel: Et segment er baseret på et objekt, der indeholder kundeaktivitetsdata, som er relateret til objektet *Kunde*.</span><span class="sxs-lookup"><span data-stu-id="a609c-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="a609c-167">Segmentet søger efter alle kunder, der har ringet til Helpdesk inden for de seneste 60 dage.</span><span class="sxs-lookup"><span data-stu-id="a609c-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="a609c-168">Du kan vælge at føje varigheden af opkaldet og antallet af opkald til alle tilsvarende kundeposter i outputobjektet.</span><span class="sxs-lookup"><span data-stu-id="a609c-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="a609c-169">Disse oplysninger kan være nyttige, hvis du vil sende en mail med nyttige links til artikler i onlinehjælp og ofte stillede spørgsmål til kunder, der ofte har ringet.</span><span class="sxs-lookup"><span data-stu-id="a609c-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="a609c-170">Projekterede attributter fungerer kun for objekter, der har en en til mange-relation til kundeobjektet.</span><span class="sxs-lookup"><span data-stu-id="a609c-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="a609c-171">En kunde kan f.eks. have flere abonnementer.</span><span class="sxs-lookup"><span data-stu-id="a609c-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="a609c-172">Du kan kun projektere attributter fra et objekt, der bruges i alle grupper af segmentforespørgsel, du er i gang med at bygge.</span><span class="sxs-lookup"><span data-stu-id="a609c-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="a609c-173">Projekterede attributter anvendes, når der bruges indstillede operatorer.</span><span class="sxs-lookup"><span data-stu-id="a609c-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="a609c-174">Vælg **Gem** for at gemme dit segment.</span><span class="sxs-lookup"><span data-stu-id="a609c-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="a609c-175">Dit segment gemmes og behandles, hvis alle krav valideres.</span><span class="sxs-lookup"><span data-stu-id="a609c-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="a609c-176">Ellers gemmes det som en kladde.</span><span class="sxs-lookup"><span data-stu-id="a609c-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="a609c-177">Vælg **Tilbage til segmenter** for at gå tilbage til siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="a609c-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="a609c-178">Hurtige segmenter</span><span class="sxs-lookup"><span data-stu-id="a609c-178">Quick segments</span></span>

<span data-ttu-id="a609c-179">Med hurtige segmenter kan du nemt oprette simple segmenter med en enkelt operator for at få hurtigere indsigt.</span><span class="sxs-lookup"><span data-stu-id="a609c-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="a609c-180">På siden **Segmenter** skal du vælge **Nyt** > **Opret fra**.</span><span class="sxs-lookup"><span data-stu-id="a609c-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="a609c-181">Vælg indstillingen **Profiler** for at oprette et segment, der er baseret på det *samlede kundeobjekt*.</span><span class="sxs-lookup"><span data-stu-id="a609c-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="a609c-182">Vælg indstillingen **Målinger** for at oprette et segment omkring de målinger, du tidligere har oprettet.</span><span class="sxs-lookup"><span data-stu-id="a609c-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="a609c-183">Vælg indstillingen **Intelligens** for at oprette en segment omkring en af de outputenheder, du har oprettet ved hjælp af funktionerne **Forudsigelser** eller **Brugerdefinerede modeller**.</span><span class="sxs-lookup"><span data-stu-id="a609c-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="a609c-184">Vælg en attribut på rullelisten **Felt** i dialogboksen **Nyt hurtigt segment**.</span><span class="sxs-lookup"><span data-stu-id="a609c-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="a609c-185">Der gives yderligere indsigt i systemet, som kan hjælpe dig med at oprette bedre segmenter af dine kunder.</span><span class="sxs-lookup"><span data-stu-id="a609c-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="a609c-186">I forbindelse med kategoriske felter vises de 10 bedste kundeantal.</span><span class="sxs-lookup"><span data-stu-id="a609c-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="a609c-187">Vælg en **Værdi**, og vælg **Gennemse**.</span><span class="sxs-lookup"><span data-stu-id="a609c-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="a609c-188">I forbindelse med en numerisk attribut viser systemet, hvilken attributværdi der er omfattet af hver enkelt kundes percentil.</span><span class="sxs-lookup"><span data-stu-id="a609c-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="a609c-189">Vælg en **Operator** og en **Værdi**, og vælg derefter **Gennemse**.</span><span class="sxs-lookup"><span data-stu-id="a609c-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="a609c-190">Systemet vil give dig en **Anslået segmentstørrelse**.</span><span class="sxs-lookup"><span data-stu-id="a609c-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="a609c-191">Du kan vælge, om du vil oprette det segment, du har defineret, eller først vil gå til det igen for at få en anden segmentstørrelse.</span><span class="sxs-lookup"><span data-stu-id="a609c-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a609c-192">![Navn og estimering for et hurtigt segment](media/quick-segment-name.png "Navn og estimering for et hurtigt segment")</span><span class="sxs-lookup"><span data-stu-id="a609c-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="a609c-193">Angiv et **Navn** til dit segment.</span><span class="sxs-lookup"><span data-stu-id="a609c-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="a609c-194">Angiv eventuelt et **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="a609c-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="a609c-195">Vælg **Gem** for at oprette dit segment.</span><span class="sxs-lookup"><span data-stu-id="a609c-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="a609c-196">Når segmentet er færdigbehandlet, kan du se det på samme måde som andre segmenter, du har oprettet.</span><span class="sxs-lookup"><span data-stu-id="a609c-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a609c-197">Næste trin</span><span class="sxs-lookup"><span data-stu-id="a609c-197">Next steps</span></span>

<span data-ttu-id="a609c-198">[Eksportere et segment](export-destinations.md) og udforske [kundekort](customer-card-add-in.md) og [connectorer](export-power-bi.md) for at få indsigt i kundeniveauet.</span><span class="sxs-lookup"><span data-stu-id="a609c-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
