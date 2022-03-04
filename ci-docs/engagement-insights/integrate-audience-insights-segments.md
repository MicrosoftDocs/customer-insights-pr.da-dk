---
title: Brug målgruppeindsigtssegmenter til at filtrere rapporter over engagementsindsigt
description: Brug målgruppeindsigtssegmenter i interaktive interaktioner med adfærdsdata, der er hentet af engagementsindsigt på en kundes websted.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230479"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Brug målgruppeindsigtssegmenter til at filtrere rapporter over engagementsindsigt

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Med engagementsindsigt kan du bruge målgruppeindsigtssegmenter i interaktive interaktioner med adfærdsdata, der er hentet af engagementsindsigt på dine websteder.

## <a name="prerequisite"></a>Forudsætning

- Et engagementsindsigtsmiljø, hvor du har data fra målgruppeindsigtssegmenter knyttet til det målgruppeindsigtsmiljø, hvor segmenter og kundeprofiler oprettes. Flere oplysninger: [Opret et link mellem målgruppeindsigt og engagementsindsigt](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Oprette målgruppeindsigtssegmenter 

> [!IMPORTANT]
> Hvis målgruppeindsigtssegmenter skal vises i engagementsindsigt, skal du først [køre fletning og downstreamprocesser](../audience-insights/merge-entities.md). Downstreamprocesser er vigtige, fordi de genererer en entydig tabel, der forbereder målgruppeindsigtssegmenter, så de kan deles med engagementsindsigt. (Hvis en systemopdatering planlægges, medtages downstreamprocesser automatisk.)

Du kan bruge målgruppeindsigtssegmenter i standdardrapporter i engagementsindsigt eller brugerdefinerede rapporter, du har oprettet. Du kan finde flere oplysninger i [Brugerdefinerede profilrapporter](profile-reports.md) og [Oprette og redigere brugerdefinerede rapporter](custom-reports.md).

**Bruge målgruppeindsigtssegmenter i rapporter over engagementsindsigt**

1. Vælg **Data** på siden **Arbejdsområde**, og vælg derefter fanen **Segmenter**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Vælg fanen Segmenter.":::

   >[!NOTE]
   > Hvis du vælger målgruppeindsigtssegment, får du målgruppeindsigt, hvor du kan finde ud af, hvordan dette segment blev oprettet med hensyn til regler og logik. Du kan finde flere oplysninger om målgruppeindsigtssegmenter i [Vise og oprette segmenter](../audience-insights/segments.md).

2. Vælg en standardrapport, eller [opret en brugerdefineret rapport](custom-reports.md), og vælg derefter **Tilføj betingelse**. (I dette eksempel vælger vi rapporten **Sidevisninger**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Tilføj en betingelse.":::

3. Vælg **Filtrer efter segment**, udvid listen **Segmenttype**, og vælg derefter **Demografi**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Vælg typen af demografisegment.":::

4. Udvid listen **Segmentnavn**, og vælg derefter et målgruppeindsigtssegment.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Vælg et segment.":::

5. Du kan anvende et eller flere segmenter, herunder adfærdsindsigt (engagementsindsigt) og demografiske (målgruppeindsigtssegmenter). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Rapporten viser rapportbegrænsninger til USA's kunder og startsidesegmenter.":::

I det foregående billede er **USA's kunder** og **startsidesegmenter** valgt, hvilket begrænser rapporten **Sidevisninger** til kun at vise disse to segmenter. 


>[!NOTE]
> Du kan bruge målgruppeindsigtssegmenter til at filtrere standdardrapporterne, brugerdefinerede rapporter og tragte i engagementsindsigt. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]