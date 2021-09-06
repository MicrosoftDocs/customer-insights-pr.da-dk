---
title: Power Automate-connector | Microsoft Docs
description: Oprette flows i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 95e0fcbfb43f2b3e7e2d0e8a1690dc7ff5a44433402b7ef3d437710eb0efff15
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035592"
---
# <a name="power-automate-connector-preview"></a>Power Automate-connector (prøveversion)

Udløs specifikke hændelser, der skal udføres automatisk, når dataene ændres, og administrer mere komplekse processer direkte i [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate-udløsere

Brug udløsere til at oprette skystrømme og automatisere tilbagevendende opgaver, f.eks. meddelelser eller mere avancerede handlinger. 

- Udløses, når en opdatering af datakilde mislykkes. 
- Udløses, når en opdatering af datakilde lykkes.
- Udløses, når en tærskel krydses i et segment. Udløseren er begrænset til krydsning over grænsen.
- Udløses, når en tærskel krydses i en forretningsmæssig måling. Det er kun forretningsmålinger uden en dimension, der understøttes. Udløseren er begrænset til krydsning over grænsen.
- Udløser, når en fuld opdatering af (datakilder, segmenter, målinger...) er fuldført.
- Udløser, når en opdatering af samlingsprocessen (tilknytning, match, fletning) er fuldført.

[Konfigurere dine udløsere i Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate-handlinger

Power Automate-connectoren giver andre handlinger end de tilgængelige udløsere. Se [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/), hvis du vil have flere oplysninger.

## <a name="create-a-power-automate-flow"></a>Oprette et Power Automate-flow

1. Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.

1. På feltet **Power Automate** skal du vælge **Konfigurer**.

1. Customer Insights-connector (prøveversion) i Power Automate åbnes. **Log på** Power Automate.

1. Vælg en af de tilgængelige udløsere, og tilføj flere trin i det nye flow. Du kan finde flere oplysninger under [Oprettelse af et skyflow i Power Automate](/power-automate/get-started-logic-flow).

Eksempler på, hvordan du bruger flow: 
- Sende en meddelelse til en Microsoft Teams-kanal, hvis en datakilde ikke kan opdateres. 
- Send en mail til dataejerne, når en grænseværdi for et segment overskrides.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
