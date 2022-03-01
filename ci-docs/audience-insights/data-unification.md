---
title: Oprette en samlet visning af dine kunder
description: Gennemgå processen til samling af data med dine data for at oprette et enkelt datasæt med kundeprofiler.
ms.date: 10/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-unify
ms.openlocfilehash: 694bfd0e407975af64ca0971a73fe4c3f5ba5a23
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648064"
---
# <a name="data-unification-overview"></a>Oversigt over datasamling

Når du har [konfigureret datakilderne](data-sources.md), kan du samle dataene. Datasamling inkluderer tre trin: **Tilknyt**, **Match** og **Flet**.

Datasamlingsprocessen giver dig mulighed for at samle spredte datakilder i et enkelt masterdatasæt, der giver en samlet visning af dine kunder. Samlingsfaser er obligatoriske og udføres i følgende rækkefølge:

1. [Tilknytning](map-entities.md)
2. [Match](match-entities.md)
3. [Flet](merge-entities.md)

Når du har fuldført datasamlingen, kan du også vælge at

- [konfigurér relationer mellem objekter](relationships.md) for at oprette avancerede segmenter
- [forbedr dine data](enrichment-hub.md) for at få mere uddybende indsigt i dine kunder
- [definer aktiviteter](activities.md) ud fra nogle af de attributter, der er indsat


[!INCLUDE[footer-include](../includes/footer-banner.md)]