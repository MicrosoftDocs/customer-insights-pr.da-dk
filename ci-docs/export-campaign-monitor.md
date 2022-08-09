---
title: Eksport segmenter til kampagneovervågning (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til kampagneovervågning.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196295"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Eksport segmenter til kampagneovervågning (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til Kampagneovervågning, og brug dem til marketingaktiviteter.

## <a name="prerequisites"></a>Forudsætninger

- En [kampagneovervågningskonto](https://www.campaignmonitor.com/) og tilsvarende administratorlegitimationsoplysninger.
- En [Liste-id for Campaign Monitor](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- En [Genereret API-nøglen](https://www.campaignmonitor.com/api/getting-started/) fra **Kontoindstillinger** i Kampagneovervågning for at få API-liste-id.
- [Konfigurerede segmenter](segments.md) i Customer Insights.
- Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Det kan tage op til 20 minutter at fuldføre op til 1 million kundeprofiler til Campaign Monitor. Antallet af kundeprofiler, du kan eksportere til Campaign Monitor, afhænger af din kontrakt med Campaign Monitor.
- Kun segmenter.

## <a name="set-up-connection-to-campaign-monitor"></a>Konfigurer forbindelse til Kampagneovervågning

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse** og vælg **Campaign Monitor**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret** forbindelse for at initialisere forbindelsen til Kampagneovervågning.

1. Vælg **Autentificer** med kampagneovervågning, og angiv administratoroplysningerne for Kampagneovervågning.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Hvis du vil oprette en ny eksport, skal du vælge **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Kampagneovervågning i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Angiv din **Kampagneovervågningsliste-id**.

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**. Det er obligatorisk at eksportere segmenter til Kampagneovervågning.

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
