---
title: Tilsætning af tredjeparts forbedringer fra Experian
description: Generelle oplysninger om Experian-forbedring fra tredjepart.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896366"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Forbedre kundeprofiler med demografi fra Experian (forbedre)

Experian er en global leder i forbruger- og virksomhedskreditrapportering og marketingservice. Med Experians dataforbedringstjenester kan du få en dybere forståelse af dine kunder ved at udvide dine kundeprofiler med demografiske data, f.eks. husstandens størrelse og indkomst og meget mere.

## <a name="prerequisites"></a>Forudsætninger

Hvis du vil konfigurere Experian, skal følgende forudsætninger være opfyldt:

- Du har et aktivt Experian-abonnement. Hvis du vil have et abonnement, skal du [kontakte Experian](https://www.experian.com/marketing-services/contact) direkte. [Få mere at vide om Experian-dataforbedring](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- En Experian-forbindelse er allerede konfigureret af en administrator *eller* du har [administratortilladelser](permissions.md#administrator). Du skal også bruge bruger-id, part-id og modelnummer for den SSH-aktiverede ST-konto (Secure Transport), som Experian har oprettet for dig.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Forbedr mine data** på Experian-feltet.

   > [!div class="mx-imgBorder"]
   > ![Experian-felt](media/experian-tile.png "Experian-felt")
   > 

1. Vælg en [forbindelse](connections.md) på rullelisten. Kontakt en administrator, hvis der ikke er nogen forbindelse. Hvis du er administrator, kan du oprette en forbindelse ved at vælge **Tilføj forbindelse** og vælge Experian på rullelisten. 

1. Vælg **Opret forbindelse til Experian** for at bekræfte den valgte forbindelse.

1.  Vælg **Næste**, og angiv de **Kundedatasæt**, du vil forbedre med demografidata fra Experian. Du kan vælge objektet **Kunde** for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Skærmbillede, når du vælger kundedatasættet.":::

1. Vælg **Næste**, og definer, hvilke felter fra dine samlede profiler der bruges til at søge efter tilsvarende demografidata fra Experian. Mindst ét af felterne **Navn og adresse**, **Telefon** eller **E-mail** er obligatorisk. Du kan opnå en mere nøjagtig overensstemmelse ved at tilføje op til to andre felter. Denne indstilling påvirker de tilknytningsfelter, du har adgang til i næste trin.

    > [!TIP]
    > Flere nøgle-id-attributter, der sendes til Experian, giver sandsynligvis større sammenfald.

1. Start felttilknytningen ved at vælge **Næste**.

1. Definer, hvilke felter fra dine samlede profiler der bruges til at søge efter tilsvarende demografidata fra Experian. Obligatoriske felter er markeret.

1. Angiv et navn, der viser forbedringen og et navn på outputobjektet.

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

## <a name="configure-the-connection-for-experian"></a>Konfiguration af forbindelsen til Experian 

Du skal være en administrator for at konfigurere forbindelser. Vælg **Tilføj forbindelse**, når du konfigurerer en konfiguration, *eller* gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i feltet Experian.

1. Vælg **Introduktion**.

1. Angiv et navn til forbindelsen i feltet **Vis navn**.

1. Angiv gyldigt bruger-id, part-id og modelnummer for din Experian Secure Transport-konto.

1. Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**

1. Vælg **Kontroller** for at validere konfigurationen.

1. Vælg **Gem**, når verifikationen er fuldført.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Side til konfiguration af Experian-forbindelse.":::

## <a name="enrichment-results"></a>Forbedringsresultater

Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen. Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab). Behandlingstiden afhænger af størrelsen på dine kundedata og de forbedringer, der er konfigureret for din konto af Experian.

Når forbedringsprocessen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**. Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.

Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.

## <a name="next-steps"></a>Næste trin

Byg oven over dine forbedrede kundedata. Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Experian, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Experian overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
