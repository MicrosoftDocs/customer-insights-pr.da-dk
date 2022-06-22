---
title: Forhøjelse af virksomhedsprofiler med tredjeparts Leadspace
description: Generelle oplysninger om Leadspace-tilsætning af tredjepart.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ca53f15bd7c71b3b4acb396c4daf52d7c7aff9eb
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954172"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Forbedring af virksomhedsprofiler med Leadspace (prøveversion)

Leadspace er et databaseret firma, der leverer en B-til-B-kundedataplatform. Det muliggør miljøer med samlede kundeprofiler baseret på firmaer at få forbedret deres data. Du kan forbedre *Kundeprofiler* med attributter som firmastørrelse, placering eller branche. Du kan forbedre *Kontaktprofiler* med attributter som f.eks. titel, karakter eller mailbekræftelse.

## <a name="prerequisites"></a>Forudsætninger

- En aktiv Leadspace-licens.
- [Samlede kundeprofiler](customer-profiles.md) baseret på firmaer.
- En Leadspace [forbindelse](connections.md) er [konfigureret](#configure-the-connection-for-leadspace) af en administrator. Kontakt [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) direkte for at få oplysninger om produktet.

## <a name="configure-the-connection-for-leadspace"></a>Konfiguration af forbindelsen til Leadspace

Du skal være en [administrator](permissions.md#admin) i Customer Insights og have den "permanente nøgle" (kaldes også **Leadspace-token**).

1. Vælg **Tilføj forbindelse**, når du konfigurerer en konfiguration, eller gå til **Admin** > **Forbindelser** og vælge **Konfigurer** i feltet Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace-forbindelsens konfigurationsside.":::

1. Angiv et navn til forbindelsen og et gyldigt Leadspace-token.

1. Gennemse og giv dit samtykke til [Beskyttelse af personlige oplysninger og overholdelse af data](#data-privacy-and-compliance) ved at vælge **Jeg accepterer**.

1. Vælg **Kontrollér** for at konfigurationen er valideret, og vælg derefter **Gem**.

### <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Leadspace, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Leadspace overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Forbedring af data** i feltet **Firmadata** fra feltet Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skærmbillede af Leadspace-feltet.":::

1. Gennemse oversigten, og vælg derefter **Næste**.

1. Vælg forbindelsen. Kontakt en administrator, hvis en ikke er tilgængelig.

1. Vælg **Næste**.

1. Vælg **Kundedatasæt**, og vælg den profil eller det segment, du vil forbedre med firmadata fra Leadspace. Objektet *Kunde* forbedrer alle dine kundeprofiler, hvorimod et segment kun forbedrer de kundeprofiler, der findes i dette segment.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Skærmbillede, når du vælger kundedatasættet.":::

1. Definer, hvilken type felter fra dine ensartede profiler der skal bruges til matchning: den primære og/eller sekundære adresse. Du kan angive en felttilknytning for begge adresser og forbedre profilerne for begge adresser separat. Det kan f.eks. være en privatadresse og en forretningsadresse. Vælg **Næste**.

1. Knyt felterne til firmadataene fra Leadspace. Feltet **Firmanavn** er obligatorisk. Hvis du vil opnå en større overensstemmelse, kan du tilføje op til to andre felter, **Virksomheds-websteder** og **Virksomhedsplacering**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-felttilknytningsrude.":::

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Markér afkrydsningsfeltet, hvis du har *Kontaktprofiler*, du vil forbedre. Customer Insights tilknytter automatisk de påkrævede felter.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Forbedring af kontaktpersonposter i Leadspace.":::

1. Vælg **Næste**.

1. Angiv et **Navn** til forbedringen og **outputobjektnavn**.

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

1. Vælg **Kør** for at starte forbedringsprocessen, eller luk for at vende tilbage til siden **Forbedringer**.

## <a name="enrichment-results"></a>Forbedringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Du kan finde flere oplysninger under [Leadspace-API'er](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
