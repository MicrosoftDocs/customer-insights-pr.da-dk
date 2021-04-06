---
title: Udfyld delvise data ved hjælp af forudsigelser
description: Brug af forudsigelser til at udfylde ufuldstændige kundedata.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595894"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="3befc-103">Fuldføre delvise data med forudsigelser</span><span class="sxs-lookup"><span data-stu-id="3befc-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3befc-104">Med forudsigelser kan du nemt oprette forventede værdier, der kan forbedre forståelsen af en kunde.</span><span class="sxs-lookup"><span data-stu-id="3befc-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="3befc-105">På siden **Intelligens** > **Forudsigelser** kan du vælge **Mine forudsigelser** for at se forudsigelser, som du har konfigureret i andre dele af målgruppen Insights, og give dig mulighed for at tilpasse dem yderligere.</span><span class="sxs-lookup"><span data-stu-id="3befc-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="3befc-106">Du kan ikke bruge denne funktion, hvis dit miljø bruger Azure Data Lake Gen 2-lager.</span><span class="sxs-lookup"><span data-stu-id="3befc-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="3befc-107">Funktionen til forudsigelser bruger automatiserede metoder til at evaluere data og foretage forudsigelser på baggrund af disse data, og det er derfor muligt at bruge denne funktion som profileringsmetode, som dette udtryk er defineret i henhold til generel forordning om databeskyttelse ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="3befc-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="3befc-108">Kundens brug af denne funktion til behandling af data kan være underlagt GDPR eller andre love eller bestemmelser.</span><span class="sxs-lookup"><span data-stu-id="3befc-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="3befc-109">Du er ansvarlig for at sikre, at brugen af Dynamics 365 Customer Insights, herunder forudsigelser, overholder alle gældende love og bestemmelser, herunder lovgivning vedrørende beskyttelse af personlige oplysninger, personlige data, biometriske data, databeskyttelse og fortrolighed i kommunikationen.</span><span class="sxs-lookup"><span data-stu-id="3befc-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3befc-110">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="3befc-110">Prerequisites</span></span>

<span data-ttu-id="3befc-111">Før din organisation kan bruge funktionen til forudsigelser, skal følgende forudsætninger være opfyldt:</span><span class="sxs-lookup"><span data-stu-id="3befc-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="3befc-112">Din organisation har en forekomst [opsat i Common Data Service](/ai-builder/build-model#prerequisites) og er i samme organisation som Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3befc-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="3befc-113">Dit miljø er knyttet til Common Data Service-forekomsten.</span><span class="sxs-lookup"><span data-stu-id="3befc-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="3befc-114">Hvis du [opretter det første miljø](manage-environments.md), skal du konfigurere det i dialogboksen **Opret et miljø** og vælge **Avanceret**.</span><span class="sxs-lookup"><span data-stu-id="3befc-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="3befc-115">Hvis du allerede har oprettet et miljø, skal du gå til indstillingerne og vælge **Avanceret**.</span><span class="sxs-lookup"><span data-stu-id="3befc-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="3befc-116">I begge tilfælde skal du i sektionen **Brug forudsigelser** angive den Common Data Service-forekomst for den URL-adresse, du vil tilknytte miljøet til.</span><span class="sxs-lookup"><span data-stu-id="3befc-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="3befc-117">Opret en forudsigelse i kundeobjektet</span><span class="sxs-lookup"><span data-stu-id="3befc-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="3befc-118">Gå til **Data** > **Objekter** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="3befc-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="3befc-119">Vælg objektet **Kunde**.</span><span class="sxs-lookup"><span data-stu-id="3befc-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="3befc-120">Vælg fanen **Felter** i objektet **Kunde: CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="3befc-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="3befc-121">Find det attributnavn, du vil forudsige værdier for, og vælg derefter ikonet **Oversigt** i kolonnen **Oversigt**.</span><span class="sxs-lookup"><span data-stu-id="3befc-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3befc-122">![Ikonet Oversigt](media/intelligence-overviewicon.png "Ikonet Oversigt")</span><span class="sxs-lookup"><span data-stu-id="3befc-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="3befc-123">Hvis der er et stort antal manglende værdier for attributten, skal du vælge **Forudsige manglende værdier** for at fortsætte med din forudsigelse.</span><span class="sxs-lookup"><span data-stu-id="3befc-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3befc-124">![Oversigtsstatus med knappen Forudsige manglende værdier vist](media/intelligence-overviewpredictmissingvalues.png "Oversigtsstatus med knappen Forudsige manglende værdier vist")</span><span class="sxs-lookup"><span data-stu-id="3befc-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="3befc-125">Angiv et **Vist navn** og et **Navn på outputobjekt** for resultaterne af forudsigelsen.</span><span class="sxs-lookup"><span data-stu-id="3befc-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="3befc-126">En liste med indstillinger, der er udfyldt på forhånd, viser, hvor du kan knytte værdierne til en forudsagt kategori.</span><span class="sxs-lookup"><span data-stu-id="3befc-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="3befc-127">I dette tilfælde er de eneste kategoriindstillinger 0 eller 1, da de knyttes til den sande/falske eller binære karakter for forudsigelse.</span><span class="sxs-lookup"><span data-stu-id="3befc-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="3befc-128">I kolonnen Kategori skal du tilknytte de feltværdier, du vil have klassificeret som "0" i den endelige forudsigelse, til "0", og de elementer, du vil klassificere som "1" i den endelige forudsigelse, til "1".</span><span class="sxs-lookup"><span data-stu-id="3befc-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3befc-129">![Eksempel, der viser tilknyttede feltværdier for kategorier](media/intelligence-categorymapping.png "Eksempel, der viser tilknyttede feltværdier for kategorier")</span><span class="sxs-lookup"><span data-stu-id="3befc-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="3befc-130">Vælg **Udført**,så forudsigelsen vil blive behandlet.</span><span class="sxs-lookup"><span data-stu-id="3befc-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="3befc-131">Behandlingen vil tage et stykke tid, afhængigt af datastørrelsen og kompleksiteten af dataene.</span><span class="sxs-lookup"><span data-stu-id="3befc-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="3befc-132">Resultaterne vil være tilgængelige i et nyt objekt, der er baseret på det **Navn på outputobjekt** for forudsigelsen, du har oprettet.</span><span class="sxs-lookup"><span data-stu-id="3befc-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="3befc-133">Oprette en forudsigelse under oprettelse af et segment</span><span class="sxs-lookup"><span data-stu-id="3befc-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="3befc-134">Det er også muligt at forudsige manglende værdier for en bestemt attribut efter eget valg, når der oprettes et segment.</span><span class="sxs-lookup"><span data-stu-id="3befc-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="3befc-135">Specielt, når du hurtigt opretter et segment baseret på enten dit samlede kundeobjekt eller Customer_Measure-objektet.</span><span class="sxs-lookup"><span data-stu-id="3befc-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="3befc-136">Som en del af dette flow vælger du en bestemt attribut til at basere dit segment på, f.eks. kundetilfredshed eller købsbeløb.</span><span class="sxs-lookup"><span data-stu-id="3befc-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="3befc-137">Når segmentet oprettes, foreslår systemet en metode til at forudsige manglende værdier for denne attribut.</span><span class="sxs-lookup"><span data-stu-id="3befc-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="3befc-138">Gå til **Segmenter**, og vælg feltet **Profiler** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="3befc-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="3befc-139">Vælg et **Felt**, som du vil oprette et segment på, og vælg en **Operator**, og vælg derefter **Gennemse**.</span><span class="sxs-lookup"><span data-stu-id="3befc-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="3befc-140">Angiv et **Navn** og et **Vist navn** til segmentet.</span><span class="sxs-lookup"><span data-stu-id="3befc-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="3befc-141">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="3befc-141">Select **Save**.</span></span>

5. <span data-ttu-id="3befc-142">Hvis det segment, du har oprettet, har ufuldstændige data i kildefeltet, kan du vælge at forudsige de manglende værdier.</span><span class="sxs-lookup"><span data-stu-id="3befc-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3befc-143">![Knappen Forudsigelse](media/segments-predictoption.png "Knappen Forudsigelse")</span><span class="sxs-lookup"><span data-stu-id="3befc-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="3befc-144">Angiv et **Vist navn** og et **Navn på outputobjekt** for resultaterne af forudsigelsen.</span><span class="sxs-lookup"><span data-stu-id="3befc-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="3befc-145">Vælg **Udført**.</span><span class="sxs-lookup"><span data-stu-id="3befc-145">Select **Done**.</span></span> <span data-ttu-id="3befc-146">Forudsigelsen oprettes hurtigt i et nyt objekt med det navn, du har angivet som **Navn på outputobjekt**.</span><span class="sxs-lookup"><span data-stu-id="3befc-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="3befc-147">Se en forudsigelse</span><span class="sxs-lookup"><span data-stu-id="3befc-147">View a prediction</span></span>

1. <span data-ttu-id="3befc-148">Gå til **Intelligens** > **Forudsigelser** > **Mine forudsigelser** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="3befc-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3befc-149">Vælg den forudsigelse, du vil gennemse.</span><span class="sxs-lookup"><span data-stu-id="3befc-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="3befc-150">Vælg ellipsen i kolonnen **Handlinger**, og vælg **Vis**.</span><span class="sxs-lookup"><span data-stu-id="3befc-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="3befc-151">Der vises en række datapunkter i visningen af din forudsigelse.</span><span class="sxs-lookup"><span data-stu-id="3befc-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3befc-152">![Siden Forudsigelser](media/intelligence-predictionsviewpage.png "Siden Forudsigelser")</span><span class="sxs-lookup"><span data-stu-id="3befc-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="3befc-153">**Forudsigelige værdier** viser den tilknytning, du har oprettet under tilknytningsfasen af feltværdien til kategori.</span><span class="sxs-lookup"><span data-stu-id="3befc-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="3befc-154">Det er de værdier i dit datasæt, der er knyttet til en bestemt kategori.</span><span class="sxs-lookup"><span data-stu-id="3befc-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="3befc-155">-**Bedste indflydelse** er de faktorer i dit datasæt, som mest sandsynligt vil have indflydelse på forudsigelsens konfidens til, at din feltværdi er knyttet til en bestemt kategori.</span><span class="sxs-lookup"><span data-stu-id="3befc-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="3befc-156">**Ydeevne** angiver, hvordan forudsigelser udføres.</span><span class="sxs-lookup"><span data-stu-id="3befc-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="3befc-157">Du kan få mere at vide ved at vælge linket.</span><span class="sxs-lookup"><span data-stu-id="3befc-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="3befc-158">**Se eksempel** viser eksempler på outputdatasæt fra forudsigelsen og sandsynligheden, eller vores konfidens, for den forudsagte værdi, hvor 0 er usikker, og 1 er sikker.</span><span class="sxs-lookup"><span data-stu-id="3befc-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="3befc-159">Opdatere en forudsigelse</span><span class="sxs-lookup"><span data-stu-id="3befc-159">Update a prediction</span></span>

1. <span data-ttu-id="3befc-160">Gå til **Intelligens** > **Forudsigelser** > **Mine forudsigelser** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="3befc-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3befc-161">Vælg den forudsigelse, du vil opdatere, og vælg ikonet **Opdater**.</span><span class="sxs-lookup"><span data-stu-id="3befc-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="3befc-162">Forudsigelsen vil blive planlagt til behandling.</span><span class="sxs-lookup"><span data-stu-id="3befc-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="3befc-163">Du kan se, hvornår den sidst blev opdateret, i kolonnen **Opdateret** på siden **Forudsigelser**.</span><span class="sxs-lookup"><span data-stu-id="3befc-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="3befc-164">Redigere en forudsigelse</span><span class="sxs-lookup"><span data-stu-id="3befc-164">Edit a prediction</span></span>

<span data-ttu-id="3befc-165">Når du har oprettet en forudsigelse, kan du tilpasse modellen i AI Builder for at øge effektiviteten for din model.</span><span class="sxs-lookup"><span data-stu-id="3befc-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="3befc-166">Gå til **Intelligens** > **Forudsigelser** > **Mine forudsigelser** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="3befc-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3befc-167">Vælg den forudsigelse, som du vil redigere.</span><span class="sxs-lookup"><span data-stu-id="3befc-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="3befc-168">Vælg ellipsen i kolonnen **Handlinger**, og vælg **Vis**.</span><span class="sxs-lookup"><span data-stu-id="3befc-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="3befc-169">Vælg **Tilpas i AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="3befc-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="3befc-170">Opdater din model i AI Builder.</span><span class="sxs-lookup"><span data-stu-id="3befc-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="3befc-171">[Få mere at vide om administration af modeller i AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="3befc-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="3befc-172">Den næste kørsel af forudsigelsen bruger den opdaterede model, du har oprettet.</span><span class="sxs-lookup"><span data-stu-id="3befc-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="3befc-173">Nye modeller, der er oprettet i AI Builder, vises ikke i målgruppen Insights, medmindre modellen er oprettet ud fra de oplevelser, der er nævnt ovenfor.</span><span class="sxs-lookup"><span data-stu-id="3befc-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="3befc-174">Fjerne en forudsigelse</span><span class="sxs-lookup"><span data-stu-id="3befc-174">Remove a prediction</span></span>

1. <span data-ttu-id="3befc-175">Gå til **Intelligens** > **Forudsigelser** > **Mine forudsigelser** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="3befc-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3befc-176">Vælg den forudsigelse, du vil slette.</span><span class="sxs-lookup"><span data-stu-id="3befc-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="3befc-177">Vælg ellipsen i kolonnen **Handlinger**, og vælg **Slet**.</span><span class="sxs-lookup"><span data-stu-id="3befc-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="3befc-178">Bekræft sletningen.</span><span class="sxs-lookup"><span data-stu-id="3befc-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="3befc-179">Fejlfinding</span><span class="sxs-lookup"><span data-stu-id="3befc-179">Troubleshooting</span></span>

<span data-ttu-id="3befc-180">Hvis du ikke kan fuldføre Common Data Service-tilknytningsprocessen på grund af en fejl, kan du prøve at fuldføre processen manuelt.</span><span class="sxs-lookup"><span data-stu-id="3befc-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="3befc-181">Der er to kendte problemer, der kan opstå i tilknytningsprocessen:</span><span class="sxs-lookup"><span data-stu-id="3befc-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="3befc-182">Løsningen til tilføjelsesprogrammet Customer Card er ikke installeret.</span><span class="sxs-lookup"><span data-stu-id="3befc-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="3befc-183">Udfør instruktionerne for at [installere og konfigurere løsningen](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="3befc-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="3befc-184">App-tilladelser tildeles ikke.</span><span class="sxs-lookup"><span data-stu-id="3befc-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="3befc-185">Gå til [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3befc-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="3befc-186">Vælg **Miljøer**.</span><span class="sxs-lookup"><span data-stu-id="3befc-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="3befc-187">Vælg ellipsen ud for det miljø, du vil føje til tilladelsen til, og vælg **Indstillinger**.</span><span class="sxs-lookup"><span data-stu-id="3befc-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="3befc-188">Udvid **Brugere + tilladelser**, og vælg **Brugere**.</span><span class="sxs-lookup"><span data-stu-id="3befc-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="3befc-189">Vælg **+ Ny**, og vælg **Bruger**.</span><span class="sxs-lookup"><span data-stu-id="3befc-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="3befc-190">Vælg **Programbruger**, hvis indstillingen ikke allerede er valgt, og angiv følgende oplysninger:</span><span class="sxs-lookup"><span data-stu-id="3befc-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="3befc-191">**Brugernavn:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3befc-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="3befc-192">**Program-id:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="3befc-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="3befc-193">**Fornavn:** Kunde</span><span class="sxs-lookup"><span data-stu-id="3befc-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="3befc-194">**Efternavn:** Insights</span><span class="sxs-lookup"><span data-stu-id="3befc-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="3befc-195">**Primær mail:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3befc-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="3befc-196">Vælg **Gem og luk**.</span><span class="sxs-lookup"><span data-stu-id="3befc-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="3befc-197">Vælg den bruger, du lige har oprettet.</span><span class="sxs-lookup"><span data-stu-id="3befc-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="3befc-198">Vælg **Administrer roller** på menulinjen foroven.</span><span class="sxs-lookup"><span data-stu-id="3befc-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="3befc-199">Vælg **Systemadministrator**, og vælg derefter **OK**.</span><span class="sxs-lookup"><span data-stu-id="3befc-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]