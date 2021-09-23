---
title: Brug demografiske dimensioner til opdeling af adfærdsdata (kuraterede dimensioner)
description: Brug samlede profil-kuraterede dimensioner til at aktivere målgruppeindsigt i egenskaber for kundeprofiler.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a3d7f9276330a6daacbe9428d84a371b81bbefe
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466341"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Brug demografiske dimensioner til opdeling af adfærdsdata

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ved hjælp af samlede demografiske profiler kan brugere af engagementsindsigt få adgang målgruppeindsigt for profilegenskaber. Du kan derefter bruge disse egenskaber i interaktive analyser af adfærdsdata, herunder data, der er hentet ved hjælp af engagementsindsigt, på dit websted eller i mobilappen.

>[!NOTE]
> Engagementsindsigt omfatter køreklare dimensioner for hændelsesegenskaber. Flere oplysninger: [Vise og oprette dimensioner](dimensions.md)

## <a name="prerequisite"></a>Forudsætning

- Et engagementsindsigtsmiljø, hvor du har kundeprofildata knyttet til det målgruppeindsigtsmiljø, hvor kundeprofilerne oprettes. Flere oplysninger: [Opret et link mellem målgruppeindsigt og engagementsindsigt](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Når du har oprettet et link mellem målgruppeindsigtsmiljøet og engagementsindsigtsmiljøerne, ønsker du måske kun data, der er specifikke for egenskaber for kundeprofiler, og som kan være nyttige som dimensioner i engagementsindsigt. Du kan finde flere oplysninger i [Aktivere målgruppeindsigts samlede profilattributter og segmenter](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Opret en ny brugerdefineret rapport

1. Vælg **Brugerdefineret** > **ny rapport** i venstre rude, og vælg derefter den ønskede metrikværdi. (I dette eksempel vælger vi **Sidevisninger efter time**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Vælg en metrikværdi.":::

2. Vælg **Dimensioner** i visualiseringseditoren, og vælg derefter **Demografi** i rullemenuen **Dimensionstype**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Vælg demografi.":::

3. Vælg en **Signal.Customer.*xxx***-dimension. (I dette eksempel vises Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Vælg en dimension.":::
  
## <a name="limitations"></a>Begrænsninger

I øjeblikket kan du kun bruge demografiske dimensioner til opdeling af adfærdsdata.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
