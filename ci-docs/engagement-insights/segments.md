---
title: Få vist og opret segmenter
description: Sådan oprettes, redigeres og slettes målgrupper, og hvor de skal bruges.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036141"
---
# <a name="view-and-create-segments"></a>Få vist og opret segmenter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmenter giver dig mulighed for at identificere undersæt af besøgende baseret på egenskaber eller interaktioner på websteder. Segmenter giver dig mulighed for at anvende filtre og analysere disse undersæt. Analysen kan hjælpe med at undersøge og reagere på tendenser i din virksomhed. 

:::image type="content" source="media/segments-page.png" alt-text="Skærmbillede af engagementsindsigtsapplikationen, der viser listen over eksisterende segmenter i et arbejdsområde.":::

## <a name="view-segments"></a>Vis segmenter

1. Vælg **Data** i venstre navigationsrude. 

1. Vælg fanen **Segmenter** for at få vist en liste over alle segmenter i arbejdsområdet. 

## <a name="create-a-segment"></a>Opret et segment

Segmenter består af regler og betingelser, der er forbundet med logiske operatorer. Betingelser anvender filtre på en valgt dimension. Hvert segment kan bruge op til fem dimensioner.

I følgende eksempel vises et segment med to betingelser i en enkelt regel. Det filtrerer alle webstedshændelser, hvor browseren er Chrome, og operativsystemerne er iOS eller Android.

:::image type="content" source="media/segment-sample.png" alt-text="Eksempelsegmenter med to betingelser i en regel, der skal filtreres til webstedshændelser.":::

I dette afsnit beskrives, hvordan du opretter *et tomt segment* fra bunden.

1. Gå til **Data** > **Segmenter**.

1. Vælg **Nyt segment**.

1. Vælg den attribut, du vil filtrere efter, i **Ressourcebibliotek**. I øjeblikket kan du kun oprette målgrupper baseret på dimensioner.

1. Vælg en operator og en værdi for den valgte attribut. Følgende handlinger understøttes.
   - **er**: kræver et nøjagtigt match for at medtage værdier. Bruger **lig med** for en enkelt værdi eller **enhver** til at medtage flere værdier.
   - **er ikke**: kræver et nøjagtigt match for at udelukke værdier. Bruger **lig med** for en enkelt værdi eller **enhver** til at medtage flere værdier.
   - **starter med**: en streng, som de tilsvarende værdier starter med.
   - **slutter med**: en streng, som de tilsvarende værdier slutter med.
   - **indeholder**: en streng, der er indeholdt i tilsvarende værdier.

1. Hvis du vil føje flere betingelser til en gruppe, kan du bruge to logiske operatorer. Projekterede attributter anvendes, når der bruges indstillede operatorer.
   - **OG**-operator: Begge betingelser skal overholdes som en del af segmenteringsprocessen. Denne indstilling er mest nyttig, når du definerer betingelser på tværs af forskellige objekter.
   - **ELLER**-operator: Den ene eller anden betingelse skal overholdes som en del af segmenteringsprocessen. Denne indstilling er mest nyttig, når du definerer flere betingelser for det samme objekt.

1. Vælg **Gem**, og skriv navnet på segmentet. 

Segmentet vises på siden Segmenter, og du kan anvende den på alle rapporter og tragte i arbejdsområdet.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Bruge et segment i en rapport eller tragt

Du kan anvende segmenter i en rapport eller en tragt for at filtrere dem baseret på betingelserne i segmentet. Du kan dog ikke anvende segmenter i brugsrapporten i realtid.

:::image type="content" source="media/segment-reports-filter.png" alt-text="En sidevisningsrapport med en udvidet rulleliste for at vælge, hvilke målgrupper der skal anvendes.":::

Hvis du vil anvende et segment, skal du åbne rapporten eller tragten. Vælg **Tilføj betingelse**, og vælg **Filtrer efter segment**. Vælg segmentet på den liste, som du vil anvende. Segmentet anvendes i rapporten. Hvis et diagram ikke understøtter segmentet, vises der en fejl.
 
Du kan anvende *op til tre segmenter* i en rapport eller tragt.

## <a name="edit-a-segment"></a>Redigere et segment

1. Gå til **Data** > **Segmenter**.
1. Vælg segmentet i listen for at åbne det. 
1. Ændre eller tilføje værdier efter behov.
1. Vælg **Gem** for at anvende dine ændringer.

## <a name="change-the-name-of-a-segment"></a>Skifte navn på et segment

1. Gå til **Data** > **Segmenter**.
1. Vælg **Mere [...]** på segmentlisten. 
1. Fra rullelisten skal du vælge **Rediger navn**.
1. Skriv det ny navn, og vælg **Omdøb**.

## <a name="delete-a-segment"></a>Slette et segment

1. Gå til **Data** > **Segmenter**.
1. Vælg **Mere [...]** på segmentlisten. 
1. Vælg **Slet** på rullelisten.
1. Vælg **Slet** for at bekræfte.

[!INCLUDE[footer-include](../includes/footer-banner.md)]