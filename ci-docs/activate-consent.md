---
title: Aktivere samtykkeregler for segmenter
description: Følg disse trin for at tilknytte samtykkedata og aktivere kontrol af samtykke i Dynamics 365 Customer Insights. En administrator kan også deaktivere kontrol af samtykke.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646046"
---
# <a name="activate-consent-rules"></a>Aktivér samtykkeregler

[Samtykkecenter (forhåndsversion)](consent-management/overview.md) hjælper dig med at indsamle samtykkedata fra forskellige kilder. Brug objektet samlet *samtykke* til at anvende standardkontrol af samtykke. Når der er importeret data om samtykke i Samtykkecenter, og reglerne er konfigureret for dataene, synkroniseres objektet *Samtykke* automatisk med Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Aktivér samtykketjek

Når der er importeret samtykkedata til Samtykkecenter (forhåndsversion), og reglerne er konfigureret, kan du aktivere tjek af samtykke. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Fanen Samtykke i Customer Insights-indstillinger med aktiverede samtykkedata.":::

1. Gå til **Administration** > **System** i Customer Insights.

1. Vælg fanen **Samtykke (forhåndsversion)**.

1. Angiv til/fra-knappen for alle de områder, du vil aktivere, til **Til** i sektionen **Aktivér samtykketjek**.

1. Markér afkrydsningsfeltet **Tillad tilsidesættelse af standardregler for samtykke** for at fjerne de standardkontroller for samtykke, der håndhæves på et bestemt segment. 

1. Vælg, hvor du vil tillade tilsidesættelser, på rullemenuen.     

1. Vælg den attribut, der bruges som id, i sektionen **Link samtykke til kundeprofiler** for at knytte samtykkedata til kundedata. Det er sandsynligvis et telefonnummer eller en mailadresse. 

1. Vælg **Gem** for at anvende indstillingerne.

## <a name="disable-consent-checks"></a>Deaktiver samtykketjek

En administrator skal opdatere systemindstillingerne efter Customer Insights for at ophøre med at bruge samtykkedata i denne indsigt.

1. Gå til **Administration** > **System** i Customer Insights.

1. Vælg fanen **Samtykke (forhåndsversion)**.

1. Angiv til/fra-knappen til **Fra** i sektionen **Aktivér samtykketjek**.

> [!TIP]
> Hvis du vil ophøre med at bruge funktionen til administration af samtykke, skal du se [Systemindstillinger i Samtykkecenter (forhåndsversion)](consent-management/system-settings.md).
