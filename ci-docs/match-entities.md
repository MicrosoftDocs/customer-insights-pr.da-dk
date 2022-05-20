---
title: Match objekter til datasamling
description: Sammenlign objekter for at oprette samlede kundeprofiler.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bc470dd932c2c981adc5840bb52d60f8dfe0de61
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740942"
---
# <a name="match-conditions"></a>Match betingelser

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

I dette trin i en samling defineres match-rækkefølgen og reglerne for matching på tværs af objekter. Dette trin kræver mindst to objekter.

> [!NOTE]
> Når du har oprettet match-vilkårene og valgt **Næste**, kan du ikke fjerne et valgt objekt eller en valgt attribut. Vælg om nødvendigt **Tilbage** for at gennemse de valgte objekter og attributter, inden du fortsætter.

## <a name="include-enriched-entities-preview"></a>Medtag forbedrede objekter (forhåndsversion)

Hvis du har forbedret objekter på datakildeniveau for at forbedre resultaterne af din samling, skal du markere dem. Du kan finde flere oplysninger i [Forbedring til datakilder](data-sources-enrichment.md). Hvis du har valgt forbedrede objekter på siden **Dublerede poster**, behøver du ikke at markere dem igen.

1. Vælg **Brug forbedrede objekter** øverst på siden **Matching poster**.

1. Vælg et eller flere forbedrede objekter i ruden **Brug forbedrede objekter**.

1. Vælg **Udført**.

## <a name="specify-the-match-order"></a>Angive matchrækkefølgen

Hvert match samler to eller flere objekter i ét samlet konsolideret objekt. Samtidig opbevares de entydige kundeposter. Overensstemmelsesrækkefølgen angiver den rækkefølge, som systemet forsøger at matche posterne i.

> [!IMPORTANT]
> Det første objekt på listen kaldes det primære objekt. Det primære objekt fungerer som udgangspunkt for dine ensartede profiler datasæt. Der føjes flere objekter, der er valgt, til dette objekt.
>
> Vigtige overvejelser:
>
> - Vælg det objekt, der har de mest fuldstændige og pålidelige profildata om kunderne, som det primære objekt.
> - Vælg det objekt, der har flere attributter til fælles med andre objekter (f.eks. navn, telefonnummer eller e-mailadresse) som det primære objekt.

1. På siden **Matching betingelser** kan du bruge pilene op og pil ned for at flytte objekterne i den ønskede rækkefølge eller trække og slippe dem. Du kan f.eks. vælge **Contacts:eCommerce** som det primære objekt og **CustomerLoyalty:Loyalty** som sekundære objekt.

1. Hvis du have alle poster i objektet som en entydig kunde, uanset om der findes et match, skal du vælge **Inkludér alle poster**. Alle poster i dette objekt, der ikke stemmer overens med poster i andre objekter, medtages i den samlede profil. Poster, der ikke stemmer overens, kaldes singletoner.
  
Det primære objekt *Contacts:eCommerce* matches med det næste objekt *CustomerLoyalty:Loyalty*. Det datasæt resultat fra første matchtrin sammenholdes med følgende objekt, hvis du har mere end to objekter.

:::image type="content" source="media/m3_match.png" alt-text="Skærmbillede af den valgte match-rækkefølge for objekterne." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definere regler for matchpar

Matchregler angiver den logik, som et bestemt par af objekter skal matches efter. En regel består af en eller flere betingelser.

Advarslen ud for et objektnavn betyder, at der ikke er defineret en match-regel for et match-par.

1. Vælg **Tilføj regel** for et objektpar for at definere match-regler.

1. Konfigurer betingelserne for reglen i ruden **Tilføj regel**.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Skærmbillede af ruden Tilføj regel.":::

   - **Vælg Objekt/felt (første række)**: Vælg et relateret objekt og en attribut for at angive en postegenskab, der sandsynligvis er entydig for en kunde. Et eksempel er et telefonnummer eller en mailadresse. Undgå matchning efter aktivitetstypeattributter. Et købs-id vil f.eks. højst sandsynligt ikke findes i andre posttyper.

   - **Vælg Objekt/felt (anden række)**: Vælg en attribut, der er relateret til attributten for det objekt, der er angivet i første række.

   - **Normaliser**: Vælg mellem følgende normaliseringsindstillinger for de valgte attributter.
     - **Tal**: Konverterer andre talsystemer, f.eks. romertal til arabertal. *VIII* bliver til *8*.
     - **Symboler**: Fjerner alle symboler og specialtegn. *Head&Shoulder* bliver til *HeadShoulder*.
     - **Tekst til små bogstaver**: Konverterer alle tegn til små bogstaver. *ALL CAPS og Titel, små/store bogstaver* bliver til *all caps og titel, små/store bogstaver*.
     - **Type (Telefon, Navn, Adresse, Organisation)**: Standardiserer navne, titler, telefonnumre, adresser og organisationer.
     - **Unicode til ASCII**: Konverter Unicode-format til ASCII-tegn. */u00B2* bliver til *2*.
     - **Blanktegn**: Fjerner alle mellemrum. *Hej   verden* bliver til *Hejverden*.

   - **Præcision** : Angiv det præcisionsniveau, der skal gælde for denne betingelse.
     - **Grundlæggende**: Vælg mellem *Lav (30 %)*, *Mellem (60 %)*, *Høj (80 %)* og *Nøjagtig (100 %)*. Vælg **Nøjagtig**, hvis du kun vil matche poster, der svarer til 100 procent.
     - **Brugerdefineret** : Angiv en procentdel, som posterne skal matche. Systemet vil kun matche poster, der opfylder denne grænse.

   - **Navn**: Navn på reglen.

1. Hvis du kun vil matche objekter, hvis attributterne opfylder flere betingelser, skal du vælge **Tilføj** > **Tilføj betingelse** for at føje flere betingelser til en match-regel. Betingelser er knyttet til en logisk AND-operator og køres derfor kun, hvis alle betingelser er opfyldt.

1. Du kan også overveje avancerede indstillinger, f.eks. [undtagelser](#add-exceptions-to-a-rule) eller [betingelser for brugerdefineret match](#specify-custom-match-conditions).

1. Vælg **Udført** for at afslutte reglen.

1. Du kan også [tilføje flere regler](#add-rules-to-a-match-pair).

1. Klik på **Næste**.

> [!div class="nextstepaction"]
> [Næste trin: Unify felter](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Føje regler til et matchpar

Matchregler repræsenterer sæt af betingelser. Hvis du vil matche objekter efter betingelser ud fra flere attributter, skal du tilføje flere regler.

1. Vælg **Tilføj regel** for det objekt, du vil føje regler til.

1. Følg trinnene under [Definer regler for matchpar](#define-rules-for-match-pairs).

> [!NOTE]
> Rækkefølgen af regler er vigtig. Den matching algoritme forsøger at matche en bestemt kundepost på baggrund af din første regel og fortsætter kun til den anden regel, hvis der ikke blev identificeret nogen matches med den første regel.

## <a name="advanced-options"></a>Avancerede indstillinger

### <a name="add-exceptions-to-a-rule"></a>Føje undtagelser til en regel

I de fleste tilfælde fører objektets matching til entydige kundeprofiler med samlede data. Hvis du dynamisk vil håndtere sjældne tilfælde af falsk positive og false negativer, kan du definere undtagelser for en overensstemmelsesregel. Undtagelser anvendes efter behandling af overensstemmelsesreglerne og undgå matchning af alle poster, der opfylder undtagelseskriterierne.

Hvis din matchregel f.eks. kombinerer efternavn, by og fødselsdato, identificerer systemet de samme efternavn, der lever i samme bybillede som den samme profil. Du kan angive en undtagelse, der ikke stemmer overens med profilerne, hvis fornavn i de objekter, du kombinerer, ikke er de samme.

1. I ruden **Rediger regel**, vælg **Tilføj** > **Tilføj undtagelse**.

1. Angiv undtagelseskriterierne.

1. Vælg **Udført** for at gemme reglen.

### <a name="specify-custom-match-conditions"></a>Angive brugerdefinerede matchbetingelser

Du kan angive betingelser, der tilsidesætter standardoverensstemmelseslogikken. Der findes følgende fire indstillinger:

|Mulighed  |Description |Eksempel  |
|---------|---------|---------|
|Match altid     | Definerer værdier, der altid sammenholdes.         |  Du skal altid matche *Mike* og *MikeR*.       |
|Match aldrig     | Definerer værdier, der aldrig matcher.        | Du skal aldrig matche *John* og *Jonathan*.        |
|Brugerdefineret tilsidesætter     | Definerer værdier, som systemet altid skal ignorere i match-fasen. |  Ignorer værdierne *11111* og *Ukendt* under match.        |
|Aliastilknytning    | Definition af værdier, som skal overvejes som den samme værdi i systemet.         | Overvej, om *Joe* skal være lig *Joseph*.        |

1. Vælg **Brugerdefineret**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Knappen Brugerdefineret":::

1. Vælg **Brugerdefineret type,** og vælg **Hent skabelon**. Du skal bruge en separat skabelon for hver enkelt matchindstilling.

1. Åbn den hentede skabelonfil, og udfyld detaljerne. Skabelonen indeholder felter til angivelse af det objekt og de primære nøgleværdier for objektet, der skal bruges i det brugerdefinerede match. Hvis din primære nøgle *12345* fra objektet *Salg* f.eks. altid skal matche den primære nøgle *34567* fra objektet *Kontakt*, skal du udfylde skabelonen:
    - Entity1: Salg
    - Entity1Key: 12345
    - Entity2: Kontakt
    - Entity2Key: 34567

   Den samme skabelonfil kan angive brugerdefinerede matchposter fra flere objekter.

   Hvis du vil angive brugerdefineret matchning for deduplikering for et objekt, skal du angive det samme objekt som både Objekt1 og Objekt2 og angive de forskellige værdier for primære nøgler.

1. Når du har tilføjet alle tilsidesættelser, skal du gemme skabelonfilen.

1. Gå til **Data** > **Datakilder**, og indsæt skabelonfilerne som nye objekter.

1. Når filerne er overført, skal du vælge den indstillingen **Brugerdefineret** igen. Vælg de nødvendige objekter på rullelisten, og vælg **Udført**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Skærmbillede af dialogboksen til valg af tilsidesættelser for et brugerdefineret matchscenario.":::

1. Anvendelse af det brugerdefinerede match afhænger af den matchindstilling, du vil bruge.

   - Fortsæt til næste trin for **Altid at matche** eller **Aldrig at matche**.
   - For **Omgå** eller **Aliastilknytning** skal du vælge **Rediger** for en eksisterende match-regel eller oprette en ny regel. Vælg indstillingen **Brugerdefineret bypass** eller **Alias-tilknytning** på rullelisten Normaliseringer, og vælg **Udført**.

1. Vælg **Udført** i ruden **Brugerdefineret** for at anvende den brugerdefinerede match-konfiguration.

> [!div class="nextstepaction"]
> [Næste trin: Unify felter](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
