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
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741422"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="e7561-103">Oprette et segment på baggrund af en forudsigelse model (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="e7561-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="e7561-104">Resultaterne af forudsigelser gælder undertiden kun for en delmængde af dine kunder.</span><span class="sxs-lookup"><span data-stu-id="e7561-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="e7561-105">Øg tilpasningen af anbefalingerne ved at oprette segmenter ud fra resultaterne fra forudsigelsesmodeller.</span><span class="sxs-lookup"><span data-stu-id="e7561-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="e7561-106">Du kan f.eks. komme med specifikke anbefalinger til kunder, der foretrækker en bestemt type service.</span><span class="sxs-lookup"><span data-stu-id="e7561-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e7561-107">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="e7561-107">Prerequisites</span></span>

- <span data-ttu-id="e7561-108">Mindst [bidragydertilladelser](permissions.md) i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e7561-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="e7561-109">En produktanbefaling, transaktionsafgang, abonnementsafgang eller værdimodel for kundens levetid, der er konfigureret i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e7561-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="e7561-110">Gennemgå kravene for at konfigurere de forskellige modeller:</span><span class="sxs-lookup"><span data-stu-id="e7561-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="e7561-111">Produktanbefalingsmodel</span><span class="sxs-lookup"><span data-stu-id="e7561-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="e7561-112">Model til abonnementsafgang</span><span class="sxs-lookup"><span data-stu-id="e7561-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="e7561-113">Model for transaktionsafgang</span><span class="sxs-lookup"><span data-stu-id="e7561-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="e7561-114">Værdimodel for kundens levetid</span><span class="sxs-lookup"><span data-stu-id="e7561-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="e7561-115">Opret et kundesegment ud fra forudsigelser</span><span class="sxs-lookup"><span data-stu-id="e7561-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="e7561-116">Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**.</span><span class="sxs-lookup"><span data-stu-id="e7561-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="e7561-117">Vælg de lodrette ellipser ud for den model, du vil gennemse, og vælg **Vis**.</span><span class="sxs-lookup"><span data-stu-id="e7561-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="e7561-118">Vælg **Opret segment** på resultatsiden.</span><span class="sxs-lookup"><span data-stu-id="e7561-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="e7561-119">Du kan finde flere oplysninger om resultatsiden i artiklen om modellen.</span><span class="sxs-lookup"><span data-stu-id="e7561-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Skærmbillede af siden forudsigelsesresultater med fremhævelse af handlingen Opret segment.":::

1. <span data-ttu-id="e7561-121">Opret et nyt segment på baggrund af outputobjektet for den valgte model.</span><span class="sxs-lookup"><span data-stu-id="e7561-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="e7561-122">Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e7561-122">For more information, see [Create and manage segments](segments.md).</span></span>