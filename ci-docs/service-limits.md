---
title: Servicebegrænsninger i Dynamics 365 Customer Insights
description: Forstå grænser og begrænsninger.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791974"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Servicegrænser i funktioner i Customer Insights

I denne artikel beskrives de indbyggede begrænsninger for Customer Insights-tjenesten, som er udviklet for at sikre pålidelighed og stabilitet af tjenesten. Anmodninger om ændringer kan foretages i [ideforum](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Indsigt i målgruppe

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Tjenestebegrænsninger i Dynamics 365 Customer Insights-funktionen med målgruppen Insights

| Område  | Grænser  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenter, mål og forudsigelser | 300  | Det samlede antal kombinerede [segmenter](audience-insights/segments.md), [mål](audience-insights/measures.md) og [forudsigelser](audience-insights/predictions.md) må ikke være større end 300.  |
| Relationer | 20 niveauers relationer i objektstier. | Når du opretter [segmenter](audience-insights/segments.md) eller [måler](audience-insights/measures.md) ved hjælp af brugergrænsefladen i generatoren, kan objektstier have op til 20 relationsforløb mellem startobjektet og destinationsobjektet.  |


## <a name="engagement-insights"></a>Engagementsindsigt

### <a name="workspace-and-event-quotas"></a>Arbejdsområde- og hændelseskvoter

Engagementsindsigt er et yderst skalerbart program, der kan understøtte millioner af arrangementer i sekundet. Under offentlig forhåndsversion har hændelser en volumentærskelværdi. Der er også en grænse for antallet af arbejdsområder i en organisation.

### <a name="engagement-insights-limits"></a>Begrænsninger i engagementsindsigt

- Maksimalt hændelsesmængde pr. arbejdsområde = 100 hændelser i sekundet

- Maksimalt antal arbejdsområder pr. organisation = 100

Når hændelser overskrider grænsen, kan det medføre tab af data i rapporter baseret på disse hændelser. Du kan [kontakte support](https://go.microsoft.com/fwlink/?linkid=2145734) for at anmode om en forøgelse af mængden, før du overskrider grænseværdierne. Vi vil arbejde sammen med dig om at finde ud af, om du har brug for at øge mængden, og så vi kan understøtte din anmodning.


[!INCLUDE[footer-include](includes/footer-banner.md)]
