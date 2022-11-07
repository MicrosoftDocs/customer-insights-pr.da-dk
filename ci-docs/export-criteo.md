---
title: Eksportere segmenter til Criteo (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 61435030254638965fbeb7980312e73695416aa2
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724782"
---
# <a name="export-segments-to-criteo-preview"></a>Eksportere segmenter til Criteo (forhåndsversion)

Eksportér segmenter af samlede kundeprofiler for at generere kampagner, levere mailmarketing og bruge bestemte kundegrupper med Criteo.

## <a name="prerequisites"></a>Forudsætninger

- En [Criteo Dynamics Retargeting-konto](https://www.criteo.com/login/) og tilhørende administratorlegitimationsoplysninger.
- [Konfigurerede segmenter](segments.md).
- Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Private Link i kombination med BYOS (Bring your own storage) understøttes ikke.
- Du kan eksportere op til 1 million kundeprofiler pr. eksport til Criteo, og det kan tage op til 30 minutter at fuldføre den. Antallet af kundeprofiler, du kan eksportere til Criteo, afhænger af din kontrakt med Criteo.
- Kun segmenter.

## <a name="set-up-connection-to-criteo"></a>Konfigurer forbindelsen til Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Criteo**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen.

1. Vælg **Godkend med Criteo**, og angiv brugernavnet og legitimationsoplysningerne for administrator for Criteo.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse fra Criteo-sektionen i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**.

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
