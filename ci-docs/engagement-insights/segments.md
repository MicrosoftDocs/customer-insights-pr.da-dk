---
title: Få vist og opret segmenter
description: Sådan oprettes, redigeres og slettes målgrupper, og hvor de skal bruges.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: e99c04e6c92d8ca16c2d69957e0f5b7dba0ac757
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225369"
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

1. Vælg (+) ud for den attribut, du vil filtrere efter, i **Ressourcebibliotek**. I øjeblikket kan du kun oprette målgrupper baseret på dimensioner.

   :::image type="content" source="media/create-new-segment.png" alt-text="Opret et nyt segment.":::

1. Vælg en operator og en værdi for den valgte attribut i sektionen **Regel**. Følgende handlinger understøttes.

   :::image type="content" source="media/choose-operator-segment.png" alt-text="Vælg en operator til det nye segment.":::

   - **er**: kræver et nøjagtigt match for at medtage værdier. Bruger **lig med** for en enkelt værdi eller **enhver** til at medtage flere værdier.
   - **er ikke**: kræver et nøjagtigt match for at udelukke værdier. Bruger **lig med** for en enkelt værdi eller **enhver** til at medtage flere værdier.
   - **starter med**: en streng, som de tilsvarende værdier starter med.
   - **slutter med**: en streng, som de tilsvarende værdier slutter med.
   - **indeholder**: en streng, der er indeholdt i tilsvarende værdier.

1. Hvis du vil føje flere betingelser til en gruppe, kan du bruge logiske operatorer. Projekterede attributter anvendes, når der bruges indstillede operatorer.
   - **OG**-operator: Begge betingelser skal overholdes som en del af segmenteringsprocessen. Denne indstilling er mest nyttig, når du definerer betingelser på tværs af forskellige objekter.
   - **ELLER**-operator: Den ene eller anden betingelse skal overholdes som en del af segmenteringsprocessen. Denne indstilling er mest nyttig, når du definerer flere betingelser for det samme objekt.

1. Vælg **Gem**, og skriv navnet på segmentet. 

Segmentet vises på siden **Segmenter**, og du kan anvende det på alle rapporter og tragte i arbejdsområdet.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Bruge et segment i en rapport eller tragt

Du kan anvende segmenter i en rapport eller en tragt for at filtrere dem baseret på betingelserne i segmentet. Du kan dog ikke anvende segmenter i brugsrapporten i realtid.

:::image type="content" source="media/segment-reports-filter.png" alt-text="En sidevisningsrapport med en udvidet rulleliste for at vælge, hvilke målgrupper der skal anvendes.":::

Hvis du vil anvende et segment, skal du åbne rapporten eller tragten. Vælg **+ Tilføj betingelse**, og vælg **Filtrer efter segment**. Vælg segmentet på den liste, som du vil anvende. Segmentet anvendes i rapporten. Hvis et diagram ikke understøtter segmentet, vises der en fejl. Du kan finde flere oplysninger under [Oprette og administrere tragtrapporter](funnel-reports.md).
 
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
