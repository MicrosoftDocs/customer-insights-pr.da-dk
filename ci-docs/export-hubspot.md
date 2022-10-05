---
title: Eksportere Customer Insights-data til HubSpot
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporten til HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588901"
---
# <a name="export-segments-to-hubspot-preview"></a>Eksportere segmenter til HubSpot (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til HubSpot, og brug dem til mailmarketing.

## <a name="prerequisites-for-a-connection"></a>Forudsætninger for en forbindelse

- En [HubSpot-konto](https://www.hubspot.com/) og tilsvarende administratorlegitimationsoplysninger.
- [API-nøgle](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) fra HubSpot.
- [Konfigurerede segmenter](segments.md) i Customer Insights.

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 100.000 kundeprofiler pr. eksport til HubSpot, som kan tage op til 15 minutter at gennemføre. Antallet af kundeprofiler, du kan eksportere til HubSpot, er begrænset og afhænger af din kontrakt med HubSpot.
- Kun segmenter.

## <a name="set-up-connection-to-hubspot"></a>Konfigurere forbindelsen til HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **HubSpot** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv dine HubSpot-legitimationsoplysninger, når du bliver bedt om dem.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til HubSpot.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Hvis du vil oprette en ny eksport, skal du vælge **Tilføj eksport**.

1. Vælg en forbindelse i sektionen HubSpot i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**. Gentag de samme trin for andre valgfrie felter.

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
