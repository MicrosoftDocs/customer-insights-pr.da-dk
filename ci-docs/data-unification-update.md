---
title: Opdater samlingsindstillingerne
description: Opdater regler for dubletter, regler for overensstemmelse eller ensartede felter i indstillingerne for samling.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: a7cf06c07e4b95b848a55dfe5fe0b09397fe744e
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245587"
---
# <a name="update-the-unification-settings"></a>Opdater samlingsindstillingerne

Hvis du vil gennemse eller ændre indstillingerne for samling, når der er oprettet en unified profil, skal du udføre følgende trin.

1. Gå til **Data** > **Samle**.

   :::image type="content" source="media/m3_unified.png" alt-text="Skærmbillede af siden Data Unify, når dataene er samlet.":::

   > [!TIP]
   > Feltet **Matching betingelser** vises kun, hvis der er valgt flere objekter.

1. Vælg, hvad du vil opdatere:
   - [Kildefelter](#edit-source-fields) til tilføjelse af objekter eller attributter eller ændring af attributtyper.
   - [Dublerede poster](#manage-deduplication-rules) for at administrere regler for dubletter eller flette indstillinger.
   - [Tilsvarende betingelser](#manage-match-rules) for opdatering af matchning-regler på tværs af to eller flere objekter.
   - [Ensartede kundefelter](#manage-unified-fields) for at felter kan kombineres eller udelades. Du kan også gruppere relaterede profiler i klynger.

1. Når du har foretaget ændringerne, skal du vælge den næste indstilling:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Skærmbillede af siden Data Unify, hvor indstillingerne Unify er fremhævet.":::

   - Hvis du vil evaluere kvaliteten af matchning-betingelserne (uden at deduplikere og matche regler) uden at opdatere den samlede profil, skal du se [Kørsel af matching-betingelser](#run-matching-conditions). Indstillingen **Kør kun matching betingelser** vises ikke for det enkelte objekt.
   - [Foren kundeprofiler](#run-updates-to-the-unified-customer-profile) for at køre mach af betingelser of opdatere unified customer profile-objektet, uden at det påvirker afhængigheder (f.eks. afhængigheder, segmenter eller mål). Afhængige processer køres ikke, men opdateres som [defineret i opdateringsplanen](schedule-refresh.md).
   - [Foren kundeprofiler og afhængigheder](#run-updates-to-the-unified-customer-profile) for at køre mach af betingelser of opdatere unified customer profile-objektet og alle afhængigheder (f.eks. afhængigheder, segmenter eller mål). Alle processer køres automatisk igen.

## <a name="edit-source-fields"></a>Rediger kildefelter

Du kan ikke fjerne en attribut eller et objekt, hvis de allerede er blevet samlet.

1. Vælg **Rediger** i ruden **Kildefelter**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Skærmbillede af side med kildefelter, der viser antallet af primære nøgler, tilknyttede og ikke-tilknyttede felter":::

   Antallet af tilknyttede og ikke-tilknyttede felter vises.

1. Vælg **Vælg objekter og felter** for at tilføje andre attributter eller objekter. Brug søgning eller rulning til at søge efter og vælge de ønskede attributter og objekter. Vælg **Anvend**.

1. Du kan også ændre den primære nøgle for et objekt, attributtyperne og skifte **Intelligent tilknytning** til eller fra. Du kan finde flere oplysninger i [Vælge primær nøgle og semantisk type for attributter](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Vælg **Næste** for at foretage ændringer af regler for duplikering, eller vælg **Gem og luk**, og vend tilbage til [Opdater indstillingerne for samling](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Administrere deduplikeringsregler

1. Vælg **Rediger** i ruden **Dublerede poster**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Skærmbillede af siden Dublerede poster, der viser antallet af duplikerede poster" lightbox="media/m3_duplicates_edit.png":::

   Antallet af Dublerede poster, der blev fundet, vises under **Dubletter**. Kolonnen **Poster, der er dubleret** viser, hvilke objekter der indeholder dubletposter, og procentdelen af duplikerede poster.

1. Hvis du har tilføjet et forbedret objekt, skal du vælge **Brug forbedrede objekter**. Du kan finde flere oplysninger i [Forbedring til datakilder](data-sources-enrichment.md).

1. Du kan administrere regler for duplikering ved at vælge en af følgende indstillinger:
   - **Opret en ny regel**: Vælg **Tilføj regel** under det relevante objekt. Du kan finde flere oplysninger i [Definition af deduplikeringsregler](remove-duplicates.md#define-deduplication-rules).
   - **Rediger regelbetingelser**: Markér reglen, og derefter **Rediger**. Rediger felter, tilføj eller fjern betingelser, eller tilføj eller fjern undtagelser.
   - **Forhåndsversion**: Vælg reglen, og se derefter **Forhåndsversion** for at få vist de seneste resultater af kørslen for denne regel.
   - **Deaktiver en regel**: Markér reglen, og derefter **Deaktiver** for at bevare en duplikeringsregel, samtidig med at den udelukkes fra matchning-processen.
   - **Dupliker en regel**: Markér reglen, og derefter **Dupliker** for at oprette en lignende regel med ændringer.
   - **Slet en regel**: Markér reglen, og derefter **Slet**.

1. Hvis du vil ændre indstillingerne for fletning, skal du markere objektet. Du kan kun ændre indstillingerne, hvis der oprettes en regel.
   1. Vælg **Rediger indstillingerne for fletning**, og rediger indstillingen **Post, der skal bevares**.
   1. Hvis du vil ændre indstillingerne for fletning for individuelle attributter for et objekt, skal du vælge **Avanceret** og foretage de nødvendige ændringer.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Skærmbillede af indstillinger for avanceret fletning, der viser den nyeste e-mail og den mest fuldstændige adresse":::

   1. Vælg **Udført**.

1. Vælg **Næste** for at foretage ændringer af betingelser for matching, eller vælg **Gem og luk**, og vend tilbage til [Opdater indstillingerne for samling](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Administrere matchregler

Du kan omkonfigurere og finjustere de fleste af matchparametrene. Du kan ikke tilføje eller slette objekter. Match-regler gælder ikke for et enkelt objekt.

1. Vælg **Rediger** i ruden **Matching betingelser**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Skærmbillede af siden med Matching regler og betingelser med statistikker." lightbox="media/m3_match_edit.png":::

   På siden vises matching-rækkefølgen og definerede regler og følgende statistiske data:
   - **Entydige kildeposter** viser antallet af individuelle kildeposter, der blev behandlet i sidste matchkørsel.
   - **Matchede og ikke-matchede poster** fremhæver, hvor mange entydige poster der er tilbage efter behandling af matchreglerne.
   - **Kun matchede poster** viser kun antallet af matches på tværs af alle dine matchpar.

1. Du kan få vist resultaterne af alle regler og deres pointtal ved at vælge **Vis sidste kørsel**. Resultaterne vises, herunder de alternative kontakt-ID'er. Du kan hente resultaterne.

1. Hvis du vil have vist resultaterne og pointtal for en bestemt regel, skal du vælge reglen og derefter **Forhåndsversion**. Resultaterne vises. Du kan hente resultaterne.

1. Hvis du vil have vist resultaterne for en bestemt regel, skal du vælge reglen og derefter **Rediger**. Vælg **Forhåndsversion** i ruden Rediger under betingelsen. Du kan hente resultaterne.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafisk repræsentation af ikke-matchede og matchede poster, herunder en liste over data.":::

1. Hvis du har tilføjet et forbedret objekt, skal du vælge **Brug forbedrede objekter**. Du kan finde flere oplysninger i [Forbedring til datakilder](data-sources-enrichment.md).

1. Du kan administrere regler ved at vælge en af følgende indstillinger:
   - **Opret en ny regel**: Vælg **Tilføj regel** under det relevante objekt. Du kan finde flere oplysninger under [Definere regler for matchpar](match-entities.md#define-rules-for-match-pairs).
   - **Rediger rækkefølgen af reglerne**, hvis du har defineret flere regler: Træk og slip reglerne i den ønskede rækkefølge. Du kan finde flere oplysninger i [Angiv match-rækkefølge](match-entities.md#specify-the-match-order).
   - **Rediger regelbetingelser**: Markér reglen, og derefter **Rediger**. Rediger felter, tilføj eller fjern betingelser, eller tilføj eller fjern undtagelser.
   - **Deaktiver en regel**: Markér reglen, og derefter **Deaktiver** for at bevare en match-regel, samtidig med at den udelukkes fra matching-processen.
   - **Dupliker en regel**: Markér reglen, og derefter **Dupliker** for at oprette en lignende regel med ændringer.
   - **Slet en regel**: Markér reglen, og derefter **Slet**.

1. Vælg **Næste** for at foretage ændringer af samlede felter, eller vælg **Gem og luk**, og vend tilbage til [Opdater indstillingerne for samling](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Administrere samlede felter

1. Vælg **Rediger** i ruden **Unified customer fields**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Skærmbillede af Unified customer-felter":::

1. Gennemse de kombinerede og udelukkede felter, og foretag eventuelle ændringer efter behov. Tilføjelse eller redigering af CustomerID-nøglen eller gruppeprofiler i klynger. Du kan finde flere oplysninger i [Unify customer fields](merge-entities.md).

1. Vælg **Næste** for at gennemse indstillingerne for samling og [opdatere den samlede profil og afhængighederne](#run-updates-to-the-unified-customer-profile), eller vælg **Gem og luk**, og vend tilbage til [Opdater indstillingerne for samling](#update-the-unification-settings) for at foretage flere ændringer.

## <a name="run-matching-conditions"></a>Køre matchende betingelser

Kør matchningsbetingelser kører kun regler for duplikering og overensstemmelse og opdaterer objekterne *Deduplication_* og *ConflationMatchPair*.

1. På siden **Data** > **Unify** vælges **Kør kun matchende betingelser**.

   Felterne **Dublerede poster** og **Matchende betingelser** vises i status **Kø** eller **Opdaterer**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Når matching-processen er fuldført, skal du vælge **Rediger** i feltet **Matchende betingelser**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Beskåret skærmbillede af nøglemålepunkter på siden Match med tal og detaljer.":::

1. Hvis du vil foretage ændringer, skal du se [Administrere regler for duplikering](#manage-deduplication-rules) eller [Administrere matching-regler](#manage-match-rules).

1. Kør match-processen igen, eller [kør opdateringer til kundeprofilen](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Kør opdateringer til unified customer profile

1. På siden **Data** > **Unify** vælges:

   - **Foren kundeprofiler**: Kører mach af betingelser of opdateringer af unified customer profile-objektet, uden at det påvirker afhængigheder (f.eks. afhængigheder, segmenter eller mål). Afhængige processer køres ikke, men opdateres som [defineret i opdateringsplanen](schedule-refresh.md).

   - **Unify kundeprofiler og afhængigheder**: Kører matchende betingelser og opdateringer af den samlede profil og alle afhængigheder. Alle processer køres automatisk igen. Når alle downstream-processer er fuldført, afspejler kundeprofilen de opdaterede data.

   Felterne **Dublerede poster**, **Matchende betingelser** og **Unified customer-felter** viser status **Sat i kø** eller **Opdaterer**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Resultaterne af en vellykket kørsel vises på siden **Unify**, der viser antallet af samlede kundeprofiler.
