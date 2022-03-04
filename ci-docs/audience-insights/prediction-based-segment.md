---
title: Segmenter baseret på forudsigelsesoutput
description: Opret segmenter på baggrund af outputobjektet for en forudsigelsesmodel.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0b3357cdf3c049bd92f6c3f690f27433df9117b
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226656"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Oprette et segment på baggrund af en forudsigelse model (forhåndsversion)

Resultaterne af forudsigelser gælder undertiden kun for en delmængde af dine kunder. Øg tilpasningen af anbefalingerne ved at oprette segmenter ud fra resultaterne fra forudsigelsesmodeller. Du kan f.eks. komme med specifikke anbefalinger til kunder, der foretrækker en bestemt type service. 

## <a name="prerequisites"></a>Forudsætninger

- Mindst [bidragydertilladelser](permissions.md) i Customer Insights.

- En produktanbefaling, transaktionsafgang, abonnementsafgang eller værdimodel for kundens levetid, der er konfigureret i Customer Insights. Gennemgå kravene for at konfigurere de forskellige modeller:

  - [Produktanbefalingsmodel](predict-product-recommendation.md)
  - [Model til abonnementsafgang](predict-subscription-churn.md)
  - [Model for transaktionsafgang](predict-transactional-churn.md)
  - [Værdimodel for kundens levetid](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Opret et kundesegment ud fra forudsigelser

1. Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**.

1. Vælg de lodrette ellipser ud for den model, du vil gennemse, og vælg **Vis**.

1. Vælg **Opret segment** på resultatsiden. Du kan finde flere oplysninger om resultatsiden i artiklen om modellen.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Skærmbillede af siden forudsigelsesresultater med fremhævelse af handlingen Opret segment.":::

1. Opret et nyt segment på baggrund af outputobjektet for den valgte model. Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).