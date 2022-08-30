---
title: Opret komplekse segmenter med segmentgenerator
description: Brug segmentopbygger for at oprette komplekse segmenter af kunder efter grupper, hvor de er baseret på forskellige attributter.
ms.date: 08/12/2022
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
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304742"
---
# <a name="create-complex-segments-with-segment-builder"></a>Opret komplekse segmenter med segmentgenerator

Definer komplekse filtre omkring det samlede kunde- eller kontaktobjekt og dets tilknyttede objekter. Hvert enkelt segment opretter efter behandling et sæt kunde- eller kontaktposter, som du kan eksportere og udføre handlinger på.

> [!TIP]
> Segmenter, der er baseret på **individuelle kunder**, indeholder automatisk tilgængelige kontaktoplysninger for segmentmedlemmer. Hvis i **forretningskonti** har [samlet](data-unification.md) både firmaer og kontakter , skal du vælge, om segmentet er baseret på firmaer eller forretningskontakter. Hvis du vil eksportere til en destination, hvor der forventes kontaktoplysninger, skal du bruge et kontaktsegment. Hvis du vil eksportere til en destination, hvor der forventes firmaoplysninger, skal du bruge et firmasegment.

## <a name="segment-builder"></a>Segmentgenerator

I følgende billede illustreres de forskellige aspekter i segmentgeneratoren. Her vises et segment, der resulterer i en gruppe kunder. Kunderne har bestilt varer i en bestemt tidsramme og har indsamlet bonuspoint eller brugt en bestemt sum penge.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementer i segmentgeneratoren." lightbox="media/segment-builder-overview.png":::

1. Organiser dit segment med regler og underregler. Hver enkelt regel eller underregel består af betingelser. Kombinere betingelserne med logiske operatorer.

1. Vælg [relationsstien](relationships.md) mellem objekter, der gælder for en regel. Relationsstien bestemmer, hvilke attributter der kan bruges i en betingelse.

1. Administrer regler og underregler. Rediger placeringen af en regel, eller slet den.

1. Tilføj betingelser, og opret det rette indlejreniveau ved hjælp af underregler.

1. Anvend sæthandlinger på tilknyttede regler.

1. Brug attributruden til at tilføje tilgængelige objektattributter eller at oprette betingelser baseret på attributter. I ruden vises listen over objekter og attributter, der er tilgængelige for den valgte regel, på baggrund af den valgte relationssti.

1. Føj betingelser, der er baseret på attributter, til eksisterende regler og underregler, eller føj dem til en ny regel.

1. Fortryd ændringerne, og annuller fortrydelse af ændringer, mens segmentet bygges op.

Eksemplet ovenfor illustrerer segmenteringsfunktionaliteten. Vi har defineret et segment for kunder, der som minimum sælger $500 online *og* har interesse i softwareudvikling.

## <a name="create-a-new-segment-with-segment-builder"></a>Opret nye segmenter med segmentgenerator

1. Gå til **Segmenter**

1. Vælg **Ny** > **opbyg din egen**. Du kan definere eller oprette regler på siden Segmentgenerator. En regel består af en eller flere betingelser, der definerer et sæt kunder.

   > [!NOTE]
   > I miljøer, der er baseret på forretningskonti, skal du vælge **Nyt** > **Segment af firmaer** eller **Segment af kontakter (forhåndsversion)** på baggrund af den type segment, du vil oprette. Hvis der er defineret et [firmahierarki](relationships.md#set-up-account-hierarchies), og du vil oprette regler til filtrering af data på baggrund af underordnede og overordnede relationer, skal du vælge **Brug hierarki? (forhåndsversion)**, vælge hierarkiet og derefter **Anvend**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Rude med segmentvalg af firmahierarki.":::

1. Vælg **Rediger detaljer** ud for Ikke-navngivet segment. Angiv et navn til segmentet, og opdater det foreslåede **Navn på outputobjekt** for segmentet. Du kan også føje en beskrivelse og [koder](work-with-tags-columns.md#manage-tags) til segmentet.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialogboksen Rediger detaljer.":::

1. Vælg en attribut til et objekt, du vil filtrere kunder efter, i sektionen **Regel1**. Du kan vælge attributter på to måder.
   - Gennemse listen over tilgængelige objekter og attributter i ruden **Føj til regel**, og vælg ikonet **+** ud for den attribut, der skal tilføjes. Vælg, om du vil føje attributten til en eksisterende regel eller bruge den til at oprette en ny regel.
   - Skriv navnet på attributten i regelafsnittet for at få vist tilsvarende forslag.

1. Vælg operatorerne for at angive de tilsvarende værdier for betingelsen. Attributten kan have en af fire datatyper som værdi: numerisk, streng, dato eller boolesk. Afhængigt af datatypen af attributten er der forskellige operatorer, der kan angive betingelsen.

1. Vælg **Tilføj betingelse** for at føje flere betingelser til en regel. Hvis du vil oprette en regel under den aktuelle regel, skal du vælge **Tilføj underregel**.

1. Hvis en regel bruger andre objekter end objektet *Kunde* (eller objektet *ContactProfile* for B-til-B), skal du vælge **Angiv relationssti** for at knytte det valgte objekt til det samlede kundeobjekt. Hvis der kun er én mulig relationssti, vælges den automatisk af systemet. Forskellige [relationsstier](relationships.md#relationship-paths) kan give forskellige resultater. Alle regler kan have sin egen relationssti.

   :::image type="content" source="media/relationship-path.png" alt-text="Mulig relationssti, når du opretter en regel baseret på et objekt, der er knyttet til det samlede kundeobjekt.":::

1. Hvis der findes flere betingelser i en regel, kan du vælge, hvilken logisk operator der skal forbinde dem.  
   - **OG**-operator: Alle betingelser skal være opfyldt, for at der kan inkluderes en post i segmentet. Brug denne indstilling, når du definerer betingelser på tværs af forskellige objekter.
   - **ELLER**-operator: En af betingelserne skal være opfyldt, for at der kan inkluderes en post i segmentet. Brug denne indstilling, når du definerer flere betingelser for det samme objekt.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regel med to OG-betingelser.":::

   Når du bruger ELLER-operatoren, skal alle betingelser være baseret på objekter, der er inkluderet i relationsstien.

1. Du kan oprette flere regler for at oprette forskellige sæt kundeposter. Du kan kombinere grupper for at medtage de kunder, der kræves til din sag. Hvis du ikke kan inkludere og have et objekt i en regel på grund af den angivne relationssti, skal du oprette en ny regel for at vælge attributformularen.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Føj en ny regel til et segment, og vælg den indstillede operator.":::

   1. Vælg **Tilføj regel**.
   1. Vælg en af de indstillede operatorer: **Foreningsmængde**, **Overlapning** eller **Undtagen**.

      - **Foreningsmængde** forener de to grupper.
      - **Overlapning** overlapper de to grupper. Kun data, *der er fælles* for begge grupper, forbliver i den samlede gruppe.
      - **Undtagen** kombinerer de to grupper. Kun data i gruppe A, *der ikke er fælles* for data i gruppe B, bevares.

1. Som standard opretter segmenter det outputobjekt, der automatisk indeholder alle attributter af kundeprofiler, som stemmer overens med de definerede filtre. Når du bruger objektet *ContactProfile* i B-til-B, medtages firma-id'et automatisk. Hvis et segment er baseret på andre objekter end *Kunde*-objektet eller til at medtage flere attributter fra *ContactProfile*, skal du vælge **Projektattributter** for at føje flere attributter fra disse objekter til outputobjektet.
 
   Eksempel: Et segment er baseret på et objekt, der indeholder indkøbsdata, som er relateret til objektet *Kunde*. Segmentet søger efter alle kunder fra Spanien, der har købt varer i det indeværende år. Du kan vælge at føje attributter som varers pris eller købsdatoen til alle tilsvarende kundeposter i outputobjektet. Disse oplysninger kan være nyttige, hvis du vil analysere sammenhængene mellem overensstemmelse og det samlede forbrug.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Eksempel på projicerede attributter, der er valgt i sideruden, og som skal føjes til outputobjektet.":::
 
   Et eksempelresultat for et segment, der er baseret på forretningskonti med projektattributter for kontakter, kunne se sådan ud:

   |Id  |Firmanavn  |Indtægt  |Navn på kontakt  | Kontaktrolle|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100.000 | [Abbie Moss, Ruth Soto]  | [CEO, projektstyring]

   > [!NOTE]
   > - **Projektattributter** fungerer kun for objekter, der har en en til mange-relation til objektet *Kunde* eller *ContactProfile*. En kunde kan f.eks. have flere abonnementer.
   > - Hvis den attribut, du vil projektere, er mere end ét hop væk fra objektet *Kunde* eller *ContactProfile*, som defineret af relationen, skal den pågældende attribut bruges i alle regler i den segmentforespørgsel, du er ved at oprette.
   > - Hvis den attribut, du vil projektere, kun er ét hop væk fra objektet *Kunde* eller *ContactProfile*, skal den pågældende attribut ikke nødvendigvis findes i alle regler i den segmentforespørgsel, du er ved at oprette.
   > - **Projekterede attributter** anvendes, når der bruges faste operatorer.

1. Vælg **Kør** for at oprette segmentet. Vælg **Gem**, hvis du vil bevare den aktuelle konfiguration og køre segmentet senere. Gå til siden **Segmenter**.

### <a name="segment-builder-tips"></a>Segmentgenerator-tips

Når du opretter et segment ved hjælp af segmentgeneratoren, skal du huske på følgende tip:

- Segmentgeneratoren foreslår ikke gyldige værdier fra objekter, når operatorerne angives for betingelserne. Du kan gå til **Data** > **Objekter** og hente objektdataene for at se, hvilke værdier der er tilgængelige.
- Betingelser, der er baseret på datoerne, giver dig mulighed for at skifte mellem faste datoer og et flydende datointerval.
- Hvis du har flere regler for dit segment, har den regel, du redigerer, en lodret blå linje ud for den.
- Du kan flytte regler og betingelser til andre steder i segmentdefinitionen. Vælg den lodrette ellipse (&vellip;) ud for en regel eller betingelse, og vælg, hvordan og hvor den skal flyttes hen.
- Med kontrolelementerne **Fortryd** og **Annuller fortryd** på kommandolinjen kan du annullere ændringerne.
- Når du har oprettet et segment, kan du i visse segmenter [spore brugen af dette segment](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Næste trin

[Eksportér et segment](export-destinations.md), og udforsk [integrationen med kundekort](customer-card-add-in.md) for at bruge segmenter i andre programmer.

[!INCLUDE [footer-include](includes/footer-banner.md)]
