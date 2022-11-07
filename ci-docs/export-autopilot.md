---
title: Eksportér segmenter til Autopilot (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724750"
---
# <a name="export-segments-to-autopilot-preview"></a>Eksportér segmenter til Autopilot (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til Autopilot, og brug dem til mailmarketing i Autopilot.

## <a name="prerequisites-for-a-connection"></a>Forudsætninger for en forbindelse

- En [Autopilot-konto](https://www.autopilothq.com/) og tilsvarende administratorlegitimationsoplysninger.
- En [Autopilot API-nøgle](https://autopilot.docs.apiary.io/#)
- [Konfigurerede segmenter](segments.md) i Customer Insights.
- Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Private Link i kombination med BYOS (Bring your own storage) understøttes ikke.
- Det kan tage op til et par timer at eksportere op til 100.000 kundeprofiler til Autopilot. Antallet af kundeprofiler, du kan eksportere til Autopilot, afhænger af din kontrakt med Autopilot.
- Kun segmenter.

## <a name="set-up-connection-to-autopilot"></a>Konfigurer forbindelsen til Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Autopilot**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv Autopilot-API-nøglen.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Autopilot i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**.

1. Du kan også eksportere andre felter, f.eks. **fornavn** og **efternavn**.

1. Vælg de segmenter, der skal eksporteres med tilknyttede kendte begrænsninger.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
