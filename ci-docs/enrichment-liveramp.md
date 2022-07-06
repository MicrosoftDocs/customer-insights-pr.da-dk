---
title: Forbedre kundeprofiler med identitetsdata fra LiveRamp (forhåndsversion)
description: Forbedre kundeprofiler med LiveRamp-data.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 334440493c50448005ec90d0cfac11358d677b73
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080997"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Forbedre kundeprofiler med identitetsdata fra LiveRamp (forhåndsversion)

LiveRamp leverer deterministisk identitetsløsning til offline og en sammenlægning af kundedata. Du kan knytte personlige id'er i kundedataene til AbiliTec-identitetsgrafen og modtage AbiliTec-id'er. Du kan derefter bruge disse id'er til at opnå en bedre samling af kundedata.

## <a name="supported-countriesregions"></a>Understøttede lande/områder

I øjeblikket understøtter vi kun forbedring af kundeprofiler med LiveRamp-data i USA.

## <a name="prerequisites"></a>Forudsætninger

- Et aktivt LiveRamp-abonnement. Hvis du vil have et abonnement, skal du kontakte dit LiveRamp-firmateam eller [dynamics@liveramp.com](mailto:dynamics@liveramp.com) for at få flere oplysninger.

- Et aktivt AbiliTec-abonnement med et klient-id og en hemmelighed til at få adgang til API'en. Du kan finde flere oplysninger i [AbiliTec API Udvikler-hub](https://developers.liveramp.com/abilitec-api/).

- En LiveRamp [forbindelse](connections.md) er [konfigureret](#configure-the-connection-for-liveramp) af en administrator.

## <a name="configure-the-connection-for-liveramp"></a>Konfiguration af forbindelsen til LiveRamp

Du skal være en [administrator](permissions.md#admin) i Customer Insights og have et aktivt LiveRamp-klient-id og en hemmelighed.

1. Vælg **Tilføj forbindelse**, når du konfigurerer en forbedring, eller gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i feltet LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfigurationsruden til at konfigurere forbindelsen til tjenesten LiveRamp AbiliTec. ":::

1. Angiv et navn til forbindelsen og et gyldigt LiveRamp-klient-id samt en hemmelighed.

1. Gennemse og giv dit samtykke til [Beskyttelse af personlige oplysninger og overholdelse af data](#data-privacy-and-compliance) ved at vælge **Jeg accepterer**.

1. Vælg **Kontrollér** for at konfigurationen er valideret, og vælg derefter **Gem**.

### <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til LiveRamp, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at LiveRamp overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have. Du kan finde yderligere oplysninger ved at gennemse [Erklæring om beskyttelse af personlige oplysninger i Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Forbedring af data** i feltet **Identitet** fra feltet LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identitetsfelt i oversigtssiden for forbedring. ":::

1. Gennemse oversigten, og vælg derefter **Næste**.

1. Vælg forbindelsen. Kontakt en administrator, hvis en ikke er tilgængelig.

1. Vælg **Næste**.

1. Vælg **Kundedatasæt**, og vælg den profil eller det segment, du vil forbedre med identitetsdata fra LiveRamp. Objektet *Kunde* forbedrer alle dine kundeprofiler, hvorimod et segment kun forbedrer de kundeprofiler, der findes i dette segment.

1. Definer, hvilken type felter fra dine ensartede profiler der skal bruges til at matche identitetsdata fra LiveRamp. Mindst ét af felterne **Navn og adresse**, **Telefon** eller **E-mail** er obligatorisk. Tilføj andre felter for at opnå en mere nøjagtig overensstemmelse. Vælg **Næste**.

1. Knyt felterne til identifikationsdataene fra LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Indstillinger for datatilknytning for LiveRamp-forbedring.":::

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Angiv et **Navn** til forbedringen og **outputobjektnavn**.

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

1. Vælg **Kør** for at starte forbedringsprocessen, eller luk for at vende tilbage til siden **Forbedringer**.

## <a name="view-enrichment-results"></a>Vise forbedringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antal kunder, der er forbedret med felt** angiver en detailudledning i dækningen af hvert enkelt forbedret felt.

## <a name="next-steps"></a>Næste trin

Byg oven over dine forbedrede kundedata. Brug AbiliTec-id'er til at samle kundeprofiler i en personbaseret visning.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
