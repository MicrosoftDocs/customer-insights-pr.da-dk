---
title: Målingsoversigt
description: Få mere at vide om, hvordan foranstaltninger kan hjælpe dig med at analysere og afspejle resultaterne i virksomheden.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 880c06bffcfa269151d96cb4c597eed4832fc61b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081203"
---
# <a name="measures-overview"></a>Målingsoversigt

Foranstaltninger hjælper dig med at få en bedre forståelse af kundernes adfærd og virksomhedens præstation. De ser på relevante værdier fra [ensartede profiler](data-unification.md). En virksomhed vil f.eks. se det *samlede forbrug pr. kunde* for at forstå en enkelt kundes købsoversigt eller måle firmaets samlede salg for at forstå den *samlede omsætning i hele virksomheden*.  

Målinger oprettes [ved hjælp af målegeneratoren](measure-builder.md), en platform til dataforespørgsel med forskellige operatorer og simple tilknytningsindstillinger. Du kan filtrere dataene, gruppere resultater, registrere [objektrelationsstier](relationships.md) og gennemse outputtet. Du kan [bruge foruddefinerede skabeloner](measure-templates.md) til effektivt at konfigurere almindeligt anvendte foranstaltninger.

Brug målegeneratoren til at planlægge forretningsaktiviteter ved at forespørge om kundedata og udtrække indsigt. Hvis du f.eks. opretter et mål for det *samlede forbrug pr. kunde* og det *samlede afkast pr. kunde*, kan du identificere en gruppe kunder med et højt forbrug, men et højt afkast. Du kan [oprette et segment](segments.md) baseret på disse foranstaltninger for at opnå de bedste handlinger.

## <a name="manage-your-measures"></a>Administrere dine målinger

Du kan finde listen over mål på siden **Målinger**.

Du kan finde oplysninger om målingstype, oprettelsesdato, status og tilstand. Når du vælger et mål på listen, kan du gennemse outputtet og hente en CSV-fil.

:::image type="content" source="media/measures-actions.png" alt-text="Handlinger til administration af enkelte målinger."lightbox="media/measures-actions.png":::

Følgende handlinger er tilgængelige, når du vælger en måleenhed:

- **Rediger** konfigurationen af målingen.
- **Dupliker** en måling. Du kan vælge at redigere egenskaberne med det samme eller ganske enkelt gemme dubletten.
- **Opdater** målingen på baggrund af de seneste data. Hvis du vil opdatere alle målingerne på én gang, skal du markere alle målinger og derefter **Opdater**.
- **Omdøb** målingen.
- **Aktivere** eller **deaktivere**. Inaktive målinger opdateres ikke under en [planlagt opdatering](system.md#schedule-tab).
- **Kode** til [administration af koder](work-with-tags-columns.md#manage-tags) for segmentet.
- **Slet** målingen.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Næste trin

Du kan bruge eksisterende mål til at oprette [et kundesegment](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
