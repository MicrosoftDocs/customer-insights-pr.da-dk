---
title: Administrere standardregler for samtykke i segmenter
description: Med muligheden for at administrere samtykke kan du deaktivere eller ændre standardreglerne for samtykke, hvis tilsidesættelser er aktiveret.
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884163"
---
# <a name="disable-or-change-default-consent-rules"></a>Deaktivere eller ændre standardregler for samtykke

Hvis dine organisationer bruger [muligheden for at administrere samtykke](../consent-management/overview.md) sammen med målgruppeindsigt, kan [administratorer gennemtvinge samtykkeregler](activate-consent.md) for segmenter. 

Med håndhævede regler for samtykke i segmentområdet informerer alle segmenter om tilstanden for kontrol af og regler for samtykke. Hvis tilsidesættelser er tilladt, er standardregler for samtykke deaktiveret for bestemte segmenter. Alle, der opretter et segment, kan tilføje flere regler for samtykke oven på standardreglerne til et segment. 

## <a name="for-administrators"></a>Til administratorer

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Segmentgenerator med indstillinger for regler for samtykke.":::

**Sådan deaktiverer du standardregler for samtykke:**

1. Vælg **Se detaljer** i meddelelsen om **regler for samtykke**. 

1. Indstil **standardreglerne for samtykke** til **Fra**.

**Sådan tilføjer du flere samtykkeregler:**

1. Vælg **Se detaljer** i meddelelsen om **regler for samtykke**. 

1. Vælg **Tilføj regler for samtykke**, og vælg en samtykkeregel på rullelisten **Vælg datatype for samtykke**.

1. Vælg **Gem** for at anvende den nye regel på segmentet.

## <a name="for-contributors"></a>Til bidragydere

Hvis du vil oprette et segment uden håndhævede regler for samtykke, skal du arbejde med din administrator for at deaktivere dem på dit segment. Du kan dog føje dine egne samtykkeregler til de segmenter, du ejer og administrerer.

Det er en proces i tre trin: 
1. [Opret segmentet](segments.md) i en målgruppeindsigt, og gem det. 

1. Del segmentnavnet med din administrator, og bed vedkommende om at [aktivere tilsidesættelser for dit segment](activate-consent.md). 

1. Åbn segmenterne igen. I meddelelsen om **regler for samtykke** skal du vælge **Se detaljer** og tilføje de regler for samtykke, du vil anvende. Vælg **Gem** og **Kør** dit segment.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
