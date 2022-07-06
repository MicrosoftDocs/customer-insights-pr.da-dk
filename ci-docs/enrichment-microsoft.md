---
title: Forbedre kundeprofiler med data om kunder og interesser fra Microsoft (forhåndsversion)
description: Brug beskyttede data fra Microsoft til at forbedre dine kundedata med tilhørsforhold og stemmeandel.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: e1827adca10a3b193c02a20c4abccacf73194a77
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081111"
---
# <a name="enrich-customer-profiles-with-brands-and-interests-data-from-microsoft-preview"></a>Forbedre kundeprofiler med data om kunder og interesser fra Microsoft (forhåndsversion)

Brug Microsofts beskyttede data til at forbedre dine kundedata med mærketilhørsforhold, interessetilhørsforhold og stemmeandel (SoV). Disse tilhørsforhold og SoV er baseret på data fra personer med samme demografi som dine kunder. Disse oplysninger hjælper dig med bedre at forstå og segmentere dine kunder ud fra deres tilhørsforhold eller SoV til bestemte mærker og interesser.

## <a name="how-we-determine-affinities-and-sov"></a>Sådan afgør vi tilhørsforhold og SoV

Vi bruger Microsofts onlinesøgedata til at finde tilhørsforhold og SoV for mærker og interesser på tværs af forskellige demografiske segmenter (defineret efter alder, køn eller placering). Omfanget af onlinesøgning for et mærke eller en interesse udgør grundlaget for fastlæggelse af tilhørsforhold eller SoV. De giver dog hver især et forskelligt perspektiv til at forstå dine kunder.

- Tilhørsforhold kan sammenlignes på tværs af demografiske segmenter. Du kan bruge disse oplysninger til at identificere demografiske segmenter, der har det højeste tilhørsforhold til et bestemt mærke eller en bestemt interesse sammenlignet med andre segmenter.

- Stemmeandel kan sammenlignes på tværs af dine valgte mærker eller interesser. Du kan bruge disse oplysninger til at identificere, hvilket mærke eller hvilken interesse der har den højeste stemmeandel for et bestemt demografisk segment sammenlignet med andre mærker eller interesser, du har valgt.

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

## <a name="share-of-voice-sov"></a>Stemmeandel (SoV)

SoV beregnes på en skala med 100 point. Den samlede SoV på tværs af alle mærker eller interesser for alle forbedrede kundeprofiler bliver i alt 100. I modsætning til tilhørsforhold er SoV relativ i forhold til de mærker og interesser, du vælger. SoV-værdierne for 'Microsoft' kan for eksempel være forskellige, hvis de valgte mærker er ('Microsoft', 'GitHub') i forhold til ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Understøttede lande/områder

I øjeblikket understøttes følgende lande-/områdeindstillinger: Australien, Canada (engelsk), Frankrig, Tyskland, Storbritannien og USA (engelsk).

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

   - Hvis du vil konfigurere forbedringer af mærketilhørsforhold og SoV, skal du vælge **Forbedr mine data** i feltet **Mærker**.

   - Hvis du vil konfigurere interessetilhørsforhold og SoV, skal du vælge **Forbedr mine data** i feltet **Interesser**.

   > [!div class="mx-imgBorder"]
   > ![Brands og interesser-felter.](media/BrandsInterest-tile-Hub.png "Brands og interesse-felter")

1. Gennemse oversigten, og vælg derefter **Næste**.

1. Hvis du vil ændre dit land eller område, skal du **Skift** ud for **Land/område**. Vælg et [understøttet land/område](#supported-countriesregions) i ruden **Indstillinger for land/område**, og vælg **Anvend**.

   > [!NOTE]
   > Når du vælger din egne mærker, viser systemet forslag, der er baseret på det valgte land eller område. Når du vælger en branche, får du de mest relevante mærker eller oplysninger baseret på det valgte land eller område.

1. Vælg op til fem brands eller interesser ved hjælp af en eller begge af disse indstillinger:

   - **Branche**: Vælg din branche på rullelisten, og vælg derefter mellem de bedste mærker eller interesser for den pågældende branche.
   - **Vælg dit eget**: Angiv et brand eller en interesse, der er relevant for din organisation, og vælg derefter mellem de matchende forslag. Hvis du ikke kan se en liste over de brands eller interesser, du leder efter, kan du sende os feedback ved hjælp af linket **Forslag**.

1. Vælg **Næste**, og gennemse præferencerne for standardpræferencer, og opdater dem efter behov.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skærmbillede af vinduet med præferencer for forbedringer.":::

1. Vælg **Næste**.

1. Vælg **Kundedatasæt**, og vælg den profil eller det segment, du vil forbedre med firmadata fra Microsoft. Objektet *Kunde* forbedrer alle dine kundeprofiler, hvorimod et segment kun forbedrer de kundeprofiler, der findes i dette segment.

1. Vælg **Næste**.

1. Knyt felterne fra det samlede kundeobjekt til Microsoft-dataene.

   > [!NOTE]
   > Der skal som minimum angives attributter af samme værdi som Dato for fødsel eller Køn. Land/område og som minimum By (og Område) eller Postnummer kræves. Det anbefales, at fødselsdatoen konverteres til typen DateTime under dataindtagelse. Alternativt kan det være en streng i [ISO 8601-format](https://www.iso.org/iso-8601-date-and-time-format.html) "yyyy-MM-dd" eller "yyyy-MM-ddTHH:mm:ss".

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Angiv et Navn til forbedringen. **Output-objektnavnet** udfyldes automatisk.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Siden Gennemse og navngive interesser.":::

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

1. Vælg **Kør** for at starte forbedringsprocessen, eller luk for at vende tilbage til siden **Forbedringer**.

   Når vi forbedrer profiler, forbedrer vi alle kundeprofiler, som vi får data for de valgte brands og interesser, herunder profiler, der ikke er i det valgte land eller område. Hvis du f.eks. har valgt Tyskland, forbedrer vi profiler i USA, hvis der er tilgængelige data for de valgte virksomheder og interesser i USA.

## <a name="view-enrichment-results"></a>Vise forbedringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Eksempel på resultater efter kørsel af en forbedringsproces.":::

Resultaterne omfatter **Tilhørsforholdsniveau** eller **Deling af synspunkter**-diagrammer.

De objekter, der oprettes ud fra de oprettede objekter, er angivet under gruppen **Forbedringer** i **Data** > **Objekter**. Forbedrede data for mærker sendes til objekterne **BrandAffinityFromMicrosoft** og **BrandShareOfVoiceFromMicrosoft**. Data for interesser findes i objekterne **InterestAffinityFromMicrosoft** og **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Se forbedringsdata på kundekortet

SoV for mærke og interesse kan også ses på de enkelte kundekort. Gå til **Kunder**, og vælg en kundeprofil. I kundekortet kan du finde diagrammer for SoV for mærke eller interesse baseret på personer i den pågældende kundes demografiske profil.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundekort med forbedrede data.":::

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
