---
title: Forbedring af virksomhedsprofiler med Dun & Bradstreet
description: Generelle oplysninger om tredjepartsforbedringer i Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755393"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Forbedring af virksomhedsprofiler med Dun & Bradstreet (Forhåndsversion)

Dun & Bradstreet leverer kommercielle data, analyser og indsigt til virksomheder. Den gør det muligt for kunder, der har en samlet kundeprofil for virksomheder, at forbedre deres data. Forbedringer omfatter attributter, herunder DUNS-nummer, virksomhedsstørrelse, adresse, branche og mere.

## <a name="prerequisites"></a>Forudsætninger

Hvis du vil konfigurere en Dun & Bradstreet-forbedring, skal følgende forudsætninger være opfyldt:

- Du har en aktiv [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights)-licens.
- Du har [samlede kundeprofiler](customer-profiles.md) til virksomheder.
- En Dun & Bradstreet [forbindelse](connections.md) konfigureres af en administrator. Du kan oprette den, hvis du har [administrator](permissions.md#admin)-tilladelser og legitimationsoplysningerne fra Dun & Bradstreet Connect.

## <a name="setting-up-your-dun--bradstreet-project"></a>Konfiguration af dit Dun & Bradstreet-projekt

Som licensbruger af Dun & Bradstreet kan du oprette et projekt i [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).


1. Forbind til [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Hvis du vil hente legitimationsoplysninger, skal du [gendanne din adgangskode](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Hent [vores csv-skabelonfil](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), der skal bruges til at knytte Customer Insights-felter til de tilsvarende felter i Dun & Bradstreet.

1. Overfør filen i trinnet **Overfør data** i Dun & Bradstreet-projektoprettelsesoplevelsen.

1. Vælg de vandrette prikker under den relevante **kilde** i det nyoprettede Dun & Bradstreet-projekt for at se de tilgængelige indstillinger.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Skærmbillede af prikker i et Dun & Madsen-projekt.":::

1. Vælg **Hent oplysninger om S3**. Gem disse oplysninger på et sikkert sted. Du skal bruge den til at [konfigurere forbindelsen til forbedringen](#configure-a-connection-for-dun--bradstreet) i Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Skærmbillede af valg af s3-oplysninger i et Dun & Bradstreet-projekt.":::

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**.

1. Vælg **Forbedre mine data** i feltet Dun & Bradstreet, og vælg **Introduktion**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Skærmbillede af feltet Dun & Bradstreet.":::

1. Vælg en [værdi](connections.md) på rullelisten. Kontakt en administrator, hvis der ikke er nogen forbindelse. Hvis du er en administrator, kan du oprette forbindelse. Vælg **Tilføj forbindelse**, og vælg **Dun & Bradstreet**.

1. Vælg **Opret forbindelse til Dun & Bradstreet** for at bekræfte forbindelsen.

1. Vælg **Næste**, og vælg det **Kundedatasæt**, du vil forbedre med virksomhedsdata fra Dun & Bradstreet. Du kan vælge objektet **Kunde** for at forbedre alle dine kundeprofiler eller vælge et segment-objekt for kun at forbedre de samlede kundeprofiler, der findes i dette segment.

1. Vælg **Næste**, og definer, hvilken type felter fra dine ensartede profiler der skal bruges til at søge efter tilsvarende virksomhedsdata fra Dun & Bradstreet. Du skal enten udfylde feltet **DUNS-nummer** eller **Firmanavn** og **Land**. Landefeltet understøtter [landekoder på to eller tre bogstaver](https://www.iso.org/iso-3166-country-codes.html), landenavn på engelsk, landenavn på modersmål og telefonpræfiks. Nogle almindelige landevarianter omfatter:

- USA: USA, USA, USA og USA.
- CA: Canada.
- GB: Storbritannien, UK, Det Forenede Kongerige, GB, Det Forenede Kongerige Storbritannien og Nordirland, Det Forenede Kongerige Storbritannien.
- AU: Australien, Australien.
- Fransk: Frankrig, Frankrig
- DE: Tyskland, Tysk, Deutschland, Tyskland, Tyskland, Tyskland.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Felttilknytningsruden Dun & Bradstreet.":::

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Angiv et navn til den forbedring, du udvælger, og angiv **Vælg forbedring**, når du har gennemset dine valg.

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfiguration af en forbindelse til Dun & Bradstreet

Du skal være en administrator for at konfigurere forbindelser. Vælg **Tilføj forbindelse**, når du konfigurerer en forbedring, *eller* gå til **Administration** > **Forbindelser**, og vælg **Konfigurer** i feltet Dun & Bradstreet.

1. Vælg **Start her**.

1. Angiv et navn til forbindelsen i feltet **Vis navn**.

1. Angiv gyldige legitimationsoplysninger til Dun & Bradstreet og oplysninger om Dun & Bradstreet-projektdetaljerne *Område, Sti til slipmappe og Mappenavn til slip*. Du [får disse oplysninger](#setting-up-your-dun--bradstreet-project) fra Dun & Bradstreet-projektet.

1. Gennemse og giv dit samtykke til **Beskyttelse af personlige oplysninger og overholdelse af data** ved at vælge **Jeg accepterer**.

1. Vælg **Kontroller** for at validere konfigurationen.

1. Vælg **Gem**, når verifikationen er fuldført.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Konfiguration af forbindelsesside til Dun & Bradstreet":::

## <a name="enrichment-results"></a>Forbedringsresultater

Når du har opdateret forbedring, kan du gennemse de netop forbedrede virksomhedsdata under [Mine forbedringer](enrichment-hub.md). Du kan se tidspunktet for den seneste opdatering og antallet af forbedrede profiler.

Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights til at overføre data til Dun & Bradstreet, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personoplysninger. Microsoft kan overføre sådanne data efter dine instruktioner, men du er ansvarlig for at sikre, at Dun & Bradstreet overholder alle forpligtelser i forbindelse med sikkerhed eller beskyttelse af personlige oplysninger. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.

[!INCLUDE[footer-include](includes/footer-banner.md)]
