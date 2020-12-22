---
title: Find lignende kunder med AI
description: Find lignende kundesegmenter med kunstig intelligens.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405440"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="b653b-103">Lignende kunder (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="b653b-103">Similar Customers (preview)</span></span>

<span data-ttu-id="b653b-104">Denne funktion giver dig mulighed for at finde lignende kunder i kundebasen ved hjælp af kunstig intelligens.</span><span class="sxs-lookup"><span data-stu-id="b653b-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="b653b-105">Du skal have oprettet mindst ét segment for at bruge denne funktion.</span><span class="sxs-lookup"><span data-stu-id="b653b-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="b653b-106">Hvis du udvider kriterierne for et eksisterende segment, får du hjælp til at finde de kunder, der ligner dette segment.</span><span class="sxs-lookup"><span data-stu-id="b653b-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="b653b-107">*Find lignende kunder* bruger automatiserede metoder til at evaluere data og foretage forudsigelser på baggrund af disse data, og de kan derfor bruges som en metode til profilering, som dette udtryk er defineret i generel forordning om databeskyttelse ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="b653b-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="b653b-108">Kundens brug af denne funktion til behandling af data kan være underlagt GDPR eller andre love eller bestemmelser.</span><span class="sxs-lookup"><span data-stu-id="b653b-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="b653b-109">Du er ansvarlig for at sikre, at brugen af Dynamics 365 Customer Insights, herunder forudsigelser, overholder alle gældende love og bestemmelser, herunder lovgivning vedrørende beskyttelse af personlige oplysninger, personlige data, biometriske data, databeskyttelse og fortrolighed i kommunikationen.</span><span class="sxs-lookup"><span data-stu-id="b653b-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="b653b-110">Finde lignende kunder</span><span class="sxs-lookup"><span data-stu-id="b653b-110">Finding similar customers</span></span>

1. <span data-ttu-id="b653b-111">Gå til **Segmenter**, og vælg det segment, du vil basere det nye segment på, i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="b653b-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="b653b-112">Det er *kildesegmentet*.</span><span class="sxs-lookup"><span data-stu-id="b653b-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="b653b-113">Vælg **Find lignende kunder** på handlingslinjen .</span><span class="sxs-lookup"><span data-stu-id="b653b-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="b653b-114">Gennemgå det foreslåede navn på det nye segment, og rediger det, hvis det er nødvendigt.</span><span class="sxs-lookup"><span data-stu-id="b653b-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="b653b-115">Gennemgå de felter, der definerer det nye segment.</span><span class="sxs-lookup"><span data-stu-id="b653b-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="b653b-116">I disse felter defineres det udgangspunkt, som systemet vil bruge til at finde lignende kunder i et kildesegment.</span><span class="sxs-lookup"><span data-stu-id="b653b-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="b653b-117">Systemet vil som standard vælge anbefalede felter.</span><span class="sxs-lookup"><span data-stu-id="b653b-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="b653b-118">Felter, der kan reducere modellens ydeevne drastisk, udelukkes automatisk:</span><span class="sxs-lookup"><span data-stu-id="b653b-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="b653b-119">Felter med følgende datatyper: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="b653b-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="b653b-120">Felter med en kardinalitet (antallet af elementer i et felt) på mindre end 2 eller mere end 30</span><span class="sxs-lookup"><span data-stu-id="b653b-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="b653b-121">Vælg, om du vil medtage **Alle kunder** eller kun kunder i et **Bestemt eksisterende segment** i det nye segment.</span><span class="sxs-lookup"><span data-stu-id="b653b-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="b653b-122">Udeluk kunder i kildesegmentet ved at markere afkrydsningsfeltet **Udelad alle i kildesegment**.</span><span class="sxs-lookup"><span data-stu-id="b653b-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="b653b-123">Systemet foreslår som standard kun 20 % af målgruppens størrelse i outputtet.</span><span class="sxs-lookup"><span data-stu-id="b653b-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="b653b-124">Rediger denne tærskel efter behov.</span><span class="sxs-lookup"><span data-stu-id="b653b-124">Edit this threshold as needed.</span></span> <span data-ttu-id="b653b-125">Hvis tærskelværdien øges, reduceres præcisionen.</span><span class="sxs-lookup"><span data-stu-id="b653b-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="b653b-126">Vælg **Kør** nederst på siden for at starte en binær klassificeringsopgave (en metode til maskinel indlæring), som analyserer datasættet.</span><span class="sxs-lookup"><span data-stu-id="b653b-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="b653b-127">Se det lignende segment</span><span class="sxs-lookup"><span data-stu-id="b653b-127">View the similar segment</span></span>

<span data-ttu-id="b653b-128">Når du har behandlet det lignende segment, vil du finde det nye segment på siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="b653b-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b653b-129">![Lignende kundesegment](media/expanded-segment.png "Lignende kundesegment")</span><span class="sxs-lookup"><span data-stu-id="b653b-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="b653b-130">Vælg **Vis** på handlingslinjen for at åbne segmentoplysningerne.</span><span class="sxs-lookup"><span data-stu-id="b653b-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="b653b-131">Denne visning indeholder oplysninger om resultatfordelingen på tværs af [lighedsscorer](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="b653b-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="b653b-132">Du kan også finde værdierne for lighedsscore i **Eksempel på segmentmedlemmer**.</span><span class="sxs-lookup"><span data-stu-id="b653b-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="b653b-133">Bruge output af et lignende segment</span><span class="sxs-lookup"><span data-stu-id="b653b-133">Use the output of a similar segment</span></span>

<span data-ttu-id="b653b-134">Du kan [arbejde med outputtet af et lignende segment](segments.md) på samme måde som med andre segmenter.</span><span class="sxs-lookup"><span data-stu-id="b653b-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="b653b-135">Du kan f.eks. eksportere segmentet eller oprette en måling.</span><span class="sxs-lookup"><span data-stu-id="b653b-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="b653b-136">Opdatere og redigere et lignende segment</span><span class="sxs-lookup"><span data-stu-id="b653b-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="b653b-137">Hvis du vil opdatere et lignende segment, skal du vælge det på siden **Segmenter** og vælge **Opdater** på handlingslinjen.</span><span class="sxs-lookup"><span data-stu-id="b653b-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="b653b-138">Hvis du redigerer et lignende segment, behandles dataene igen.</span><span class="sxs-lookup"><span data-stu-id="b653b-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="b653b-139">Det tidligere oprettede segment opdateres med nye data.</span><span class="sxs-lookup"><span data-stu-id="b653b-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="b653b-140">Hvis du vil redigere et lignende segment, skal du vælge det på siden **Segmenter** og vælge **Rediger** på handlingslinjen.</span><span class="sxs-lookup"><span data-stu-id="b653b-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="b653b-141">Anvend ændringerne, og vælg **Kør** for at starte behandlingen.</span><span class="sxs-lookup"><span data-stu-id="b653b-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="b653b-142">Slette et lignende segment</span><span class="sxs-lookup"><span data-stu-id="b653b-142">Delete a similar segment</span></span>

<span data-ttu-id="b653b-143">Vælg segmentet på siden **Segmenter**, og vælg **Slet** på handlingslinjen.</span><span class="sxs-lookup"><span data-stu-id="b653b-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="b653b-144">Bekræft sletningen.</span><span class="sxs-lookup"><span data-stu-id="b653b-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="b653b-145">Om lighedsscore</span><span class="sxs-lookup"><span data-stu-id="b653b-145">About similarity scores</span></span>

<span data-ttu-id="b653b-146">Den binære klassificerings maskinelle indlæringsmodel tildeler kunderne en score i det lignende segment.</span><span class="sxs-lookup"><span data-stu-id="b653b-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="b653b-147">Scoren er baseret på lighed med kunderne i kildesegmentet.</span><span class="sxs-lookup"><span data-stu-id="b653b-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="b653b-148">Lighedsscore under 0,55 er kunder, som systemet klassificerer som *ligner ikke* kunder i kildesegmentet</span><span class="sxs-lookup"><span data-stu-id="b653b-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="b653b-149">Lighedsscorer mellem 0,55 og 0,7 klassificeres som *nogenlunde ens*</span><span class="sxs-lookup"><span data-stu-id="b653b-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="b653b-150">Lighedsscorer mellem 0,7 og 0,85 klassificeres som *lignende*</span><span class="sxs-lookup"><span data-stu-id="b653b-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="b653b-151">Lighedsscorer mellem 0,85 og 1 er kunder, som systemet klassificerer som *meget lignende*</span><span class="sxs-lookup"><span data-stu-id="b653b-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="b653b-152">Kunder med lighedsscorer på under 0,4 medtages ikke i modellens output.</span><span class="sxs-lookup"><span data-stu-id="b653b-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="b653b-153">Systemet betragter dem ikke som tilstrækkeligt lig med kildesegmentet.</span><span class="sxs-lookup"><span data-stu-id="b653b-153">The system doesn't consider them similar enough to the source segment.</span></span>
