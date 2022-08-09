---
title: Eksportere segmenter til MoEngage
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199087"
---
# <a name="export-segments-to-moengage-preview"></a>Eksportér segmenter til MoEngage (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til MoEngage, og brug dem til mailmarketing i MoEngage.

## <a name="prerequisites-for-a-connection"></a>Forudsætninger for en forbindelse

- En [MoEngage-konto](https://www.moengage.com/) og tilsvarende administratorlegitimationsoplysninger.
- MoEngage API-nøgle fra Settings > API i MoEngage.
- [Konfigurerede segmenter](segments.md) i Customer Insights.

## <a name="known-limitations"></a>Kendte begrænsninger

- Det kan tage op til 15 minutter at eksportere op til 100.000 profiler til MoEngage. Antallet af kundeprofiler, du kan eksportere til MoEngage, afhænger af din kontrakt med MoEngage.
- Kun segmenter.

## <a name="set-up-connection-to-moengage"></a>Konfigurer forbindelsen til MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **MoEngage** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv dit [MoEngage-data-API-id og din API-nøgle](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til MoEngage.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Hvis du vil oprette en ny eksport, skal du vælge **Tilføj eksport**.

1. Vælg en forbindelse i sektionen MoEngage i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**. Gentag de samme trin for andre valgfrie felter.

1. Vælg de segmenter, du vil eksportere. Vi opretter et eller flere segmenter med samme navn som de valgte segmenter i MoEngage under **Segmenter** > **Brugerdefinerede segmenter**.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
