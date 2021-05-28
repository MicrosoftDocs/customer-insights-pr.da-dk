---
title: Foreslåede segmenter baseret på aktivitet.
description: Lad maskinel indlæring hjælpe dig med at finde nye interessante segmenter baseret på kundeaktivitet.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034061"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="a9f5b-103">Foreslåede segmenter baseret på aktivitetsdata (forhåndsversion).</span><span class="sxs-lookup"><span data-stu-id="a9f5b-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="a9f5b-104">Opdag interessante segmenter af kunder, der er baseret på kundeaktivitetsdata, som er indtaget i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="a9f5b-105">Eksempler på aktivitetsdata er transaktioner, varighed af supportopkald, indkøb eller returvarer.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="a9f5b-106">For at foreslå segmenter analyseres aktivitetsdata for nyhed, hyppighed og pengeværdi (eller varighed).</span><span class="sxs-lookup"><span data-stu-id="a9f5b-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="a9f5b-107">Du kan også oprette [foreslåede segmenter for at forbedre målingen eller få en bedre forståelse af, hvad der påvirker en attribut](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="a9f5b-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Fanen Foreslåede segmenter, der viser segmentforslag til aktivitetsbaserede og attributbaserede segmenter.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="a9f5b-109">Kategorisere kunder efter aktivitet</span><span class="sxs-lookup"><span data-stu-id="a9f5b-109">Categorize customers by activity</span></span>

<span data-ttu-id="a9f5b-110">Med [aktivitetsdata](activities.md) tilgængelige i Customer Insights kan vi generere forslag, der repræsenterer kundegrupper:</span><span class="sxs-lookup"><span data-stu-id="a9f5b-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="a9f5b-111">mest aktive kunder</span><span class="sxs-lookup"><span data-stu-id="a9f5b-111">most active customers</span></span> 
- <span data-ttu-id="a9f5b-112">kunder, der har foretaget de fleste køb</span><span class="sxs-lookup"><span data-stu-id="a9f5b-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="a9f5b-113">kunder, der genererede den største omsætning</span><span class="sxs-lookup"><span data-stu-id="a9f5b-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="a9f5b-114">kunder, der ikke har været aktive for nylig</span><span class="sxs-lookup"><span data-stu-id="a9f5b-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="a9f5b-115">kunder, der ofte interagerer med din virksomhed</span><span class="sxs-lookup"><span data-stu-id="a9f5b-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="a9f5b-116">Hvis du har en detailvirksomhed, kan du finde ud af, hvilke kunder der genererer den største omsætning, og belønne dem med en værdikupon.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="a9f5b-117">Du kan også identificere lejlighedsvise kunder og tilbyde dem at tilmelde sig et belønningsprogram, så de besøger din virksomhed oftere.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="a9f5b-118">Hvis du arbejder inden for sundhedssektoren med folkesundhed, og dit mål er at minimere udgifterne for de enkelte patienter.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="a9f5b-119">Det kan du gøre ved at reducere antallet af tilbagevendende besøg ved at yde den bedst mulige behandling på så få besøg som muligt.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="a9f5b-120">I dette tilfælde er dit mål at holde besøgshyppigheden lav og minimere tilbagevendende omkostninger for patienterne.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="a9f5b-121">Du kan også identificere de segmenter af patienter, der ofte har aftaler, og høje tilbagevendende omkostninger og analysere disse sager for at forbedre behandlingen for den enkelte person.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="a9f5b-122">Påkrævede data</span><span class="sxs-lookup"><span data-stu-id="a9f5b-122">Required data</span></span>

<span data-ttu-id="a9f5b-123">Forslag oprettes på baggrund af de valgte inputdata.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="a9f5b-124">Kundeprofiler: Alle kunder eller medlemmer af et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="a9f5b-125">Tidsperiode: Sidste måned, sidste år eller en brugerdefineret tidsramme.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="a9f5b-126">Aktivitetstype: køb, detailtransaktioner, onlinetransaktioner, kundesupportsager, abonnementer osv.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="a9f5b-127">Objekt i Customer Insights, der indeholder aktivitetsdataene: Objektet UnifiedActivity eller objektet for en bestemt aktivitet.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="a9f5b-128">Dimensioner, der skal inkluderes: seneste dato, hyppighed eller pengebeløb, afhængigt af virksomhedens behov.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="a9f5b-129">Generér foreslåede målgrupper</span><span class="sxs-lookup"><span data-stu-id="a9f5b-129">Generate suggested segments</span></span>

1. <span data-ttu-id="a9f5b-130">Gå til **Segmenter**</span><span class="sxs-lookup"><span data-stu-id="a9f5b-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="a9f5b-131">Vælg fanen **Forslag (prøveversion)**.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="a9f5b-132">Vælg **Søg efter nye forslag**, og vælg **Se eller forudse kundeadfærd**.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="a9f5b-133">Vælg **Start** for at køre den styrede oplevelse.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Første trin i guiden Konfiguration for et foreslået segment baseret på aktivitet.":::

1. <span data-ttu-id="a9f5b-135">Angiv de nødvendige inputdata, og vælg **Næste** for at fortsætte.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="a9f5b-136">Vælg kunder: Medtag alle kunder eller et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="a9f5b-137">Vælg aktivitet: Vælg aktivitetstypen og de objekter, der beskriver aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="a9f5b-138">Præferencer: Angiv den tidsperiode, der skal overvejes, faktorerne til forslag, og tilknyt attributterne.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="a9f5b-139">Gennemse dit input, og vælg **Kør** for at køre modellen og oprette forslag.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="a9f5b-140">Afhængigt af antallet af kundeprofiler og valgte aktiviteter kan det tage et par minutter at fuldføre.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="a9f5b-141">Når du har genereret forslagene, kan du filtrere dem efter den dimension eller værdi, du er mest interesseret i.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="a9f5b-142">Vise oplysninger om foreslået segment</span><span class="sxs-lookup"><span data-stu-id="a9f5b-142">View details of a suggested segment</span></span>

<span data-ttu-id="a9f5b-143">Når forslagene er genereret, vises de i afsnittet **Aktivitetsbaserede forslag**, som vises i **Segmenter** > **Forslag (forhåndsversion)**.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Udvidet siderude, der viser detaljerede data for et foreslået segment.":::

<span data-ttu-id="a9f5b-145">Vælg **Se forslag** på et foreslået segment for at få vist detaljerne for det pågældende segment.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="a9f5b-146">Sideruden indeholder detaljer som omfanget af de enkelte dimensioner i sammenligning med målgruppen.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="a9f5b-147">Der fremhæves også antallet af potentielle medlemmer i segmentet og den tilsvarende procentdel af de samlede kunder.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="a9f5b-148">Hvis du vil bevare forslag som et segment, skal du vælge **Opret segment**.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="a9f5b-149">Gemme et forslag som et segment</span><span class="sxs-lookup"><span data-stu-id="a9f5b-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="a9f5b-150">Gå til **Segmenter** > **Forslag (prøveversion)**.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="a9f5b-151">Vælg det segment, du vil gemme.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="a9f5b-152">Vælg **Opret segment** i sideruden.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="a9f5b-153">Når du har gemt segmentet, vises det på listen over segmenter under fanen **Alle segmenter**. Det kan nu [opdateres eller slettes på samme måde som et hvilket som helst andet segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a9f5b-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="a9f5b-154">Du kan ikke redigere detaljer om segmentet.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-154">You can't edit the segment details.</span></span> <span data-ttu-id="a9f5b-155">Du kan dog ændre inputkriterierne for forslagene og oprette forskellige forslag.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="a9f5b-156">Opdatere eller redigere et sæt forslag</span><span class="sxs-lookup"><span data-stu-id="a9f5b-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="a9f5b-157">Gå til **Segmenter** > **Forslag (forhåndsversion)**, og søg efter segmentet i sektionen **Aktivitetsbaserede forslag**.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="a9f5b-158">Vælg **Opdater forslag** for at opdatere forslagene, mens du bevarer konfigurerede attributter.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="a9f5b-159">Du kan også vælge **Rediger forslag** for at ændre de konfigurerede attributter.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="a9f5b-160">Systemet kører processen igen, opretter segmentforslag baseret på de nyeste data og erstatter de aktuelle forslag.</span><span class="sxs-lookup"><span data-stu-id="a9f5b-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
