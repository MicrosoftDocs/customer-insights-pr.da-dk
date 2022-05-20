---
title: Oprette en samlet visning af dine kunder
description: Gennemgå processen til samling af data med dine data for at oprette et enkelt datasæt med unified customer profiles.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755727"
---
# <a name="data-unification-overview"></a>Oversigt over datasamling

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Når du har [konfigureret datakilderne](data-sources.md), kan du samle dataene. Med data unification kan du samle én gang forskellige datakilder i en enkelt datasæt, der giver en ensartet visning af de pågældende data. For individuelle brugere (B-til-C), hvor dataene er centreret omkring de enkelte brugere, giver en enhed en ensartet visning af kunderne. For virksomhedskonti (B-til-B), hvor dataene er centreret omkring de konti, giver en enhed en ensartet visning af dine konti.

Data kan være samlet i et enkelt objekt eller flere objekter. Samling udføres i følgende rækkefølge:

1. [Kildefelter](map-entities.md) (tidligere kaldet Tilknytning): I trinnet med kildefelter skal du vælge de objekter og felter, der skal inkluderes i unify-processen. Knyt felter til en almindelig semantisk type, der beskriver formålet med feltet.

1. [Dublerede poster](remove-duplicates.md) (tidligere en del af overensstemmelse): I trinnet med dubletter kan du også definere regler, der fjerner duplikerede kundeposter fra de enkelte objekter.

1. [Matchning-betingelser](match-entities.md) (tidligere kaldet Match): I trinnet med matchning-betingelser skal du definere regler, der svarer til kundeposter mellem objekter. Når der findes en kunde i to eller flere objekter, oprettes der en enkelt samlet post med alle kolonner og data fra hvert objekt.

1. [Unified customer-felter](merge-entities.md) (tidligere kaldet Flet): I trinnet med Unified customer-felter kan du bestemme, hvilke kildefelter der skal inkluderes, udelukkes eller flettes sammen til en unified customer profile.  

1. [Gennemse](review-unification.md) og opret den samlede profil.

Når du har fuldført datasamlingen, kan du også vælge at:

- [Konfigurere relationer mellem objekter](relationships.md) for at oprette avancerede segmenter.
- [Forbedre dine data](enrichment-hub.md) for at få mere uddybende indsigt i dine kunder.
- [Definere aktiviteter](activities.md) ud fra nogle af de attributter, der er indsat.
- [Opbygge målepunkter](measures.md), der bedre forstår kundernes funktionsmåde og forretningsresultater.

[!INCLUDE [footer-include](includes/footer-banner.md)]
