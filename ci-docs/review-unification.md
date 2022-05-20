---
title: Gennemgang af datasamling
description: Gennemgå trinene til samling af data, opret unified customer profiles, og gennemse resultaterne
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741660"
---
# <a name="review-data-unification"></a>Gennemgang af datasamling

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

I dette sidste trin i processen til samling vises en oversigt over trinnene i processen, og der er mulighed for at foretage ændringer, før du opretter den samlede profil.

:::image type="content" source="media/m3_review.png" alt-text="Skærmbillede af Gennemsyn, og opret kundeprofiler.":::

## <a name="review-the-data-unification-steps"></a>Gennemse trin til datasamling

1. Vælg **Rediger** på et af trinene til samling af data for at gennemse og foretage ændringer.

1. Hvis du er tilfreds med dine valg, skal du vælge **Opret kundeprofiler**. Siden **Unify** vises, mens unified customer profile oprettes. Det tager tid at fuldføre algoritmen til samling, og du kan ikke ændre konfigurationen, før den er fuldført.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Når processen til samling er fuldført, vises unified customer profile-objektet, der kaldes *Kunde*, på objektsiden i **Objekter** i sektionen **Profiler**. Ved den første vellykkede kørsel af en samling oprettes objektet samlet *Kunde*. Alle efterfølgende kørsler udvider objektet.

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
