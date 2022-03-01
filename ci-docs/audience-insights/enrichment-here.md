---
title: Tilsætning af tredjeparts forbedringer fra HERE Technologies
description: Generelle oplysninger om HERE Technologies-forbedringer.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668671"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Tilsætning af kundeprofiler ved hjælp af HERE Technologies (prøveversion)

HERE Technologies er en lokationsplatformsvirksomhed, der leverer geografiske data og tjenester, der er centreret. Med dataforbedringstjenester i HERE Technologies kan du oprette en mere præcis placering for dine kunder med normalisering af adresser, bredde- og længdegrader og meget mere.

## <a name="prerequisites"></a>Forudsætninger

Følgende forudsætninger skal være opfyldt, hvis du vil konfigurere HERE Technologies-forbedringer:

- Du skal have et aktivt HERE Technologies-abonnement. Hvis du vil have et abonnement, kan du [tilmelde dig her](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkte. [Få mere at vide om HERE Technologies Forbedring af placeringsdata.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Du har API-nøglen til HERE Technologies.

- Du har [Administrator](permissions.md#administrator)-tilladelser.

## <a name="configuration"></a>Konfiguration

1. Gå til **Data** > **Forbedring**.

1. Vælg **Forbedring af dine data** på feltet HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies-felt](media/HERE-tile.png "HERE Technologies-felt")

1. Angiv en aktiv **HERE Technologies-API-nøgle**. Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**. 

1. Bekræft begge input ved at vælge **Opret forbindelse til HERE**.

1. Vælg **Tilføj data**, og vælg, hvis du vil knytte felter til den primære og/eller sekundære adresse. Du kan angive en felttilknytning for begge adresser (f. eks. privat-og firmaadresse) og forbedre profilerne for begge adresser separat. Vælg **Næste**.

1. Definér, hvilke felter fra dine samlede profiler der skal bruges til at søge efter de tilsvarende placeringsdata fra HERE Technologies. Felterne **Gade 1** og **postnummer** er obligatoriske for den valgte primære og/eller sekundære adresse. Hvis du vil opnå en større overensstemmelse, kan du tilføje flere felter.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies forbedret konfigurationsside](media/enrichment-HERE-configuration.png "HERE Technologies forbedret konfigurationsside")

1. Vælg **Anvend** for at fuldføre felttilknytningen.

## <a name="enrichment-results"></a>Forbedringsresultater

Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen. Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab). Behandlingstiden afhænger af størrelsen på dine kundedata og de API-svartider, der er knyttet til HERE Technologies.

Når forbedringsprocessen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**. Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.

Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.

## <a name="next-steps"></a>Næste trin

Byg oven over dine forbedrede kundedata. Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til HERE Technologies, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data under din instruktion, men du er ansvarlig for at sikre, at HERE Technologies overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.
