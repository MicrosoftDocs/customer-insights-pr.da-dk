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
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896595"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Forbedre kundeprofiler med brand- og interessetilhørsforhold (eksempel)

Brug beskyttede data fra Microsoft til at forbedre dine kundedata med tilhørsforhold til varemærker og interesse. Disse tilhørsforhold bestemmes på baggrund af data fra personer med lignende demografi i forhold til dine kunder. Disse oplysninger hjælper dig med at få bedre indsigt i og segmentere dine kunder på baggrund af deres tilhørsforhold til specifikke mærker og interesser.

I målgruppeindsigt skal du gå til **Data** > **Forbedring** for at [konfigurere og få vist forbedring](enrichment-hub.md).

Hvis du vil konfigurere forbedring af mærketilhørsforhold, skal du gå til fanen **Opdag** og vælge **Forbedr mine data** i feltet **Mærker**.

Hvis du vil konfigurere forbedring af interessetilhørsforhold, skal du gå til fanen **Opdag** og vælge **Forbedr mine data** i feltet **Interesser**.

   > [!div class="mx-imgBorder"]
   > ![Mærker og interesser-felter](media/BrandsInterest-tile-Hub.png "Mærker og interesser-felter")

## <a name="how-we-determine-affinities"></a>Sådan afgør vi tilhørsforhold

Vi bruger Microsofts onlinesøgningsdata til at finde tilhørsforhold til og interesser på tværs af forskellige demografiske segmenter (defineret efter alder, køn eller lokation). Antal søgninger online for et brand eller en interesse bestemmer, hvor stærkt tilhørsforholdet til et demografisk segment er for det pågældende brand eller den pågældende interesse i forhold til andre segmenter. mærke eller interesse.

## <a name="affinity-level-and-score"></a>Tilhørsniveau og point

På alle forbedrede kundeprofiler leverer vi to relaterede værdier: tilhørsniveau og tilhørspoint. Du kan bruge disse værdier til at bestemme, hvor stærk tilhørsforholdet er for profilens demografiske segment, for et mærke eller en interesse i forhold til andre demografiske segmenter.

*Tilhørsniveau* består af fire niveauer, og *tilhørspoint* beregnes på en skala på 100 point, der knyttes til tilhørsniveauer.


|Tilhørsniveau |Score for tilhørsforhold  |
|---------|---------|
|Meget høj     | 85 - 100       |
|Høj     | 70 - 84        |
|Medium     | 35 - 69        |
|Lav     | 1 - 34        |

Afhængigt af den granularitet, du vil måle tilhørsforholdet med, kan du enten bruge affinitetsniveau eller resultat. Tilhørspoint giver dig mere præcis styring.

## <a name="supported-countriesregions"></a>Understøttede lande/områder

I øjeblikket understøttes følgende lande-/områdeindstillinger: Australien, Canada (engelsk), Frankrig, Tyskland, Storbritannien og USA (engelsk).

Hvis du vil vælge et land, skal du åbne **Brandforbedring** eller **Interesseudvidelse** og vælge **Skift** ud for **Land/område**. Vælg en indstilling i ruden **Indstillinger for land/område**, og vælg **Anvend**.

### <a name="implications-related-to-country-selection"></a>Implikationer i forbindelse med valg af land

- Når du [vælger din egne mærker](#define-your-brands-or-interests), viser systemet forslag, der er baseret på det valgte land eller område.

- Når du [vælger en branche](#define-your-brands-or-interests), får du de mest relevante mærker eller oplysninger baseret på det valgte land eller område.

- Ved [forbedring af profiler](#refresh-enrichment) forbedrer vi alle de kundeprofiler, vi får data fra til de valgte kundeprofiler og interesser. Herunder profiler, der ikke er i det valgte land eller område. Hvis du f.eks. har valgt Tyskland, forbedrer vi profiler i USA, hvis der er tilgængelige data for de valgte virksomheder og interesser i USA.

## <a name="configure-enrichment"></a>Konfigurere forbedring

En styret oplevelse hjælper dig gennem konfigurationen af forbedringerne. 

### <a name="define-your-brands-or-interests"></a>Definer dine mærker eller interesser

Vælg en af følgende indstillinger:

- **Branche**: Systemet identificerer de vigtigste mærker eller interesser, der er relevante for din branche, og forbedrer kundedataene med dem.
- **Vælg din egen**: Vælg op til fem elementer på listen over de mærker og interesser, der er mest relevante for din organisation.

Hvis du vil tilføje et brand eller en interesse, skal du angive det i inputområdet for at hente forslag på baggrund af matchende termer. Hvis du ikke kan se en liste over de brands eller interesser, du leder efter, kan du sende os feedback ved hjælp af linket **Forslag**.

### <a name="review-enrichment-preferences"></a>Gennemse indstillinger for forbedring

Gennemse præferencerne for foretrukne indstillinger for standardpræferencer, og opdater dem efter behov.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skærmbillede af vinduet med præferencer for forbedringer.":::

### <a name="select-entity-to-enrich"></a>Vælge objekt, der skal forbedres

Vælg **Forbedret objekt**, og vælg det datasæt, du vil forbedre med virksomhedsdata fra Microsoft. Du kan vælge objektet Kunde for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.

### <a name="map-your-fields"></a>Tilknyt dine felter

Tilknyt felter fra det samlede kundeobjekt for at definere det demografiske segment, som systemet skal bruge til forbedring af kundedata. Tilknyt land/område og som minimum attributterne Fødselsdato eller Køn. Du skal desuden tilknytte mindst én by (og område) eller et postnummer. Vælg **Rediger** for at definere tilknytningen af felterne, og vælg **Anvend**, når du er færdig. Vælg **Gem** for at fuldføre felttilknytningen.

Følgende formater og værdier understøttes, og der skelnes ikke mellem store og små bogstaver i værdierne:

- **Fødselsdato**: Vi anbefaler, at fødselsdato konverteres til typen DateTime under dataindtagelse. Alternativt kan det være en streng i [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)-formatet "åååå-MM-dd" eller "åååå-MM-ddTHH: mm:ssZ".
- **Køn**: mand, kvinde, ukendt
- **Postnummer**: Femcifrede postnumre til USA, standardpostnummer alle andre steder
- **By**: Bynavn på engelsk
- **Område**: Forkortelse på to bogstaver for USA og Canada. Forkortelse på to eller tre bogstaver for Australien. Gælder ikke for Frankrig, Tyskland eller Storbritannien.
- **Land/område**:

  - US: Amerikas Forenede Stater, Forenede Stater, USA, Amerika
  - CA: Canada, CA
  - GB: Storbritannien, UK, Det Forenede Kongerige, GB, Det Forenede Kongerige Storbritannien og Nordirland, Det Forenede Kongerige Storbritannien
  - AU: Australien, AU, Australien
  - FR: Frankrig, FR, Den Franske Republik
  - DE: Tyskland, tysk, Deutschland, Allemagne, DE, Forbundsrepublikken Tyskland, Republikken Tyskland

## <a name="review-and-name-the-enrichment"></a>Gennemse og navngive forbedringen

Til sidst får du mulighed for at gennemse oplysningerne og angive et navn, der gør det muligt at bruge forbedringen.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Siden Gennemse og navngive interesser.":::

## <a name="refresh-enrichment"></a>Opdatere forbedring

Kør forbedringen, når du har konfigureret brands, interesser og felttilknytningen for demografi. Start processen ved at vælge **Kør** på siden for mærke- eller interessekonfiguration. Derudover kan du gøre det muligt for systemet at køre forbedring automatisk som en del af en planlagt opdatering.
Afhængigt af størrelsen på dine kundedata, kan det vare nogle minutter, før en forbedring kan fuldføres.

> [!TIP]
> Opgaver og processer indeholder [seks typer status](system.md#status-types). De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies). Du kan vælge status for en proces for at se statusdetaljer for hele jobbet. Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.

## <a name="enrichment-results"></a>Forbedringsresultater

Når du har kørt forbedringen, skal du gå til **Mine forbedringer** for at gennemgå det samlede antal forbedrede kunder og en oversigt over mærker eller interesser i de forbedrede kundeprofiler.

:::image type="content" source="media/my-enrichments.png" alt-text="Eksempel på resultater efter kørsel af en forbedringsproces":::

Gennemse de forbedrede data ved at vælge **Vis forbedrede data** i diagrammet. Forbedrede data for brands sendes til objektet **BrandAffinityFromMicrosoft**. Data for interesser findes i objektet **InterestAffinityFromMicrosoft**. Du kan også finde disse objekter på listen i gruppen **Forbedring** i **Data** > **Objekter**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Se forbedringsdata på kundekortet

Det er også muligt at få vist tilhørsforhold til mærker og interesser på individuelle kundekort. Gå til **Kunder**, og vælg en kundeprofil. På kundekortet finder du diagrammer til de mærker eller interesser, som personer i den pågældende kundes demografiske profil har tilhørsforhold til.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundekort med forbedrede data":::

## <a name="next-steps"></a>Næste trin

Byg oven over dine forbedrede kundedata. Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
