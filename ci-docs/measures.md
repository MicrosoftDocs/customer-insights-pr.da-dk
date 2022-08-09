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
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170813"
---
# <a name="measures-overview"></a>Målingsoversigt

Foranstaltninger hjælper dig med at få en bedre forståelse af kundernes adfærd og virksomhedens præstation. De ser på relevante værdier fra [ensartede profiler](data-unification.md). En virksomhed vil f.eks. se det *samlede forbrug pr. kunde* for at forstå en enkelt kundes købsoversigt eller måle firmaets samlede salg for at forstå den *samlede omsætning i hele virksomheden*.

Opret målinger til at planlægge forretningsaktiviteter ved at forespørge om kundedata og udtrække indsigt. Hvis du f.eks. opretter et mål for det *samlede forbrug pr. kunde* og det *samlede afkast pr. kunde*, kan du identificere en gruppe kunder med et højt forbrug, men et højt afkast. Derefter kan du [oprette et segment](segments.md) baseret på disse foranstaltninger for at opnå de bedste handlinger.

## <a name="create-a-measure"></a>Oprette en måling

Vælg, hvordan du vil oprette en måleenhed på baggrund af publikum.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

- Fra bunden med måleværktøj: [Opbyg dine egne](measure-builder.md).
- [Brug foruddefinerede skabeloner](measure-templates.md) med almindeligt anvendte foranstaltninger.

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

Fra bunden med måleværktøj: [Opbyg dine egne](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Administrere eksisterende målinger

Gå til siden **Målinger** for at få vist de mål, du har oprettet, deres status, måletype og sidste gang dataene blev opdateret. Du kan sortere listen over målinger efter en hvilken som helst kolonne eller bruge søgefeltet til at søge efter de målinger, der skal håndteres.

Vælg en måling for at få vist tilgængelige handlinger. Vælg en målingsnavn på listen, kan du gennemse outputtet og hente en CSV-fil.

:::image type="content" source="media/measures-actions.png" alt-text="Handlinger til administration af enkelte målinger."lightbox="media/measures-actions.png":::

- **Rediger** målingen for at ændre dets egenskaber.
- **Opdater** målingen, så den indeholder de seneste data.
- **Omdøb** målingen.
- **Aktivér** eller **Deaktiver** målingen. Inaktive målinger kan ikke opdateres under en [planlagt opdatering](system.md#schedule-tab) og har **Status** angivet som **Sprunget over** som tegn på, at en opdatering ikke er forsøgt udført.
- **Kode** til [administration af koder](work-with-tags-columns.md#manage-tags) for måling.
- **Slet** målingen.
- **Kolonner** til [tilpasning af de kolonner](work-with-tags-columns.md#customize-columns), der vises.
- **Filtrer** til [filter på koder](work-with-tags-columns.md#filter-on-tags).
- **Søgenavn** til at søge efter målingsnavn.

## <a name="refresh-measures"></a>Måling blev opdateret

Målinger kan opdateres automatisk i en automatisk planlægning eller opdateres manuelt efter behov. Hvis du manuelt vil opdatere en eller flere målinger, skal du vælge dem og vælge **Opdater**. Hvis du vil [planlægge en automatisk opdatering](system.md#schedule-tab), skal du gå til **Administrator** > **System** > **Plan**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
