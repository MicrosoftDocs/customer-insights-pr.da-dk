---
title: Eksportere segmenter til Omnisend (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Omnisend.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fb57e2bd70592f4ce4e1a13e21901dc69734f6bf
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725163"
---
# <a name="export-segments-to-omnisend-preview"></a>Eksportere segmenter til Omnisend (forhåndsversion)

Eksportere segmenter med ensartede kundeprofiler til Omnisend, og brug dem til marketingaktiviteter.

## <a name="prerequisites"></a>Forudsætninger

- En [Omnisend-konto](https://www.omnisend.com/) og tilsvarende administratorlegitimationsoplysninger.
- En [Omnisend API-nøgle](https://support.omnisend.com/en/articles/1061890-generating-api-key).
- [Konfigurerede segmenter](segments.md) i Customer Insights.
- Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Private Link i kombination med BYOS (Bring your own storage) understøttes ikke.
- Du kan eksportere op til 1 million kundeprofiler pr. eksport til Omnisend, og det kan tage op til fire timer at fuldføre den. Antallet af kundeprofiler, du kan eksportere til Omnisend, afhænger af din kontrakt med Omnisend.
- Kun segmenter.

## <a name="set-up-connection-to-omnisend"></a>Konfigurer forbindelsen til Omnisend

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Omnisend**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv Omnisend-API-nøglen.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Omnisend i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**.

1. Du kan også eksportere **Fornavn**, **Efternavn**, **Adresse**, **Land/område**, **Stat**, **By** og **Postnummer** for at oprette mere personlige e-mails. Vælg **Tilføj attribut** for at tilknytte disse felter.

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
