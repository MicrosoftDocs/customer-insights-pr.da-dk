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
ms.openlocfilehash: 73d8006c670268420f8cd6a2b37cb214ba1bbd6c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597872"
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