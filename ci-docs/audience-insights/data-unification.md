---
title: Datasamling
description: Få mere at vide om, hvordan du samler indsættelse af data.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: cb96763d4b5b67b5110db757eb7d160c294d6fc3
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539062"
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