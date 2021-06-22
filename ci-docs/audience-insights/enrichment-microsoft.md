---
title: Forbedre kundeprofiler med data fra Microsoft
description: Brug beskyttede data fra Microsoft til at forbedre dine kundedata med tilhørsforhold til varemærker og interesse.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245700"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="80ebb-103">Forbedre kundeprofiler med brand- og interessetilhørsforhold (eksempel)</span><span class="sxs-lookup"><span data-stu-id="80ebb-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="80ebb-104">Brug beskyttede data fra Microsoft til at forbedre dine kundedata med tilhørsforhold til varemærker og interesse.</span><span class="sxs-lookup"><span data-stu-id="80ebb-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="80ebb-105">Disse tilhørsforhold bestemmes på baggrund af data fra personer med lignende demografi i forhold til dine kunder.</span><span class="sxs-lookup"><span data-stu-id="80ebb-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="80ebb-106">Disse oplysninger hjælper dig med at få bedre indsigt i og segmentere dine kunder på baggrund af deres tilhørsforhold til specifikke mærker og interesser.</span><span class="sxs-lookup"><span data-stu-id="80ebb-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="80ebb-107">I målgruppeindsigt skal du gå til **Data** > **Forbedring** for at [konfigurere og få vist forbedring](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="80ebb-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="80ebb-108">Hvis du vil konfigurere forbedring af mærketilhørsforhold, skal du gå til fanen **Opdag** og vælge **Forbedr mine data** i feltet **Mærker**.</span><span class="sxs-lookup"><span data-stu-id="80ebb-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="80ebb-109">Hvis du vil konfigurere forbedring af interessetilhørsforhold, skal du gå til fanen **Opdag** og vælge **Forbedr mine data** i feltet **Interesser**.</span><span class="sxs-lookup"><span data-stu-id="80ebb-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="80ebb-110">![Mærker og interesser-felter](media/BrandsInterest-tile-Hub.png "Mærker og interesser-felter")</span><span class="sxs-lookup"><span data-stu-id="80ebb-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="80ebb-111">Sådan afgør vi tilhørsforhold</span><span class="sxs-lookup"><span data-stu-id="80ebb-111">How we determine affinities</span></span>

<span data-ttu-id="80ebb-112">Vi bruger Microsofts onlinesøgningsdata til at finde tilhørsforhold til og interesser på tværs af forskellige demografiske segmenter (defineret efter alder, køn eller lokation).</span><span class="sxs-lookup"><span data-stu-id="80ebb-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="80ebb-113">Antal søgninger online for et brand eller en interesse bestemmer, hvor stærkt tilhørsforholdet til et demografisk segment er for det pågældende brand eller den pågældende interesse i forhold til andre segmenter.</span><span class="sxs-lookup"><span data-stu-id="80ebb-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="80ebb-114">Tilhørsniveau og point</span><span class="sxs-lookup"><span data-stu-id="80ebb-114">Affinity level and score</span></span>

<span data-ttu-id="80ebb-115">På alle forbedrede kundeprofiler leverer vi to relaterede værdier: tilhørsniveau og tilhørspoint.</span><span class="sxs-lookup"><span data-stu-id="80ebb-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="80ebb-116">Du kan bruge disse værdier til at bestemme, hvor stærk tilhørsforholdet er for profilens demografiske segment, for et mærke eller en interesse i forhold til andre demografiske segmenter.</span><span class="sxs-lookup"><span data-stu-id="80ebb-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="80ebb-117">*Tilhørsniveau* består af fire niveauer, og *tilhørspoint* beregnes på en skala på 100 point, der knyttes til tilhørsniveauer.</span><span class="sxs-lookup"><span data-stu-id="80ebb-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="80ebb-118">Tilhørsniveau</span><span class="sxs-lookup"><span data-stu-id="80ebb-118">Affinity level</span></span> |<span data-ttu-id="80ebb-119">Score for tilhørsforhold</span><span class="sxs-lookup"><span data-stu-id="80ebb-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="80ebb-120">Meget høj</span><span class="sxs-lookup"><span data-stu-id="80ebb-120">Very high</span></span>     | <span data-ttu-id="80ebb-121">85 - 100</span><span class="sxs-lookup"><span data-stu-id="80ebb-121">85-100</span></span>       |
|<span data-ttu-id="80ebb-122">Høj</span><span class="sxs-lookup"><span data-stu-id="80ebb-122">High</span></span>     | <span data-ttu-id="80ebb-123">70 - 84</span><span class="sxs-lookup"><span data-stu-id="80ebb-123">70-84</span></span>        |
|<span data-ttu-id="80ebb-124">Medium</span><span class="sxs-lookup"><span data-stu-id="80ebb-124">Medium</span></span>     | <span data-ttu-id="80ebb-125">35 - 69</span><span class="sxs-lookup"><span data-stu-id="80ebb-125">35-69</span></span>        |
|<span data-ttu-id="80ebb-126">Lav</span><span class="sxs-lookup"><span data-stu-id="80ebb-126">Low</span></span>     | <span data-ttu-id="80ebb-127">1 - 34</span><span class="sxs-lookup"><span data-stu-id="80ebb-127">1-34</span></span>        |

<span data-ttu-id="80ebb-128">Afhængigt af den granularitet, du vil måle tilhørsforholdet med, kan du enten bruge affinitetsniveau eller resultat.</span><span class="sxs-lookup"><span data-stu-id="80ebb-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="80ebb-129">Tilhørspoint giver dig mere præcis styring.</span><span class="sxs-lookup"><span data-stu-id="80ebb-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="80ebb-130">Understøttede lande/områder</span><span class="sxs-lookup"><span data-stu-id="80ebb-130">Supported countries/regions</span></span>

<span data-ttu-id="80ebb-131">I øjeblikket understøttes følgende lande-/områdeindstillinger: Australien, Canada (engelsk), Frankrig, Tyskland, Storbritannien og USA (engelsk).</span><span class="sxs-lookup"><span data-stu-id="80ebb-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="80ebb-132">Hvis du vil vælge et land, skal du åbne **Brandforbedring** eller **Interesseudvidelse** og vælge **Skift** ud for **Land/område**.</span><span class="sxs-lookup"><span data-stu-id="80ebb-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="80ebb-133">Vælg en indstilling i ruden **Indstillinger for land/område**, og vælg **Anvend**.</span><span class="sxs-lookup"><span data-stu-id="80ebb-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="80ebb-134">Implikationer i forbindelse med valg af land</span><span class="sxs-lookup"><span data-stu-id="80ebb-134">Implications related to country selection</span></span>

- <span data-ttu-id="80ebb-135">Når du [vælger din egne mærker](#define-your-brands-or-interests), viser systemet forslag, der er baseret på det valgte land eller område.</span><span class="sxs-lookup"><span data-stu-id="80ebb-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="80ebb-136">Når du [vælger en branche](#define-your-brands-or-interests), får du de mest relevante mærker eller oplysninger baseret på det valgte land eller område.</span><span class="sxs-lookup"><span data-stu-id="80ebb-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="80ebb-137">Ved [forbedring af profiler](#refresh-enrichment) forbedrer vi alle de kundeprofiler, vi får data fra til de valgte kundeprofiler og interesser.</span><span class="sxs-lookup"><span data-stu-id="80ebb-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="80ebb-138">Herunder profiler, der ikke er i det valgte land eller område.</span><span class="sxs-lookup"><span data-stu-id="80ebb-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="80ebb-139">Hvis du f.eks. har valgt Tyskland, forbedrer vi profiler i USA, hvis der er tilgængelige data for de valgte virksomheder og interesser i USA.</span><span class="sxs-lookup"><span data-stu-id="80ebb-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="80ebb-140">Konfigurere forbedring</span><span class="sxs-lookup"><span data-stu-id="80ebb-140">Configure Enrichment</span></span>

<span data-ttu-id="80ebb-141">En styret oplevelse hjælper dig gennem konfigurationen af forbedringerne.</span><span class="sxs-lookup"><span data-stu-id="80ebb-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="80ebb-142">Definer dine mærker eller interesser</span><span class="sxs-lookup"><span data-stu-id="80ebb-142">Define your brands or interests</span></span>

<span data-ttu-id="80ebb-143">Vælg op til fem brands eller interesser ved hjælp af en eller begge af disse indstillinger:</span><span class="sxs-lookup"><span data-stu-id="80ebb-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="80ebb-144">**Branche**: Vælg din branche på rullelisten, og vælg derefter mellem de bedste brands eller interesser for den pågældende branche.</span><span class="sxs-lookup"><span data-stu-id="80ebb-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="80ebb-145">**Vælg dit eget**: Angiv et brand eller en interesse, der er relevant for din organisation, og vælg derefter mellem de matchende forslag.</span><span class="sxs-lookup"><span data-stu-id="80ebb-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="80ebb-146">Hvis du ikke kan se en liste over de brands eller interesser, du leder efter, kan du sende os feedback ved hjælp af linket **Forslag**.</span><span class="sxs-lookup"><span data-stu-id="80ebb-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="80ebb-147">Gennemse indstillinger for forbedring</span><span class="sxs-lookup"><span data-stu-id="80ebb-147">Review enrichment preferences</span></span>

<span data-ttu-id="80ebb-148">Gennemse præferencerne for foretrukne indstillinger for standardpræferencer, og opdater dem efter behov.</span><span class="sxs-lookup"><span data-stu-id="80ebb-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skærmbillede af vinduet med præferencer for forbedringer.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="80ebb-150">Vælge objekt, der skal forbedres</span><span class="sxs-lookup"><span data-stu-id="80ebb-150">Select entity to enrich</span></span>

<span data-ttu-id="80ebb-151">Vælg **Forbedret objekt**, og vælg det datasæt, du vil forbedre med virksomhedsdata fra Microsoft.</span><span class="sxs-lookup"><span data-stu-id="80ebb-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="80ebb-152">Du kan vælge objektet Kunde for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.</span><span class="sxs-lookup"><span data-stu-id="80ebb-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="80ebb-153">Tilknyt dine felter</span><span class="sxs-lookup"><span data-stu-id="80ebb-153">Map your fields</span></span>

<span data-ttu-id="80ebb-154">Tilknyt felter fra det samlede kundeobjekt for at definere det demografiske segment, som systemet skal bruge til forbedring af kundedata.</span><span class="sxs-lookup"><span data-stu-id="80ebb-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="80ebb-155">Tilknyt land/område og som minimum attributterne Fødselsdato eller Køn.</span><span class="sxs-lookup"><span data-stu-id="80ebb-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="80ebb-156">Du skal desuden tilknytte mindst én by (og område) eller et postnummer.</span><span class="sxs-lookup"><span data-stu-id="80ebb-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="80ebb-157">Vælg **Rediger** for at definere tilknytningen af felterne, og vælg **Anvend**, når du er færdig.</span><span class="sxs-lookup"><span data-stu-id="80ebb-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="80ebb-158">Vælg **Gem** for at fuldføre felttilknytningen.</span><span class="sxs-lookup"><span data-stu-id="80ebb-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="80ebb-159">Følgende formater og værdier understøttes, og der skelnes ikke mellem store og små bogstaver i værdierne:</span><span class="sxs-lookup"><span data-stu-id="80ebb-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="80ebb-160">**Fødselsdato**: Vi anbefaler, at fødselsdato konverteres til typen DateTime under dataindtagelse.</span><span class="sxs-lookup"><span data-stu-id="80ebb-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="80ebb-161">Alternativt kan det være en streng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-formatet "åååå-MM-dd" eller "åååå-MM-ddTHH: mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="80ebb-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="80ebb-162">**Køn**: mand, kvinde, ukendt</span><span class="sxs-lookup"><span data-stu-id="80ebb-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="80ebb-163">**Postnummer**: Femcifrede postnumre til USA, standardpostnummer alle andre steder</span><span class="sxs-lookup"><span data-stu-id="80ebb-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="80ebb-164">**By**: Bynavn på engelsk</span><span class="sxs-lookup"><span data-stu-id="80ebb-164">**City**: City name in English</span></span>
- <span data-ttu-id="80ebb-165">**Område**: Forkortelse på to bogstaver for USA og Canada.</span><span class="sxs-lookup"><span data-stu-id="80ebb-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="80ebb-166">Forkortelse på to eller tre bogstaver for Australien.</span><span class="sxs-lookup"><span data-stu-id="80ebb-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="80ebb-167">Gælder ikke for Frankrig, Tyskland eller Storbritannien.</span><span class="sxs-lookup"><span data-stu-id="80ebb-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="80ebb-168">**Land/område**:</span><span class="sxs-lookup"><span data-stu-id="80ebb-168">**Country/Region**:</span></span>

  - <span data-ttu-id="80ebb-169">US: Amerikas Forenede Stater, Forenede Stater, USA, Amerika</span><span class="sxs-lookup"><span data-stu-id="80ebb-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="80ebb-170">CA: Canada, CA</span><span class="sxs-lookup"><span data-stu-id="80ebb-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="80ebb-171">GB: Storbritannien, UK, Det Forenede Kongerige, GB, Det Forenede Kongerige Storbritannien og Nordirland, Det Forenede Kongerige Storbritannien</span><span class="sxs-lookup"><span data-stu-id="80ebb-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="80ebb-172">AU: Australien, AU, Australien</span><span class="sxs-lookup"><span data-stu-id="80ebb-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="80ebb-173">FR: Frankrig, FR, Den Franske Republik</span><span class="sxs-lookup"><span data-stu-id="80ebb-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="80ebb-174">DE: Tyskland, tysk, Deutschland, Allemagne, DE, Forbundsrepublikken Tyskland, Republikken Tyskland</span><span class="sxs-lookup"><span data-stu-id="80ebb-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="80ebb-175">Gennemse og navngive forbedringen</span><span class="sxs-lookup"><span data-stu-id="80ebb-175">Review and name the enrichment</span></span>

<span data-ttu-id="80ebb-176">Til sidst får du mulighed for at gennemse oplysningerne og angive et navn, der gør det muligt at bruge forbedringen.</span><span class="sxs-lookup"><span data-stu-id="80ebb-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Siden Gennemse og navngive interesser.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="80ebb-178">Opdatere forbedring</span><span class="sxs-lookup"><span data-stu-id="80ebb-178">Refresh enrichment</span></span>

<span data-ttu-id="80ebb-179">Kør forbedringen, når du har konfigureret brands, interesser og felttilknytningen for demografi.</span><span class="sxs-lookup"><span data-stu-id="80ebb-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="80ebb-180">Start processen ved at vælge **Kør** på siden for mærke- eller interessekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="80ebb-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="80ebb-181">Derudover kan du gøre det muligt for systemet at køre forbedring automatisk som en del af en planlagt opdatering.</span><span class="sxs-lookup"><span data-stu-id="80ebb-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="80ebb-182">Afhængigt af størrelsen på dine kundedata, kan det vare nogle minutter, før en forbedring kan fuldføres.</span><span class="sxs-lookup"><span data-stu-id="80ebb-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="80ebb-183">Opgaver og processer indeholder [seks typer status](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="80ebb-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="80ebb-184">De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="80ebb-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="80ebb-185">Du kan vælge status for en proces for at se statusdetaljer for hele jobbet.</span><span class="sxs-lookup"><span data-stu-id="80ebb-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="80ebb-186">Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.</span><span class="sxs-lookup"><span data-stu-id="80ebb-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="80ebb-187">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="80ebb-187">Enrichment results</span></span>

<span data-ttu-id="80ebb-188">Når du har kørt forbedringen, skal du gå til **Mine forbedringer** for at gennemgå det samlede antal forbedrede kunder og en oversigt over mærker eller interesser i de forbedrede kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="80ebb-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Eksempel på resultater efter kørsel af en forbedringsproces":::

<span data-ttu-id="80ebb-190">Gennemse de forbedrede data ved at vælge **Vis forbedrede data** i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="80ebb-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="80ebb-191">Forbedrede data for brands sendes til objektet **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="80ebb-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="80ebb-192">Data for interesser findes i objektet **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="80ebb-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="80ebb-193">Du kan også finde disse objekter på listen i gruppen **Forbedring** i **Data** > **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="80ebb-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="80ebb-194">Se forbedringsdata på kundekortet</span><span class="sxs-lookup"><span data-stu-id="80ebb-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="80ebb-195">Det er også muligt at få vist tilhørsforhold til mærker og interesser på individuelle kundekort.</span><span class="sxs-lookup"><span data-stu-id="80ebb-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="80ebb-196">Gå til **Kunder**, og vælg en kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="80ebb-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="80ebb-197">På kundekortet finder du diagrammer til de mærker eller interesser, som personer i den pågældende kundes demografiske profil har tilhørsforhold til.</span><span class="sxs-lookup"><span data-stu-id="80ebb-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundekort med forbedrede data":::

## <a name="next-steps"></a><span data-ttu-id="80ebb-199">Næste trin</span><span class="sxs-lookup"><span data-stu-id="80ebb-199">Next steps</span></span>

<span data-ttu-id="80ebb-200">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="80ebb-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="80ebb-201">Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.</span><span class="sxs-lookup"><span data-stu-id="80ebb-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
