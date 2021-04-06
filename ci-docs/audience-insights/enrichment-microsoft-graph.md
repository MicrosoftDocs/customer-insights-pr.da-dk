---
title: Forbedring af kundeprofiler i Microsoft Graph
description: Brug beskyttede data fra Microsoft Graph til at forbedre dine kundedata med brand- og interessetilhørsforhold.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: aa46dac4f9c0d27881371877b14a92a6725710da
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596446"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="548b7-103">Forbedre kundeprofiler med brand- og interessetilhørsforhold (eksempel)</span><span class="sxs-lookup"><span data-stu-id="548b7-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="548b7-104">Brug beskyttede data fra Microsoft Graph til at forbedre dine kundedata med brand- og interessetilhørsforhold.</span><span class="sxs-lookup"><span data-stu-id="548b7-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="548b7-105">Disse tilhørsforhold bestemmes på baggrund af data fra personer med lignende demografi i forhold til dine kunder.</span><span class="sxs-lookup"><span data-stu-id="548b7-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="548b7-106">Disse oplysninger hjælper dig med at få bedre indsigt i og segmentere dine kunder på baggrund af deres tilhørsforhold til specifikke mærker og interesser.</span><span class="sxs-lookup"><span data-stu-id="548b7-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="548b7-107">I målgruppeindsigt skal du gå til **Data** > **Forbedring** for at [konfigurere og få vist forbedring](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="548b7-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="548b7-108">Hvis du vil konfigurere forbedring af mærketilhørsforhold, skal du gå til fanen **Opdag** og vælge **Forbedr mine data** i feltet **Mærker**.</span><span class="sxs-lookup"><span data-stu-id="548b7-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="548b7-109">Hvis du vil konfigurere forbedring af interessetilhørsforhold, skal du gå til fanen **Opdag** og vælge **Forbedr mine data** i feltet **Interesser**.</span><span class="sxs-lookup"><span data-stu-id="548b7-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="548b7-110">![Mærker og interesser-felter](media/BrandsInterest-tile-Hub.png "Mærker og interesser-felter")</span><span class="sxs-lookup"><span data-stu-id="548b7-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="548b7-111">Om Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="548b7-111">About Microsoft Graph</span></span>

<span data-ttu-id="548b7-112">Vi bruger onlinesøgedata fra Microsoft Graph til at finde tilhørsforhold for brands og interesser på tværs af forskellige demografiske segmenter (defineret efter alder, køn eller sted).</span><span class="sxs-lookup"><span data-stu-id="548b7-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="548b7-113">Antal søgninger online for et brand eller en interesse bestemmer, hvor stærkt tilhørsforholdet til et demografisk segment er for det pågældende brand eller den pågældende interesse i forhold til andre segmenter.</span><span class="sxs-lookup"><span data-stu-id="548b7-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="548b7-114">[Få mere at vide om Microsoft Graph](/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="548b7-114">[Learn more about Microsoft Graph](/graph/overview).</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="548b7-115">Tilhørsniveau og point</span><span class="sxs-lookup"><span data-stu-id="548b7-115">Affinity level and score</span></span>

<span data-ttu-id="548b7-116">På alle forbedrede kundeprofiler leverer vi to relaterede værdier: tilhørsniveau og tilhørspoint.</span><span class="sxs-lookup"><span data-stu-id="548b7-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="548b7-117">Du kan bruge disse værdier til at bestemme, hvor stærk tilhørsforholdet er for profilens demografiske segment, for et mærke eller en interesse i forhold til andre demografiske segmenter.</span><span class="sxs-lookup"><span data-stu-id="548b7-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="548b7-118">*Tilhørsniveau* består af fire niveauer, og *tilhørspoint* beregnes på en skala på 100 point, der knyttes til tilhørsniveauer.</span><span class="sxs-lookup"><span data-stu-id="548b7-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="548b7-119">Tilhørsniveau</span><span class="sxs-lookup"><span data-stu-id="548b7-119">Affinity level</span></span> |<span data-ttu-id="548b7-120">Score for tilhørsforhold</span><span class="sxs-lookup"><span data-stu-id="548b7-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="548b7-121">Meget høj</span><span class="sxs-lookup"><span data-stu-id="548b7-121">Very high</span></span>     | <span data-ttu-id="548b7-122">85 - 100</span><span class="sxs-lookup"><span data-stu-id="548b7-122">85-100</span></span>       |
|<span data-ttu-id="548b7-123">Høj</span><span class="sxs-lookup"><span data-stu-id="548b7-123">High</span></span>     | <span data-ttu-id="548b7-124">70 - 84</span><span class="sxs-lookup"><span data-stu-id="548b7-124">70-84</span></span>        |
|<span data-ttu-id="548b7-125">Medium</span><span class="sxs-lookup"><span data-stu-id="548b7-125">Medium</span></span>     | <span data-ttu-id="548b7-126">35 - 69</span><span class="sxs-lookup"><span data-stu-id="548b7-126">35-69</span></span>        |
|<span data-ttu-id="548b7-127">Lav</span><span class="sxs-lookup"><span data-stu-id="548b7-127">Low</span></span>     | <span data-ttu-id="548b7-128">1 - 34</span><span class="sxs-lookup"><span data-stu-id="548b7-128">1-34</span></span>        |

<span data-ttu-id="548b7-129">Afhængigt af den granularitet, du vil måle tilhørsforholdet med, kan du enten bruge affinitetsniveau eller resultat.</span><span class="sxs-lookup"><span data-stu-id="548b7-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="548b7-130">Tilhørspoint giver dig mere præcis styring.</span><span class="sxs-lookup"><span data-stu-id="548b7-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="548b7-131">Understøttede lande/områder</span><span class="sxs-lookup"><span data-stu-id="548b7-131">Supported countries/regions</span></span>

<span data-ttu-id="548b7-132">I øjeblikket understøttes følgende lande-/områdeindstillinger: Australien, Canada (engelsk), Frankrig, Tyskland, Storbritannien og USA (engelsk).</span><span class="sxs-lookup"><span data-stu-id="548b7-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="548b7-133">Hvis du vil vælge et land, skal du åbne **Brandforbedring** eller **Interesseudvidelse** og vælge **Skift** ud for **Land/område**.</span><span class="sxs-lookup"><span data-stu-id="548b7-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="548b7-134">Vælg en indstilling i ruden **Indstillinger for land/område**, og vælg **Anvend**.</span><span class="sxs-lookup"><span data-stu-id="548b7-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="548b7-135">Implikationer i forbindelse med valg af land</span><span class="sxs-lookup"><span data-stu-id="548b7-135">Implications related to country selection</span></span>

- <span data-ttu-id="548b7-136">Når du [vælger din egne mærker](#define-your-brands-or-interests), viser systemet forslag, der er baseret på det valgte land eller område.</span><span class="sxs-lookup"><span data-stu-id="548b7-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="548b7-137">Når du [vælger en branche](#define-your-brands-or-interests), får du de mest relevante mærker eller oplysninger baseret på det valgte land eller område.</span><span class="sxs-lookup"><span data-stu-id="548b7-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="548b7-138">Ved [forbedring af profiler](#refresh-enrichment) forbedrer vi alle de kundeprofiler, vi får data fra til de valgte kundeprofiler og interesser.</span><span class="sxs-lookup"><span data-stu-id="548b7-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="548b7-139">Herunder profiler, der ikke er i det valgte land eller område.</span><span class="sxs-lookup"><span data-stu-id="548b7-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="548b7-140">Hvis du f.eks. har valgt Tyskland, forbedre vi profiler, der findes i USA, hvis vi har Microsoft Graph-data tilgængelige for de udvalgte brands og interesser i USA.</span><span class="sxs-lookup"><span data-stu-id="548b7-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="548b7-141">Konfigurere forbedring</span><span class="sxs-lookup"><span data-stu-id="548b7-141">Configure Enrichment</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="548b7-142">Definer dine mærker eller interesser</span><span class="sxs-lookup"><span data-stu-id="548b7-142">Define your brands or interests</span></span>

<span data-ttu-id="548b7-143">Vælg en af følgende indstillinger:</span><span class="sxs-lookup"><span data-stu-id="548b7-143">Select one of the following options:</span></span>

- <span data-ttu-id="548b7-144">**Branche**: Systemet identificerer de vigtigste mærker eller interesser, der er relevante for din branche, og forbedrer kundedataene med dem.</span><span class="sxs-lookup"><span data-stu-id="548b7-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="548b7-145">**Vælg din egen**: Vælg op til fem elementer på listen over de mærker og interesser, der er mest relevante for din organisation.</span><span class="sxs-lookup"><span data-stu-id="548b7-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="548b7-146">Hvis du vil tilføje et brand eller en interesse, skal du angive det i inputområdet for at hente forslag på baggrund af matchende termer.</span><span class="sxs-lookup"><span data-stu-id="548b7-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="548b7-147">Hvis du ikke kan se en liste over de brands eller interesser, du leder efter, kan du sende os feedback ved hjælp af linket **Forslag**.</span><span class="sxs-lookup"><span data-stu-id="548b7-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="548b7-148">Gennemse indstillinger for forbedring</span><span class="sxs-lookup"><span data-stu-id="548b7-148">Review enrichment preferences</span></span>

<span data-ttu-id="548b7-149">Gennemse præferencerne for foretrukne indstillinger for standardpræferencer, og opdater dem efter behov.</span><span class="sxs-lookup"><span data-stu-id="548b7-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skærmbillede af vinduet med præferencer for forbedringer.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="548b7-151">Vælge objekt, der skal forbedres</span><span class="sxs-lookup"><span data-stu-id="548b7-151">Select entity to enrich</span></span>

<span data-ttu-id="548b7-152">Vælg **Forbedret objekt**, og vælg det datasæt, du vil forbedre med virksomhedsdata, fra Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="548b7-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft Graph.</span></span> <span data-ttu-id="548b7-153">Du kan vælge objektet Kunde for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.</span><span class="sxs-lookup"><span data-stu-id="548b7-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="548b7-154">Tilknyt dine felter</span><span class="sxs-lookup"><span data-stu-id="548b7-154">Map your fields</span></span>

<span data-ttu-id="548b7-155">Tilknyt felter fra det samlede kundeobjekt for at definere det demografiske segment, som systemet skal bruge til forbedring af kundedata.</span><span class="sxs-lookup"><span data-stu-id="548b7-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="548b7-156">Tilknyt land/område og som minimum attributterne Fødselsdato eller Køn.</span><span class="sxs-lookup"><span data-stu-id="548b7-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="548b7-157">Du skal desuden tilknytte mindst én by (og område) eller et postnummer.</span><span class="sxs-lookup"><span data-stu-id="548b7-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="548b7-158">Vælg **Rediger** for at definere tilknytningen af felterne, og vælg **Anvend**, når du er færdig.</span><span class="sxs-lookup"><span data-stu-id="548b7-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="548b7-159">Vælg **Gem** for at fuldføre felttilknytningen.</span><span class="sxs-lookup"><span data-stu-id="548b7-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="548b7-160">Følgende formater og værdier understøttes, og der skelnes ikke mellem store og små bogstaver i værdierne:</span><span class="sxs-lookup"><span data-stu-id="548b7-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="548b7-161">**Fødselsdato**: Vi anbefaler, at fødselsdato konverteres til typen DateTime under dataindtagelse.</span><span class="sxs-lookup"><span data-stu-id="548b7-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="548b7-162">Alternativt kan det være en streng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-formatet "åååå-MM-dd" eller "åååå-MM-ddTHH: mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="548b7-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="548b7-163">**Køn**: mand, kvinde, ukendt</span><span class="sxs-lookup"><span data-stu-id="548b7-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="548b7-164">**Postnummer**: Femcifrede postnumre til USA, standardpostnummer alle andre steder</span><span class="sxs-lookup"><span data-stu-id="548b7-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="548b7-165">**By**: Bynavn på engelsk</span><span class="sxs-lookup"><span data-stu-id="548b7-165">**City**: City name in English</span></span>
- <span data-ttu-id="548b7-166">**Område**: Forkortelse på to bogstaver for USA og Canada.</span><span class="sxs-lookup"><span data-stu-id="548b7-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="548b7-167">Forkortelse på to eller tre bogstaver for Australien.</span><span class="sxs-lookup"><span data-stu-id="548b7-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="548b7-168">Gælder ikke for Frankrig, Tyskland eller Storbritannien.</span><span class="sxs-lookup"><span data-stu-id="548b7-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="548b7-169">**Land/område**:</span><span class="sxs-lookup"><span data-stu-id="548b7-169">**Country/Region**:</span></span>

  - <span data-ttu-id="548b7-170">US: Amerikas Forenede Stater, Forenede Stater, USA, Amerika</span><span class="sxs-lookup"><span data-stu-id="548b7-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="548b7-171">CA: Canada, CA</span><span class="sxs-lookup"><span data-stu-id="548b7-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="548b7-172">GB: Storbritannien, UK, Det Forenede Kongerige, GB, Det Forenede Kongerige Storbritannien og Nordirland, Det Forenede Kongerige Storbritannien</span><span class="sxs-lookup"><span data-stu-id="548b7-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="548b7-173">AU: Australien, AU, Australien</span><span class="sxs-lookup"><span data-stu-id="548b7-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="548b7-174">FR: Frankrig, FR, Den Franske Republik</span><span class="sxs-lookup"><span data-stu-id="548b7-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="548b7-175">DE: Tyskland, tysk, Deutschland, Allemagne, DE, Forbundsrepublikken Tyskland, Republikken Tyskland</span><span class="sxs-lookup"><span data-stu-id="548b7-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="548b7-176">Opdatere forbedring</span><span class="sxs-lookup"><span data-stu-id="548b7-176">Refresh enrichment</span></span>

<span data-ttu-id="548b7-177">Kør forbedringen, når du har konfigureret brands, interesser og felttilknytningen for demografi.</span><span class="sxs-lookup"><span data-stu-id="548b7-177">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="548b7-178">Start processen ved at vælge **Kør** på siden for mærke- eller interessekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="548b7-178">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="548b7-179">Derudover kan du gøre det muligt for systemet at køre forbedring automatisk som en del af en planlagt opdatering.</span><span class="sxs-lookup"><span data-stu-id="548b7-179">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="548b7-180">Afhængigt af størrelsen på dine kundedata, kan det vare nogle minutter, før en forbedring kan fuldføres.</span><span class="sxs-lookup"><span data-stu-id="548b7-180">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="548b7-181">Opgaver og processer indeholder [seks typer status](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="548b7-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="548b7-182">De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="548b7-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="548b7-183">Du kan vælge status for en proces for at se statusdetaljer for hele jobbet.</span><span class="sxs-lookup"><span data-stu-id="548b7-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="548b7-184">Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.</span><span class="sxs-lookup"><span data-stu-id="548b7-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="548b7-185">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="548b7-185">Enrichment results</span></span>

<span data-ttu-id="548b7-186">Når du har kørt forbedringen, skal du gå til **Mine forbedringer** for at gennemgå det samlede antal forbedrede kunder og en oversigt over mærker eller interesser i de forbedrede kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="548b7-186">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Eksempel på resultater efter kørsel af en forbedringsproces":::

<span data-ttu-id="548b7-188">Gennemse de forbedrede data ved at vælge **Vis forbedrede data** i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="548b7-188">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="548b7-189">Forbedrede data for brands sendes til objektet **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="548b7-189">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="548b7-190">Data for interesser findes i objektet **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="548b7-190">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="548b7-191">Du kan også finde disse objekter på listen i gruppen **Forbedring** i **Data** > **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="548b7-191">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="548b7-192">Se forbedringsdata på kundekortet</span><span class="sxs-lookup"><span data-stu-id="548b7-192">See enrichment data on the customer card</span></span>

<span data-ttu-id="548b7-193">Det er også muligt at få vist tilhørsforhold til mærker og interesser på individuelle kundekort.</span><span class="sxs-lookup"><span data-stu-id="548b7-193">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="548b7-194">Gå til **Kunder**, og vælg en kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="548b7-194">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="548b7-195">På kundekortet finder du diagrammer til de mærker eller interesser, som personer i den pågældende kundes demografiske profil har tilhørsforhold til.</span><span class="sxs-lookup"><span data-stu-id="548b7-195">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundekort med forbedrede data":::

## <a name="next-steps"></a><span data-ttu-id="548b7-197">Næste trin</span><span class="sxs-lookup"><span data-stu-id="548b7-197">Next steps</span></span>

<span data-ttu-id="548b7-198">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="548b7-198">Build on top of your enriched customer data.</span></span> <span data-ttu-id="548b7-199">Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.</span><span class="sxs-lookup"><span data-stu-id="548b7-199">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]