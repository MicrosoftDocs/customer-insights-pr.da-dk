---
title: Oprette og administrere segmenter
description: Opret segmenter med kunder for at gruppere dem på baggrund af forskellige attributter.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064930"
---
# <a name="create-and-manage-segments"></a>Oprette og administrere segmenter

Definer komplekse filtre omkring det samlede kundeobjekt og dets tilknyttede objekter. Hvert enkelt segment vil efter behandling oprette et sæt kundeposter, som du kan eksportere og udføre handlinger på. Segmenter administreres på siden **Segmenter**. 

I følgende eksempel vises segmenteringsfunktionen. Vi har defineret et segment for kunder, der har bestilt mindst $500 varer over de seneste 90 dage, *og* som har været en del af et kundeserviceopkald, der blev eskaleret.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Skærmbillede af brugergrænsefladen til segmentgenerator med to grupper, der angiver et kundesegment.":::

## <a name="create-a-new-segment"></a>Oprette et nyt segment

Der er flere måder, du kan oprette et nyt segment på. I dette afsnit beskrives, hvordan du opretter *et tomt segment* fra bunden. Du kan også oprette et *hurtigt segment*, der er baseret på eksisterende objekter, eller gøre brug af modeller til maskinel indlæring for at få *forslag til segmenter*. Flere oplysninger: [Oversigt over segmenter](segments.md).

Når du opretter et segment, kan du gemme en kladde. Den gemmes som et inaktivt segment og kan ikke aktiveres, før den er fuldført med en gyldig konfiguration.

1. Gå til siden **Segmenter**.

1. Vælg **Ny** > **Tomt segment**.

1. Vælg en segmenttype i ruden **Nyt segment**:

   - **Dynamiske segmenter** [opdateres](segments.md#refresh-segments) efter en tilbagevendende tidsplan.
   - **Statiske segmenter** køres én gang, når du opretter dem.

1. Angiv **Navn på outputobjekt** for segmentet. Du kan også angive et vist navn og en beskrivelse, der hjælper med at identificere segmentet.

1. Vælg **Næste** for at gå til siden **Segmentgenerator**, hvor du definerer en gruppe. En gruppe er et sæt kunder.

1. Vælg det objekt, der indeholder den attribut, du vil segmentere efter.

1. Vælg den attribut, der skal segmenteres efter. Denne attribut kan have en af fire værdityper: numerisk, streng, dato eller boolesk.

1. Vælg en operator og en værdi for den valgte attribut.

   > [!div class="mx-imgBorder"]
   > ![Brugerdefineret gruppefilter](media/customer-group-numbers.png "Kundegruppefilter")

   |Antal |Definition  |
   |---------|---------|
   |0     |Enhed          |
   |2     |Attribut          |
   |3    |Operatør         |
   |4    |Værdi         |

   1. Hvis du vil føje flere betingelser til en gruppe, kan du bruge to logiske operatorer:

      - **OG**-operator: Begge betingelser skal overholdes som en del af segmenteringsprocessen. Denne indstilling er mest nyttig, når du definerer betingelser på tværs af forskellige objekter.

      - **ELLER**-operator: Den ene eller anden betingelse skal overholdes som en del af segmenteringsprocessen. Denne indstilling er mest nyttig, når du definerer flere betingelser for det samme objekt.

      > [!div class="mx-imgBorder"]
      > ![ELLER-operator, hvor en af betingelserne skal overholdes](media/segmentation-either-condition.png "ELLER-operator, hvor en af betingelserne skal overholdes")

      Det er aktuelt muligt at indlejre en **ELLER**-operator under en **OG**-operator, men ikke den anden vej rundt.

   1. Hver gruppe matcher sæt af kundegrupper. Du kan kombinere grupper for at medtage de kunder, der kræves til din sag.    
   Vælg **Tilføj gruppe**.

      > [!div class="mx-imgBorder"]
      > ![Tilføje kundegruppe](media/customer-group-add-group.png "Tilføje kundegruppe")

   1. Vælg en af de indstillede operatorer: **Foreningsmængde**, **Overlapning** eller **Undtagen**.

   > [!div class="mx-imgBorder"]
   > ![Tilføje foreningsmængde af kundegruppe](media/customer-group-union.png "Tilføje foreningsmængde af kundegruppe")

   - **Foreningsmængde** forener de to grupper.

   - **Overlapning** overlapper de to grupper. Kun data, der *er fælles* for begge grupper, bevares i den samlede gruppe.

   - **Undtagen** kombinerer de to grupper. Kun data i gruppe A, der *ikke er fælles* med data i gruppe B, bevares.

1. Hvis objektet er knyttet til det samlede kundeobjekt via [Relationer](relationships.md), skal du definere relationsstien for at oprette et gyldigt segment. Tilføj objekterne fra relationsstien, indtil du kan vælge objektet **Kunde: CustomerInsights** på rullelisten. Vælg derefter **Alle poster** for hvert trin.

   > [!div class="mx-imgBorder"]
   > ![Relationsstien under oprettelse af segmenter](media/segments-multiple-relationships.png "Relationsstien under oprettelse af segmenter")

1. Som standard opretter segmenter et outputobjekt, der indeholder alle attributter af kundeprofiler, som stemmer overens med de definerede filtre. Hvis et segment er baseret på andre objekter end *Kunde*-objektet, kan du føje flere attributter fra disse objekter til outputobjektet. Vælg **Projektattributter** for at vælge de attributter, der skal føjes til outputobjektet.  
  
   Eksempel: Et segment er baseret på et objekt, der indeholder kundeaktivitetsdata, som er relateret til objektet *Kunde*. Segmentet søger efter alle kunder, der har ringet til Helpdesk inden for de seneste 60 dage. Du kan vælge at føje varigheden af opkaldet og antallet af opkald til alle tilsvarende kundeposter i outputobjektet. Disse oplysninger kan være nyttige, hvis du vil sende en mail med nyttige links til artikler i onlinehjælp og ofte stillede spørgsmål til kunder, der ofte har ringet.

   > [!NOTE]
   > - Projekterede attributter fungerer kun for objekter, der har en en til mange-relation til kundeobjektet. En kunde kan f.eks. have flere abonnementer.
   > - Du kan kun projektere attributter fra et objekt, der bruges i alle grupper af segmentforespørgsel, du er i gang med at bygge.
   > - Projekterede attributter anvendes, når der bruges indstillede operatorer.

1. Vælg **Gem** for at gemme dit segment. Dit segment gemmes og behandles, hvis alle krav valideres. Ellers gemmes det som en kladde.

1. Vælg **Tilbage til segmenter** for at gå tilbage til siden **Segmenter**.



## <a name="quick-segments"></a>Hurtige segmenter

Med hurtige segmenter kan du nemt oprette simple segmenter med en enkelt operator for at få hurtigere indsigt.

1. På siden **Segmenter** skal du vælge **Nyt** > **Opret fra**.

   - Vælg indstillingen **Profiler** for at oprette et segment, der er baseret på det *samlede kundeobjekt*.
   - Vælg indstillingen **Målinger** for at oprette et segment omkring de målinger, du tidligere har oprettet.
   - Vælg indstillingen **Intelligens** for at oprette en segment omkring en af de outputenheder, du har oprettet ved hjælp af funktionerne **Forudsigelser** eller **Brugerdefinerede modeller**.

2. Vælg en attribut på rullelisten **Felt** i dialogboksen **Nyt hurtigt segment**.

3. Der gives yderligere indsigt i systemet, som kan hjælpe dig med at oprette bedre segmenter af dine kunder.
   - I forbindelse med kategoriske felter vises de 10 bedste kundeantal. Vælg en **Værdi**, og vælg **Gennemse**.

   - I forbindelse med en numerisk attribut viser systemet, hvilken attributværdi der er omfattet af hver enkelt kundes percentil. Vælg en **Operator** og en **Værdi**, og vælg derefter **Gennemse**.

4. Systemet vil give dig en **Anslået segmentstørrelse**. Du kan vælge, om du vil oprette det segment, du har defineret, eller først vil gå til det igen for at få en anden segmentstørrelse.

    > [!div class="mx-imgBorder"]
    > ![Navn og estimering for et hurtigt segment](media/quick-segment-name.png "Navn og estimering for et hurtigt segment")

5. Angiv et **Navn** til dit segment. Angiv eventuelt et **Vist navn**.

6. Vælg **Gem** for at oprette dit segment.

7. Når segmentet er færdigbehandlet, kan du se det på samme måde som andre segmenter, du har oprettet.

## <a name="next-steps"></a>Næste trin

[Eksportere et segment](export-destinations.md) og udforske [kundekort](customer-card-add-in.md) og [connectorer](export-power-bi.md) for at få indsigt i kundeniveauet.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
