---
title: Flet objekter i datasamling
description: Flet objekter for at oprette samlede kundeprofiler.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305623"
---
# <a name="merge-entities"></a><span data-ttu-id="e41e0-103">Flet objekter</span><span class="sxs-lookup"><span data-stu-id="e41e0-103">Merge entities</span></span>

<span data-ttu-id="e41e0-104">Flettefasen er den sidste fase i datasamlingsprocessen.</span><span class="sxs-lookup"><span data-stu-id="e41e0-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="e41e0-105">Dens formål er at afstemme data, der er i konflikt.</span><span class="sxs-lookup"><span data-stu-id="e41e0-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="e41e0-106">Af eksempler på data, der er i konflikt, kan nævnes et kundenavn, der findes i to af dine datasæt, men som vises en smule anderledes i hvert sæt ("Claus Madsen" i forhold til "Klaus Madsen") eller et telefonnummer, der adskiller sig i formatet (617-803-091X i forhold til 617803091X).</span><span class="sxs-lookup"><span data-stu-id="e41e0-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="e41e0-107">Fletning af disse datapunkter, der er i konflikt, sker på attribut for attribut-basis.</span><span class="sxs-lookup"><span data-stu-id="e41e0-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Siden Flet i processen til datasamling, der viser en tabel med flettede felter, der definerer den samlede kundeprofil.":::

<span data-ttu-id="e41e0-109">Når du har fuldført [matchfasen](match-entities.md), starter du flettefasen ved at vælge feltet **Flet** på siden **Saml**.</span><span class="sxs-lookup"><span data-stu-id="e41e0-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="e41e0-110">Gennemgå systemanbefalinger</span><span class="sxs-lookup"><span data-stu-id="e41e0-110">Review system recommendations</span></span>

<span data-ttu-id="e41e0-111">I **Data** > **Saml** > **Flet** skal du vælge og udelade attributter, der skal flettes i objektet med den samlede kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="e41e0-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="e41e0-112">Den samlede kundeprofil er resultatet af processen til samling af data.</span><span class="sxs-lookup"><span data-stu-id="e41e0-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="e41e0-113">Nogle attributter flettes automatisk af systemet.</span><span class="sxs-lookup"><span data-stu-id="e41e0-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="e41e0-114">Hvis du vil have vist de attributter, der er inkluderet i en af dine automatisk flettede attributter, skal du vælge den flettede attribut under fanen **Kundefelter** i tabellen.</span><span class="sxs-lookup"><span data-stu-id="e41e0-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="e41e0-115">De attributter, der udgør den flettede attribut, vises i to nye rækker under den flettede attribut.</span><span class="sxs-lookup"><span data-stu-id="e41e0-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="e41e0-116">Adskille, omdøbe, udelade og redigere flettede felter</span><span class="sxs-lookup"><span data-stu-id="e41e0-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="e41e0-117">Du kan ændre, hvordan flettede attributter skal behandles i systemet for at oprette den samlede kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="e41e0-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="e41e0-118">Vælg **Vis mere**, og vælg, hvad du vil ændre.</span><span class="sxs-lookup"><span data-stu-id="e41e0-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Indstillinger i rullemenuen Vis flere for at administrere flettede attributter.":::

<span data-ttu-id="e41e0-120">Der er flere oplysninger i følgende afsnit.</span><span class="sxs-lookup"><span data-stu-id="e41e0-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="e41e0-121">Adskille flettede felter</span><span class="sxs-lookup"><span data-stu-id="e41e0-121">Separate merged fields</span></span>

<span data-ttu-id="e41e0-122">Hvis du vil adskille flettede felter, skal du søge efter attributten i tabellen.</span><span class="sxs-lookup"><span data-stu-id="e41e0-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="e41e0-123">Adskilte felter vises som individuelle datapunkter i den samlede kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="e41e0-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="e41e0-124">Vælg det flettede felt.</span><span class="sxs-lookup"><span data-stu-id="e41e0-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="e41e0-125">Vælg **Vis flere**, og vælg **Separate felter**.</span><span class="sxs-lookup"><span data-stu-id="e41e0-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="e41e0-126">Bekræft separationen.</span><span class="sxs-lookup"><span data-stu-id="e41e0-126">Confirm the separation.</span></span>

1. <span data-ttu-id="e41e0-127">Vælg **Gem** og **Kør** for at behandle ændringerne.</span><span class="sxs-lookup"><span data-stu-id="e41e0-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="e41e0-128">Omdøbe flettede felter</span><span class="sxs-lookup"><span data-stu-id="e41e0-128">Rename merged fields</span></span>

<span data-ttu-id="e41e0-129">Omdøb det viste navn på flettede attributter.</span><span class="sxs-lookup"><span data-stu-id="e41e0-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="e41e0-130">Du kan ikke ændre navnet på outputobjektet.</span><span class="sxs-lookup"><span data-stu-id="e41e0-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="e41e0-131">Vælg det flettede felt.</span><span class="sxs-lookup"><span data-stu-id="e41e0-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="e41e0-132">Vælg **Vis flere**, og vælg **Omdøb**.</span><span class="sxs-lookup"><span data-stu-id="e41e0-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="e41e0-133">Bekræft det ændrede viste navn.</span><span class="sxs-lookup"><span data-stu-id="e41e0-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="e41e0-134">Vælg **Gem** og **Kør** for at behandle ændringerne.</span><span class="sxs-lookup"><span data-stu-id="e41e0-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="e41e0-135">Udelade flettede felter</span><span class="sxs-lookup"><span data-stu-id="e41e0-135">Exclude merged fields</span></span>

<span data-ttu-id="e41e0-136">Udelad en attribut fra den samlede kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="e41e0-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="e41e0-137">Hvis feltet bruges i andre processer, f.eks. i et segment, skal du fjerne det fra disse processer, før det udelades i kundeprofilen.</span><span class="sxs-lookup"><span data-stu-id="e41e0-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="e41e0-138">Vælg det flettede felt.</span><span class="sxs-lookup"><span data-stu-id="e41e0-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="e41e0-139">Vælg **Vis flere**, og vælg **Udelad**.</span><span class="sxs-lookup"><span data-stu-id="e41e0-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="e41e0-140">Bekræft udeladelsen.</span><span class="sxs-lookup"><span data-stu-id="e41e0-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="e41e0-141">Vælg **Gem** og **Kør** for at behandle ændringerne.</span><span class="sxs-lookup"><span data-stu-id="e41e0-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="e41e0-142">Vælg **Udeladte felter** på siden **Flet** for at se listen over alle udeladte felter.</span><span class="sxs-lookup"><span data-stu-id="e41e0-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="e41e0-143">Med denne rude kan du tilføje udeladte felter igen.</span><span class="sxs-lookup"><span data-stu-id="e41e0-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="e41e0-144">Kombinere felter manuelt</span><span class="sxs-lookup"><span data-stu-id="e41e0-144">Manually combine fields</span></span>

<span data-ttu-id="e41e0-145">Angiv en flettet attribut manuelt.</span><span class="sxs-lookup"><span data-stu-id="e41e0-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="e41e0-146">Vælg **Kombiner felter** på siden **Flet**.</span><span class="sxs-lookup"><span data-stu-id="e41e0-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="e41e0-147">Angiv et **Navn** og et **Navn på outputfelt**.</span><span class="sxs-lookup"><span data-stu-id="e41e0-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="e41e0-148">Vælg et felt, der skal tilføjes.</span><span class="sxs-lookup"><span data-stu-id="e41e0-148">Choose a field to add.</span></span> <span data-ttu-id="e41e0-149">Vælg **Tilføj felter** for at kombinere flere felter.</span><span class="sxs-lookup"><span data-stu-id="e41e0-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="e41e0-150">Bekræft udeladelsen.</span><span class="sxs-lookup"><span data-stu-id="e41e0-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="e41e0-151">Vælg **Gem** og **Kør** for at behandle ændringerne.</span><span class="sxs-lookup"><span data-stu-id="e41e0-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="e41e0-152">Ændre rækkefølgen for felter</span><span class="sxs-lookup"><span data-stu-id="e41e0-152">Change the order of fields</span></span>

<span data-ttu-id="e41e0-153">Nogle objekter indeholder flere detaljer end andre.</span><span class="sxs-lookup"><span data-stu-id="e41e0-153">Some entities contain more details than others.</span></span> <span data-ttu-id="e41e0-154">Hvis et objekt indeholder de nyeste data om et felt, kan du prioritere det frem for andre objekter, når du fletter værdier.</span><span class="sxs-lookup"><span data-stu-id="e41e0-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="e41e0-155">Vælg det flettede felt.</span><span class="sxs-lookup"><span data-stu-id="e41e0-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="e41e0-156">Vælg **Vis flere**, og vælg **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="e41e0-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="e41e0-157">Vælg **Flyt op/ned** i ruden **Kombiner felter** for at angive rækkefølgen, eller træk og slip dem til den ønskede placering.</span><span class="sxs-lookup"><span data-stu-id="e41e0-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="e41e0-158">Bekræft ændringen.</span><span class="sxs-lookup"><span data-stu-id="e41e0-158">Confirm the change.</span></span>

1. <span data-ttu-id="e41e0-159">Vælg **Gem** og **Kør** for at behandle ændringerne.</span><span class="sxs-lookup"><span data-stu-id="e41e0-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="e41e0-160">Køre fletningen</span><span class="sxs-lookup"><span data-stu-id="e41e0-160">Run your merge</span></span>

<span data-ttu-id="e41e0-161">Uanset om du fletter attributter manuelt eller lader systemet flette dem, kan du altid køre fletningen.</span><span class="sxs-lookup"><span data-stu-id="e41e0-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="e41e0-162">Vælg **Kør** på siden **Flet** for at starte processen.</span><span class="sxs-lookup"><span data-stu-id="e41e0-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e41e0-163">![Gemme og køre datafletning](media/configure-data-merge-save-run.png "Gemme og køre datafletning")</span><span class="sxs-lookup"><span data-stu-id="e41e0-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="e41e0-164">Vælg **Kør kun fletning**, hvis du kun vil se outputtet afspejlet i det samlede kundeobjekt.</span><span class="sxs-lookup"><span data-stu-id="e41e0-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="e41e0-165">Downstream-processer opdateres som [defineret i opdateringsplanen](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e41e0-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="e41e0-166">Vælg **Kør flettede og downstream-processer** for at opdatere systemet med ændringerne.</span><span class="sxs-lookup"><span data-stu-id="e41e0-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="e41e0-167">Alle processer, herunder forbedringer, segmenter og målinger, køres automatisk igen.</span><span class="sxs-lookup"><span data-stu-id="e41e0-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="e41e0-168">Når alle downstream-processer er fuldført, afspejler kundeprofilerne eventuelle ændringer, du har foretaget.</span><span class="sxs-lookup"><span data-stu-id="e41e0-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="e41e0-169">Hvis du vil foretage flere ændringer og køre trinnet igen, kan du annullere en igangværende fletning.</span><span class="sxs-lookup"><span data-stu-id="e41e0-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="e41e0-170">Vælg **Opdaterer...**, og vælg **Annuller job** i den siderude, der vises.</span><span class="sxs-lookup"><span data-stu-id="e41e0-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="e41e0-171">Opgaver og processer indeholder [seks typer status](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="e41e0-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e41e0-172">De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e41e0-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e41e0-173">Du kan vælge status for en proces for at se statusdetaljer for hele jobbet.</span><span class="sxs-lookup"><span data-stu-id="e41e0-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e41e0-174">Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.</span><span class="sxs-lookup"><span data-stu-id="e41e0-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="e41e0-175">Næste trin</span><span class="sxs-lookup"><span data-stu-id="e41e0-175">Next Step</span></span>

<span data-ttu-id="e41e0-176">Konfigurer [aktiviteter](activities.md), [forbedring](enrichment-hub.md) eller [relationer](relationships.md) for at få mere indsigt i dine kunder.</span><span class="sxs-lookup"><span data-stu-id="e41e0-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="e41e0-177">Hvis du allerede har konfigureret aktiviteter, forbedringer eller segmenter, behandles de automatisk til at bruge de nyeste kundedata.</span><span class="sxs-lookup"><span data-stu-id="e41e0-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
