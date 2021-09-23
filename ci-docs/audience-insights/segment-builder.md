---
title: Opret segmenter med segmentgenerator
description: Opret segmenter med kunder for at gruppere dem på baggrund af forskellige attributter.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494488"
---
# <a name="create-segments"></a>Oprette segmenter

Definer komplekse filtre omkring det samlede kundeobjekt og dets tilknyttede objekter. Hvert enkelt segment vil efter behandling oprette et sæt kundeposter, som du kan eksportere og udføre handlinger på. Segmenter administreres på siden **Segmenter**. Du kan [oprette nye segmenter](#create-a-new-segment) ved hjælp af [segmentgenerator](#segment-builder) eller [oprette hurtige segmenter](#quick-segments) fra andre områder af appen.

## <a name="segment-builder"></a>Segmentgenerator

I følgende billede illustreres de forskellige aspekter i segmentgeneratoren. Her vises et segment, der resulterer i en gruppe kunder. Kunderne har bestilt varer i en bestemt tidsramme og indsamlet et antal point, eller de har brugt en bestemt sum penge. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementer i segmentgeneratoren." lightbox="media/segment-builder-overview.png":::

1 – Organiser dit segment med regler og underregler. Hver enkelt regel eller underregel består af betingelser. Kombinere betingelserne med logiske operatorer

2 – Vælg [relationsstien](relationships.md) mellem objekter, der gælder for en regel. Relationsstien bestemmer, hvilke attributter der kan bruges i en betingelse.

3 – Administrere regler og underregler. Rediger placeringen af en regel, eller slet den.

4 – Tilføj betingelser, og opret det rette indlejreniveau ved hjælp af underregler.

5 – Anvend sæthandlinger på tilknyttede regler.

6 – Brug attributruden til at tilføje tilgængelige objektattributter eller til at oprette betingelser baseret på attributter. I ruden vises listen over objekter og attributter, der er tilgængelige for den valgte regel, på baggrund af den valgte relationssti.

7 – Føj betingelser, der er baseret på attributter, til eksisterende regler og underregler, eller føj dem til en ny regel.

8 – Fortryd ændringerne, og annuller fortryd ændringerne, mens segmentet bygges op.

Eksemplet ovenfor illustrerer segmenteringsfunktionaliteten. Vi har defineret et segment for kunder, der som minimum sælger $500 online *og* har interesse i softwareudvikling.

## <a name="create-a-new-segment"></a>Oprette et nyt segment

Der er flere måder, du kan oprette et nyt segment på. I dette afsnit beskrives, hvordan du kan opbygge dit eget segment fra bunden. Du kan også oprette et *hurtigt segment*, der er baseret på eksisterende objekter, eller gøre brug af modeller til maskinel indlæring for at få *forslag til segmenter*. Flere oplysninger: [Oversigt over segmenter](segments.md).

Når du opretter et segment, kan du gemme en kladde. Den gemmes som et inaktivt segment og kan ikke aktiveres, før den er fuldført med en gyldig konfiguration.

1. Gå til siden **Segmenter**.

1. Vælg **Ny** > **opbyg din egen**.

1. På siden med segmentgenerator skal du definere den første regel. En regel består af en eller flere betingelser og definerer et sæt kunder.

1. Vælg en attribut til et objekt, som du vil filtrere kunderne efter, i sektionen **Regel1**. Du kan vælge attributter på to måder. 
   - Gennemse listen over tilgængelige objekter og attributter i ruden **Føj til regel**, og vælg ikonet **+** ud for den attribut, der skal tilføjes. Vælg, om du vil føje attributten til en eksisterende regel eller bruge den til at oprette en ny regel.
   - Skriv navnet på attributten i regelafsnittet for at få vist tilsvarende forslag.

1. Vælg operatorerne for at angive de tilsvarende værdier for betingelsen. Attributten kan have en af fire datatyper som værdi: numerisk, streng, dato eller boolesk. Afhængigt af datatypen af attributten er der forskellige operatorer, der kan angive betingelsen. 

1. Vælg **Tilføj betingelse** for at føje flere betingelser til en regel. Hvis du vil oprette en regel under den aktuelle regel, skal du vælge **Tilføj underregel**.

1. Hvis en regel bruger andre objekter end objektet *Kunde*, skal du angive relationsstien. Relationsstien skal informere systemet om de relationer, der skal have adgang til det samlede profilobjekt. Vælg **Angiv relationssti** for at knytte det valgte objekt til det samlede kundeobjekt. Hvis der kun er én mulig relationssti, vælges den automatisk af systemet. Forskellige relationsstier kan give forskellige resultater. Alle regler kan have sin egen relationssti.

   :::image type="content" source="media/relationship-path.png" alt-text="Mulig relationssti, når du opretter en regel baseret på et objekt, der er knyttet til det samlede kundeobjekt.":::

   Objektenheden *eCommerce_eCommercePurchases* i skærmbilledet indeholder f.eks. fire funktioner, der kan knyttes til objektet *Kunde*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Kunde
   - eCommerce_eCommercePurchases > kunde
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > kunde
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Kunde Når du vælger den sidste indstilling, kan vi medtage attributter fra alle de viste objekter i regelbetingelserne. Vi får sandsynligvis færre resultater, fordi de tilsvarende kundeposter skal være en del af alle objekter. I dette eksempel har de købt varer via e-handel (*eCommerce_eCommercePurchases*), på et salgspunkt (*POS_posPurchases*) og deltage i vores loyalitetsprogram (*loyaltyScheme_loyCustomers*). Når du vælger den anden indstilling, kan vi kun vælge attributter *eCommerce_eCommercePurchases* fra objektet *Kunde*. Dette resulterer højst sandsynligt i flere kundeprofiler.

1. Hvis der findes flere betingelser i en regel, kan du vælge, hvilken logisk operator der skal forbinde dem.

   - **OG**-operator: Alle betingelser skal være opfyldt, for at der kan inkluderes en post i segmentet. Denne indstilling er mest nyttig, når du definerer betingelser på tværs af forskellige objekter.

   - **ELLER**-operator: En af betingelserne skal være opfyldt, for at der kan inkluderes en post i segmentet. Denne indstilling er mest nyttig, når du definerer flere betingelser for det samme objekt.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regel med to OG-betingelser.":::

   Når du bruger ELLER-operatoren, skal alle betingelser være baseret på objekter, der er inkluderet i relationsstien.

   1. Du kan oprette flere regler for at oprette forskellige sæt kundeposter. Du kan kombinere grupper for at medtage de kunder, der kræves til din sag. Vælg **Tilføj regel** for at oprette en ny regel. Hvis du ikke kan inkludere og objektet i en regel på grund af den angivne relationssti, skal du oprette en ny regel for at vælge attributformularen.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Føj en ny regel til et segment, og vælg den indstillede operator.":::

   1. Vælg en af de indstillede operatorer: **Foreningsmængde**, **Overlapning** eller **Undtagen**.

   - **Foreningsmængde** forener de to grupper.

   - **Overlapning** overlapper de to grupper. Kun data, der *er fælles* for begge grupper, bevares i den samlede gruppe.

   - **Undtagen** kombinerer de to grupper. Kun data i gruppe A, der *ikke er fælles* med data i gruppe B, bevares.

1. Som standard opretter segmenter det outputobjekt, der indeholder alle attributter af kundeprofiler, som stemmer overens med de definerede filtre. Hvis et segment er baseret på andre objekter end *Kunde*-objektet, kan du føje flere attributter fra disse objekter til outputobjektet. Vælg **Projektattributter** for at vælge de attributter, der skal føjes til outputobjektet.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Eksempel på projicerede attributter, der er valgt i sideruden, og som skal føjes til outputobjektet.":::
  
   Eksempel: Et segment er baseret på et objekt, der indeholder købsdata, som er relateret til objektet *Kunde*. Segmentet søger efter alle kunder fra Spanien, der har købt varer i det indeværende år. Du kan vælge at føje attributter som varers pris eller købsdatoen til alle tilsvarende kundeposter i outputobjektet. Disse oplysninger kan være nyttige, hvis du vil analysere sammenhængene mellem overensstemmelse og det samlede forbrug.

   > [!NOTE]
   > - Projekterede attributter fungerer kun for objekter, der har en en til mange-relation til kundeobjektet. En kunde kan f.eks. have flere abonnementer.
   > - Du kan kun projektattributter fra et objekt, der bruges i alle regler for de segmentforespørgsel, du er ved at opbygge.
   > - Projekterede attributter anvendes, når der bruges indstillede operatorer.

1. Før du gemmer og kører segmentet, skal du vælge **Rediger detaljer** ud for segmentnavnet. Angiv et navn til målgruppen, og opdater det foreslåede **outputobjektnavn** for segmentet. Du kan også føje en beskrivelse til målgruppen.

1. Vælg **Kør** for at gemme og behandle dit segment, hvis alle krav er valideret. Ellers gemmes den som en inaktiv segment kladde.

1. Vælg **Tilbage til segmenter** for at gå tilbage til siden **Segmenter**.

> [!TIP]
> - Segmentgeneratoren foreslår ikke gyldige værdier fra objekter, når operatorerne angives for betingelserne. Du kan gå til **Data** > **Objekter** og hente objektdataene for at se, hvilke værdier der er tilgængelige.
> - Betingelser, der er baseret på datoerne, giver dig mulighed for at skifte mellem faste datoer og et flydende datointerval.
> - Hvis du har flere regler for dit segment, kan du se en blå linje omkring den regel, du redigerer.
> - Du kan flytte regler og betingelser til andre steder i segmentdefinitionen. Vælg [...] ud for en regel eller betingelse, og vælg, hvordan og hvor den skal flyttes.
> - Med kontrolelementerne **Fortryd** og **Annuller fortryd** på kommandolinjen kan du annullere ændringerne.

## <a name="quick-segments"></a>Hurtige segmenter

Med hurtige segmenter kan du nemt oprette simple segmenter med en enkelt operator for at få hurtigere indsigt.

1. På siden **Segmenter** skal du vælge **Nyt** > **Opret fra**.

   - Vælg indstillingen **Profiler** for at oprette et segment, der er baseret på det *samlede kundeobjekt*.
   - Vælg indstillingen **Målinger** for at oprette et segment omkring de målinger, du tidligere har oprettet.
   - Vælg indstillingen **Intelligens** for at oprette en segment omkring en af de outputenheder, du har oprettet ved hjælp af funktionerne **Forudsigelser** eller **Brugerdefinerede modeller**.

2. Vælg en attribut på rullelisten **Felt** i dialogboksen **Nyt hurtigt segment**.

3. Systemet vil give dig mere indsigt, der kan hjælpe dig med at oprette bedre kundesegmenter.
   - I forbindelse med kategoriske felter vises de 10 bedste kundeantal. Vælg en **Værdi**, og vælg **Gennemse**.

   - I forbindelse med en numerisk attribut viser systemet, hvilken attributværdi der er omfattet af hver enkelt kundes percentil. Vælg en **Operator** og en **Værdi**, og vælg derefter **Gennemse**.

4. Systemet vil give dig en **Anslået segmentstørrelse**. Du kan vælge, om du vil oprette det segment, du har defineret, eller først vil gå til det igen for at få en anden segmentstørrelse.

    > [!div class="mx-imgBorder"]
    > ![Navn og estimering for et hurtigt segment.](media/quick-segment-name.png "Navn og estimering for et hurtigt segment")

5. Angiv et **Navn** til dit segment. Angiv eventuelt et **Vist navn**.

6. Vælg **Gem** for at oprette dit segment.

7. Når segmentet er færdigbehandlet, kan du se det på samme måde som andre segmenter, du har oprettet.

## <a name="next-steps"></a>Næste trin

[Eksportér et segment](export-destinations.md), og udforsk [integrationen med kundekort](customer-card-add-in.md) for at bruge segmenter i andre programmer.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
