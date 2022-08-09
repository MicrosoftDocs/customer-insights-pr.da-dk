---
title: Gennemgang af datasamling
description: Gennemgå trinene til samling af data, opret unified customer profiles, og gennemse resultaterne
ms.date: 06/02/2022
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
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139569"
---
# <a name="review-data-unification"></a>Gennemgang af datasamling

I dette sidste trin i processen til samling vises en oversigt over trinnene i processen, og der er mulighed for at foretage ændringer, før du opretter den samlede profil.

:::image type="content" source="media/m3_review.png" alt-text="Skærmbillede af Gennemsyn, og opret kundeprofiler.":::

## <a name="review-the-data-unification-steps"></a>Gennemse trin til datasamling

1. Vælg **Rediger** på et af trinene til samling af data for at gennemse og foretage ændringer.

1. Hvis du er tilfreds med dine valg, skal du vælge **Opret kundeprofiler**. Siden **Unify** vises, mens unified customer profile oprettes. Alle felter undtagen **kildefelter** viser statussen **Kø** eller **Opdatering**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Skærmbillede af siden Unify med felter, der viser Kø eller Opdateres.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Det tager tid at fuldføre algoritmen til samling, og du kan ikke ændre konfigurationen, før den er fuldført. Når processen til samling er fuldført, vises unified customer profile-objektet, der kaldes *Kunde*, på objektsiden i **Objekter** i sektionen **Profiler**. Ved den første vellykkede kørsel af en samling oprettes objektet samlet *Kunde*. Alle efterfølgende kørsler udvider objektet.

## <a name="review-the-results-of-data-unification"></a>Gennemse resultaterne af datasamling

Efter en samling vises antallet af unified customer profiles på siden **Data** > **Unify**. Resultaterne af hvert trin i processen til samling vises på de enkelte felter. **Kildefelter** viser f.eks. antallet af tilknyttede attributter (felter) og antallet af **dubletposter**, der er fundet.

:::image type="content" source="media/m3_unified.png" alt-text="Skærmbillede af siden Data Unify, når dataene er samlet.":::

> [!TIP]
> Feltet **Matching betingelser** vises kun, hvis der er valgt flere objekter.

Det anbefales, at du gennemgår resultaterne, især kvaliteten af [matchreglerne](data-unification-update.md#manage-match-rules), og om nødvendigt finjustere dem.

Du kan om nødvendigt [foretage ændringer af indstillingerne for samling](data-unification-update.md) og køre den samlede profil igen.

## <a name="next-step"></a>Næste trin

Konfigurer [aktiviteter](activities.md), [fordel](enrichment-hub.md), [relationer](relationships.md) eller [målepunkter](measures.md) for at få mere indsigt i kunderne.

[!INCLUDE[footer-include](includes/footer-banner.md)]
