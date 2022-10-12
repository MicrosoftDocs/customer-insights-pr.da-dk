---
title: Planlæg opdatering af system
description: Planlæg det tidspunkt, hvor systemet skal opdateres
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610321"
---
# <a name="schedule-system-refresh"></a>Planlæg opdatering af system

Planlæg automatiske opdateringer for alle dine [indsatte datakilder](data-sources.md). Automatiske opdateringer er med til at sikre, at opdateringer fra dine datakilder afspejles i dine samlede kundeprofiler.

> [!NOTE]
> Power Query-datakilder, der administreres af dig, opdaterer dem efter deres egne planer. Hvis du vil planlægge opdatering af disse Power Query-datakilder, der administreres af dig, skal du konfigurere opdateringsindstillinger på datakilde fra siden **Datakilder**. Tilpas timingen med tidsplanen for opdatering af upstreamdata, så alle opdateringer ikke udføres på én gang.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Indstillinger til opdatering af dataflow.":::

## <a name="set-system-refresh-schedule"></a>Indstil plan for opdatering af system

1. Gå til **Administration** > **System**, og vælg fanen **Planlægning**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Fanen Planlæg opdatering fra systemsiden.":::

1. Standardtilstanden for den planlagte opdatering er **Fra**. Hvis du vil aktivere planlagte opdateringer, skal du ændre indstillingen øverst på skærmen til **Til**.

1. Vælg mellem **Ugentlig** (standard) og **Daglig** opdatering. Hvis du vil planlægge ugentlige opdateringer, skal du vælge en eller flere dage, hvor du vil køre opdateringen.

1. Angiv din **Tidszone**, og brug derefter **Tid**-rullelisten til at angive timingen af opdatering. Hvis du vil planlægge flere opdateringer på en enkelt dag, skal du vælge **Tilføj et andet tidspunkt**. Du kan tilføje op til fire opdateringer.

1. Vælg **Gem** for at anvende dine ændringer.

[!INCLUDE [footer-include](includes/footer-banner.md)]
