---
title: Forbedring af virksomhedsprofiler med Dun & Bradstreet (forhåndsversion)
description: Generelle oplysninger om tredjepartsforbedringer i Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 71b35e4295e19c13edadc6548ac79715555e8183
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196019"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Forbedring af virksomhedsprofiler med Dun & Bradstreet (forhåndsversion)

Dun & Bradstreet leverer kommercielle data, analyser og indsigt til virksomheder. Den gør det muligt for kunder, der har en samlet kundeprofil for virksomheder, at forbedre deres data. Forbedringer omfatter attributter, herunder DUNS-nummer, virksomhedsstørrelse, adresse, branche og mere.

## <a name="prerequisites"></a>Forudsætninger

- En aktiv [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights)-licens.
- [Ensartede kundeprofiler](customer-profiles.md) til virksomheder.
- Der er oprettet et Dun & Madsen-[projekt](#set-up-your-dun--bradstreet-project).
- En Dun & Bradstreet-[forbindelse](connections.md) [konfigureres](#configure-a-connection-for-dun--bradstreet) af en administrator.

## <a name="set-up-your-dun--bradstreet-project"></a>Konfiguration af dit Dun & Bradstreet-projekt

Som licensbruger af Dun & Bradstreet kan du oprette et projekt i [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Forbind til [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Hvis du vil hente legitimationsoplysninger, skal du [gendanne din adgangskode](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Hent [vores csv-skabelonfil](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), der skal bruges til at knytte Customer Insights-felter til de tilsvarende felter i Dun & Bradstreet.

1. Overfør filen i trinnet **Overfør data** i Dun & Bradstreet-projektoprettelsesoplevelsen.

1. Vælg de vandrette prikker under den relevante **kilde** i det nyoprettede Dun & Bradstreet-projekt for at se de tilgængelige indstillinger.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Skærmbillede af prikker i et Dun & Madsen-projekt.":::

1. Vælg **Hent oplysninger om S3**. Gem disse oplysninger på et sikkert sted. Du skal bruge den til at [konfigurere forbindelsen til forbedringen](#configure-a-connection-for-dun--bradstreet) i Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Skærmbillede af valg af s3-oplysninger i et Dun & Bradstreet-projekt.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfiguration af en forbindelse til Dun & Bradstreet

Du skal være [administrator](permissions.md#admin) i Customer Insights og have legitimationsoplysningerne fra Dun & Bradstreet Connect.

1. Vælg **Tilføj forbindelse**, når du konfigurerer en forbedring, eller gå til **Admin** > **Forbindelser** og vælg **Konfigurer** i feltet Dun & Bradstreet.

1. Angiv et navn for forbindelsen.

1. Angiv gyldige legitimationsoplysninger til Dun & Bradstreet og oplysninger om Dun & Bradstreet-projektdetaljerne *Område, Sti til slipmappe og Mappenavn til slip*. Du [får disse oplysninger](#set-up-your-dun--bradstreet-project) fra Dun & Bradstreet-projektet.

1. Gennemse og giv dit samtykke til [Beskyttelse af personlige oplysninger og overholdelse af data](#data-privacy-and-compliance) ved at vælge **Jeg accepterer**.

1. Vælg **Kontrollér** for at konfigurationen er valideret, og vælg derefter **Gem**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Konfiguration af forbindelsesside til Dun & Bradstreet":::

### <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights til at overføre data til Dun & Bradstreet, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personoplysninger. Microsoft kan overføre sådanne data efter dine instruktioner, men du er ansvarlig for at sikre, at Dun & Bradstreet overholder alle forpligtelser i forbindelse med sikkerhed eller beskyttelse af personlige oplysninger. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.

## <a name="supported-countries-or-regions"></a>Understøttede lande eller områder

Vi understøtter i øjeblikket følgende lande/område-indstillinger: Canada (engelsk) eller USA (engelsk).

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Forbedring af data** i feltet **Firmadata** fra feltet Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Skærmbillede af feltet Dun & Bradstreet.":::

1. Gennemse oversigten, og vælg derefter **Næste**.

1. Vælg forbindelsen, og bekræft. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Vælg **Næste**.

1. Vælg **Kundedatasæt**, og vælg den profil eller det segment, du vil forbedre med firmadata fra Dun & Bradstreet. Objektet *Kunde* forbedrer alle dine kundeprofiler, hvorimod et segment kun forbedrer de kundeprofiler, der findes i dette segment.

1. Definer, hvilken type felter fra dine ensartede profiler der skal bruges til at matche firmadata fra Dun & Bradstreet. Mindst ét af felterne **Navn og adresse**, **Telefon** eller **E-mail** er obligatorisk.

1. Vælg **Næste**

1. Knyt firmafelterne til firmadataene fra Dun & Bradstreet. Du skal enten udfylde feltet **DUNS-nummer** eller **Firmanavn** og **Land**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Felttilknytningsruden Dun & Bradstreet.":::

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Angiv et **Navn** til forbedringen og **outputobjektnavn**.

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

1. Vælg **Kør** for at starte forbedringsprocessen, eller luk for at vende tilbage til siden **Forbedringer**.

## <a name="view-enrichment-results"></a>Vise forbedringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
