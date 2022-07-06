---
title: Segmentindsigter (prøveversion)
description: Få indsigt i eksisterende segmenter for at få vist forskelle og fællestræk.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: e90bdc523c3f8857c150ccba9d81f055d39f9feb
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051584"
---
# <a name="segment-insights-preview"></a>Segmentindsigter (prøveversion)

Opdag yderligere oplysninger og indsigt i dine eksisterende segmenter. Find ud af, hvad der adskiller to segmenter, eller hvad de har til fælles.

## <a name="segment-overlap"></a>Segmentoverlap

Analyse af segmentoverlap viser, hvor mange og hvilke kunder der er fælles for to eller flere segmenter. F.eks. hvordan et segment af hyppige kunder overlapper med et segment, der indeholder kunder, som er tilfreds med din service eller dit produkt.
Du kan også analysere, hvordan overlapningen ændres for bestemte attributter.

### <a name="run-an-overlap-analysis"></a>Køre en overlapningsanalyse

1. Gå til **Segmenter**, og vælg fanen **Indsigt (prøveversion)**.

1. Vælg **Ny**, og vælg indstillingen **Overlap** i ruden **Vælg indsigtstype**.

1. Vælg de ønskede segmenter, og vælg **Næste**.

1. Du kan også vælge et eller flere felter af interesse for at analysere overlapninger for alle mulige feltværdier og vælge **Næste**.

1. Giv dig et navn til din overlapningsanalyse, et valgfrit vist navn og en beskrivelse.

1. Vælg **Gem** for at starte analysen. Overlapningsanalysen er klar, når status ændres fra Opdaterer til Gennemført.

### <a name="view-and-optimize-an-overlap-analysis"></a>Se og optimere en overlapningsanalyse

Når analysen er fuldført, kan du finde oplysninger om denne indsigt i **Segmenter** > **Indsigt (prøveversion)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Oplysninger om indsigt i segmentoverlapning.":::

Vælg en indsigt for at få vist analyseresultaterne:

- Antallet af medlemmer, der overlapper de segmenter, der er valgt til analyse.
- Antallet af medlemmer, der er inkluderet i en af segmenterne, men ikke i resten af segmenterne.
- Hvis du har valgt felter, mens du konfigurerede overlapningsanalysen, kan du finde dem under de tilhørende faner. Du kan bruge filter-rullelisten til at vælge et hvilket som helst attributniveau, og tabellen nederst viser de tilsvarende data.

## <a name="segment-differentiators"></a>Segmentdifferentieringer

Segmentdifferentieringer hjælper dig med at finde ud af, hvad der adskiller et segment fra resten af kunderne eller fra et andet segment. Du skal blot vælge et segment, hvorefter systemet identificerer de profilattributter og målinger, der adskiller det valgte segment.

### <a name="run-a-differentiator-analysis"></a>Køre en differentieringsanalyse

1. Gå til **Segmenter**, og vælg fanen **Indsigt (prøveversion)**.

1. Vælg **Ny**, og vælg indstillingen **Overlap** i ruden **Vælg indsigtstype**.

1. Vælg det segment, du vil analysere som **Primært segment**, og vælg **Næste**.

1. Vælg **Alle kunder** eller et **Sekundært segment** for at sammenligne dit primære segment med det, og vælg **Næste**.

1. Du kan også vælge et eller flere interesseområder for at fokusere analysen på bestemte attributter og vælge **Næste**.

1. Giv dig et navn til din overlapningsanalyse, et valgfrit vist navn og en beskrivelse.

1. Vælg **Gem** for at starte analysen. Overlapningsanalysen er klar, når status ændres fra Opdaterer til Gennemført.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Se og optimere en differentieringsanalyse

Når analysen er fuldført, kan du finde oplysninger om denne indsigt i **Segmenter** > **Indsigt (prøveversion)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Oplysninger om indsigt i segmentdifferentiering.":::

Vælg en indsigt for at få vist analyseresultaterne. En differentieringsanalyse indeholder to faner. Fanen **Attributter** indeholder en liste over profilattributter, der opfattes som en differentiering. Fanen **Målinger** viser differentieringer. Der findes følgende oplysninger under de enkelte faner:

- Rangeret liste over differentieringer, sorteret efter differencescore.
- **Differencescore** for hver differentiering. Differencescoren repræsenterer graden af forskel på en attribut mellem to segmenter. Jo højere differencescore, desto mere er attributterne forskellige for de to segmenter. Vælg en score for at åbne ruden **Differencescore** med fordelingen af værdier for den pågældende attribut.

## <a name="manage-segment-insights"></a>Administrere segmentindsigt

Du kan bruge følgende indstillinger i indsigten fra kommandolinjen:

- **Tilbage** for at returnere til listen over indsigt
- **Opdater** for at køre analysen igen
- **Slet** for at fjerne denne indsigt


[!INCLUDE [footer-include](includes/footer-banner.md)]
