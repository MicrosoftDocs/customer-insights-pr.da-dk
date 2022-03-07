---
title: Forhøjelse af virksomhedsprofiler med tredjeparts Leadspace
description: Generelle oplysninger om Leadspace-tilsætning af tredjepart.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305195"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Forbedring af virksomhedsprofiler med Leadspace (prøveversion)

Leadspace er en videnskabelig datavirksomhed, der leverer en B2B-kundedataplatform. Den gør det muligt for kunder, der har en samlet kundeprofil for virksomheder, at forbedre deres data. Forbedringer omfatter flere attributter, herunder firmastørrelse, lokation, branche og meget mere.

## <a name="prerequisites"></a>Forudsætninger

Hvis du vil konfigurere Leadspace, skal følgende forudsætninger være opfyldt:

- Du har en aktiv Leadspace-licens.
- Du har [samlede kundeprofiler](customer-profiles.md) til virksomheder.
- En Leadspace-forbindelse er allerede konfigureret af en administrator, eller du har [administrator](permissions.md#administrator)-tilladelser og den "permanente nøgle" (kaldes også **Leadspace-token**). Kontakt [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) direkte for at få oplysninger om produktet.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring** i målgruppeindsigt.

1. Vælg **Forbedr mine data** i feltet Leadspace, og vælg **Start her**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skærmbillede af Leadspace-feltet.":::

1. Vælg en [værdi](connections.md) på rullelisten. Kontakt en administrator, hvis der ikke er nogen forbindelse. Hvis du er administrator, kan du oprette en forbindelse ved at vælge **Tilføj forbindelse** og vælge **Leadspace**. 

1. Vælg **Opret forbindelse til Leadspace** for at bekræfte den valgte forbindelse.

1. Vælg **Næste**, og angiv de **Kundedatasæt**, du vil forbedre med firmadata fra Leadspace. Du kan vælge objektet **Kunde** for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Skærmbillede, når du vælger kundedatasættet.":::

1. Vælg **Næste**, og definer, hvilke felter fra dine samlede profiler der bruges til at søge efter tilsvarende virksomhedsdata fra Leadspace. Feltet **Firmanavn** er obligatorisk. Hvis du vil opnå en større overensstemmelse, kan du tilføje op til to andre felter, **Virksomheds-websteder** og **Virksomhedsplacering**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-felttilknytningsruden.":::

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Angiv et navn til den forbedring, du udvælger, og angiv **Vælg forbedring**, når du har gennemset dine valg.


## <a name="configure-the-connection-for-leadspace"></a>Konfiguration af forbindelsen til Leadspace 

Du skal være en administrator for at konfigurere forbindelser. Vælg **Tilføj forbindelse**, når du konfigurerer en konfiguration, *eller* gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i feltet Leadspace.

1. Vælg **Introduktion**. 

1. Angiv et navn til forbindelsen i feltet **Vis navn**.

1. Angiv dit Leadspace-token

1. Gennemse og giv dit samtykke til **Beskyttelse af personlige oplysninger og overholdelse af data** ved at vælge **Jeg accepterer**.

1. Vælg **Kontroller** for at validere konfigurationen.

1. Vælg **Gem**, når verifikationen er fuldført.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace-forbindelsens konfigurationsside.":::

## <a name="enrichment-results"></a>Forbedringsresultater

Når du har opdateret forbedring, kan du gennemse de netop forbedrede virksomhedsdata under [Mine forbedringer](enrichment-hub.md). Du kan se tidspunktet for den seneste opdatering og antallet af forbedrede profiler.

Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.

Du kan finde flere oplysninger under [Leadspace-API'er](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Næste trin

Byg oven over dine forbedrede kundedata. Opret [segmenter](segments.md) og [målpunkter](measures.md), og [eksporter endda dataene](export-destinations.md) for at levere personlige oplevelser til dine kunder.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Leadspace, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Leadspace overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
