---
title: Oprette en samlet visning af dine kunder
description: Gennemgå processen til samling af data med dine data for at oprette et enkelt datasæt med firma- eller kundeprofiler.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304420"
---
# <a name="data-unification-overview"></a>Oversigt over datasamling

Når du har [konfigureret datakilderne](data-sources.md), kan du samle dataene. Med data unification kan du samle én gang forskellige datakilder i en enkelt datasæt, der giver en ensartet visning af de pågældende data.

For individuelle brugere (B-til-C), hvor dataene er centreret omkring de enkelte brugere, giver en enhed en ensartet visning af kunderne. For virksomhedskonti (B-til-B), hvor dataene er centreret omkring de konti, giver en enhed en ensartet visning af dine konti. [Kontaktsamling (forhåndsversion)](data-unification-contacts.md) tillader kontakter for disse firmaer at være samlet særskilt og tilknyttet til kontiene.

Data kan være samlet i et enkelt objekt eller flere objekter.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

I processen til samling tilknyttes kundedata fra dine datakilder, dubletter fjernes, dataene matches på tværs af objekter, og der oprettes en samlet profil. Samling udføres i følgende rækkefølge:

1. [Kildefelter](map-entities.md) (tidligere kaldet Tilknytning): I trinnet med kildefelter skal du vælge de objekter og felter, der skal inkluderes i unify-processen. Knyt felter til en almindelig semantisk type, der beskriver formålet med feltet.

1. [Dublerede poster](remove-duplicates.md) (tidligere en del af overensstemmelse): I trinnet med dubletter kan du også definere regler, der fjerner duplikerede kundeposter fra de enkelte objekter.

1. [Matchning-betingelser](match-entities.md) (tidligere kaldet Match): I trinnet med matchning-betingelser skal du definere regler, der svarer til kundeposter mellem objekter. Når der findes en kunde i to eller flere objekter, oprettes der en enkelt samlet post med alle kolonner og data fra hvert objekt.

1. [Unified customer-felter](merge-entities.md) (tidligere kaldet Flet): I trinnet med Unified customer-felter kan du bestemme, hvilke kildefelter der skal inkluderes, udelukkes eller flettes sammen til en unified customer profile.  

1. [Gennemse](review-unification.md) og opret den samlede profil.

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

I samlingsprocessen tilknyttes firmadata fra dine datakilder, dubletter fjernes, dataene matches på tværs af objekter, og der oprettes en samlet profil. Samling udføres i følgende rækkefølge:

1. [Kildefelter](map-entities.md) (tidligere kaldet Tilknytning): I trinnet med kildefelter skal du vælge de objekter og felter, der skal inkluderes i foreningsfirmaprocessen. Knyt felter til en almindelig semantisk type, der beskriver formålet med feltet.

1. [Dublerede poster](remove-duplicates.md) (tidligere en del af overensstemmelse): I trinnet med dubletter kan du også definere regler, der fjerner duplikerede firmaposter fra de enkelte objekter.

1. [Matchning-betingelser](match-entities.md) (tidligere kaldet Match): I trinnet med matchning-betingelser skal du definere regler, der svarer til firmaposter mellem objekter. Når der findes et firma i to eller flere objekter, oprettes der en enkelt samlet post med alle kolonner og data fra hvert objekt.

1. [Unified customer-felter](merge-entities.md) (tidligere kaldet Flet): I trinnet med Unified customer-felter kan du bestemme, hvilke kildefelter der skal inkluderes, udelukkes eller flettes sammen til en unified customer profile.  

1. [Gennemse](review-unification.md) og opret den samlede profil.

Når du har samlet firmaer, kan du eventuelt [samle kontakter (forhåndsversion)](data-unification-contacts.md) for disse firmaer og knytte de samlede kontakter til de samlede firmaer.

---

Når du har fuldført datasamlingen, kan du også vælge at:

- [Konfigurere relationer mellem objekter](relationships.md) for at oprette avancerede segmenter.
- [Forbedre dine data](enrichment-hub.md) for at få mere uddybende indsigt i dine kunder.
- [Definere aktiviteter](activities.md) ud fra nogle af de attributter, der er indsat.
- [Opbygge målepunkter](measures.md), der bedre forstår kundernes funktionsmåde og forretningsresultater.

[!INCLUDE [footer-include](includes/footer-banner.md)]
