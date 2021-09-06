---
title: Segmenter baseret på forudsigelsesoutput
description: Opret segmenter på baggrund af outputobjektet for en forudsigelsesmodel.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b89754aea2b0da33f27dea5b26d212920f0c090885f951a37cf42ff11c7b6e93
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036412"
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