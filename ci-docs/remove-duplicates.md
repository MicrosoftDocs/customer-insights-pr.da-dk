---
title: Fjerne dubletter, før du forener data
description: Det andet trin i processen til samling er at vælge, hvilken post der skal bevares, når der findes dubletter.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 3f84c1c149f0befcbe489ccdd8a666ce6d5d798a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304466"
---
# <a name="remove-duplicates-before-unifying-data"></a>Fjerne dubletter, før du forener data

I dette valgfri trin n i en samling kan du også konfigurere regler for eliminering af dubletposter **i** et objekt. Duplikering identificerer flere poster for en kunde og vælger den bedste post, der skal bevares (baseret på grundlæggende indstillinger for fletning), eller fletter posterne til én (baseret på avancerede indstillinger for fletning). Kildeposter knyttes til den flettede post med alternative id'er. Hvis regler ikke er konfigureret, anvendes systemdefinerede regler.

## <a name="default-deduplication"></a>Standard-deduplikering

Hvis der ikke er tilføjet sådanne regler, anvendes de systemdefinerede regler.

- Den primære nøgle deduplikeres.
  For poster med samme primære nøgle er **den mest udfyldte** post (den post, der har færrest null-værdier) vundet.
- Alle regler for match på tværs af objekter anvendes på objektet.
  Hvis objekt A f.eks. sammenholdes med objekt B på *FullName* og *DateofBirth*, er objekt A også deduplikeret af *FullName* og *DateofBirth*. Da *FullName* og *DateofBirth* er gyldige nøgler til identifikation af en kunde i objekt A, er disse nøgler også gyldige til identifikation af dubletkunder i objekt A.

## <a name="include-enriched-entities-preview"></a>Medtag forbedrede objekter (forhåndsversion)

Hvis du har forbedret objekter på datakildeniveau for at forbedre resultaterne af din samling, skal du markere dem. Du kan finde flere oplysninger i [Forbedring til datakilder](data-sources-enrichment.md).

1. Vælg **Brug forbedrede objekter** øverst på siden **Dublerede poster**.

1. Vælg et eller flere forbedrede objekter i ruden **Brug forbedrede objekter**.

1. Vælg **Udført**.

## <a name="define-deduplication-rules"></a>Definere deduplikeringsregler

1. Vælg et objekt på siden **Dublerede poster**, og vælg **Tilføj regel** for at definere reglerne for deduplikering.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Skærmbillede af siden Dublerede poster, hvor objektet er fremhævet, og Tilføj regel vises"  lightbox="media/m3_duplicates_showmore.png":::

   1. Angiv følgende oplysninger i ruden **Tilføj regel**:
      - **Vælg felt**: Vælg på listen over tilgængelige felter fra det objekt, du vil søge efter dubletter for. Vælg felter, der sandsynligvis er entydige for hver enkelt kunde. Det kan f.eks. være en mailadresse eller en kombination af navn, by og telefonnummer.
      - **Normaliser**: Vælg mellem følgende normaliseringsindstillinger for de valgte attributter.
        - **Tal**: Konverterer andre talsystemer, f.eks. romertal til arabertal. *VIII* bliver til *8*.
        - **Symboler**: Fjerner alle symboler og specialtegn. *Head&Shoulder* bliver til *HeadShoulder*.
        - **Tekst til små bogstaver: Konverterer alle tegn til små bogstaver**. *ALL CAPS og Titel, små/store bogstaver* bliver til *all caps og titel, små/store bogstaver*.
        - **Type (Telefon, Navn, Adresse, Organisation)**: Standardiserer navne, titler, telefonnumre, adresser osv.
        - **Unicode til ASCII**: Konverter Unicode-format til ASCII-tegn. */u00B2* bliver til *2*.
        - **Blanktegn**: Fjerner alle mellemrum. *Hej   verden* bliver til *Hejverden*.
      - **Præcision** : Angiv det præcisionsniveau, der skal gælde for denne betingelse.
        - **Grundlæggende**: Vælg mellem *Lav (30 %)*, *Mellem (60 %)*, *Høj (80 %)* og *Nøjagtig (100 %)*. Vælg **Nøjagtig**, hvis du kun vil matche poster, der svarer til 100 procent.
        - **Brugerdefineret** : Angiv en procentdel, som posterne skal matche. Systemet vil kun matche poster, der opfylder denne grænse.
      - **Navn**: Navn på reglen.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Skærmbillede af ruden Tilføj regel til fjernelse af dubletter.":::

   1. Du kan også vælge **Tilføj** > **Tilføj betingelse** for at føje flere betingelser til reglen. Betingelser er knyttet til en logisk AND-operator og køres derfor kun, hvis alle betingelser er opfyldt.

   1. Det er også muligt at **Tilføj** > **Tilføj undtagelse** for at [føje undtagelser til reglen](match-entities.md#add-exceptions-to-a-rule). Undtagelser bruges til at adressere sjældne tilfælde af falsk positive og false negativer.

   1. Vælg **Udført** for at oprette reglen.

1. Du kan også [tilføje flere regler](#define-deduplication-rules).

1. Vælg et objekt, og derefter **Rediger indstillingerne for fletning**.

1. Gør følgende i ruden **Flet præferencer**:
   1. Vælg en af tre indstillinger for at bestemme, hvilken post der skal bevares, hvis der findes en dublet:
      - **Flest udfyldte**: Identificerer posten med de fleste udfyldte attributfelter som vinderposten. Dette er standardfletteindstillingen.
      - **Nyeste**: Identificerer vinderposten baseret på de nyeste. Kræver en dato eller et numerisk felt for at definere nyeste.
      - **Mindst nyeste**: Identificerer vinderposten baseret på de mindst nyeste. Kræver en dato eller et numerisk felt for at definere nyeste.

      Hvis der opstår problemer, er vinderposten den post, der har værdien MAKS (PK) eller den større primære nøgle.

   1. Du kan også definere indstillinger for fletning for individuelle attributter for et objekt ved at vælge **Avanceret** nederst i ruden. Du kan f.eks. vælge at bevare den nyeste e-mail og den mest fuldstændige adresse fra forskellige poster. Udvid objektet for at se alle attributterne, og definer, hvilken indstilling der skal bruges til de enkelte attributter. Hvis du vælger en rekursbaseret indstilling, skal du også angive et dato/klokkeslætsfelt, der definerer rekursen.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Ruden med indstillinger for avanceret fletning viser den nyeste e-mail og den fuldstændige adresse":::

   1. Vælg **Fuldført** for at anvende flettepræferencer.

1. Når du har defineret reglerne for duplikering og flettet indstillingerne, skal du vælge **Næste**.
  
> [!div class="nextstepaction"]
> [Næste trin for et enkelt objekt: Unify felter](merge-entities.md)

> [!div class="nextstepaction"]
> [Næste trin for flere objekter: Matching betingelser](match-entities.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
