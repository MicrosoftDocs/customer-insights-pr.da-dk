---
title: Forbedring ved hjælp af tredjepartsforbedringer HERE Technologies
description: Generelle oplysninger om HERE Technologies-forbedringer.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c131ffb230a62b76e123334ff3c6776c8f9aa06e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646146"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Tilsætning af kundeprofiler ved hjælp af HERE Technologies (prøveversion)

HERE Technologies er en lokationsplatformsvirksomhed, der leverer geografiske data og tjenester, der er centreret. Med dataforbedringstjenester i HERE Technologies kan du oprette en mere præcis placering for dine kunder med normalisering af adresser, bredde- og længdegrader og meget mere.

## <a name="prerequisites"></a>Forudsætninger

Følgende forudsætninger skal være opfyldt, hvis du vil konfigurere HERE Technologies-forbedringer:

- Du skal have et aktivt HERE Technologies-abonnement. Hvis du vil have et abonnement, kan du [tilmelde dig her](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkte. [Få mere at vide om HERE Technologies Forbedring af placeringsdata.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- En HERE [forbindelse](connections.md) er tilgængelig, *eller* du har [administratortilladelser](permissions.md#admin) og HERE Technologies API-nøgle.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**. 

1. Vælg **Forbedr mine data** i feltet HERE Technologies, og vælg **Start her**.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies-felt.](media/HERE-tile.png "HERE Technologies-felt")

1. Vælg en [værdi](connections.md) på rullelisten. Kontakt en administrator, hvis der ikke er nogen forbindelse. Hvis du er administrator, kan du oprette en forbindelse ved at vælge **Tilføj forbindelse**. Vælg **HERE Technologies** på rullelisten. 

1. Vælg **Opret forbindelse til HERE Technologies** for at bekræfte valget.

1.  Vælg **Næste**, og angiv de **Kundedatasæt**, du vil forbedre med lokationsdata fra HERE Technologies. Du kan vælge objektet **Kunde** for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Skærmbillede, når du vælger kundedatasættet.":::

1. Vælg, om du vil knytte felter til den primære og/eller sekundære adresse. Du kan angive en felttilknytning for begge adresser og forbedre profilerne for begge adresser separat. Hvis der f.eks. er en privatadresse og en forretningsadresse. Vælg **Næste**.

1. Definér, hvilke felter fra dine samlede profiler der skal bruges til at søge efter de tilsvarende placeringsdata fra HERE Technologies. Felterne **Gade 1** og **postnummer** er obligatoriske for den valgte primære og/eller sekundære adresse. Hvis du vil opnå en større overensstemmelse, kan du tilføje flere felter.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies forbedret konfigurationsside.](media/enrichment-HERE-configuration.png "HERE Technologies forbedret konfigurationsside")

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Angiv et Navn til forbedringen. 

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

## <a name="configure-the-connection-for-here-technologies"></a>Konfiguration af forbindelsen til HERE Technologies 

Du skal være en administrator for at konfigurere forbindelser. Vælg **Tilføj forbindelse**, når du konfigurerer en konfiguration, *eller* gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i feltet HERE Technologies.

1. Angiv et navn til forbindelsen i feltet **Vis navn**.

1. Angiv en gyldig API-nøgle til HERE Technologies.

1. Gennemse og giv dit samtykke til **Beskyttelse af personlige oplysninger og overholdelse af data** ved at vælge **Jeg accepterer**.

1. Vælg **Kontroller** for at validere konfigurationen.

1. Vælg **Gem**, når verifikationen er fuldført.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologies-forbindelsens konfigurationsside.](media/enrichment-HERE-connection.png "HERE Technologies-forbindelsens konfigurationsside")

## <a name="enrichment-results"></a>Forbedringsresultater

Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen. Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab). Behandlingstiden afhænger af størrelsen på dine kundedata og de API-svartider, der er knyttet til HERE Technologies.

Når forbedringsprocessen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**. Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.

Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til HERE Technologies, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data under din instruktion, men du er ansvarlig for at sikre, at HERE Technologies overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.


[!INCLUDE [footer-include](includes/footer-banner.md)]
