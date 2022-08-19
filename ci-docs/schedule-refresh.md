---
title: Planlæg opdatering af system
description: Planlæg det tidspunkt, hvor systemet skal opdateres
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: ce10fcfe9906d33209270f8f6930a51b045b13e2
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246335"
---
# <a name="schedule-system-refresh"></a>Planlæg opdatering af system

Planlæg automatiske opdateringer for alle dine [indsatte datakilder](data-sources.md). Automatiske opdateringer er med til at sikre, at opdateringer fra dine datakilder afspejles i dine samlede kundeprofiler.

> [!NOTE]
> Power Query-datakilder, der administreres af dig, opdaterer dem efter deres egne planer. Hvis du vil planlægge opdatering af disse Power Query-datakilder, der administreres af dig, skal du konfigurere opdateringsindstillinger på datakilde fra siden **Datakilder**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Indstillinger til opdatering af dataflow.":::

## <a name="set-system-refresh-schedule"></a>Indstil plan for opdatering af system

1. Gå til **Administration** > **System**, og vælg fanen **Planlægning**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Fanen Planlæg opdatering fra systemsiden.":::

1. Standardtilstanden for den planlagte opdatering er **Fra**. Hvis du vil aktivere planlagte opdateringer, skal du ændre indstillingen øverst på skærmen til **Til**.

1. Vælg mellem **Ugentlig** (standard) og **Daglig** opdatering. Hvis du vil planlægge ugentlige opdateringer, skal du vælge en eller flere dage, hvor du vil køre opdateringen.

1. Angiv din **Tidszone**, og brug derefter **Tid**-rullelisten til at angive timingen af opdatering. Hvis du vil planlægge flere opdateringer på en enkelt dag, skal du vælge **Tilføj et andet tidspunkt**.

1. Vælg **Gem** for at anvende dine ændringer.

[!INCLUDE [footer-include](includes/footer-banner.md)]
