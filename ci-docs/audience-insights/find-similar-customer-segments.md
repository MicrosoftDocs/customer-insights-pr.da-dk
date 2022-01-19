---
title: Find lignende kunder med AI (indeholder video)
description: Find lignende kundesegmenter med kunstig intelligens.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: de337ae989558c81fff25a6ff7cca01890ed306b
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934833"
---
# <a name="similar-customers-preview"></a>Lignende kunder (prøveversion)

Denne funktion giver dig mulighed for at finde lignende kunder i kundebasen ved hjælp af kunstig intelligens. Du skal have oprettet mindst ét segment for at bruge denne funktion. Hvis du udvider kriterierne for et eksisterende segment, får du hjælp til at finde de kunder, der ligner dette segment.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Find lignende kunder* bruger automatiserede metoder til at evaluere data og foretage forudsigelser på baggrund af disse data, og de kan derfor bruges som en metode til profilering, som dette udtryk er defineret i generel forordning om databeskyttelse ("GDPR"). Kundens brug af denne funktion til behandling af data kan være underlagt GDPR eller andre love eller bestemmelser. Du er ansvarlig for at sikre, at brugen af Dynamics 365 Customer Insights, herunder forudsigelser, overholder alle gældende love og bestemmelser, herunder lovgivning vedrørende beskyttelse af personlige oplysninger, personlige data, biometriske data, databeskyttelse og fortrolighed i kommunikationen.

## <a name="finding-similar-customers"></a>Finde lignende kunder

1. Gå til **Segmenter**, og vælg det segment, du vil basere det nye segment på, i målgruppen Insights. Det er *kildesegmentet*.

1. Vælg **Find lignende kunder** på handlingslinjen .

1. Gennemgå det foreslåede navn på det nye segment, og rediger det, hvis det er nødvendigt.

1. Gennemgå de felter, der definerer det nye segment. I disse felter defineres det udgangspunkt, som systemet vil bruge til at finde lignende kunder i et kildesegment. Systemet vil som standard vælge anbefalede felter.
  Felter, der kan reducere modellens ydeevne drastisk, udelukkes automatisk:
  
   - Felter med følgende datatyper: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Felter med en kardinalitet (antallet af elementer i et felt) på mindre end 2 eller mere end 30

1. Vælg, om du vil medtage **Alle kunder** eller kun kunder i et **Bestemt eksisterende segment** i det nye segment.

1. Udeluk kunder i kildesegmentet ved at markere afkrydsningsfeltet **Udelad alle i kildesegment**.

1. Systemet foreslår som standard kun 20 % af målgruppens størrelse i outputtet. Rediger denne tærskel efter behov. Hvis tærskelværdien øges, reduceres præcisionen.

1. Vælg **Kør** nederst på siden for at starte en binær klassificeringsopgave (en metode til maskinel indlæring), som analyserer datasættet.

## <a name="view-the-similar-segment"></a>Se det lignende segment

Når du har behandlet det lignende segment, vil du finde det nye segment på siden **Segmenter**.

> [!div class="mx-imgBorder"]
> ![Lignende kundesegment.](media/expanded-segment.png "Lignende kundesegment")

Vælg **Vis** på handlingslinjen for at åbne segmentoplysningerne. Denne visning indeholder oplysninger om resultatfordelingen på tværs af [lighedsscorer](#about-similarity-scores). Du kan også finde værdierne for lighedsscore i **Eksempel på segmentmedlemmer**.

## <a name="use-the-output-of-a-similar-segment"></a>Bruge output af et lignende segment

Du kan [arbejde med outputtet af et lignende segment](segments.md) på samme måde som med andre segmenter. Du kan f.eks. eksportere segmentet eller oprette en måling.

## <a name="refresh-and-edit-a-similar-segment"></a>Opdatere og redigere et lignende segment

Hvis du vil opdatere et lignende segment, skal du vælge det på siden **Segmenter** og vælge **Opdater** på handlingslinjen.

Hvis du redigerer et lignende segment, behandles dataene igen. Det tidligere oprettede segment opdateres med nye data.    
Hvis du vil redigere et lignende segment, skal du vælge det på siden **Segmenter** og vælge **Rediger** på handlingslinjen. Anvend ændringerne, og vælg **Kør** for at starte behandlingen.

## <a name="delete-a-similar-segment"></a>Slette et lignende segment

Vælg segmentet på siden **Segmenter**, og vælg **Slet** på handlingslinjen. Bekræft sletningen.

## <a name="about-similarity-scores"></a>Om lighedsscore

Den binære klassificerings maskinelle indlæringsmodel tildeler kunderne en score i det lignende segment. Scoren er baseret på lighed med kunderne i kildesegmentet.

- Lighedsscore under 0,55 er kunder, som systemet klassificerer som *ligner ikke* kunder i kildesegmentet
- Lighedsscorer mellem 0,55 og 0,7 klassificeres som *nogenlunde ens*
- Lighedsscorer mellem 0,7 og 0,85 klassificeres som *lignende*
- Lighedsscorer mellem 0,85 og 1 er kunder, som systemet klassificerer som *meget lignende*

Kunder med lighedsscorer på under 0,4 medtages ikke i modellens output. Systemet betragter dem ikke som tilstrækkeligt lig med kildesegmentet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]