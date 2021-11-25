---
title: Aktivér regler for samtykke for segmenter målgruppeindsigt
description: Trin til tilknytning af samtykkedata og aktivering af kontrol af samtykke i målgruppeindsigt.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 33ec3a684c2ca47badb4e5461f069d1b2e4a4f3d
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753054"
---
# <a name="activate-consent-rules"></a>Aktivér samtykkeregler

[Samtykkecenter (forhåndsversion)](../consent-management/overview.md) hjælper dig med at indsamle samtykkedata fra forskellige kilder. Brug objektet samlet *samtykke* til at anvende standardkontrol af samtykke. Når der er importeret data om samtykke i Samtykkecenter og konfigureret reglerne for de importerede samtykkedata, synkroniseres objektet *Samtykke* automatisk til målgruppeindsigt.

## <a name="enable-consent-checks"></a>Aktivér samtykketjek

Når der er konfigureret samtykkedata til Samtykkecenter (forhåndsversion) og regler, kan du aktivere kontrol af dit samtykke målgruppeindsigt. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Fanen Samtykke i målgruppeindsigtsindstillinger med aktiverede samtykkedata.":::

1. Gå til **Admin** > **System** i målgruppen Insights.

1. Vælg fanen **Samtykke (forhåndsversion)**.

1. Angiv skift for det område, du vil aktivere, til **Til** i sektionen **Aktivér kontrol af samtykke**.

1. Markér afkrydsningsfeltet **Tillad tilsidesættelse af standardregler for samtykke** for at fjerne de standardkontroller for samtykke, der håndhæves på et bestemt segment. 

1. Vælg, hvor du vil tillade tilsidesættelser, på rullemenuen.     

1. Vælg den attribut, der bruges som id, i sektionen **Link til kundeprofiler** for at knytte samtykkedata til kundedata. Det er sandsynligvis et telefonnummer eller en e-mailadresse. 

1. Vælg **Gem** for at anvende indstillingerne.

## <a name="disable-consent-checks"></a>Deaktiver samtykketjek

En administrator skal opdatere systemindstillingerne efter målgruppe for at ophøre med at bruge samtykkedata i denne indsigt.

1. Gå til **Admin** > **System** i målgruppen Insights.

1. Vælg fanen **Samtykke (forhåndsversion)**.

1. Angiv skift til **Fra** i sektionen **Aktiver godkendelseskontrol**.
