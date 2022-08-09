---
title: Opret simple segmenter med hurtige segmenter
description: Opret simple segmenter med kunder for at gruppere dem på baggrund af forskellige attributter.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171129"
---
# <a name="create-simple-segments-with-quick-segments"></a>Opret simple segmenter med hurtige segmenter

Med hurtige segmenter kan du nemt oprette simple segmenter med en enkelt operator for at få hurtigere indsigt. Hurtige segmenter understøttes kun i miljøer for **individuelle kunder**.

## <a name="create-a-new-segment-with-quick-segments"></a>Opret nye segmenter med hurtige segmenter

1. Gå til **Segmenter**

1. Vælg **Nyt** > **Opret fra**.
   - Vælg indstillingen **Profiler** for at oprette et segment, der er baseret på det *samlede kundeobjekt*.
   - Vælg indstillingen **Målinger** for at oprette et segment omkring de målinger, du tidligere har oprettet.
   - Vælg indstillingen **Intelligens** for at oprette en segment omkring en af de outputenheder, du har oprettet ved hjælp af funktionerne **Forudsigelser** eller **Brugerdefinerede modeller**.

1. Vælg en attribut på rullelisten **Felt** i dialogboksen **Nyt hurtigt segment**. Afhængigt af dit valg har systemet forskellige værdier.
   - I forbindelse med kategoriske felter vises de 10 bedste kundeantal. Vælg en **Værdi**, og vælg **Gennemse**.
   - I forbindelse med en numerisk attribut viser systemet, hvilken attributværdi der er omfattet af hver enkelt kundes percentil. Vælg en **Operator** og en **Værdi**, og vælg derefter **Gennemse**.

1. Systemet vil give dig en **Anslået segmentstørrelse**. Du kan vælge, om du vil oprette det segment, du har defineret, eller gå tilbage til at vælge et andet felt.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Navn og estimering for et hurtigt segment.":::

1. Angiv et **Navn** og **Outputobjektnavn** til segmentet. Du kan også tilføje [koder](work-with-tags-columns.md#manage-tags).

1. Vælg **Gem** for at oprette dit segment. Gå til siden **Segmenter**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Næste trin

[Eksportér et segment](export-destinations.md), og udforsk [integrationen med kundekort](customer-card-add-in.md) for at bruge segmenter i andre programmer.

[!INCLUDE [footer-include](includes/footer-banner.md)]
