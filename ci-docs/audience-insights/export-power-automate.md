---
title: Power Automate-connector | Microsoft Docs
description: Oprette flows i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405408"
---
# <a name="power-automate-connector-preview"></a>Power Automate-connector (prøveversion)

Udløs specifikke hændelser, der skal udføres automatisk, når dataene ændres, og administrer mere komplekse processer direkte i [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate-udløsere

Du kan bruge forskellige udløsere, som giver dig mulighed for at oprette flow til at automatisere rutineopgaver, f.eks. meddelelser eller mere avancerede handlinger. 

- Udløses, når en opdatering af datakilde mislykkes. 
- Udløses, når en opdatering af datakilde lykkes.
- Udløses, når en tærskel krydses i et segment. Udløseren er begrænset til krydsning over grænsen.
- Udløses, når en tærskel krydses i en forretningsmæssig måling. Udløseren er begrænset til krydsning over grænsen.
- Udløser, når en fuld opdatering af (datakilder, segmenter, målinger....) er fuldført.
- Udløser, når en opdatering af samlingsprocessen (tilknytning, match, fletning) er fuldført.

[Konfigurere dine udløsere i Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate-handlinger
Power Automate-connectoren giver andre handlinger end de tilgængelige udløsere. Se [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/), hvis du vil have flere oplysninger.

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Opret et Power Automate-flow i målgruppen Insights

1. Gå til **Admin** > **System** i målgruppen Insights.

1. Vælg fanen **Status** på siden **System**.

1. Vælg **Flow** i sektionen **Datakilder**, og vælg **Opret et flow** på rullelisten.
   > [!div class="mx-imgBorder"]
   > ![Power Automate-connector viser Opret et flow-handling](media/power-automate-connector-create-flow.png "Power Automate-connector viser Opret et flow-handling")

1. I Power Automate skal du vælge en af de tilgængelige udløsere for at oprette dit foretrukne flow. Hvis du opretter dit første flow, skal du først godkendes af Power Automate-connectoren.
