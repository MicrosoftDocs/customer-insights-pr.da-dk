---
title: Opdatere samlingsindstillingerne for kunde, firma eller kontakt
description: Opdater regler for dubletter, matchregler eller samlede felter i indstillingerne for kunde- eller firmasamling.
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392464"
---
# <a name="update-unification-settings"></a>Opdatere samlingsindstillinger

Hvis du vil gennemse eller ændre indstillingerne for samling, når der er oprettet en unified profil, skal du udføre følgende trin.

1. Gå til **Data** > **Samle**.

   For de enkelte kunder (B-til-C) viser siden **Samle** antallet af samlede kundeprofiler og felter for hvert samlingstrin.

   :::image type="content" source="media/m3_unified.png" alt-text="Skærmbillede af siden Data Unify, når dataene er samlet." lightbox="media/m3_unified.png":::

   For forretningskonti (B-til-B) viser siden **Samle** antallet af samlede firmaprofiler og felter for hvert firmasamlingstrin. Hvis kontakter er samlet, vises antallet af samlede kontaktprofiler og felter for hver af trinene i den samlede kontakt. Vælg det relevante felt under **Foren firmaer** eller **Foren kontakter (forhåndsversion)**, afhængigt af hvad du vil opdatere.

   :::image type="content" source="media/b2b_unified.png" alt-text="Skærmbillede af siden Samle data, når firma- og kontaktdata er samlet." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Feltet **Matching betingelser** vises kun, hvis der er valgt flere objekter.

1. Vælg, hvad du vil opdatere:
   - [Kildefelter](#edit-source-fields) til tilføjelse af objekter eller attributter eller ændring af attributtyper. Hvis du vil fjerne en attribut, skal du se [Fjerne et forenet felt](#remove-a-unified-field). Hvis du vil fjerne et objekt, skal du se [Fjerne et forenet objekt](#remove-a-unified-entity).
   - [Dublerede poster](#manage-deduplication-rules) for at administrere regler for dubletter eller flette indstillinger.
   - [Tilsvarende betingelser](#manage-match-rules) for opdatering af matchning-regler på tværs af to eller flere objekter.
   - [Ensartede kundefelter](#manage-unified-fields) for at felter kan kombineres eller udelades. Du kan også gruppere relaterede profiler i klynger.
   - [Semantiske felter](#manage-semantic-fields-for-unified-contacts) til administration af semantiske typer for samlede kontaktfelter.
   - [Relationer](#manage-contact-and-account-relationships) til at administrere relationen mellem kontakt og firma.

1. Når du har foretaget ændringerne, skal du vælge den næste indstilling:

   - Hvis du vil evaluere kvaliteten af matchning-betingelserne (uden at deduplikere og matche regler) uden at opdatere den samlede profil, skal du se [Kørsel af matching-betingelser](#run-matching-conditions). Indstillingen **Kør kun matching betingelser** vises ikke for det enkelte objekt.
   - [Foren profiler](#run-updates-to-the-unified-profile) for at køre mach af betingelser of opdatere det forenede profilobjekt, uden at det påvirker afhængigheder (f.eks. forbedringer, segmenter eller målinger). Afhængige processer køres ikke, men opdateres som [defineret i opdateringsplanen](schedule-refresh.md).
   - [Foren profiler og afhængigheder](#run-updates-to-the-unified-profile) for at køre match af betingelser, opdatere det forenede profilobjekt og opdatere alle afhængigheder (f.eks. forbedringer, segmenter eller målinger). Alle processer køres automatisk igen. I B-til-B køres samling på både firma- og kontaktpersonobjekter, og der opdateres forenede profiler.

## <a name="edit-source-fields"></a>Rediger kildefelter

1. Vælg **Rediger** i ruden **Kildefelter**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Skærmbillede af side med kildefelter, der viser antallet af primære nøgler, tilknyttede og ikke-tilknyttede felter":::

   Antallet af tilknyttede og ikke-tilknyttede felter vises.

1. Vælg **Vælg objekter og felter** for at tilføje andre attributter eller objekter.

1. Du kan også ændre den primære nøgle for et objekt, attributtyperne og skifte **Intelligent tilknytning** til eller fra. Du kan finde flere oplysninger i [Vælg kildefelter](map-entities.md).

1. Vælg **Næste** for at foretage ændringer af regler for duplikering, eller vælg **Gem og luk**, og vend tilbage til [Opdatere samlingsindstillinger](#update-unification-settings).

### <a name="remove-a-unified-field"></a>Fjerne et forenet felt

Hvis du vil fjerne et felt, der er blevet forenet, skal feltet fjernes fra alle afhængigheder, f.eks. segmenter, mål, forbedringer eller relationer.

1. Når alle afhængigheder for feltet er fjernet, skal du gå til **Data** > **Foren**.

1. Vælg **Rediger** i ruden **Samlede kundefelter**.

1. Markér alle forekomster af feltet, og vælg derefter **Udelad**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Skærmbillede af siden Samlede kundefelter, der viser markerede felter og knappen Udelad":::

1. Vælg **Udført** for at bekræfte, og vælg derefter **Gem og luk**.

   > [!TIP]
   > Hvis du får vist meddelelsen "En forening kunne ikke gemmes. Den angivne ressource kan ikke ændres eller slettes pga. downstream-afhængigheder". bruges feltet stadig i en downstream-afhængighed.

1. Hvis feltet bruges i en regel for dubletposter eller matchbetingelser, skal du udføre følgende trin. Ellers skal du gå til det næste trin.
   1. Vælg **Rediger** i ruden **Dublerede poster**.
   1. Fjern feltet fra alle de regler, det eventuelt bruges i, og vælg derefter **Næste**.
   1. Fjern feltet fra alle de regler, det eventuelt bruges i, på siden **Matchende betingelser**, og vælg derefter **Gem og luk**.
   1. Vælg **Foren** > **Foren kundeprofiler og afhængigheder**. Vent, indtil foreningen er fuldført, før du går videre til næste trin.

1. Vælg **Rediger** i ruden **Kildefelter**.

1. Markér **Vælg objekter og felter**, og fjern markeringen i afkrydsningsfeltet ud for hver forekomst af feltet.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Skærmbillede af dialogboksen Vælg objekter og felter, hvor der vises afkrydsningsfelter uden markering":::

1. Vælg **Anvend**.

1. Vælg **Gem og luk**.

1. Vælg **Foren** > **Foren kundeprofiler og afhængigheder** for at opdatere den samlede profil.

### <a name="remove-a-unified-entity"></a>Fjerne et forenet objekt

Hvis du vil fjerne et objekt, der er blevet forenet, skal objektet fjernes fra alle afhængigheder, f.eks. segmenter, mål, forbedringer eller relationer.

1. Når alle afhængigheder for objektet er fjernet, skal du gå til **Data** > **Foren**.

1. Vælg **Rediger** i ruden **Samlede kundefelter**.

1. Vælg alle felterne for objektet, og vælg derefter **Udelad**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Skærmbillede af Samlede kundefelter med alle felter for et objekt og knappen Udelad":::

1. Vælg **Udført** for at bekræfte, og vælg derefter **Gem og luk**.

   > [!TIP]
   > Hvis du får vist meddelelsen "En forening kunne ikke gemmes. Den angivne ressource kan ikke ændres eller slettes pga. downstream-afhængigheder", bruges objektet stadig i en downstream-afhængighed.

1. Vælg **Rediger** i ruden **Dublerede poster**.

1. Fjern alle eventuelle regler fra objektet, og vælg derefter **Næste**.

1. Vælg objektet på siden **Matchende betingelser**, og vælg derefter **Slet**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Skærmbillede af Matchende betingelser med objektet valgt og knappen Slet":::

1. Vælg **Gem og luk**.

1. Vælg **Rediger** i ruden **Kildefelter**.

1. Markér **Vælg objekter og felter**, og fjern markeringen i afkrydsningsfeltet ud for objektet.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Skærmbillede af dialogboksen Vælg objekter og felter med objektafkrydsningsfelt uden markering":::

1. Vælg **Anvend**.

1. Vælg **Gem og luk**.

1. Vælg **Foren** > **Foren kundeprofiler og afhængigheder** for at opdatere den samlede profil.

## <a name="manage-deduplication-rules"></a>Administrere deduplikeringsregler

1. Vælg **Rediger** i ruden **Dublerede poster**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Skærmbillede af siden Dublerede poster, der viser antallet af duplikerede poster" lightbox="media/m3_duplicates_edit.png":::

   Antallet af Dublerede poster, der blev fundet, vises under **Dubletter**. Kolonnen **Poster, der er dubleret** viser, hvilke objekter der indeholder dubletposter, og procentdelen af duplikerede poster.

1. Hvis du vil bruge et forbedret objekt, skal du vælge **Brug forbedrede objekter**. Du kan finde flere oplysninger i [Forbedring til datakilder](data-sources-enrichment.md).

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

   1. Vælg **Udført**.

1. Vælg **Næste** for at foretage ændringer af betingelser for matching, eller vælg **Gem og luk**, og vend tilbage til [Opdatere samlingsindstillinger](#update-unification-settings).

## <a name="manage-match-rules"></a>Administrere matchregler

Du kan omkonfigurere og finjustere de fleste af matchparametrene. Du kan ikke tilføje eller slette objekter. Match-regler gælder ikke for et enkelt objekt.

1. Vælg **Rediger** i ruden **Matching betingelser**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Skærmbillede af siden med Matching regler og betingelser med statistikker." lightbox="media/m3_match_edit.png":::

   På siden vises matching-rækkefølgen og definerede regler og følgende statistiske data:
   - **Entydige kildeposter** viser antallet af individuelle kildeposter, der blev behandlet i sidste matchkørsel.
   - **Matchede og ikke-matchede poster** fremhæver, hvor mange entydige poster der er tilbage efter behandling af matchreglerne.
   - **Kun matchede poster** viser kun antallet af matches på tværs af alle dine matchpar.

1. Du kan få vist resultaterne af alle regler og deres pointtal ved at vælge **Vis sidste kørsel**. Resultaterne vises, herunder de alternative kontakt-id'er. Du kan hente resultaterne.

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

1. Vælg **Næste** for at foretage ændringer af samlede felter, eller vælg **Gem og luk**, og vend tilbage til [Opdatere samlingsindstillinger](#update-unification-settings).

## <a name="manage-unified-fields"></a>Administrere samlede felter

1. Vælg **Rediger** i ruden **Unified customer fields**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Skærmbillede af Unified customer-felter":::

1. Gennemse de kombinerede og udelukkede felter, og foretag eventuelle ændringer efter behov. Tilføjelse eller redigering af CustomerID-nøglen eller gruppeprofiler i klynger. Du kan finde flere oplysninger i [Unify customer fields](merge-entities.md).

1. Vælg **Næste** for at gennemse og [opdatere den samlede profil og afhængighederne](#run-updates-to-the-unified-profile) for kunder eller firmaer. Eller vælg **Gem og luk**, og vend tilbage til [Opdatere samlingsindstillinger](#update-unification-settings) for at foretage flere ændringer.

   For kontakter skal du vælge **Næste** for at administrere semantiske felter. Eller vælg **Gem og luk**, og vend tilbage til [Opdatere samlingsindstillinger](#update-unification-settings) for at foretage flere ændringer.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Administrere semantiske felter for samlede kontakter

1. Vælg **Rediger** i feltet **Semantiske felter**.

1. Hvis du vil ændre den semantiske type for et samlet felt, skal du vælge en ny type. Du kan finde flere oplysninger under [Definere de semantiske felter for samlede kontakter](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Vælg **Næste** for at administrere relationen mellem firma og kontakt, eller vælg **Gem og luk**, og vend tilbage til [Opdatere samlingsindstillinger](#update-unification-settings).

## <a name="manage-contact-and-account-relationships"></a>Administrere firma- og kontaktrelationer

1. Vælg **Rediger** på feltet **Relationer**.

1. Hvis du vil ændre kontakt- og firmarelationen, skal du ændre en af følgende oplysninger:

   - **Fremmed nøgle fra kontaktobjekt**: Vælg den attribut, der opretter forbindelse mellem kontaktobjektet og firmaet.
   - **Til firmaobjekt**: Vælg det firmaobjekt, der er knyttet til kontakten.

1. Vælg **Næste** for at gennemse indstillingerne for samling og [opdatere den samlede profil og afhængighederne](#run-updates-to-the-unified-profile), eller vælg **Gem og luk**, og vend tilbage til [Opdatere samlingsindstillinger](#update-unification-settings) for at foretage flere ændringer.

## <a name="run-matching-conditions"></a>Køre matchende betingelser

Kør matchningsbetingelser kører kun regler for duplikering og overensstemmelse og opdaterer objekterne *Deduplication_* og *ConflationMatchPair*.

1. På siden **Data** > **Unify** vælges **Kør kun matchende betingelser**.

   Felterne **Dublerede poster** og **Matchende betingelser** vises i status **Kø** eller **Opdaterer**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Når matching-processen er fuldført, skal du vælge **Rediger** i feltet **Matchende betingelser**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Beskåret skærmbillede af nøglemålepunkter på siden Match med tal og detaljer.":::

1. Hvis du vil foretage ændringer, skal du se [Administrere regler for duplikering](#manage-deduplication-rules) eller [Administrere matching-regler](#manage-match-rules).

1. Kør match-processen igen, eller [kør opdateringer til profilen](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Køre opdateringer til den samlede profil

- Hvis du vil køre matchningsbetingelser og opdatere det samlede profilobjekt, *uden* at det påvirker afhængigheder (f.eks. kundekort, forbedringer, segmenter eller mål), skal du vælge **Foren kundeprofiler**. For firmaer skal du vælge **Foren firmaer** > **Foren profiler**. For kontakter skal du vælge **Foren kontakter (forhåndsversion)** > **Foren profiler**. Afhængige processer køres ikke, men opdateres som [defineret i opdateringsplanen](schedule-refresh.md).
- Hvis du vil køre matchende betingelser, opdatere den samlede profil og køre alle afhængigheder, skal du vælge **Foren kundeprofiler og afhængigheder**. Alle processer køres automatisk igen. For firmaer og kontakter skal du vælge **Foren firmaer** > **Foren profiler og afhængigheder**. Matchningsbetingelserne køres for både firmaer og kontakter, hvor begge samlede profiler opdateres, og alle andre afhængigheder køres.

Alle felter undtagen **Kildefelter** viser statussen **I kø** eller **Opdaterer**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Resultaterne af en vellykket kørsel vises på siden **Foren**, der viser antallet af samlede profiler.
