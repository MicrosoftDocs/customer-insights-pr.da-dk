---
title: Forhøjelse af virksomhedsprofiler med tredjeparts Leadspace
description: Generelle oplysninger om Leadspace-tilsætning af tredjepart.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597642"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Forbedring af virksomhedsprofiler med Leadspace (prøveversion)

Leadspace er en videnskabelig datavirksomhed, der leverer en B2B-kundedataplatform. Den gør det muligt for kunder, der har en samlet kundeprofil for virksomheder, at forbedre deres data. Forbedringer omfatter yderligere attributter som f.eks. firmastørrelse, lokation, branche og meget mere.

## <a name="prerequisites"></a>Forudsætninger

Hvis du vil konfigurere Leadspace, skal følgende forudsætninger være opfyldt:

- Du har en aktiv Leadspace-licens og den "permanente nøgle" (kaldes **Leadspace token**). Kontakt direkte [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for at få oplysninger om deres produkt.
- Du har [Administrator](permissions.md#administrator)-tilladelser.
- Du har [samlede kundeprofiler](customer-profiles.md) til virksomheder.

## <a name="configuration"></a>Konfiguration

1. Gå til **Data** > **Forbedring** i målgruppeindsigt.

1. Vælg **Forbedr mine data** på Leadspace-feltet.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skærmbillede af Leadspace-feltet.":::

1. Vælg **Start her**, og angiv derefter et aktivt **Leadspace-token** (permanent nøgle). Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**. Bekræft begge input ved at vælge **Opret forbindelse til Leadspace**.

1. Vælg **Tilknyt data** , og vælg det datasæt, du vil forbedre med firmadata fra Leadspace. Du kan vælge objektet *Kunde* for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Vælg mellem kundeprofil og forbedring af segment.":::

1. Klik på **Næste**, og definer, hvilke felter fra dine samlede profiler der skal bruges til at søge efter de tilsvarende virksomhedsdata fra Leadspace. Feltet **Firmanavn** er obligatorisk. Hvis du vil opnå en større overensstemmelse, kan du tilføje op til to andre felter, **Virksomheds-websteder** og **Virksomhedsplacering**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-felttilknytningsruden.":::
   
1. Vælg **Anvend** for at fuldføre felttilknytningen.

1. Vælg **Kør** for at forbedre firmaprofilerne. Hvor længe en forbedring tager, afhænger af antallet af samlede kundeprofiler.

## <a name="enrichment-results"></a>Forbedringsresultater

Når du har opdateret forbedring, kan du gennemse de netop forbedrede virksomhedsdata under [Mine forbedringer](enrichment-hub.md). Du kan se tidspunktet for den seneste opdatering og antallet af forbedrede profiler.

Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.

Du kan finde flere oplysninger under [Leadspace-API'er](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Næste trin

Byg oven over dine forbedrede kundedata. Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Leadspace, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Leadspace overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]