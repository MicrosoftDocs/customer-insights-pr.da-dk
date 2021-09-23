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
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483655"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Servicegrænser i funktioner i Customer Insights

I denne artikel beskrives de indbyggede begrænsninger for Customer Insights-tjenesten, som er udviklet for at sikre pålidelighed og stabilitet af tjenesten. Anmodninger om ændringer kan foretages i [ideforum](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Indsigt i målgruppe

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Tjenestebegrænsninger i Dynamics 365 Customer Insights-funktionen med målgruppen Insights

| Område  | Grænser  | Noter |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenter og målinger | 100 segmenter eller målpunkter. | Det samlede antal aktive [segmenter](audience-insights/segments.md) og [målpunkter](audience-insights/measures.md), der er kombineret, må ikke overstige 100.  |
| Relationer | 20 niveauers relationer i objektstier. | Når du opretter [segmenter](audience-insights/segments.md) eller [måler](audience-insights/measures.md) ved hjælp af brugergrænsefladen i generatoren, kan objektstier have op til 20 relationsforløb mellem startobjektet og destinationsobjektet.  |


## <a name="engagement-insights"></a>Engagementsindsigt

### <a name="workspace-and-event-quotas"></a>Arbejdsområde- og hændelseskvoter

Engagementsindsigt er et yderst skalerbart program, der kan understøtte millioner af arrangementer i sekundet. Under offentlig forhåndsversion har hændelser en volumentærskelværdi. Der er også en grænse for antallet af arbejdsområder i en organisation.

### <a name="engagement-insights-limits"></a>Begrænsninger i engagementsindsigt

- Maksimalt hændelsesmængde pr. arbejdsområde = 100 hændelser i sekundet

- Maksimalt antal arbejdsområder pr. organisation = 100

Når hændelser overskrider grænsen, kan det medføre tab af data i rapporter baseret på disse hændelser. Du kan [kontakte support](https://go.microsoft.com/fwlink/?linkid=2145734) for at anmode om en forøgelse af mængden, før du overskrider grænseværdierne. Vi vil arbejde sammen med dig om at finde ud af, om du har brug for at øge mængden, og så vi kan understøtte din anmodning.


[!INCLUDE[footer-include](includes/footer-banner.md)]