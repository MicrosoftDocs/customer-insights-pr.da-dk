---
title: Segmentindsigt i eksisterende segmenter
description: Få indsigt i eksisterende segmenter for at få vist forskelle og fællestræk.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 90ebcaab896c628b04e751ad9857e924749895e7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595327"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="ac197-103">Segmentindsigter (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="ac197-103">Segment insights (preview)</span></span>

<span data-ttu-id="ac197-104">Opdag yderligere oplysninger og indsigt i dine eksisterende segmenter.</span><span class="sxs-lookup"><span data-stu-id="ac197-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="ac197-105">Find ud af, hvad der adskiller to segmenter, eller hvad de har til fælles.</span><span class="sxs-lookup"><span data-stu-id="ac197-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="ac197-106">Segmentoverlap</span><span class="sxs-lookup"><span data-stu-id="ac197-106">Segment overlap</span></span>

<span data-ttu-id="ac197-107">Analyse af segmentoverlap viser, hvor mange og hvilke kunder der er fælles for to eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="ac197-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="ac197-108">F.eks. hvordan et segment af hyppige kunder overlapper med et segment, der indeholder kunder, som er tilfreds med din service eller dit produkt.</span><span class="sxs-lookup"><span data-stu-id="ac197-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="ac197-109">Du kan også analysere, hvordan overlapningen ændres for bestemte attributter.</span><span class="sxs-lookup"><span data-stu-id="ac197-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="ac197-110">Køre en overlapningsanalyse</span><span class="sxs-lookup"><span data-stu-id="ac197-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="ac197-111">Gå til **Segmenter**, og vælg fanen **Indsigt (prøveversion)**.</span><span class="sxs-lookup"><span data-stu-id="ac197-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="ac197-112">Vælg **Ny**, og vælg indstillingen **Overlap** i ruden **Vælg indsigtstype**.</span><span class="sxs-lookup"><span data-stu-id="ac197-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="ac197-113">Vælg de ønskede segmenter, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="ac197-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="ac197-114">Du kan også vælge et eller flere felter af interesse for at analysere overlapninger for alle mulige feltværdier og vælge **Næste**.</span><span class="sxs-lookup"><span data-stu-id="ac197-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="ac197-115">Giv dig et navn til din overlapningsanalyse, et valgfrit vist navn og en beskrivelse.</span><span class="sxs-lookup"><span data-stu-id="ac197-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="ac197-116">Vælg **Gem** for at starte analysen.</span><span class="sxs-lookup"><span data-stu-id="ac197-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="ac197-117">Overlapningsanalysen er klar, når status ændres fra Opdaterer til Gennemført.</span><span class="sxs-lookup"><span data-stu-id="ac197-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="ac197-118">Se og optimere en overlapningsanalyse</span><span class="sxs-lookup"><span data-stu-id="ac197-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="ac197-119">Når analysen er fuldført, kan du finde oplysninger om denne indsigt i **Segmenter** > **Indsigt (prøveversion)**.</span><span class="sxs-lookup"><span data-stu-id="ac197-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Oplysninger om indsigt i segmentoverlapning":::

<span data-ttu-id="ac197-121">Vælg en indsigt for at få vist analyseresultaterne:</span><span class="sxs-lookup"><span data-stu-id="ac197-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="ac197-122">Antallet af medlemmer, der overlapper de segmenter, der er valgt til analyse.</span><span class="sxs-lookup"><span data-stu-id="ac197-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="ac197-123">Antallet af medlemmer, der er inkluderet i en af segmenterne, men ikke i resten af segmenterne.</span><span class="sxs-lookup"><span data-stu-id="ac197-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="ac197-124">Hvis du har valgt felter, mens du konfigurerede overlapningsanalysen, kan du finde dem under de tilhørende faner.</span><span class="sxs-lookup"><span data-stu-id="ac197-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="ac197-125">Du kan bruge rullelisten med filter til at vælge et hvilket som helst attributniveau, så den nederste tabel indeholder de tilsvarende data.</span><span class="sxs-lookup"><span data-stu-id="ac197-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="ac197-126">Segmentdifferentieringer</span><span class="sxs-lookup"><span data-stu-id="ac197-126">Segment differentiators</span></span>

<span data-ttu-id="ac197-127">Segmentdifferentieringer hjælper dig med at finde ud af, hvad der adskiller et segment fra resten af kunderne eller fra et andet segment.</span><span class="sxs-lookup"><span data-stu-id="ac197-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="ac197-128">Du skal blot vælge et segment, hvorefter systemet identificerer de profilattributter og målinger, der adskiller det valgte segment.</span><span class="sxs-lookup"><span data-stu-id="ac197-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="ac197-129">Køre en differentieringsanalyse</span><span class="sxs-lookup"><span data-stu-id="ac197-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="ac197-130">Gå til **Segmenter**, og vælg fanen **Indsigt (prøveversion)**.</span><span class="sxs-lookup"><span data-stu-id="ac197-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="ac197-131">Vælg **Ny**, og vælg indstillingen **Overlap** i ruden **Vælg indsigtstype**.</span><span class="sxs-lookup"><span data-stu-id="ac197-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="ac197-132">Vælg det segment, du vil analysere som **Primært segment**, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="ac197-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="ac197-133">Vælg **Alle kunder** eller et **Sekundært segment** for at sammenligne dit primære segment med det, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="ac197-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="ac197-134">Du kan også vælge et eller flere interesseområder for at fokusere analysen på bestemte attributter og vælge **Næste**.</span><span class="sxs-lookup"><span data-stu-id="ac197-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="ac197-135">Giv dig et navn til din overlapningsanalyse, et valgfrit vist navn og en beskrivelse.</span><span class="sxs-lookup"><span data-stu-id="ac197-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="ac197-136">Vælg **Gem** for at starte analysen.</span><span class="sxs-lookup"><span data-stu-id="ac197-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="ac197-137">Overlapningsanalysen er klar, når status ændres fra Opdaterer til Gennemført.</span><span class="sxs-lookup"><span data-stu-id="ac197-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="ac197-138">Se og optimere en differentieringsanalyse</span><span class="sxs-lookup"><span data-stu-id="ac197-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="ac197-139">Når analysen er fuldført, kan du finde oplysninger om denne indsigt i **Segmenter** > **Indsigt (prøveversion)**.</span><span class="sxs-lookup"><span data-stu-id="ac197-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Oplysninger om indsigt i segmentdifferentiering":::

<span data-ttu-id="ac197-141">Vælg en indsigt for at få vist analyseresultaterne.</span><span class="sxs-lookup"><span data-stu-id="ac197-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="ac197-142">En differentieringsanalyse indeholder to faner.</span><span class="sxs-lookup"><span data-stu-id="ac197-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="ac197-143">Fanen **Attributter** indeholder en liste over profilattributter, der opfattes som en differentiering.</span><span class="sxs-lookup"><span data-stu-id="ac197-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="ac197-144">Fanen **Målinger** viser differentieringer.</span><span class="sxs-lookup"><span data-stu-id="ac197-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="ac197-145">Der findes følgende oplysninger under de enkelte faner:</span><span class="sxs-lookup"><span data-stu-id="ac197-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="ac197-146">Rangeret liste over differentieringer, sorteret efter differencescore.</span><span class="sxs-lookup"><span data-stu-id="ac197-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="ac197-147">**Differencescore** for hver differentiering.</span><span class="sxs-lookup"><span data-stu-id="ac197-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="ac197-148">Differencescoren repræsenterer graden af forskel på en attribut mellem to segmenter.</span><span class="sxs-lookup"><span data-stu-id="ac197-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="ac197-149">Jo højere differencescore, desto mere er attributterne forskellige for de to segmenter.</span><span class="sxs-lookup"><span data-stu-id="ac197-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="ac197-150">Vælg en score for at åbne ruden **Differencescore** med fordelingen af værdier for den pågældende attribut.</span><span class="sxs-lookup"><span data-stu-id="ac197-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="ac197-151">Administrere segmentindsigt</span><span class="sxs-lookup"><span data-stu-id="ac197-151">Manage segment insights</span></span>

<span data-ttu-id="ac197-152">Du kan bruge følgende indstillinger i indsigten fra kommandolinjen:</span><span class="sxs-lookup"><span data-stu-id="ac197-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="ac197-153">**Tilbage** for at returnere til listen over indsigt</span><span class="sxs-lookup"><span data-stu-id="ac197-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="ac197-154">**Opdater** for at køre analysen igen</span><span class="sxs-lookup"><span data-stu-id="ac197-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="ac197-155">**Slet** for at fjerne denne indsigt</span><span class="sxs-lookup"><span data-stu-id="ac197-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]