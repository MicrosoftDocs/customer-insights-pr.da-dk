---
title: Forbedre kundeprofiler med demografi fra Experian (forhåndsversion)
description: Generelle oplysninger om Experian-tredjeparts forbedring.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237989"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Forbedre kundeprofiler med demografi fra Experian (forhåndsversion)

Experian er førende på globalt plan inden for rapportering om forbruger- og virksomhedskreditering og marketingtjenester. Med Experian-tjeneste til indsamling af data kan du få en større forståelse af kunderne ved at forbedre dine kundeprofiler med demografiske data som størrelse, indkomst og meget mere.

## <a name="supported-countriesregions"></a>Understøttede lande/områder

I øjeblikket understøtter vi kun forbedring af kundeprofiler i USA.

## <a name="prerequisites"></a>Forudsætninger

- Et aktivt Experian-abonnement. Hvis du vil have et abonnement, skal du [kontakte Experian](https://www.experian.com/marketing-services/contact) direkte. [Få mere at vide om Experian-dataforbedring](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- En Experian-[forbindelse](connections.md) [konfigureres](#configure-the-connection-for-experian) af en administrator.

- Experian Bruger-id, Gruppe-id og modelnummer for den SSH-aktiverede ST-konto (Secure Transport), som Experian har oprettet for dig.

## <a name="configure-the-connection-for-experian"></a>Konfiguration af forbindelse til Experian

Du skal være en [administrator](permissions.md#admin) i Customer Insights og have et Experian Bruger-id, Gruppe-id og modelnummer.

1. Vælg **Tilføj forbindelse**, når du konfigurerer en forbedring, eller gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i feltet Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian forbindelseskonfigurationsfelt.":::

1. Angiv et navn til forbindelsen og et gyldigt bruger-id, part-id og modelnummer for din Experian Secure Transport-konto.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Kontrollér** for at konfigurationen er valideret, og vælg derefter **Gem**.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Forbedring af data** i **Demografi** i feltet Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian-felt i oversigtssiden for forbedring. ":::

1. Gennemse oversigten, og vælg derefter **Næste**.

1. Vælg forbindelsen. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Vælg **Næste**.

1. Vælg **Kundedatasæt**, og vælg den profil eller det segment, du vil forbedre med demografidata fra Experian. Objektet *Kunde* forbedrer alle dine kundeprofiler, hvorimod et segment kun forbedrer de kundeprofiler, der findes i dette segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Skærmbillede, når du vælger kundedatasættet.":::

1. Definer, hvilken type felter fra dine ensartede profiler der skal bruges til at matche demografidata fra Experian. Mindst ét af felterne **Navn og adresse**, **Telefon** eller **E-mail** er obligatorisk. Tilføj andre felter for at opnå en mere nøjagtig overensstemmelse. Vælg **Næste**.

1. Knyt felterne til demografidataene fra Experian.

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
