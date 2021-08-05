---
title: Tjenestebegrænsninger
description: Forstå grænser og begrænsninger.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604362"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Tjenestebegrænsninger i Dynamics 365 Customer Insights-funktionen med målgruppen Insights

I denne artikel beskrives de indbyggede begrænsninger for Customer Insights-tjenesten, som er udviklet for at sikre pålidelighed og stabilitet af tjenesten. Anmodninger om ændringer kan foretages i [ideforum](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Område  | Grænser  | Noter |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenter og målinger | 100 segmenter eller målpunkter. | Det samlede antal aktive [segmenter](segments.md) og [målpunkter](measures.md), der er kombineret, må ikke overstige 100.  |
| Relationer | 20 niveauers relationer i objektstier. | Når du opretter [segmenter](segments.md) eller [måler](measures.md) ved hjælp af brugergrænsefladen i builderen, kan objektstier have op til 20 relationsforløb mellem startobjektet og destinationsobjektet.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]