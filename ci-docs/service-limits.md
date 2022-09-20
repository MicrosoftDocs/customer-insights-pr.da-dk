---
title: Servicegrænser i Customer Insights
description: Forstå grænser og begrænsninger i Customer Insights SaaS-tjeneste.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c3863b1a72fd92ddc87755699feda11371ec9214
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463212"
---
# <a name="service-limits-in-customer-insights"></a>Servicegrænser i Customer Insights

 Customer Insights har indbyggede grænser for at sikre pålidelighed og stabilitet af servicen. Anmodninger om ændringer kan foretages i [ideforum](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Område  | Grænser  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenter, mål og forudsigelser | 300  | Det samlede antal kombinerede [segmenter](segments.md), [mål](measures.md) og [forudsigelser](predictions-overview.md) må ikke være større end 300.  |
| Relationer | 20 niveauers relationer i objektstier. | Når du opretter [segmenter](segments.md) eller [måler](measures.md) ved hjælp af brugergrænsefladen i generatoren, kan objektstier have op til 20 relationsforløb mellem startobjektet og destinationsobjektet.  |
|Dataindtagelse| Der er begrænset antal samtidige evalueringer for Power Query-datakilder. | Customer Insights har de samme [opdateringsbegrænsninger som dataflow i PowerBI.com](/power-query/power-query-online-limits#refresh-limits). |

## <a name="fair-scheduling-of-jobs"></a>Rimelig planlægning af job

Customer Insights er en SaaS-tjeneste, der bruger delte Azure-ressourcer. Kunder med forskellige arbejdsbelastninger og efter forskellige planer. For at sikre fair adgang til de underliggende ressourcer sikrer vi, at systemprocesser udføres i fair rækkefølge. Eksempler på systemprocesser er job, der er relateret til datas enhed, segmentopdateringer eller måling af beregninger. Den rimelige planlægning beskytter dig mod kø for ressourcer, hvis der er anmodet om job. Samtidig garanterer Customer Insights ikke, at alle job, du sætter i kø, behandles parallelt.

[!INCLUDE [footer-include](includes/footer-banner.md)]
