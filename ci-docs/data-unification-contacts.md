---
title: Oprette en samlet kontaktprofil (forhåndsversion)
description: Gennemgå processen til samling af data for at oprette et enkelt datasæt med kontakter.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305014"
---
# <a name="create-a-unified-contact-profile-preview"></a>Oprette en samlet kontaktprofil (forhåndsversion)

Når du har [samlet forretningskonti](map-entities.md), kan du eventuelt samle kontakter for disse firmaer og knytte de samlede kontakter til de samlede firmaer. I processen til samling af kontakter tilknyttes kontaktdata fra flere datakilder, dubletter fjernes, dataene matches på tværs af objekter, semantisk tilknytning konfigureres, der oprettes relationer mellem kontakter og firmaer, og derefter oprettes der en samlet kontaktprofil.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

De første par trin er identiske med de samlende firmatrin.

## <a name="prerequisites"></a>Forudsætninger

Firma- og kontaktpersonposter skal have en entydig nøgle (kaldes en fremmed nøgle), der opretter forbindelse til dem. Det kan f.eks. være et firma-id, der findes i firmaposten og kontaktpersonposten, og som knytter firma- og kontaktpersonposten sammen.

## <a name="preview-limitations"></a>Begrænsninger i forhåndsversionen

- Kontakter, der ikke har et link til et firma, droppes.
- Hvis et firma deduplikeres, identificeres der en vinderpost baseret på indstillingerne for fletning. Taberposter vælges ikke og droppes derfor. Kontakter, der er knyttet til taberposter, droppes.
- Et firma kan have flere kontakter, men en kontakt knyttes til et enkelt firma.
- De kontaktattributter, der er tilknyttet i det semantiske tilknytningstrin, er de eneste attributter, der kan vises på kundekortet. Der findes dog 17 tilgængelige attributter.

## <a name="select-source-fields"></a>Vælg kildefelter

1. Vælg **Start her** under **Foren kontakter (forhåndsversion)**

1. [Vælg objekter og felter](map-entities.md) til kontaktdatakilderne, herunder de primære nøgler og attributtyper.

1. Vælg **Næste**.

## <a name="remove-duplicate-records"></a>Fjern dubletposter

1. Du kan også [definere deduplikeringsregler](remove-duplicates.md) for de valgte objekter.

1. Vælg **Næste**.

## <a name="match-conditions"></a>Match betingelser

1. [Definer matchrækkefølge og regler](match-entities.md) for matchning på tværs af objekter.

1. Vælg **Næste**.

## <a name="unify-contact-fields"></a>Forene kontaktfelter

1. [Kombinere og udelade kontaktfelter](merge-entities.md).

1. Vælg **Næste**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definer de semantiske felter for samlede kontakter

I dette trin i foreningsprocessen knyttes de samlede kontaktfelter til semantiske typer. I B-til-B viser kundekortene firmaer. Når kortet er valgt, vises alle de kontakter, der er knyttet til firmaet. De felter, du tilknytter i dette trin, er de felter, der vises på kortene.

1. Vælg den semantiske type, der knyttes til hvert samlet felt. Vælg **Ingen**, hvis en semantisk type ikke er tilgængelig.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Skærmbillede af siden Semantiske felter til at definere de semantiske typer." lightbox="media/semantic_mapping.png":::

1. Vælg **Næste**, når du har tilknyttet alle forenede felter.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Angiv relationen mellem kontakter og firmaer

Dette trin i foreningsprocessen knytter dine kontaktdata til de tilhørende firmadata.

1. Angiv følgende oplysninger for hvert enkelt objekt:

   - **Fremmed nøgle fra kontaktobjekt**: Vælg den attribut, der opretter forbindelse mellem kontaktobjektet og firmaet.
   - **Til firmaobjekt**: Vælg det firmaobjekt, der er knyttet til kontakten.

   :::image type="content" source="media/contact_relationship.png" alt-text="Skærmbillede af siden Relation for at oprette forbindelse mellem kontakt- og firmaobjekter.":::

1. Vælg **Næste**.

## <a name="review-contact-unification"></a>Gennemgå kontaktsamling

Gennemse oversigten over ændringer, opret en samlet profil, og gennemse resultaterne.

### <a name="review-and-create-contact-profiles"></a>Gennemse, og opret kontaktprofiler

I dette sidste trin i processen til samling vises en oversigt over trinnene i processen, og der er mulighed for at foretage ændringer, før du opretter den samlede kontaktprofil.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Skærmbillede af Gennemse, og opret kontaktprofiler.":::

1. Vælg **Rediger** på et af trinnene til kontaktsamling for at gennemse det og foretage ændringer.

1. Hvis du er tilfreds med dine valg, skal du vælge **Opret kontaktprofiler**. Siden **Foren** vises, mens den forenede kontaktprofil oprettes.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Skærmbillede af siden Foren kontakter med felter, der viser I kø eller Opdateres.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Det tager tid at fuldføre algoritmen til samling, og du kan ikke ændre konfigurationen, før den er fuldført.

### <a name="view-the-results-of-contact-unification"></a>Se resultaterne af kontaktsamling

Når en samling fuldføres, vises antallet af samlede kontaktprofiler på siden **Data** > **Foren**. Resultaterne af hvert trin i processen til samling vises på de enkelte felter. **Kildefelter** viser f.eks. antallet af tilknyttede attributter (felter) og antallet af **dubletposter**, der er fundet.

:::image type="content" source="media/unified_contacts.png" alt-text="Skærmbillede af siden Samle data, når kontakterne er samlet.":::

> [!TIP]
> Feltet **Matching betingelser** vises kun, hvis der er valgt flere objekter.

Det anbefales, at du gennemgår resultaterne, især kvaliteten af [matchreglerne](data-unification-update.md#manage-match-rules), og om nødvendigt finjustere dem.

Du kan om nødvendigt [foretage ændringer af indstillingerne for kontaktsamling](data-unification-update.md) og køre den samlede profil igen.

### <a name="verify-output-entities-from-data-unification"></a>Kontrollere outputobjekter fra datasamling

Gå til **Data** > **Objekter** for at kontrollere outputobjekterne.

Objektet for den samlede kontaktprofil, der kaldes *ContactProfile*, vises i sektionen **Semantiske objekter**. Ved den første vellykkede kørsel af en samling oprettes objektet samlet *ContactProfile*. Alle efterfølgende kørsler udvider objektet.

Objektet *ContactsCustomer* (forhåndsversion) oprettes og vises i sektionen **Profiler**. Dette objekt indeholder kontaktdataene uden links til firmaerne. Dette objekt bruges som input til den semantiske tilknytning og relationstrin til kontaktsamling.

Deduplikerings- og sammenblandingsobjekter oprettes og vises i sektionen **System**. Et deduplikeringsobjekt oprettes for hvert af kildeobjekterne med navnet **Deduplication_DataSource_Entity**. Objektet **ContactsConflationMatchPairs** indeholder oplysninger om matches på tværs af objekter.

Et deduplikeret outputobjekt indeholder følgende oplysninger:
- Id'er / nøgler
  - Primær nøgle og felter med alternativt id. Alternativt id-felt består af alle de alternative id'er, der er identificeret for en post.
  - Deduplication_GroupId-felt vises den gruppe eller klynge, der er identificeret i et objekt, og som grupperer alle lignende poster på baggrund af de angivne felter med deduplikering. Det bruges til systembehandlingsformål. Hvis der ikke er angivet nogen regler for manuel deduplikering, og der gælder systemdefinerede regler for deduplikering, kan feltet muligvis ikke findes i outputobjektet.
  - Deduplication_WinnerId: Dette felt indeholder vinder-id fra de identificerede grupper eller klynger. Hvis Deduplication_WinnerId er den samme som værdien for den primære nøgle for en post, betyder det, at posten er vinderposten.
- Felter, der bruges til at definere reglerne for deduplikering.
- Felterne Regel og Resultat angiver, hvilke af de duplikeringsregler der blev anvendt, og det antal point, der returneres af den tilsvarende algoritme.

## <a name="next-step"></a>Næste trin

Konfigurer [aktiviteter](activities.md), [forbedring](enrichment-hub.md) eller [relationer](relationships.md) for at få mere indsigt i dine kontakter.
