---
title: Forbedring af kundeprofiler i Microsoft Graph
description: Brug beskyttede data fra Microsoft Graph til at forbedre dine kundedata med brand- og interessetilhørsforhold.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405420"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Forbedre kundeprofiler med brand- og interessetilhørsforhold (eksempel)

Brug beskyttede data fra Microsoft Graph til at forbedre dine kundedata med brand- og interessetilhørsforhold. Disse tilhørsforhold bestemmes på baggrund af data fra personer med lignende demografi i forhold til dine kunder. Disse oplysninger hjælper dig med at få bedre indsigt i og segmentere dine kunder på baggrund af deres tilhørsforhold til specifikke mærker og interesser.

I Audience Insights skal du gå til **Data** > **Forbedring** for at [konfigurere og få vist forbedring](enrichment-hub.md).

Hvis du vil konfigurere forbedring af mærketilhørsforhold, skal du gå til fanen **Opdag** og vælge **Forbedr mine data** i feltet **Mærker**.

Hvis du vil konfigurere forbedring af interessetilhørsforhold, skal du gå til fanen **Opdag** og vælge **Forbedr mine data** i feltet **Interesser**.

   > [!div class="mx-imgBorder"]
   > ![Mærker og interesser-felter](media/BrandsInterest-tile-Hub.png "Mærker og interesser-felter")

## <a name="about-microsoft-graph"></a>Om Microsoft Graph

Vi bruger onlinesøgedata fra Microsoft Graph til at finde tilhørsforhold for brands og interesser på tværs af forskellige demografiske segmenter (defineret efter alder, køn eller sted). Antal søgninger online for et brand eller en interesse bestemmer, hvor stærkt tilhørsforholdet til et demografisk segment er for det pågældende brand eller den pågældende interesse i forhold til andre segmenter.

[Få mere at vide om Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Score for tilhørsforhold og konfidens

**Score for tilhørsforhold** beregnes på en 100-points skala, hvor 100 repræsenterer det segment, der har det største tilhørsforhold til et mærke eller en interesse.

**Tillidsforholdets konfidens** beregnes også på en skala, der går op til 100 point. Det angiver, på hvilket konfidensniveau i systemet et segment har et tilhørsforhold til brandet eller interessen. Konfidensniveauet er baseret på segmentstørrelsen og segmentets granularitet. Segmentstørrelsen bestemmes af den mængde data, vi har for et bestemt segment. Segmentets granulering bestemmes af, hvor mange attributter (alder, køn, placering) der er tilgængelige i en profil.

Vi normaliserer ikke scoren for dit datasæt. Derfor kan du muligvis ikke se alle mulige værdier af score for tilhørsforhold for dit datasæt. Det kan f.eks. være, at der ikke er nogen forbedrede kundeprofiler med en tilhørsforholdsscore på 100 i dine data. Det er muligt, hvis der ikke findes kunder i det demografiske segment, der har scoret 100 for et givet brand eller en givet interesse.

> [!TIP]
> Når du [opretter segmenter](segments.md) ved hjælp af score for tilhørsforhold, skal du gennemgå fordelingen af score for tilhørsforhold for dit datasæt, inden du beslutter dig for de relevante tærskelværdier for score. En score for tilhørsforhold på 10 kan f.eks. være bemærkelsesværdig i et datasæt, hvis største score for tilhørsforhold kun er 25 for et givet mærke eller en bestemt interesse.

## <a name="supported-countriesregions"></a>Understøttede lande/områder

I øjeblikket understøttes følgende lande-/områdeindstillinger: Australien, Canada (engelsk), Frankrig, Tyskland, Storbritannien og USA (engelsk).

Hvis du vil vælge et land, skal du åbne **Brandforbedring** eller **Interesseudvidelse** og vælge **Skift** ud for **Land/område**. Vælg en indstilling i ruden **Indstillinger for land/område**, og vælg **Anvend**.

### <a name="implications-related-to-country-selection"></a>Implikationer i forbindelse med valg af land

- Når [du vælger dine egne brands](#define-your-brands-or-interests), kommer vi med forslag, der er baseret på det valgte land/område.

- Når du [vælger en branche](#define-your-brands-or-interests), vil vi identificere de mest relevante mærker eller interesser baseret på det valgte land/område.

- Når [du tilknytter felterne](#map-your-fields), og du ikke har tilknyttet feltet Land/område, bruger vi Microsoft Graph-data fra det valgte land/område til at forbedre dine kundeprofiler. Vi bruger også det valgte til at forbedre dine kundeprofiler, som ikke har nogen tilgængelige data for lande/områder.

- Når [du forbedrer profiler](#refresh-enrichment), forbedrer vi alle kundeprofiler, som vi har Microsoft Graph-data tilgængelige til for de valgte brands og interesser, herunder profiler, der ikke findes i det valgte land/område. Hvis du f.eks. har valgt Tyskland, forbedre vi profiler, der findes i USA, hvis vi har Microsoft Graph-data tilgængelige for de udvalgte brands og interesser i USA.

## <a name="configure-enrichment"></a>Konfigurere forbedring

Konfiguration af forbedrede mærker eller interesser består af to trin:

### <a name="define-your-brands-or-interests"></a>Definer dine mærker eller interesser

Vælg en af følgende indstillinger:

- **Branche**: Systemet identificerer de vigtigste mærker eller interesser, der er relevante for din branche, og forbedrer kundedataene med dem.
- **Vælg din egen**: Vælg op til fem elementer på listen over de mærker og interesser, der er mest relevante for din organisation.

Hvis du vil tilføje et brand eller en interesse, skal du angive det i inputområdet for at hente forslag på baggrund af matchende termer. Hvis du ikke kan se en liste over de brands eller interesser, du leder efter, kan du sende os feedback ved hjælp af linket **Forslag**.

### <a name="map-your-fields"></a>Tilknyt dine felter

Tilknyt felter fra det samlede kundeobjekt til mindst to attributter for at definere det demografiske segment, du vil have, at vi bruger til at forbedre dine kundedata. Vælg **Rediger** for at definere tilknytningen af felterne, og vælg **Anvend**, når du er færdig. Vælg **Gem** for at fuldføre felttilknytningen.

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
