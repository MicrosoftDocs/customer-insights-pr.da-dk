---
title: Eksportere segmenter til Microsoft Advertising (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196525"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Eksportere segmenter til Microsoft Advertising (forhåndsversion)

Eksporter Customer Insights-segmenter til Microsoft Advertising for at oprette målgrupper for Customer Match. Brug disse målgrupper til dine annoncekampagner.

## <a name="prerequisites"></a>Forudsætninger

- En [Microsoft Advertising-konto](https://ads.microsoft.com/) og tilsvarende administratorlegitimationsoplysninger.
- Microsoft Advertising-kunde-id og -konto-id. Find kunde-id' et (`cid`) og konto-id'et (`aid`) i parametrene for URL-adressen, når du er logget på Microsoft Advertising.
- Customer Match-betingelserne er accepteret.
- [Konfigurerede segmenter](segments.md) i Customer Insights.
- Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Det kan tage op til 10 minutter at eksportere op til 500.000 profiler til Microsoft Advertising.
- Kun segmenter.

## <a name="set-up-connection-to-microsoft-advertising"></a>Konfigurer forbindelsen til Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Microsoft Advertising**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Standarden er administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv **Microsoft Advertising-Kunde-id**.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen.

1. Vælg **Godkend med Microsoft Advertising**, og angiv administratoroplysningerne for Microsoft Advertising.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Microsoft Advertising i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Vælg de segmenter, du vil eksportere. Målgrupperne Customer Match i Microsoft Advertising oprettes automatisk med navnet på de segmenter, der er valgt til eksport. Hvert segment resulterer i en separat Customer Match-målgruppe.

1. Angiv dit **Microsoft Advertising-kunde-id og -konto-id**.

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
