---
title: Eksportere segmenter til Braze (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725209"
---
# <a name="export-segments-to-braze-preview"></a>Eksportere segmenter til Braze (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til Braze, og brug dem til marketingaktiviteter.

## <a name="prerequisites"></a>Forudsætninger

- En [Braze-konto](https://www.braze.com/) og tilhørende administratorlegitimationsoplysninger.
- En [Braze-API-nøgle](https://www.braze.com/docs/api/basics/)
- Dit [Braze REST-slutpunkt](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Konfigurerede segmenter](segments.md) i Customer Insights.
- Ensartede kundeprofiler i de eksporterede segmenter indeholder et felt, der repræsenterer en mailadresse og et Braze-kunde-id.

## <a name="known-limitations"></a>Kendte begrænsninger

- Private Link i kombination med BYOS (Bring your own storage) understøttes ikke.
- Op til 1 million kundeprofiler til Braze, som kan tage op til 40 minutter at fuldføre. Antallet af kundeprofiler, du kan eksportere til Braze, afhænger af din kontrakt med Braze.
- Kun segmenter.
- Azure Private Link understøttes ikke i forbindelse med Braze-eksport.

## <a name="set-up-connection-to-braze"></a>Konfigurer forbindelsen til Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Braze**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv din Braze API-nøgle, så du fortsat kan logge på.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse fra Braze-sektionen i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv dit REST-slutpunkt i feltet **Værtsnavn** i følgende format: `rest.iad-03.braze.com`.

1. Angiv et navn for eksporten.

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**. Vælg det felt, der svarer til kundens Braze-id i feltet feltet **Kunde-id**. Segmenterne i Braze oprettes med samme navn som i Dynamics 365 Customer Insights. Du kan vælge flere valgfrie felter til tilpasning af data.

1. Markér de objekter eller segmenter, du vil eksportere.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
