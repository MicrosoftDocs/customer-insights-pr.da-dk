---
title: Aktivere samtykkeregler for segmenter
description: Følg disse trin for at tilknytte samtykkedata og aktivere kontrol af samtykke i målgruppeindsigt. En administrator kan også deaktivere kontrol af samtykke.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790769"
---
# <a name="activate-consent-rules"></a>Aktivér samtykkeregler

[Samtykkecenter (forhåndsversion)](../consent-management/overview.md) hjælper dig med at indsamle samtykkedata fra forskellige kilder. Brug objektet samlet *samtykke* til at anvende standardkontrol af samtykke. Når der er importeret data om samtykke i Samtykkecenter, og reglerne er konfigureret for dataene, synkroniseres objektet *Samtykke* automatisk med målgruppeindsigt.

## <a name="enable-consent-checks"></a>Aktivér samtykketjek

Når der er importeret samtykkedata til Samtykkecenter (forhåndsversion), og reglerne er konfigureret, kan du aktivere tjek af samtykke. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Fanen Samtykke i målgruppeindsigtsindstillinger med aktiverede samtykkedata.":::

1. Gå til **Admin** > **System** i målgruppen Insights.

1. Vælg fanen **Samtykke (forhåndsversion)**.

1. Angiv til/fra-knappen for alle de områder, du vil aktivere, til **Til** i sektionen **Aktivér samtykketjek**.

1. Markér afkrydsningsfeltet **Tillad tilsidesættelse af standardregler for samtykke** for at fjerne de standardkontroller for samtykke, der håndhæves på et bestemt segment. 

1. Vælg, hvor du vil tillade tilsidesættelser, på rullemenuen.     

1. Vælg den attribut, der bruges som id, i sektionen **Link samtykke til kundeprofiler** for at knytte samtykkedata til kundedata. Det er sandsynligvis et telefonnummer eller en mailadresse. 

1. Vælg **Gem** for at anvende indstillingerne.

## <a name="disable-consent-checks"></a>Deaktiver samtykketjek

En administrator skal opdatere systemindstillingerne efter målgruppe for at ophøre med at bruge samtykkedata i denne indsigt.

1. Gå til **Admin** > **System** i målgruppen Insights.

1. Vælg fanen **Samtykke (forhåndsversion)**.

1. Angiv til/fra-knappen til **Fra** i sektionen **Aktivér samtykketjek**.
