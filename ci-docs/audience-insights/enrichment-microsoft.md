---
title: Forbedre kundeprofiler med data fra Microsoft
description: Brug beskyttede data fra Microsoft til at forbedre dine kundedata med tilhørsforhold og stemmeandel.
ms.date: 11/11/2021
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
ms.openlocfilehash: 77972475c9a448186cee3b1b62eeda7b1996edfc
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355312"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Forbedre kundeprofiler med tilhørsforhold og stemmeandel (forhåndsversion)

Brug Microsofts beskyttede data til at forbedre dine kundedata med mærketilhørsforhold, interessetilhørsforhold og stemmeandel (SoV). Disse tilhørsforhold og SoV er baseret på data fra personer med samme demografi som dine kunder. Disse oplysninger hjælper dig med bedre at forstå og segmentere dine kunder ud fra deres tilhørsforhold eller SoV til bestemte mærker og interesser.

I målgruppeindsigt skal du gå til **Data** > **Forbedring** for at [konfigurere og få vist forbedring](enrichment-hub.md).

Hvis du vil konfigurere forberinger af mærketilhørsforhold og SoV, skal du gå til fanen **Opdag** og vælge **Forbedr mine data** i feltet **Mærker**.

Hvis du vil konfigurere forberinger af interessetilhørsforhold og SoV, skal du gå til fanen **Opdag** og vælge **Forbedr mine data** i feltet **Interesser**.

   > [!div class="mx-imgBorder"]
   > ![Brands og interesser-felter.](media/BrandsInterest-tile-Hub.png "Brands og interesse-felter")

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

Hvis du vil vælge et land eller område, skal du åbne **Brands-berigelse** eller **Interesseforbedring** og vælge **Skift** ud for **Land/område**. Vælg en indstilling i ruden **Indstillinger for land/område**, og vælg **Anvend**.

### <a name="implications-related-to-country-selection"></a>Implikationer i forbindelse med valg af land

- Når du [vælger din egne mærker](#define-your-brands-or-interests), viser systemet forslag, der er baseret på det valgte land eller område.

- Når du [vælger en branche](#define-your-brands-or-interests), får du de mest relevante mærker eller oplysninger baseret på det valgte land eller område.

- Når vi [forbedrer profiler](#refresh-enrichment), forbedrer vi alle kundeprofiler, som vi får data for de valgte brands og interesser, herunder profiler, der ikke er i det valgte land eller område. Hvis du f.eks. har valgt Tyskland, forbedrer vi profiler i USA, hvis der er tilgængelige data for de valgte virksomheder og interesser i USA.

## <a name="configure-enrichment"></a>Konfigurere forbedring

En styret oplevelse hjælper dig gennem konfigurationen af forbedringerne. 

### <a name="define-your-brands-or-interests"></a>Definer dine mærker eller interesser

Vælg op til fem brands eller interesser ved hjælp af en eller begge af disse indstillinger:

- **Branche**: Vælg din branche på rullelisten, og vælg derefter mellem de bedste mærker eller interesser for den pågældende branche.
- **Vælg dit eget**: Angiv et brand eller en interesse, der er relevant for din organisation, og vælg derefter mellem de matchende forslag. Hvis du ikke kan se en liste over de brands eller interesser, du leder efter, kan du sende os feedback ved hjælp af linket **Forslag**.

### <a name="review-enrichment-preferences"></a>Gennemse indstillinger for forbedring

Gennemse præferencerne for foretrukne indstillinger for standardpræferencer, og opdater dem efter behov.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Skærmbillede af vinduet med præferencer for forbedringer.":::

### <a name="select-entity-to-enrich"></a>Vælge objekt, der skal forbedres

Vælg **Forbedret objekt**, og vælg det datasæt, du vil forbedre med data fra Microsoft. Du kan vælge objektet Kunde for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.

### <a name="map-your-fields"></a>Tilknyt dine felter

Tilknyt felter fra det samlede kundeobjekt for at definere det demografiske segment, som systemet skal bruge til forbedring af kundedata. Tilknyt land/område og som minimum attributterne Fødselsdato eller Køn. Du skal desuden tilknytte mindst én by (og område) eller et postnummer. Vælg **Rediger** for at definere tilknytningen af felterne, og vælg **Anvend**, når du er færdig. Vælg **Gem** for at fuldføre felttilknytningen.

Følgende formater og værdier understøttes (der skelnes ikke mellem store og små bogstaver i værdierne):

- **Fødselsdato**: Vi anbefaler, at fødselsdato konverteres til typen DateTime under dataindtagelse. Alternativt kan det være en streng i [ISO 8601-format](https://www.iso.org/iso-8601-date-and-time-format.html) "yyyy-MM-dd" eller "yyyy-MM-ddTHH:mm:ss".
- **Køn**: mand, kvinde, ukendt.
- **Postnummer**: Femcifrede postnumre til USA, standardpostnummer alle andre steder.
- **By**: Bynavn på engelsk.
- **Område**: Forkortelse på to bogstaver for USA og Canada. Forkortelse på to eller tre bogstaver for Australien. Gælder ikke for Frankrig, Tyskland eller Storbritannien.
- **Land/område**:

  - US: Amerikas Forenede Stater, Forenede Stater, USA, Amerika
  - CA: Canada, CA
  - GB: Storbritannien, UK, Det Forenede Kongerige, GB, Det Forenede Kongerige Storbritannien og Nordirland, Det Forenede Kongerige Storbritannien
  - AU: Australien, AU, Commonwealth of Australia
  - FR: Frankrig, FR, Den Franske Republik
  - DE: Tyskland, tysk, Deutschland, Allemagne, DE, Forbundsrepublikken Tyskland, Republikken Tyskland

## <a name="review-and-name-the-enrichment"></a>Gennemse og navngive forbedringen

Til sidst får du mulighed for at gennemse oplysningerne og angive et navn, der gør det muligt at bruge forbedringen.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Siden Gennemse og navngive interesser.":::

## <a name="refresh-enrichment"></a>Opdatere forbedring

Kør forbedringen, når du har konfigureret brands, interesser og felttilknytningen for demografi. Start processen ved at vælge **Kør** på siden for mærke- eller interessekonfiguration. Derudover kan du gøre det muligt for systemet at køre forbedring automatisk som en del af en planlagt opdatering.

Afhængigt af størrelsen på dine kundedata, kan det vare nogle minutter, før en forbedring kan fuldføres.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Forbedringsresultater

Når du har kørt forbedringen, skal du gå til **Mine forbedringer** for at gennemgå det samlede antal forbedrede kunder og en oversigt over mærker eller interesser i de forbedrede kundeprofiler.

:::image type="content" source="media/my-enrichments.png" alt-text="Eksempel på resultater efter kørsel af en forbedringsproces.":::

Du kan finde et diagram med antallet af forbedrede kundeprofiler over tid og eksempler på forbedrede objekter. Gennemse de forbedrede data ved at vælge **Se mere** i diagrammerne **Affinitetsniveau** eller **Del af stemmen**. Forbedrede data for mærker sendes til objekterne **BrandAffinityFromMicrosoft** og **BrandShareOfVoiceFromMicrosoft**. Data for interesser findes i objekterne **InterestAffinityFromMicrosoft** og **InterestShareOfVoiceFromMicrosoft**. Du kan også finde disse objekter på listen i gruppen **Forbedring** i **Data** > **Objekter**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Se forbedringsdata på kundekortet

SoV for mærke og interesse kan også ses på de enkelte kundekort. Gå til **Kunder**, og vælg en kundeprofil. I kundekortet kan du finde diagrammer for SoV for mærke eller interesse baseret på personer i den pågældende kundes demografiske profil.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kundekort med forbedrede data.":::

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
