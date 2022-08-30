---
title: Gennemgang af datasamling
description: Gennemgå trinene til samling af data, opret unified customer profiles, og gennemse resultaterne
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303960"
---
# <a name="review-data-unification"></a>Gennemgang af datasamling

Gennemse oversigten over ændringer, opret en samlet profil, og gennemse resultaterne.

## <a name="review-and-create-customer-profiles"></a>Gennemse, og opret kundeprofiler

I dette sidste trin i processen til samling vises en oversigt over trinnene i processen, og der er mulighed for at foretage ændringer, før du opretter den samlede profil.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Skærmbillede af Gennemse, og opret kundeprofiler.":::

1. Vælg **Rediger** på et af trinene til samling af data for at gennemse og foretage ændringer.

1. Hvis du er tilfreds med dine valg, skal du vælge **Opret kundeprofiler** (eller **Opret kontoprofiler** for B-til-B). Siden **Unify** vises, mens unified customer profile oprettes.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Skærmbillede af siden Unify med felter, der viser Kø eller Opdateres.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Det tager tid at fuldføre algoritmen til samling, og du kan ikke ændre konfigurationen, før den er fuldført.

## <a name="view-the-results-of-data-unification"></a>Se resultaterne af datasamling

Efter en samling vises antallet af samlede kundeprofiler på siden **Data** > **Foren** (eller firmaprofiler for B-til-B). Resultaterne af hvert trin i processen til samling vises på de enkelte felter. **Kildefelter** viser f.eks. antallet af tilknyttede attributter (felter) og antallet af **dubletposter**, der er fundet.

:::image type="content" source="media/m3_unified.png" alt-text="Skærmbillede af siden Data Unify, når dataene er samlet.":::

> [!TIP]
> Feltet **Matching betingelser** vises kun, hvis der er valgt flere objekter.

Det anbefales, at du gennemgår resultaterne, især kvaliteten af [matchreglerne](data-unification-update.md#manage-match-rules), og om nødvendigt finjustere dem.

Du kan om nødvendigt [foretage ændringer af indstillingerne for samling](data-unification-update.md) og køre den samlede profil igen.

### <a name="verify-output-entities-from-data-unification"></a>Kontrollere outputobjekter fra datasamling

Gå til **Data** > **Objekter** for at kontrollere outputobjekterne.

Det samlede kundeprofilobjekt kaldes *Kunde* og vises i sektionen **Profiler**. Ved den første vellykkede kørsel af en samling oprettes objektet samlet *Kunde*. Alle efterfølgende kørsler udvider objektet.

Deduplikerings- og sammenblandingsobjekter oprettes og vises i sektionen **System**. Et deduplikeringsobjekt oprettes for hvert af kildeobjekterne med navnet **Deduplication_DataSource_Entity**. Objektet **ConflationMatchPairs** indeholder oplysninger om matches på tværs af objekter.

Et deduplikeret outputobjekt indeholder følgende oplysninger:
- Id'er / nøgler
  - Primær nøgle og felter med alternativt id. Alternativt id-felt består af alle de alternative id'er, der er identificeret for en post.
  - Deduplication_GroupId-felt vises den gruppe eller klynge, der er identificeret i et objekt, og som grupperer alle lignende poster på baggrund af de angivne felter med deduplikering. Det bruges til systembehandlingsformål. Hvis der ikke er angivet nogen regler for manuel deduplikering, og der gælder systemdefinerede regler for deduplikering, kan feltet muligvis ikke findes i outputobjektet.
  - Deduplication_WinnerId: Dette felt indeholder vinder-id fra de identificerede grupper eller klynger. Hvis Deduplication_WinnerId er den samme som værdien for den primære nøgle for en post, betyder det, at posten er vinderposten.
- Felter, der bruges til at definere reglerne for deduplikering.
- Felterne Regel og Resultat angiver, hvilke af de duplikeringsregler der blev anvendt, og det antal point, der returneres af den tilsvarende algoritme.

## <a name="next-step"></a>Næste trin

- For B-til-B kan du også udføre en [kontaktsamling](data-unification-contacts.md).

- For B-til-C skal du konfigurere [aktiviteter](activities.md), [forbedringer](enrichment-hub.md), [relationer](relationships.md) eller [målinger](measures.md) for at få mere indsigt i kunderne.

[!INCLUDE[footer-include](includes/footer-banner.md)]
