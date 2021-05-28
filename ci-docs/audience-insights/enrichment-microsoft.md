---
title: Forbedre kundeprofiler med data fra Microsoft
description: Brug beskyttede data fra Microsoft til at forbedre dine kundedata med tilhørsforhold til varemærker og interesse.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064884"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="ab93f-103">Forbedre kundeprofiler med brand- og interessetilhørsforhold (eksempel)</span><span class="sxs-lookup"><span data-stu-id="ab93f-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="ab93f-104">Brug beskyttede data fra Microsoft til at forbedre dine kundedata med tilhørsforhold til varemærker og interesse.</span><span class="sxs-lookup"><span data-stu-id="ab93f-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="ab93f-105">Disse tilhørsforhold bestemmes på baggrund af data fra personer med lignende demografi i forhold til dine kunder.</span><span class="sxs-lookup"><span data-stu-id="ab93f-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="ab93f-106">Disse oplysninger hjælper dig med at få bedre indsigt i og segmentere dine kunder på baggrund af deres tilhørsforhold til specifikke mærker og interesser.</span><span class="sxs-lookup"><span data-stu-id="ab93f-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="ab93f-107">I målgruppeindsigt skal du gå til **Data** > **Forbedring** for at [konfigurere og få vist forbedring](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="ab93f-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="ab93f-108">Hvis du vil konfigurere forbedring af mærketilhørsforhold, skal du gå til fanen **Opdag** og vælge **Forbedr mine data** i feltet **Mærker**.</span><span class="sxs-lookup"><span data-stu-id="ab93f-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="ab93f-109">Hvis du vil konfigurere forbedring af interessetilhørsforhold, skal du gå til fanen **Opdag** og vælge **Forbedr mine data** i feltet **Interesser**.</span><span class="sxs-lookup"><span data-stu-id="ab93f-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ab93f-110">![Mærker og interesser-felter](media/BrandsInterest-tile-Hub.png "Mærker og interesser-felter")</span><span class="sxs-lookup"><span data-stu-id="ab93f-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="ab93f-111">Sådan afgør vi tilhørsforhold</span><span class="sxs-lookup"><span data-stu-id="ab93f-111">How we determine affinities</span></span>

<span data-ttu-id="ab93f-112">Vi bruger Microsofts onlinesøgningsdata til at finde tilhørsforhold til og interesser på tværs af forskellige demografiske segmenter (defineret efter alder, køn eller lokation).</span><span class="sxs-lookup"><span data-stu-id="ab93f-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="ab93f-113">Antal søgninger online for et brand eller en interesse bestemmer, hvor stærkt tilhørsforholdet til et demografisk segment er for det pågældende brand eller den pågældende interesse i forhold til andre segmenter.</span><span class="sxs-lookup"><span data-stu-id="ab93f-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="ab93f-114">Tilhørsniveau og point</span><span class="sxs-lookup"><span data-stu-id="ab93f-114">Affinity level and score</span></span>

<span data-ttu-id="ab93f-115">På alle forbedrede kundeprofiler leverer vi to relaterede værdier: tilhørsniveau og tilhørspoint.</span><span class="sxs-lookup"><span data-stu-id="ab93f-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="ab93f-116">Du kan bruge disse værdier til at bestemme, hvor stærk tilhørsforholdet er for profilens demografiske segment, for et mærke eller en interesse i forhold til andre demografiske segmenter.</span><span class="sxs-lookup"><span data-stu-id="ab93f-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="ab93f-117">*Tilhørsniveau* består af fire niveauer, og *tilhørspoint* beregnes på en skala på 100 point, der knyttes til tilhørsniveauer.</span><span class="sxs-lookup"><span data-stu-id="ab93f-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="ab93f-118">Tilhørsniveau</span><span class="sxs-lookup"><span data-stu-id="ab93f-118">Affinity level</span></span> |<span data-ttu-id="ab93f-119">Score for tilhørsforhold</span><span class="sxs-lookup"><span data-stu-id="ab93f-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="ab93f-120">Meget høj</span><span class="sxs-lookup"><span data-stu-id="ab93f-120">Very high</span></span>     | <span data-ttu-id="ab93f-121">85 - 100</span><span class="sxs-lookup"><span data-stu-id="ab93f-121">85-100</span></span>       |
|<span data-ttu-id="ab93f-122">Høj</span><span class="sxs-lookup"><span data-stu-id="ab93f-122">High</span></span>     | <span data-ttu-id="ab93f-123">70 - 84</span><span class="sxs-lookup"><span data-stu-id="ab93f-123">70-84</span></span>        |
|<span data-ttu-id="ab93f-124">Medium</span><span class="sxs-lookup"><span data-stu-id="ab93f-124">Medium</span></span>     | <span data-ttu-id="ab93f-125">35 - 69</span><span class="sxs-lookup"><span data-stu-id="ab93f-125">35-69</span></span>        |
|<span data-ttu-id="ab93f-126">Lav</span><span class="sxs-lookup"><span data-stu-id="ab93f-126">Low</span></span>     | <span data-ttu-id="ab93f-127">1 - 34</span><span class="sxs-lookup"><span data-stu-id="ab93f-127">1-34</span></span>        |

<span data-ttu-id="ab93f-128">Afhængigt af den granularitet, du vil måle tilhørsforholdet med, kan du enten bruge affinitetsniveau eller resultat.</span><span class="sxs-lookup"><span data-stu-id="ab93f-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="ab93f-129">Tilhørspoint giver dig mere præcis styring.</span><span class="sxs-lookup"><span data-stu-id="ab93f-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="ab93f-130">Understøttede lande/områder</span><span class="sxs-lookup"><span data-stu-id="ab93f-130">Supported countries/regions</span></span>

<span data-ttu-id="ab93f-131">I øjeblikket understøttes følgende lande-/områdeindstillinger: Australien, Canada (engelsk), Frankrig, Tyskland, Storbritannien og USA (engelsk).</span><span class="sxs-lookup"><span data-stu-id="ab93f-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="ab93f-132">Hvis du vil vælge et land, skal du åbne **Brandforbedring** eller **Interesseudvidelse** og vælge **Skift** ud for **Land/område**.</span><span class="sxs-lookup"><span data-stu-id="ab93f-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="ab93f-133">Vælg en indstilling i ruden **Indstillinger for land/område**, og vælg **Anvend**.</span><span class="sxs-lookup"><span data-stu-id="ab93f-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="ab93f-134">Implikationer i forbindelse med valg af land</span><span class="sxs-lookup"><span data-stu-id="ab93f-134">Implications related to country selection</span></span>

- <span data-ttu-id="ab93f-135">Når du [vælger din egne mærker](#define-your-brands-or-interests), viser systemet forslag, der er baseret på det valgte land eller område.</span><span class="sxs-lookup"><span data-stu-id="ab93f-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="ab93f-136">Når du [vælger en branche](#define-your-brands-or-interests), får du de mest relevante mærker eller oplysninger baseret på det valgte land eller område.</span><span class="sxs-lookup"><span data-stu-id="ab93f-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="ab93f-137">Ved [forbedring af profiler](#refresh-enrichment) forbedrer vi alle de kundeprofiler, vi får data fra til de valgte kundeprofiler og interesser.</span><span class="sxs-lookup"><span data-stu-id="ab93f-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="ab93f-138">Herunder profiler, der ikke er i det valgte land eller område.</span><span class="sxs-lookup"><span data-stu-id="ab93f-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="ab93f-139">Hvis du f.eks. har valgt Tyskland, forbedrer vi profiler i USA, hvis der er tilgængelige data for de valgte virksomheder og interesser i USA.</span><span class="sxs-lookup"><span data-stu-id="ab93f-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="ab93f-140">Konfigurere forbedring</span><span class="sxs-lookup"><span data-stu-id="ab93f-140">Configure Enrichment</span></span>

<span data-ttu-id="ab93f-141">En styret oplevelse hjælper dig gennem konfigurationen af forbedringerne.</span><span class="sxs-lookup"><span data-stu-id="ab93f-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="ab93f-142">Definer dine mærker eller interesser</span><span class="sxs-lookup"><span data-stu-id="ab93f-142">Define your brands or interests</span></span>

<span data-ttu-id="ab93f-143">Vælg en af følgende indstillinger:</span><span class="sxs-lookup"><span data-stu-id="ab93f-143">Select one of the following options:</span></span>

- <span data-ttu-id="ab93f-144">**Branche**: Systemet identificerer de vigtigste mærker eller interesser, der er relevante for din branche, og forbedrer kundedataene med dem.</span><span class="sxs-lookup"><span data-stu-id="ab93f-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="ab93f-145">**Vælg din egen**: Vælg op til fem elementer på listen over de mærker og interesser, der er mest relevante for din organisation.</span><span class="sxs-lookup"><span data-stu-id="ab93f-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="ab93f-146">Hvis du vil tilføje et brand eller en interesse, skal du angive det i inputområdet for at hente forslag på baggrund af matchende termer.</span><span class="sxs-lookup"><span data-stu-id="ab93f-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="ab93f-147">Hvis du ikke kan se en liste over de brands eller interesser, du leder efter, kan du sende os feedback ved hjælp af linket **Forslag**.</span><span class="sxs-lookup"><span data-stu-id="ab93f-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="ab93f-148">Gennemse indstillinger for forbedring</span><span class="sxs-lookup"><span data-stu-id="ab93f-148">Review enrichment preferences</span></span>

<span data-ttu-id="ab93f-149">Gennemse præferencerne for foretrukne indstillinger for standardpræferencer, og opdater dem efter behov.</span><span class="sxs-lookup"><span data-stu-id="ab93f-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skærmbillede af vinduet med præferencer for forbedringer.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="ab93f-151">Vælge objekt, der skal forbedres</span><span class="sxs-lookup"><span data-stu-id="ab93f-151">Select entity to enrich</span></span>

<span data-ttu-id="ab93f-152">Vælg **Forbedret objekt**, og vælg det datasæt, du vil forbedre med virksomhedsdata fra Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ab93f-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="ab93f-153">Du kan vælge objektet Kunde for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.</span><span class="sxs-lookup"><span data-stu-id="ab93f-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="ab93f-154">Tilknyt dine felter</span><span class="sxs-lookup"><span data-stu-id="ab93f-154">Map your fields</span></span>

<span data-ttu-id="ab93f-155">Tilknyt felter fra det samlede kundeobjekt for at definere det demografiske segment, som systemet skal bruge til forbedring af kundedata.</span><span class="sxs-lookup"><span data-stu-id="ab93f-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="ab93f-156">Tilknyt land/område og som minimum attributterne Fødselsdato eller Køn.</span><span class="sxs-lookup"><span data-stu-id="ab93f-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="ab93f-157">Du skal desuden tilknytte mindst én by (og område) eller et postnummer.</span><span class="sxs-lookup"><span data-stu-id="ab93f-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="ab93f-158">Vælg **Rediger** for at definere tilknytningen af felterne, og vælg **Anvend**, når du er færdig.</span><span class="sxs-lookup"><span data-stu-id="ab93f-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="ab93f-159">Vælg **Gem** for at fuldføre felttilknytningen.</span><span class="sxs-lookup"><span data-stu-id="ab93f-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="ab93f-160">Følgende formater og værdier understøttes, og der skelnes ikke mellem store og små bogstaver i værdierne:</span><span class="sxs-lookup"><span data-stu-id="ab93f-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="ab93f-161">**Fødselsdato**: Vi anbefaler, at fødselsdato konverteres til typen DateTime under dataindtagelse.</span><span class="sxs-lookup"><span data-stu-id="ab93f-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="ab93f-162">Alternativt kan det være en streng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-formatet "åååå-MM-dd" eller "åååå-MM-ddTHH: mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="ab93f-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="ab93f-163">**Køn**: mand, kvinde, ukendt</span><span class="sxs-lookup"><span data-stu-id="ab93f-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="ab93f-164">**Postnummer**: Femcifrede postnumre til USA, standardpostnummer alle andre steder</span><span class="sxs-lookup"><span data-stu-id="ab93f-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="ab93f-165">**By**: Bynavn på engelsk</span><span class="sxs-lookup"><span data-stu-id="ab93f-165">**City**: City name in English</span></span>
- <span data-ttu-id="ab93f-166">**Område**: Forkortelse på to bogstaver for USA og Canada.</span><span class="sxs-lookup"><span data-stu-id="ab93f-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="ab93f-167">Forkortelse på to eller tre bogstaver for Australien.</span><span class="sxs-lookup"><span data-stu-id="ab93f-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="ab93f-168">Gælder ikke for Frankrig, Tyskland eller Storbritannien.</span><span class="sxs-lookup"><span data-stu-id="ab93f-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="ab93f-169">**Land/område**:</span><span class="sxs-lookup"><span data-stu-id="ab93f-169">**Country/Region**:</span></span>

  - <span data-ttu-id="ab93f-170">US: Amerikas Forenede Stater, Forenede Stater, USA, Amerika</span><span class="sxs-lookup"><span data-stu-id="ab93f-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="ab93f-171">CA: Canada, CA</span><span class="sxs-lookup"><span data-stu-id="ab93f-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="ab93f-172">GB: Storbritannien, UK, Det Forenede Kongerige, GB, Det Forenede Kongerige Storbritannien og Nordirland, Det Forenede Kongerige Storbritannien</span><span class="sxs-lookup"><span data-stu-id="ab93f-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="ab93f-173">AU: Australien, AU, Australien</span><span class="sxs-lookup"><span data-stu-id="ab93f-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="ab93f-174">FR: Frankrig, FR, Den Franske Republik</span><span class="sxs-lookup"><span data-stu-id="ab93f-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="ab93f-175">DE: Tyskland, tysk, Deutschland, Allemagne, DE, Forbundsrepublikken Tyskland, Republikken Tyskland</span><span class="sxs-lookup"><span data-stu-id="ab93f-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="ab93f-176">Gennemse og navngive forbedringen</span><span class="sxs-lookup"><span data-stu-id="ab93f-176">Review and name the enrichment</span></span>

<span data-ttu-id="ab93f-177">Til sidst får du mulighed for at gennemse oplysningerne og angive et navn, der gør det muligt at bruge forbedringen.</span><span class="sxs-lookup"><span data-stu-id="ab93f-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Siden Gennemse og navngive interesser.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="ab93f-179">Opdatere forbedring</span><span class="sxs-lookup"><span data-stu-id="ab93f-179">Refresh enrichment</span></span>

<span data-ttu-id="ab93f-180">Kør forbedringen, når du har konfigureret brands, interesser og felttilknytningen for demografi.</span><span class="sxs-lookup"><span data-stu-id="ab93f-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="ab93f-181">Start processen ved at vælge **Kør** på siden for mærke- eller interessekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="ab93f-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="ab93f-182">Derudover kan du gøre det muligt for systemet at køre forbedring automatisk som en del af en planlagt opdatering.</span><span class="sxs-lookup"><span data-stu-id="ab93f-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="ab93f-183">Afhængigt af størrelsen på dine kundedata, kan det vare nogle minutter, før en forbedring kan fuldføres.</span><span class="sxs-lookup"><span data-stu-id="ab93f-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="ab93f-184">Opgaver og processer indeholder [seks typer status](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="ab93f-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ab93f-185">De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="ab93f-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ab93f-186">Du kan vælge status for en proces for at se statusdetaljer for hele jobbet.</span><span class="sxs-lookup"><span data-stu-id="ab93f-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ab93f-187">Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.</span><span class="sxs-lookup"><span data-stu-id="ab93f-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ab93f-188">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="ab93f-188">Enrichment results</span></span>

<span data-ttu-id="ab93f-189">Når du har kørt forbedringen, skal du gå til **Mine forbedringer** for at gennemgå det samlede antal forbedrede kunder og en oversigt over mærker eller interesser i de forbedrede kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="ab93f-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Eksempel på resultater efter kørsel af en forbedringsproces":::

<span data-ttu-id="ab93f-191">Gennemse de forbedrede data ved at vælge **Vis forbedrede data** i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="ab93f-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="ab93f-192">Forbedrede data for brands sendes til objektet **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="ab93f-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="ab93f-193">Data for interesser findes i objektet **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="ab93f-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="ab93f-194">Du kan også finde disse objekter på listen i gruppen **Forbedring** i **Data** > **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="ab93f-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="ab93f-195">Se forbedringsdata på kundekortet</span><span class="sxs-lookup"><span data-stu-id="ab93f-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="ab93f-196">Det er også muligt at få vist tilhørsforhold til mærker og interesser på individuelle kundekort.</span><span class="sxs-lookup"><span data-stu-id="ab93f-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="ab93f-197">Gå til **Kunder**, og vælg en kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="ab93f-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="ab93f-198">På kundekortet finder du diagrammer til de mærker eller interesser, som personer i den pågældende kundes demografiske profil har tilhørsforhold til.</span><span class="sxs-lookup"><span data-stu-id="ab93f-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundekort med forbedrede data":::

## <a name="next-steps"></a><span data-ttu-id="ab93f-200">Næste trin</span><span class="sxs-lookup"><span data-stu-id="ab93f-200">Next steps</span></span>

<span data-ttu-id="ab93f-201">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="ab93f-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ab93f-202">Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.</span><span class="sxs-lookup"><span data-stu-id="ab93f-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
