---
title: Find lignende kunder med AI (forhåndsversion)
description: Find lignende kundesegmenter med kunstig intelligens.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170720"
---
# <a name="find-similar-customers-with-ai-preview"></a>Find kunder, der ligner hinanden med AI (forhåndsversion)

Find lignende kunder i kundebasen ved hjælp af kunstig intelligens. Du skal have oprettet mindst ét segment for at bruge denne funktion. Hvis du udvider kriterierne for et eksisterende segment, får du hjælp til at finde de kunder, der ligner dette segment.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Find lignende kunder bruger* automatiserede metoder til at evaluere data og foretage forudsigelser på baggrund af disse data. Det har derfor mulighed for at bruges som en metode til profilering, da denne betegnelse er defineret i den generelle databeskyttelsesforordning ("GDPR"). Kundens brug af denne funktion til behandling af data kan være underlagt GDPR eller andre love eller bestemmelser. Du er ansvarlig for at sikre, at brugen af Dynamics 365 Customer Insights, herunder forudsigelser, overholder alle gældende love og bestemmelser, herunder lovgivning vedrørende beskyttelse af personlige oplysninger, personlige data, biometriske data, databeskyttelse og fortrolighed i kommunikationen.

## <a name="find-similar-customers"></a>Find lignende kunder

1. Gå til **Segmenter**, og vælg det segment, som du vil basere dit nye segment på. Det er *kildesegmentet*.

1. Vælg **Find lignende kunder**.

1. Gennemgå det foreslåede navn på det nye segment, og rediger det, hvis det er nødvendigt.

1. Du kan også føje [koder](work-with-tags-columns.md#manage-tags) til det nye segment.

1. Gennemgå de felter, der definerer det nye segment. I disse felter defineres det udgangspunkt, som systemet vil bruge til at finde lignende kunder i et kildesegment. Systemet vil som standard vælge anbefalede felter. Tilføj flere betingelser, hvis det er nødvendigt.
  Felter, der kan reducere modellens ydeevne drastisk, udelukkes automatisk:
  
   - Felter med følgende datatyper: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Felter med en kardinalitet (antallet af elementer i et felt) på mindre end 2 eller mere end 30

1. Vælg, om du vil medtage **Alle kunder** undtagen kildesegmentet, eller kun kunder i et **anderledes segment** i det nye segment.

1. Systemet foreslår som standard kun 20 % af målgruppens størrelse i outputtet. Rediger denne tærskel efter behov. Hvis tærskelværdien øges, reduceres præcisionen.

1. Inkluder kunder i kildesegmentet ved at markere afkrydsningsfeltet **Medtag medlemmer fra kildesegmentet ud over kunder med lignende attributter**.

1. Vælg **Kør** nederst på siden for at starte en [binær klassificeringsopgave](#about-similarity-scores) (en metode til maskinel indlæring), som analyserer datasættet.

## <a name="view-the-similar-segment"></a>Se det lignende segment

Når du har behandlet det lignende segment, vil du finde det nye segment på siden **Segmenter** med typen **Udvidelse**.

Vælg **Vis for** at se resultatdistribution på tværs af [lighedspoint](#about-similarity-scores) og lighedspointværdier under **Forhåndsversion af medlemmer af segment**.

:::image type="content" source="media/expanded-segment.png" alt-text="Lignende kundesegment.":::

## <a name="manage-a-similar-segment"></a>Administrere lignende segment

[Arbejde med og administrere et lignende segment](segments.md#manage-existing-segments) på samme måde som med andre segmenter. Du kan f.eks. eksportere segmentet eller oprette en måling.

Redigere, opdatere, omdøbe, downloade og slette et lignende segment. Redigeres et lignende segment, behandles dataene igen. Det tidligere oprettede segment opdateres med nye data.

## <a name="about-similarity-scores"></a>Om lighedsscore

Den binære klassificerings maskinelle indlæringsmodel tildeler kunderne en score i det lignende segment. Scoren er baseret på lighed med kunderne i kildesegmentet.

- Lighedsscore under 0,55 er kunder, som systemet klassificerer som *ligner ikke* kunder i kildesegmentet
- Lighedsscorer mellem 0,55 og 0,7 klassificeres som *nogenlunde ens*
- Lighedsscorer mellem 0,7 og 0,85 klassificeres som *lignende*
- Lighedsscorer mellem 0,85 og 1 er kunder, som systemet klassificerer som *meget lignende*

Kunder med lighedsscorer på under 0,4 medtages ikke i modellens output. Systemet betragter dem ikke som tilstrækkeligt lig med kildesegmentet.

[!INCLUDE [footer-include](includes/footer-banner.md)]
