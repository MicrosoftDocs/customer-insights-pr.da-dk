---
title: Opret og rediger målinger
description: Definer kunderelaterede målinger for at analysere og afspejle ydeevnen af bestemte forretningsområder.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405451"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="96825-103">Definere og administrere målinger</span><span class="sxs-lookup"><span data-stu-id="96825-103">Define and manage measures</span></span>

<span data-ttu-id="96825-104">**Målinger** repræsenterer nøgletal (KPI'er), der afspejler ydeevnen og tilstanden af bestemte forretningsområder.</span><span class="sxs-lookup"><span data-stu-id="96825-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="96825-105">Målgruppen Insights giver en intuitiv oplevelse til opbygning af forskellige typer målpunkter ved hjælp af en forespørgselsgenerator, der ikke kræver, at du koder eller validerer dine målpunkter manuelt.</span><span class="sxs-lookup"><span data-stu-id="96825-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="96825-106">Du kan spore dine forretningsmålinger på **startsiden**, se målinger for bestemte kunder på **Kundekort** og bruge målinger til at definere kundesegmenter på siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="96825-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="96825-107">Oprette en måling</span><span class="sxs-lookup"><span data-stu-id="96825-107">Create a measure</span></span>

<span data-ttu-id="96825-108">I dette afsnit gennemgås, hvordan du opretter en måling fra bunden.</span><span class="sxs-lookup"><span data-stu-id="96825-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="96825-109">Du kan oprette målinger med data fra flere datakilder, der er forbundet via kundeobjektet.</span><span class="sxs-lookup"><span data-stu-id="96825-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="96825-110">Der gælder nogle [tjenestebegrænsninger](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="96825-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="96825-111">Gå til **Målinger** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="96825-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="96825-112">Vælg **Ny måling**.</span><span class="sxs-lookup"><span data-stu-id="96825-112">Select **New measure**.</span></span>

3. <span data-ttu-id="96825-113">Vælg målingen **Type**:</span><span class="sxs-lookup"><span data-stu-id="96825-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="96825-114">**Kundeattribut**: Et enkelt felt pr. kunde, der afspejler en score, værdi eller tilstand for kunden.</span><span class="sxs-lookup"><span data-stu-id="96825-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="96825-115">Kundeattributter oprettes som attributter i et nyt systemgenereret objekt, der kaldes **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="96825-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="96825-116">**Kundemåling**: Indsigt i kundeadfærd med fordeling efter valgte dimensioner.</span><span class="sxs-lookup"><span data-stu-id="96825-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="96825-117">Der oprettes et nyt objekt for hver måling, der muligvis har flere poster pr. kunde.</span><span class="sxs-lookup"><span data-stu-id="96825-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="96825-118">**Forretningsmæssig måling**: Sporer din virksomheds præstationer og tilstand.</span><span class="sxs-lookup"><span data-stu-id="96825-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="96825-119">Forretningsmæssige målinger kan have to forskellige output: Et numerisk output, der vises på **Startside**, eller et nyt objekt, som du finder på siden **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="96825-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="96825-120">Angiv et **Navn** og et valgfrit **Vist navn**, og vælg derefter **Næste**.</span><span class="sxs-lookup"><span data-stu-id="96825-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="96825-121">I sektionen **Objekt** skal du vælge det første objekt på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="96825-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="96825-122">På dette tidspunkt skal du finde ud af, om der skal bruges yderligere objekter som en del af din målingsdefinition.</span><span class="sxs-lookup"><span data-stu-id="96825-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="96825-123">![Definition af måling](media/measure-definition.png "Definition af måling")</span><span class="sxs-lookup"><span data-stu-id="96825-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="96825-124">Hvis du vil tilføje flere objekter, skal du vælge **Tilføj objekt** og vælge de objekter, du vil bruge til målingen.</span><span class="sxs-lookup"><span data-stu-id="96825-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="96825-125">Du kan kun vælge objekter, der har en relation til dit startobjekt.</span><span class="sxs-lookup"><span data-stu-id="96825-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="96825-126">Du kan finde flere oplysninger om definition af relationer under [Relationer](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="96825-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="96825-127">Du kan også konfigurere variabler.</span><span class="sxs-lookup"><span data-stu-id="96825-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="96825-128">Vælg **Ny variabel** i sektionen **Variabler**.</span><span class="sxs-lookup"><span data-stu-id="96825-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="96825-129">Variabler er beregninger, der er foretaget på de valgte poster.</span><span class="sxs-lookup"><span data-stu-id="96825-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="96825-130">F.eks. opsummering af POS og onlinesalg for hver af dine kunders poster.</span><span class="sxs-lookup"><span data-stu-id="96825-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="96825-131">Angiv et **Navn** til variablen.</span><span class="sxs-lookup"><span data-stu-id="96825-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="96825-132">Vælg et felt i området **Udtryk**, hvor du vil begynde at foretage beregningen.</span><span class="sxs-lookup"><span data-stu-id="96825-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="96825-133">Skriv et udtryk i området **Udtryk**, mens du vælger flere felter, der skal inkluderes i beregningen.</span><span class="sxs-lookup"><span data-stu-id="96825-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="96825-134">I øjeblikket understøttes kun matematiske udtryk.</span><span class="sxs-lookup"><span data-stu-id="96825-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="96825-135">Variabel beregning understøttes heller ikke for objekter fra forskellige [objektstier](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="96825-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="96825-136">Vælg **Udført**.</span><span class="sxs-lookup"><span data-stu-id="96825-136">Select **Done**.</span></span>

11. <span data-ttu-id="96825-137">I sektionen **Definition af måling** kan du definere, hvordan de valgte objekter og beregnede variabler skal samles i et nyt målingsobjekt eller en ny attribut.</span><span class="sxs-lookup"><span data-stu-id="96825-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="96825-138">Vælg **Ny dimension**.</span><span class="sxs-lookup"><span data-stu-id="96825-138">Select **New dimension**.</span></span> <span data-ttu-id="96825-139">Du kan betragte en dimension som en *gruppér efter*-funktion.</span><span class="sxs-lookup"><span data-stu-id="96825-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="96825-140">Dataoutputtet for målingsobjektet eller attributten grupperes efter alle de definerede dimensioner.</span><span class="sxs-lookup"><span data-stu-id="96825-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="96825-141">![Vælge aggregatcyklus](media/measures-businessreport-measure-definition2.png "Vælge aggregatcyklus")</span><span class="sxs-lookup"><span data-stu-id="96825-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="96825-142">Vælg eller angiv følgende oplysninger som en del af dimensionens definition:</span><span class="sxs-lookup"><span data-stu-id="96825-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="96825-143">**Objekt**: Hvis du definerer et målingsobjekt, skal det inkludere mindst én attribut.</span><span class="sxs-lookup"><span data-stu-id="96825-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="96825-144">Hvis du definerer en målingsattribut, medtages der som standard kun én attribut.</span><span class="sxs-lookup"><span data-stu-id="96825-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="96825-145">Denne indstilling bruges til at vælge det objekt, der indeholder den pågældende attribut.</span><span class="sxs-lookup"><span data-stu-id="96825-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="96825-146">**Felt**: Vælg den specifikke attribut, der skal inkluderes, enten i målingsenheden eller -attributten.</span><span class="sxs-lookup"><span data-stu-id="96825-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="96825-147">**Bucket**: Vælg, om du vil samle data på en daglig, månedlig eller årlig basis.</span><span class="sxs-lookup"><span data-stu-id="96825-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="96825-148">Det er kun nødvendigt at bruge feltet, hvis du har valgt en Datotype-attribut.</span><span class="sxs-lookup"><span data-stu-id="96825-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="96825-149">**Som**: Definerer navnet på det nye felt.</span><span class="sxs-lookup"><span data-stu-id="96825-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="96825-150">**Vist navn**: Definerer feltets viste navn.</span><span class="sxs-lookup"><span data-stu-id="96825-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="96825-151">Din forretningsmåling gemmes som et objekt med et enkelt nummer og vises på **Startsiden**, medmindre du føjer flere dimensioner til målingen.</span><span class="sxs-lookup"><span data-stu-id="96825-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="96825-152">Når der er tilføjet flere dimensioner, vises målingen *ikke* på **Startsiden**.</span><span class="sxs-lookup"><span data-stu-id="96825-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="96825-153">Du kan også vælge at tilføje sammenlægningsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="96825-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="96825-154">Enhver sammenlægning, du opretter, resulterer i en ny værdi i målingsobjektet eller -attributten.</span><span class="sxs-lookup"><span data-stu-id="96825-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="96825-155">Understøttede sammenlægningsfunktioner er: **Min.**, **Maks.**, **Gennemsnit**, **Median**, **Sum**, **Antal entydige**, **Første** (tager den første post i en dimensionsværdi) og **Sidste** (tager den sidste post, der er føjet til en dimensionsværdi).</span><span class="sxs-lookup"><span data-stu-id="96825-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="96825-156">Vælg **Gem** for at gemme dine ændringer af målingen.</span><span class="sxs-lookup"><span data-stu-id="96825-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="96825-157">Administrere dine målinger</span><span class="sxs-lookup"><span data-stu-id="96825-157">Manage your measures</span></span>

<span data-ttu-id="96825-158">Når du har oprettet mindst ét mål, kan du se en liste over mål på siden **Mål**.</span><span class="sxs-lookup"><span data-stu-id="96825-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="96825-159">Du kan finde oplysninger om målingstype, forfatter, oprettelsesdato og -klokkeslæt, sidste redigeringsdato og -klokkeslæt, status (om målingen er aktiv, inaktiv eller mislykket) og dato og klokkeslæt for seneste opdatering.</span><span class="sxs-lookup"><span data-stu-id="96825-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="96825-160">Når du vælger en måling på listen, kan du få vist et eksempel på outputtet.</span><span class="sxs-lookup"><span data-stu-id="96825-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="96825-161">Hvis du vil opdatere alle dine målinger på én gang, skal du vælge **Opdater alle** uden at vælge en bestemt måling.</span><span class="sxs-lookup"><span data-stu-id="96825-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96825-162">![Handlinger til administration af enkelte målinger](media/measure-actions.png "Handlinger til administration af enkelte målinger")</span><span class="sxs-lookup"><span data-stu-id="96825-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="96825-163">Du kan også vælge en måling på listen og udføre en af følgende handlinger:</span><span class="sxs-lookup"><span data-stu-id="96825-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="96825-164">Vælg målingens navn for at se detaljer om den.</span><span class="sxs-lookup"><span data-stu-id="96825-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="96825-165">**Rediger** konfigurationen af målingen.</span><span class="sxs-lookup"><span data-stu-id="96825-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="96825-166">**Omdøb** målingen.</span><span class="sxs-lookup"><span data-stu-id="96825-166">**Rename** the measure.</span></span>
- <span data-ttu-id="96825-167">**Slet** målingen.</span><span class="sxs-lookup"><span data-stu-id="96825-167">**Delete** the measure.</span></span>
- <span data-ttu-id="96825-168">Vælg ellipsen (...), og vælg **Opdater** for at starte opdateringsprocessen for målingen.</span><span class="sxs-lookup"><span data-stu-id="96825-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="96825-169">Vælg ellipsen (...), og **Hent** for at hente en. CSV-fil for målingen.</span><span class="sxs-lookup"><span data-stu-id="96825-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="96825-170">Opgaver og processer indeholder [seks typer status](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="96825-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="96825-171">De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="96825-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="96825-172">Du kan vælge status for en proces for at se statusdetaljer for hele jobbet.</span><span class="sxs-lookup"><span data-stu-id="96825-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="96825-173">Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.</span><span class="sxs-lookup"><span data-stu-id="96825-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="96825-174">Næste trin</span><span class="sxs-lookup"><span data-stu-id="96825-174">Next step</span></span>

<span data-ttu-id="96825-175">Du kan bruge eksisterende målinger til at oprette dit første kundesegment på siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="96825-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="96825-176">Du kan finde flere oplysninger under [Segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="96825-176">For more information, see [Segments](segments.md).</span></span>
