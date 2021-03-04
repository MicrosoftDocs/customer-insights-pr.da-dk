---
title: Power Automate-connector | Microsoft Docs
description: Oprette flows i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268817"
---
# <a name="power-automate-connector-preview"></a>Power Automate-connector (prøveversion)

Udløs specifikke hændelser, der skal udføres automatisk, når dataene ændres, og administrer mere komplekse processer direkte i [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate-udløsere

Brug udløsere til at oprette skystrømme og automatisere tilbagevendende opgaver, f.eks. meddelelser eller mere avancerede handlinger. 

- Udløses, når en opdatering af datakilde mislykkes. 
- Udløses, når en opdatering af datakilde lykkes.
- Udløses, når en tærskel krydses i et segment. Udløseren er begrænset til krydsning over grænsen.
- Udløses, når en tærskel krydses i en forretningsmæssig måling. Udløseren er begrænset til krydsning over grænsen.
- Udløser, når en fuld opdatering af (datakilder, segmenter, målinger....) er fuldført.
- Udløser, når en opdatering af samlingsprocessen (tilknytning, match, fletning) er fuldført.

[Konfigurere dine udløsere i Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate-handlinger
Power Automate-connectoren giver andre handlinger end de tilgængelige udløsere. Se [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/), hvis du vil have flere oplysninger.

## <a name="create-a-power-automate-flow"></a>Oprette et Power Automate-flow

1. Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.

1. På feltet **Power Automate** skal du vælge **Konfigurer**.

1. Customer Insights-connector (prøveversion) i Power Automate åbnes. **Log på** Power Automate.

1. Vælg en af de tilgængelige udløsere, og tilføj flere trin i det nye flow. Du kan finde flere oplysninger under [Oprettelse af et skyflow i Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Eksempler på, hvordan du bruger flow: 
- Sende en meddelelse til en Microsoft Teams-kanal, hvis en datakilde ikke kan opdateres. 
- Send en mail til dataejerne, når en grænseværdi for et segment overskrides.



[!INCLUDE[footer-include](../includes/footer-banner.md)]