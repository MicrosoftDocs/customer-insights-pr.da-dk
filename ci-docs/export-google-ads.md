---
title: Eksport af segmenter til Google Ads (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725071"
---
# <a name="export-segments-to-google-ads-preview"></a>Eksport af segmenter til Google Ads (forhåndsversion)

Eksporter segmenter af samlede kundeprofiler til en Liste over Google Ads-målgruppe, og brug dem til at annoncere på Google Søgning, Gmail, YouTube og Google Display Network.

## <a name="prerequisites"></a>Forudsætninger

- En [Google Ads-konto](https://ads.google.com/) og tilsvarende administratorlegitimationsoplysninger.
- En [Google Ads-kunde-id](https://support.google.com/google-ads/answer/1704344).
- Du opfylder kravene i [Politik for Customer Match](https://support.google.com/adspolicy/answer/6299717).
- Du opfylder kravene til [listestørrelser for re-marketing](https://support.google.com/google-ads/answer/7558048).
- [Konfigurerede segmenter](segments.md).
- Ensartede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en mailadresse, en telefon, et mobil annoncør-id, et tredjepartsbruger-id eller en adresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Private Link i kombination med BYOS (Bring your own storage) understøttes ikke.
- Op til 1 millioner kundeprofiler pr. eksport til Google Ads, som kan tage op til 30 minutter at fuldføre på grund af begrænsninger på udbydersiden.
- Kun segmenter.
- Det kan tage op til 48 timer at foretage match i Google Ads.

## <a name="set-up-connection-to-google-ads"></a>Konfigurer forbindelse til Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Google Ads**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv din Google Ads-kunde-id.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Godkendelse med Google Ads**, og angiv dine Google Ads-legitimationsoplysninger.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Google Ads i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Vælg, om du vil bruge en eksisterende målgruppe eller oprette et nyt:
   - Hvis du vil opdatere en eksisterende Google Ads-målgruppe, skal du angive dit [Google Ads-målgruppe-id](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Hvis du vil oprette en ny målgruppe, skal du lade Google Målgruppe-id være tomt. Customer Insights opretter automatisk en ny målgruppe i din Google Ads-konto og bruger navnet på det eksporterede segment.

1. Vælg et eller flere datafelter, du vil eksportere, i sektionen **Datatilpasning**, og vælg det felt, der repræsenterer de tilsvarende datafelter i Customer Insights.

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
