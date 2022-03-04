---
title: Servicebegrænsninger i Dynamics 365 Customer Insights
description: Forstå grænser og begrænsninger.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350400"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Servicegrænser i funktioner i Customer Insights

I denne artikel beskrives de indbyggede begrænsninger for Customer Insights-tjenesten, som er udviklet for at sikre pålidelighed og stabilitet af tjenesten. Anmodninger om ændringer kan foretages i [ideforum](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Indsigt i målgruppe

| Område  | Grænser  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmenter, mål og forudsigelser | 300  | Det samlede antal kombinerede [segmenter](audience-insights/segments.md), [mål](audience-insights/measures.md) og [forudsigelser](audience-insights/predictions.md) må ikke være større end 300.  |
| Relationer | 20 niveauers relationer i objektstier. | Når du opretter [segmenter](audience-insights/segments.md) eller [måler](audience-insights/measures.md) ved hjælp af brugergrænsefladen i generatoren, kan objektstier have op til 20 relationsforløb mellem startobjektet og destinationsobjektet.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
