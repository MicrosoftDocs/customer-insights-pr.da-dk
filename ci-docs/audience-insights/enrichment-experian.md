---
title: Tilsætning af tredjeparts forbedringer fra Experian
description: Generelle oplysninger om Experian-forbedring fra tredjepart.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668800"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Forbedre kundeprofiler med demografi fra Experian (forbedre)

Experian er en global leder i forbruger- og virksomhedskreditrapportering og marketingservice. Med Experians dataforbedringstjenester kan du få en dybere forståelse af dine kunder ved at udvide dine kundeprofiler med demografiske data, f.eks. husstandens størrelse og indkomst og meget mere.

## <a name="prerequisites"></a>Forudsætninger

Hvis du vil konfigurere Experian, skal følgende forudsætninger være opfyldt:

- Du har et aktivt Experian-abonnement. Hvis du vil have et abonnement, skal du [kontakte Experian](https://www.experian.com/marketing-services/contact) direkte. [Få mere at vide om Experian-dataforbedring](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Du har et bruger-id, part-id og modelnummer til din SSH-konto (Secure Transport), som Experian har oprettet for dig.
- Du har [Administrator](permissions.md#administrator)-tilladelser i målgruppeindsigt.

## <a name="configuration"></a>Konfiguration

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Forbedr mine data** på Experian-feltet.

   > [!div class="mx-imgBorder"]
   > ![Experian-felt](media/experian-tile.png "Experian-felt")

1. Vælg **Start her**, og angiv bruger-id, part-id og modelnummer for din Experian-konto til Secure Transport. Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**. Bekræft alle input ved at vælge **Anvend**.

## <a name="map-your-fields"></a>Tilknyt dine felter

1. Vælg **Tilføj data**, og vælg dine nøgle-id'er fra **Navn og adresse**, **Mail** eller **Telefon**, der skal sendes til Experian for identitetsfortolkning.

   > [!TIP]
   > Flere nøgle-id-attributter, der sendes til Experian, giver sandsynligvis større sammenfald.

1. Vælg **Næste**, og knyt de tilsvarende attributter fra det samlede kundeobjekt for de valgte nøgle-id-felter.

1. Vælg **Tilføj attribut** for at tilknytte eventuelle yderligere attributter, du vil sende til Experian.

1.  Vælg **Gem** for at fuldføre felttilknytningen.

   > [!div class="mx-imgBorder"]
   > ![Experian-felttilknytning](media/experian-field-mapping.png "Experian-felttilknytning")

## <a name="enrichment-results"></a>Forbedringsresultater

Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen. Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab). Behandlingstiden afhænger af størrelsen på dine kundedata og de forbedringer, der er konfigureret for din konto af Experian.

Når forbedringsprocessen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**. Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.

Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.

## <a name="next-steps"></a>Næste trin

Byg oven over dine forbedrede kundedata. Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Experian, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Experian overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.
