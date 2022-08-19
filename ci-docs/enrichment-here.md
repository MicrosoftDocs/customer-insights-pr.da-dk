---
title: Forbedre kundeprofiler med HERE Technologies (forhåndsversion)
description: Generelle oplysninger om HERE Technologies-forbedringer.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237851"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Forbedre kundeprofiler med HERE Technologies (forhåndsversion)

HERE Technologies er en lokationsplatformsvirksomhed, der leverer geografiske data og tjenester, der er centreret. HERE Technologies' tjenester til indsamling af data forbedrer præcisionen af lokationsoplysninger om kunderne. Det giver adresse normalisering, breddegrad og længdegrad og meget mere.

## <a name="prerequisites"></a>Forudsætninger

- Et aktivt HERE Technologies-abonnement. Du kan få et abonnement ved [at tilmelde dig her](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkte. [Få mere at vide om HERE Technologies Forbedring af placeringsdata.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- En HERE- [forbindelse](connections.md) [konfigureres](#configure-the-connection-for-here-technologies) af en administrator.

## <a name="configure-the-connection-for-here-technologies"></a>Konfiguration af forbindelsen til HERE Technologies

Du skal være en [administrator](permissions.md#admin) i Customer Insights og have en aktiv HERE Technologies API-nøgle.

1. Vælg **Tilføj forbindelse**, når du konfigurerer en forbedring, eller gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i feltet HERE Technologies.

1. Angiv et navn til forbindelsen og en gyldig HERE Technologies API-nøgle.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Kontrollér** for at konfigurationen er valideret, og vælg derefter **Gem**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="HERE Technologies-forbindelsens konfigurationsside.":::

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Forbedring af data** i feltet **Lokation** fra feltet HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies-felt.":::

1. Gennemse oversigten, og vælg derefter **Næste**.

1. Vælg forbindelsen. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Vælg **Næste**.

1. Vælg **Kundedatasæt**, og vælg den profil eller det segment, du vil forbedre med firmadata fra HERE Technologies. Objektet *Kunde* forbedrer alle dine kundeprofiler, hvorimod et segment kun forbedrer de kundeprofiler, der findes i dette segment.

1. Definer, hvilken type felter fra dine ensartede profiler der skal bruges til matchning: den primære og/eller sekundære adresse. Du kan angive en felttilknytning for begge adresser og forbedre profilerne for begge adresser separat. Det kan f.eks. være en privatadresse og en forretningsadresse. Vælg **Næste**.

1. Knyt felterne til demografidataene fra HERE Technologies. Felterne **Gade 1** og **postnummer** er obligatoriske for den valgte primære og/eller sekundære adresse. Tilføj flere felter for at opnå en mere nøjagtig overensstemmelse.

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Angiv et **Navn** til forbedringen og **outputobjektnavn**.

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

1. Vælg **Kør** for at starte forbedringsprocessen, eller luk for at vende tilbage til siden **Forbedringer**.

## <a name="view-enrichment-results"></a>Vise forbedringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antal kunder, der er forbedret med felt** angiver en detailudledning i dækningen af hvert enkelt forbedret felt.

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
