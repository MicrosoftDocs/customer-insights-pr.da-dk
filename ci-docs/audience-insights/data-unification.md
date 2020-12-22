---
title: Datasamling
description: Få mere at vide om, hvordan du samler indsættelse af data.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405416"
---
# <a name="data-unification"></a>Datasamling

Når du har [konfigureret datakilderne](data-sources.md), kan du samle dataene. Datasamling inkluderer tre trin: **Tilknyt**, **Match** og **Flet**.

Datasamlingsprocessen giver dig mulighed for at samle spredte datakilder i et enkelt masterdatasæt, der giver en samlet visning af dine kunder. Samlingsfaser er obligatoriske og udføres i følgende rækkefølge:

1. [Tilknytning](map-entities.md)
2. [Match](match-entities.md)
3. [Flet](merge-entities.md)

Når du har fuldført datasamlingen, kan du også vælge at

- [konfigurér relationer mellem objekter](relationships.md) for at oprette avancerede segmenter
- [forbedr dine data](enrichment-hub.md) for at få mere uddybende indsigt i dine kunder
- [definer aktiviteter](activities.md) ud fra nogle af de attributter, der er indsat
