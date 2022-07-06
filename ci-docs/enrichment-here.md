---
title: Forbedre kundeprofiler med HERE Technologies (forhåndsversion)
description: Generelle oplysninger om HERE Technologies-forbedringer.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052044"
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

1. Gennemse og giv dit samtykke til [Beskyttelse af personlige oplysninger og overholdelse af data](#data-privacy-and-compliance) ved at vælge **Jeg accepterer**.

1. Vælg **Kontrollér** for at konfigurationen er valideret, og vælg derefter **Gem**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="HERE Technologies-forbindelsens konfigurationsside.":::

### <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til HERE Technologies, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data under din instruktion, men du er ansvarlig for at sikre, at HERE Technologies overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Forbedring af data** i feltet **Lokation** fra feltet HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="HERE Technologies-felt.":::

1. Gennemse oversigten, og vælg derefter **Næste**.

1. Vælg forbindelsen. Kontakt en administrator, hvis en ikke er tilgængelig.

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
