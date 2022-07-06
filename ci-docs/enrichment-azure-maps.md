---
title: Forbedre kundeprofiler med lokationsdata fra Azure Maps (forhåndsversion)
description: Generelle oplysninger om Azure Maps -førsteparts forbedring.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: dfadc08f67beac3fded1a97e557ee9e1880664e0
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052600"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Forbedre kundeprofiler med lokationsdata fra Azure Maps (forhåndsversion)

Azure Maps leverer lokationsbaserede data og tjenester, der giver oplevelser baseret på geografiske data med indbygget lokationsintelligens. Azure Maps-tjenester til indsamling til dataforbedring øger præcisionen af lokationsoplysninger om kunderne. Den medfører funktioner som adresse normalisering og udtrækning af breddegrader og længdegrader til Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Forudsætninger

- Et aktivt abonnement på Azure Maps. Få et abonnement ved at [tilmelde sig eller få en gratis prøveversion](https://azure.microsoft.com/services/azure-maps/).

- En Azure Maps-[forbindelse](connections.md) [konfigureres](#configure-the-connection-for-azure-maps) af en administrator.

## <a name="configure-the-connection-for-azure-maps"></a>Konfiguration af forbindelsen til Azure Maps

Du skal være en [administrator](permissions.md#admin) i Customer Insights og have en aktiv Azure Maps API-nøgle.

1. Vælg **Tilføj forbindelse**, når du konfigurerer en forbedring, eller gå til **Administration** > **Forbindelser**, og vælg **Konfigurer** i feltet Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps-forbindelseskonfigurationsside.":::

1. Angiv et navn til forbindelsen og en gyldig Azure Maps API-nøgle.

1. Gennemse og giv dit samtykke til [Beskyttelse af personlige oplysninger og overholdelse af data](#data-privacy-and-compliance) ved at vælge **Jeg accepterer**.

1. Vælg **Kontrollér** for at konfigurationen er valideret, og vælg derefter **Gem**.

### <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du gør det muligt for Dynamics 365 Customer Insights at overfører data til Azure Maps, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personlige data. Microsoft kan overføre sådanne data efter dine instruktioner, men du er ansvarlig for at sikre, at Azure Maps overholder alle forpligtelser i forbindelse med sikkerhed eller beskyttelse af personlige oplysninger. Du kan finde flere oplysninger i [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Enrich my data** i feltet **Lokation** fra feltet Microsoft Azure Maps.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps-felt.":::

1. Gennemse oversigten, og vælg derefter **Næste**.

1. Vælg forbindelsen. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Vælg **Næste**.

1. Vælg **Kundedatasæt**, og vælg den profil eller det segment, du vil forbedre med firmadata fra Microsoft. Objektet *Kunde* forbedrer alle dine kundeprofiler, hvorimod et segment kun forbedrer de kundeprofiler, der findes i dette segment.

1. Definer, hvilken type felter fra dine ensartede profiler der skal bruges til matchning: den primære og/eller sekundære adresse. Du kan angive en felttilknytning for begge adresser og forbedre profilerne for begge adresser separat. Det kan f.eks. være en privatadresse og en forretningsadresse. Vælg **Næste**.

1. Knyt felterne til lokationsdataene fra Azure Maps. Felterne **Gade 1** og **postnummer** er obligatoriske for den valgte primære og/eller sekundære adresse. Tilføj flere felter for at opnå en mere nøjagtig overensstemmelse.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Attributtilknytning i Azure Maps.":::

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Gennemse **Avancerede indstillinger,** der giver maksimal fleksibilitet til håndtering af avancerede brugsmønstre. Følgende standardværdier behøver dog som regel ikke at blive ændret.

   - **Adressetyper**: Bedste adresse svarer til returneringer, selvom den ikke er komplet. Hvis du kun vil have fuldstændige adresser, f.eks. adresser, der indeholder husnummeret, skal alle afkrydsningsfelterne undtagen **Punktadresser** ryddes.
   - **Sprog**: Adresser returneres til det sprog, der er baseret på adresseområdet. Hvis du vil anvende et standardiseret adressesprog, skal du vælge sproget i rullemenuen. Hvis du f.eks. vælger **engelsk**, returneres **Copenhagen, Denmark** i stedet for **København, Danmark**.
   - **Maksimalt antal resultater**: Antal resultater pr. adresse.

1. Vælg **Næste**.

1. Angiv et **Navn** til forbedringen og **outputobjektnavn**.

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

1. Vælg **Kør** for at starte forbedringsprocessen, eller luk for at vende tilbage til siden **Forbedringer**.

## <a name="view-enrichment-results"></a>Vise forbedringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antal kunder, der er forbedret med felt** angiver en detailudledning i dækningen af hvert enkelt forbedret felt.

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
