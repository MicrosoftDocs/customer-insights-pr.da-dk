---
title: Power Automate-connector | Microsoft Docs
description: Oprette flows i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 409792bc3f12fca451ef038e3300758bdf9ecf3b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646337"
---
# <a name="power-automate-connector-preview"></a>Power Automate-connector (prøveversion)

Udløs specifikke hændelser, der skal udføres automatisk, når dataene ændres, og administrer mere komplekse processer direkte i [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Kendte begrænsninger

- Du kan foretage op til 100 opkald pr. 60 sekunder. Du kan kalde API-slutpunkt flere gange ved hjælp af $skip parameteren. [Få mere at vide om $skip parameter](/connectors/customerinsights/#get-items-from-an-entity).

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

1. Gå til **Administration** > **Eksportdestinationer**.

1. På feltet **Power Automate** skal du vælge **Konfigurer**.

1. Customer Insights-connector (prøveversion) i Power Automate åbnes. **Log på** Power Automate.

1. Vælg en af de tilgængelige udløsere, og tilføj flere trin i det nye flow. Du kan finde flere oplysninger under [Oprettelse af et skyflow i Power Automate](/power-automate/get-started-logic-flow).

Eksempler på, hvordan du bruger flow: 
- Sende en meddelelse til en Microsoft Teams-kanal, hvis en datakilde ikke kan opdateres. 
- Send en mail til dataejerne, når en grænseværdi for et segment overskrides.



[!INCLUDE [footer-include](includes/footer-banner.md)]
