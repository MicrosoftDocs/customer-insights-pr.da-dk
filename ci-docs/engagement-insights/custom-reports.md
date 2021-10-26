---
title: Om brugerdefinerede rapporter
description: Flere oplysninger om, hvordan du opretter brugerdefinerede rapporter.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3fa801bfc8b0aee65c21b90de2423a3d5d5e4e26
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582870"
---
# <a name="create-and-edit-custom-reports"></a>Oprette og redigere brugerdefinerede rapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ud over indbyggede rapporter (OOB) kan du oprette en brugerdefineret rapport med diagram- og tabelvisualiseringer, så du kan forstå brugerens adfærd. I denne artikel forklares, hvordan du kan oprette en rapport med de data, du skal bruge, ved hjælp af tabel- og diagramvisualiseringer. Du kan finde oplysninger om OOB-rapporter under [Se rapporter](view-reports.md).

## <a name="create-a-custom-report"></a>Oprette en brugerdefineret rapport

1. Gå til **Analysér** > **Brugerdefineret** for at få adgang til den brugerdefinerede rapportliste.

1. Vælg **Ny rapport** for at begynde at oprette en brugerdefineret rapport.

   :::image type="content" source="media/new-custom-report.png" alt-text="Nye brugerdefinerede rapporter.":::

1. Bestem, hvilken type rapport du vil oprette:

    - Vælg **Tilføj visualisering** på kommandolinjen for at oprette en standardtabelvisualisering.
    - Du kan også vælge en kolonne, bjælke, linje, område, cirkel, donut eller tabelvisualisering fra ruden **Rapporteditor**.

1. Vælg en af de tilgængelige indstillinger (f.eks. sidevisninger) på rullelisten **Målepunkter** i sektionen **Data** i **Visualiseringseditor**. Du kan også tilføje **Dimensioner** (f.eks. land/område), der skal medtages i visualiseringen. Du kan finde flere oplysninger i [Se og oprette målepunkter](metrics.md) og [Se og oprette dimensioner](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Vælg en metrikværdi til din rapport.":::

1. Vælg sektionen **Design** i **Visualiseringseditor** for at tilføje **Titeltekst** og skifte **Titel** til og fra.  Du kan også ændre visualiseringstypen ved at vælge et andet diagram, f.eks. **cirkeldiagram**.

1. Sådan ændrer du størrelsen og placeringen af en visualisering:
   - Vælg visualisering, og træk derefter en af de forskellige ønsker for at justere størrelsen.
   - Vælg visualisering, og flyt den til en ny placering. Du kan også bruge piletasterne til at ændre placeringen.
1. Vælg **Tilføj visuel** på kommandolinjen for at tilføje et ny visualisering.
1. Når du har tilføjet de ønskede visualiseringer for rapporten, skal du vælge **Gem** på kommandolinjen.

1. Angiv et navn til den brugerdefinerede rapport, og vælg **Gem** for at oprette den.
 
## <a name="filter-a-custom-report"></a>Filtrere en brugerdefineret rapport

Du kan vælge tidsrammen eller datointervallet i en brugerdefineret rapport for at fokusere på en værdi eller tidsperiode.

Hvis du vil bruge en tidsramme, skal du vælge en værdi på rullelisten i rapporten i øverste højre hjørne i rapportvisningen. Du kan også vælge et **Fast datointerval*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtrer efter klokkeslæt eller datointerval.":::

I forbindelse med de fleste rapporter skal du vælge **+ Tilføj betingelse** for at vælge en dimension eller et segment, rapporten skal filtreres efter. Der er flere oplysninger under [Se og oprette segmenter](segments.md).

## <a name="edit-a-custom-report"></a>Redigere en brugerdefineret rapport

1. Gå til **Analysér** > **Brugerdefineret** for at få adgang til den brugerdefinerede rapportliste.

1. Vælg **Flere [...]** på den brugerdefinerede rapportliste 

1. Vælg **Rediger navn** for at ændre navnet på rapporten.

1. Vælg navnet på rapporten, og brug indstillingerne **+ Tilføj visuelt element** og **Rediger** til at tilføje, fjerne, flytte eller tilpasse visualiseringerne.

1. Hvis du vil ændre egenskaberne for en visualisering, skal du markere det visuelle element, vælge **...** og derefter **Rediger visuelt element**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Redigering af diagramegenskaber for brugerdefinerede rapporter.":::

1. Når du har redigeret rapporten, skal du vælge **Gem** for at tage den i brug med dine ændringer. 

## <a name="delete-a-custom-report"></a>Slette en brugerdefineret rapport

1. Gå til **Analysér** > **Brugerdefineret** for at få adgang til den brugerdefinerede rapportliste.

1. Vælg **...** på den brugerdefinerede rapportliste

1. Vælg **Slet** for at fjerne rapporten.

1. Bekræft sletningen for at fjerne rapporten permanent.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
