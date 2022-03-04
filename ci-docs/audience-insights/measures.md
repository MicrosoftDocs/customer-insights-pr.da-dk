---
title: Om og administration af foranstaltninger
description: Få mere at vide om, hvordan foranstaltninger kan hjælpe dig med at analysere og afspejle resultaterne i virksomheden.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359766"
---
# <a name="measures-overview"></a>Målingsoversigt

Foranstaltninger hjælper dig med at få en bedre forståelse af kundernes adfærd og virksomhedens præstation. De ser på relevante værdier fra [ensartede profiler](data-unification.md). En virksomhed vil f.eks. se det *samlede forbrug pr. kunde* for at forstå en enkelt kundes købsoversigt eller måle firmaets samlede salg for at forstå den *samlede omsætning i hele virksomheden*.  

Målinger oprettes [ved hjælp af målegeneratoren](measure-builder.md), en platform til dataforespørgsel med forskellige operatorer og simple tilknytningsindstillinger. Du kan filtrere dataene, gruppere resultater, registrere [objektrelationsstier](relationships.md) og gennemse outputtet. Du kan [bruge foruddefinerede skabeloner](measure-templates.md) til effektivt at konfigurere almindeligt anvendte foranstaltninger.

Brug målegeneratoren til at planlægge forretningsaktiviteter ved at forespørge om kundedata og udtrække indsigt. Hvis du f.eks. opretter et mål for det *samlede forbrug pr. kunde* og det *samlede afkast pr. kunde*, kan du identificere en gruppe kunder med et højt forbrug, men et højt afkast. Du kan [oprette et segment](segments.md) baseret på disse foranstaltninger for at opnå de bedste handlinger. 

## <a name="manage-your-measures"></a>Administrere dine målinger

Du kan finde listen over mål på siden **Målinger**.

Du kan finde oplysninger om målingstype, oprettelsesdato, status og tilstand. Når du vælger et mål på listen, kan du gennemse outputtet og hente en CSV-fil.

Hvis du vil opdatere alle dine målinger på én gang, skal du vælge **Opdater alle** uden at vælge en bestemt måling.

:::image type="content" source="media/measure-actions.png" alt-text="Handlinger til administration af enkelte målinger.":::

Vælg en måling på listen for følgende indstillinger:

- Vælg målingens navn for at se detaljer om den.
- **Rediger** konfigurationen af målingen.
- **Opdater** målingen på baggrund af de seneste data.
- **Omdøb** målingen.
- **Slet** målingen.
- **Aktivere** eller **deaktivere**. Inaktive målinger opdateres ikke under en [planlagt opdatering](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Næste trin

Du kan bruge eksisterende mål til at oprette [et kundesegment](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
