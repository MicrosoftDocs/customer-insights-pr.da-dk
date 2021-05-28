---
title: Eksportere data fra Customer Insights
description: Administrer dataeksport til at dele data.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016607"
---
# <a name="exports-preview-overview"></a>Eksportoversigt (forhåndsversion)

På siden **Eksport** vises alle de konfigurerede eksporter. Eksporter deler specifikke data med forskellige programmer. De kan omfatte kundeprofiler eller objekter, skemaer og tilknytningsoplysninger. Hver eksport kræver en [forbindelse, konfigureret af en administrator, til at administrere godkendelse og adgang](connections.md).

Gå til **Data** > **Eksport** for at få vist eksportsiden. Alle brugerroller har adgang til at få vist konfigurerede eksporter. Brug af søgefeltet på kommandolinjen til at søge efter eksporter efter navn, forbindelsesnavn eller forbindelsestype.

## <a name="set-up-a-new-export"></a>Konfigurer en ny eksport

Hvis du vil konfigurere eller redigere en eksport, skal du have tilgængelige forbindelser. Forbindelser afhænger af [brugerrollen](permissions.md):
- Administratorer har adgang til alle forbindelser. De kan også oprette nye forbindelser, når en eksport konfigureres.
- Bidragydere kan have adgang til bestemte forbindelser. De er afhængige af administratorer, når de skal konfigurere og dele forbindelser. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Fremvisere kan kun få vist eksisterende eksporter, men ikke oprette dem.

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport** for at oprette en ny eksport destination.

1. Vælg, hvilken forbindelse du vil bruge, i ruden **Konfigurer eksport**. [Forbindelser](connections.md) administreres af administratorer. 

1. Angiv de nødvendige oplysninger, og vælg **Gem** for at oprette eksporten.

### <a name="edit-an-export"></a>Rediger en eksport

1. Vælg den lodrette ellipse for den eksportdestination, du vil redigere.

1. Vælg **Rediger** fra rullemenuen.

1. Opdatér de værdier, du vil opdatere, og vælg **Gem**.

## <a name="view-exports-and-export-details"></a>Få vist eksport- og eksportdetaljer

Når du har oprettet eksportmål, vises de under **Data** > **Eksport**. Alle brugere kan se, hvilke data der deles, og den seneste status.

1. Gå til **Data** > **Eksport**.

1. Brugere uden redigeringstilladelser vælger **Vis** i stedet for **Rediger**, og se eksportdetaljerne.

1. I denne siderude vises opsætningen af denne eksport. Uden redigeringstilladelser kan du ikke ændre værdier. Vælg **Luk** for at vende tilbage til eksportsiden.

## <a name="run-exports-on-demand"></a>Kør eksporter efter behov

Når du har konfigureret en eksport, køres den med alle [planlagte opdateringer](system.md#schedule-tab), så længe den har en arbejdsforbindelse.

Hvis du vil eksportere data uden at vente på en planlagt opdatering, skal du gå til **Data** > **Eksport**. Du har to muligheder:

- Hvis du vil køre alle eksporter, skal du vælge **Kør alle** på kommandolinjen. 
- Hvis du vil køre en enkelt eksport, skal du vælge ellipsen (...) på et listeelement og derefter vælge **Kør**.

## <a name="remove-an-export"></a>Fjerne en eksport

1. Gå til **Data** > **Eksport**.

1. Vælg den lodrette ellipse for den eksportdestination, du vil fjerne.

1. Vælg **Fjern** på rullelisten.

1. Bekræft fjernelsen ved at vælge **Fjern** på bekræftelsesskærmen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
