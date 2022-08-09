---
title: Eksportere segmenter til Snapchat (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195375"
---
# <a name="export-segments-to-snapchat-preview"></a>Eksportere segmenter til Snapchat (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til Snapchat, og brug dem til marketing.

## <a name="prerequisites"></a>Forudsætninger

- En [Snapchat-forretningskonto](https://business.snapchat.com/), en [Snapchat Ads-konto](https://ads.snapchat.com/) og tilsvarende legitimationsoplysninger. Du skal som minimum være medlem af en organisationskonto og datastyring for et bestemt annoncekonto.
- Du har mindst én målgruppe i Snapchat-målgruppen af typen SAM (Snap målgruppe Match).
- [Snapchat-segment/Målgruppe-ID](https://businesshelp.snapchat.com/s/article/custom-audiences). Id'et for publikum findes i webadressen, når du har valgt publikum i Snapchat publikum Manager.
- [Konfigurerede segmenter](segments.md) i Customer Insights.
- Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 1 million kundeprofiler, som kan tage op til 15 minutter at fuldføre.
- Kun segmenter.

## <a name="set-up-connection-to-snapchat"></a>Konfigurer forbindelsen til Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Snapchat**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen.

1. Vælg **Autentificer med Snapchat**, og angiv administratoroplysningerne for Snapchat.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Snapchat i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Angiv **Snapchat-segment/målgruppe-id**.

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**.

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
