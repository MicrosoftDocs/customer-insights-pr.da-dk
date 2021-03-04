---
title: Flet objekter i datasamling
description: Flet objekter for at oprette samlede kundeprofiler.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268495"
---
# <a name="merge-entities"></a><span data-ttu-id="6c9e3-103">Flet objekter</span><span class="sxs-lookup"><span data-stu-id="6c9e3-103">Merge entities</span></span>

<span data-ttu-id="6c9e3-104">Flettefasen er den sidste fase i datasamlingsprocessen.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="6c9e3-105">Dens formål er at afstemme data, der er i konflikt.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="6c9e3-106">Af eksempler på data, der er i konflikt, kan nævnes et kundenavn, der findes i to af dine datasæt, men som vises en smule anderledes i hvert sæt ("Claus Madsen" i forhold til "Klaus Madsen") eller et telefonnummer, der adskiller sig i formatet (617-803-091X i forhold til 617803091X).</span><span class="sxs-lookup"><span data-stu-id="6c9e3-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="6c9e3-107">Fletning af disse datapunkter, der er i konflikt, sker på attribut for attribut-basis.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="6c9e3-108">Når du har fuldført [matchfasen](match-entities.md), starter du flettefasen ved at vælge feltet **Flet** på siden **Saml**.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="6c9e3-109">Gennemgå systemanbefalinger</span><span class="sxs-lookup"><span data-stu-id="6c9e3-109">Review system recommendations</span></span>

<span data-ttu-id="6c9e3-110">På siden **Flet** vælger og udelader du de attributter, der skal flettes i det samlede kundeprofilobjekt (resultatet af konfigurationsprocessen).</span><span class="sxs-lookup"><span data-stu-id="6c9e3-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="6c9e3-111">Nogle attributter flettes automatisk af systemet.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="6c9e3-112">Se flettede attributter</span><span class="sxs-lookup"><span data-stu-id="6c9e3-112">View merged attributes</span></span>

<span data-ttu-id="6c9e3-113">Hvis du vil have vist de attributter, der er inkluderet i en af de automatisk flettede attributter, skal du vælge den flettede attribut.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="6c9e3-114">De to attributter, der udgør den flettede attribut, vises i to nye rækker under den flettede attribut.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6c9e3-115">![Vælge flettet attribut](media/configure-data-merge-profile-attributes.png "Vælge flettet attribut")</span><span class="sxs-lookup"><span data-stu-id="6c9e3-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="6c9e3-116">Adskille flettede attributter</span><span class="sxs-lookup"><span data-stu-id="6c9e3-116">Separate merged attributes</span></span>

<span data-ttu-id="6c9e3-117">Hvis du vil adskille eller ophæve fletning af en af de automatisk flettede attributter, skal du finde attributten i tabellen **Profilattributter**.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="6c9e3-118">Vælg ellipseknappen ( ... ).</span><span class="sxs-lookup"><span data-stu-id="6c9e3-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="6c9e3-119">Vælg **Separate felter** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="6c9e3-120">Fjerne flettede attributter</span><span class="sxs-lookup"><span data-stu-id="6c9e3-120">Remove merged attributes</span></span>

<span data-ttu-id="6c9e3-121">Hvis du vil udelade en attribut fra det endelige kundeprofilobjekt , skal du finde den i tabellen **Profilattributter**.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="6c9e3-122">Vælg ellipseknappen ( ... ).</span><span class="sxs-lookup"><span data-stu-id="6c9e3-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="6c9e3-123">Vælg **Flet ikke** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="6c9e3-124">Attributten flyttes til sektionen **Fjernet fra kundepost**.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="6c9e3-125">Manuelt tilføje en flettet attribut</span><span class="sxs-lookup"><span data-stu-id="6c9e3-125">Manually add a merged attribute</span></span>

<span data-ttu-id="6c9e3-126">Hvis du vil tilføje en flettet attribut, skal du gå til siden **Flet**.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="6c9e3-127">Vælg **Tilføj flettet attribut**.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="6c9e3-128">Angiv et **Navn**, der identificerer den på siden **Flet** senere.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="6c9e3-129">Du kan også angive et **Vist navn**, der skal vises i det samlede kundeprofilobjekt.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="6c9e3-130">Konfigurer **Vælg duplikerede attributter** for at vælge de attributter, du vil flette fra de matchede objekter.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="6c9e3-131">Du kan også søge efter attributter.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="6c9e3-132">Angiv **Ranger efter vigtighed** for at prioritere den ene attribut over de andre.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="6c9e3-133">Hvis objektet *WebAccountCSV* f.eks. indeholder de mest præcise data om attributten *Fulde navn*, kan du prioritere dette objekt højere end *ContactCSV* ved at vælge *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="6c9e3-134">Resultatet medfører, at *WebAccountCSV* flyttes til første prioritet, mens *ContactCSV* flyttes til anden prioritet, når der udtrækkes værdier til attributten *Fulde navn*.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="6c9e3-135">Køre fletningen</span><span class="sxs-lookup"><span data-stu-id="6c9e3-135">Run your merge</span></span>

<span data-ttu-id="6c9e3-136">Uanset om du fletter attributter manuelt eller lader systemet flette dem, kan du altid køre fletningen.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="6c9e3-137">Vælg **Kør** på siden **Flet** for at starte processen.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6c9e3-138">![Gemme og køre datafletning](media/configure-data-merge-save-run.png "Gemme og køre datafletning")</span><span class="sxs-lookup"><span data-stu-id="6c9e3-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="6c9e3-139">Hvis du vil foretage yderligere ændringer og køre trinnet igen, kan du annullere en igangværende fletning.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="6c9e3-140">Vælg **Opdaterer...**, og vælg **Annuller job** i den siderude, der vises.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="6c9e3-141">Når teksten **Opdaterer ...** er ændret til **Gennemført**, er fletningen fuldført, og uoverensstemmelser i dine data i henhold til de politikker, du har defineret, er løst.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="6c9e3-142">Flettede og ikke-flettede attributter inkluderes i objektet for den samlede profil.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="6c9e3-143">Udeladte attributter inkluderes ikke i objektet for den samlede profil.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="6c9e3-144">Hvis det ikke var første gang, du fuldførte en fletning, køres alle downstream-processer, herunder forbedring, segmentering og målinger, automatisk.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="6c9e3-145">Når alle downstream-processer er kørt igen, afspejler kundeprofilerne eventuelle ændringer, du har foretaget.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="6c9e3-146">Opgaver og processer indeholder [seks typer status](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="6c9e3-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="6c9e3-147">De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="6c9e3-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="6c9e3-148">Du kan vælge status for en proces for at se statusdetaljer for hele jobbet.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="6c9e3-149">Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="6c9e3-150">Næste trin</span><span class="sxs-lookup"><span data-stu-id="6c9e3-150">Next Step</span></span>

<span data-ttu-id="6c9e3-151">Konfigurer [aktiviteter](activities.md), [forbedring](enrichment-microsoft-graph.md) eller [relationer](relationships.md) for at få mere indsigt i dine kunder.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="6c9e3-152">Hvis du allerede har konfigureret aktiviteter, forbedring eller relationer, eller hvis du har defineret segmenter, behandles de automatisk, så de anvender de nyeste kundedata.</span><span class="sxs-lookup"><span data-stu-id="6c9e3-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]