---
title: Forbedring ved hjælp af tredjepart Experian
description: Generelle oplysninger om Experian-tredjeparts forbedring.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309813"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Forbedre kundeprofiler med demografi fra Experian (forhåndsversion)

Experian er førende på globalt plan inden for rapportering om forbruger- og virksomhedskreditering og marketingtjenester. Med Experian-tjeneste til indsamling af data kan du få en større forståelse af kunderne ved at forbedre dine kundeprofiler med demografiske data som størrelse, indkomst og meget mere.

## <a name="prerequisites"></a>Forudsætninger

Hvis du vil konfigurere Experian, skal følgende forudsætninger være opfyldt:

- Du skal have et aktivt abonnement på Experian. Hvis du vil have et abonnement, skal du [kontakte Experian](https://www.experian.com/marketing-services/contact) direkte. [Få mere at vide om Experian-dataforbedring](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- En Experian-forbindelse er allerede konfigureret af en administrator *eller* du har [administratortilladelser](permissions.md#administrator). Du skal også bruge bruger-id, part-id og modelnummer for den SSH-aktiverede ST-konto (Secure Transport), som Experian har oprettet til dig.

## <a name="supported-countriesregions"></a>Understøttede lande/områder

I øjeblikket understøtter vi kun forbedring af kundeprofiler i USA.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Forbedr mine data** i feltet Experian.

   > [!div class="mx-imgBorder"]
   > ![Experian felt](media/experian-tile.png "Experian tile")
   > 

1. Vælg en [værdi](connections.md) på rullelisten. Kontakt en administrator, hvis der ikke er nogen forbindelse. Hvis du er administrator, kan du oprette forbindelse ved at vælge **Tilføj forbindelse** og vælge på Experian på rullelisten. 

1. Vælg **Opret forbindelse Experian** for at bekræfte valget af forbindelse.

1.  Vælg **Næste**, og vælg det **Kundedatasæt**, du vil forbedre med demografidata fra Experian. Du kan vælge objektet **Kunde** for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Skærmbillede, når du vælger kundedatasættet.":::

1. Vælg **Næste**, og definer, hvilken type felter fra dine ensartede profiler der skal bruges til at søge efter tilsvarende demografidata fra Experian. Mindst ét af felterne **Navn og adresse**, **Telefon** eller **E-mail** er obligatorisk. Du kan opnå en mere nøjagtig overensstemmelse ved at tilføje op til to andre felter. Denne indstilling påvirker de tilknytningsfelter, du har adgang til i næste trin.

    > [!TIP]
    > Flere nøgle-id-attributter sendes til Experian for at give en højere overensstemmelseshastighed.

1. Start felttilknytningen ved at vælge **Næste**.

1. Definér, hvilke felter fra dine ensartede profiler der skal bruges til at søge efter tilsvarende demografidata fra Experian. Obligatoriske felter er markeret.

1. Angiv et navn, der viser forbedringen og et navn på outputobjektet.

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

## <a name="configure-the-connection-for-experian"></a>Konfiguration af forbindelse til Experian 

Du skal være en administrator for at konfigurere forbindelser. Vælg **Tilføj forbindelse**, når du konfigurerer en konfiguration, *eller* gå til **Administration** > **Forbindelser**, og vælg **Konfigurer** på Experian-feltet.

1. Vælg **Introduktion**.

1. Angiv et navn til forbindelsen i feltet **Vis navn**.

1. Angiv gyldigt bruger-id, part-id og modelnummer for din Experian Secure Transport-konto.

1. Gennemse og giv dit samtykke til **Beskyttelse af personlige oplysninger og overholdelse af data** ved at vælge **Jeg accepterer**.

1. Vælg **Kontroller** for at validere konfigurationen.

1. Vælg **Gem**, når verifikationen er fuldført.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian forbindelseskonfigurationsfelt.":::

## <a name="enrichment-results"></a>Forbedringsresultater

Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen. Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab). Behandlingstiden afhænger af størrelsen på dine kundedata og de processer, der er oprettet for din konto af Experian.

Når forbedringsprocessen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**. Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.

Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.

## <a name="next-steps"></a>Næste trin

Byg oven over dine forbedrede kundedata. Opret [segmenter](segments.md) og [målpunkter](measures.md), og [eksporter endda dataene](export-destinations.md) for at levere personlige oplevelser til dine kunder.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du gør det muligt at Dynamics 365 Customer Insights overfører data til Experian, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personlige data. Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at Experian overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
