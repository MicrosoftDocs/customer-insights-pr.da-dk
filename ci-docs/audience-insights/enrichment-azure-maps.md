---
title: Forbedre kundeprofiler med lokationsdata fra Azure Maps
description: Generelle oplysninger om Azure Maps -førsteparts forbedring.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 63f241c27ec86f357c83a301d6797f9ff87c2241
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466755"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Forskellige kundeprofiler med Azure Maps (forhåndsversion)

Azure Maps indeholder lokationsbaserede data og tjenester, der skal levere oplevelser baseret på geografiske data med indbygget lokationsintelligens. Azure Maps-tjenester til indsamling til dataforbedring øger præcisionen af lokationsoplysninger om kunderne. Den medfører funktioner som adresse normalisering og udtrækning af breddegrader og længdegrader til Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Forudsætninger

Hvis du vil konfigurere Azure Maps-dataforbedringer, skal følgende forudsætninger være opfyldt:

- Du skal have et aktivt Azure Maps-abonnement. Du kan få et abonnement ved at [tilmelde dig eller få en gratis prøveversion](https://azure.microsoft.com/services/azure-maps/).

- En Azure Maps-[forbindelse](connections.md) er tilgængelig, *eller* du har [administrator](permissions.md#administrator)-tilladelser og en aktiv Azure Maps API-nøgle.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**. 

1. Vælg **Forbedre mine data** i feltet **Placering**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Maps-felt.":::

1. Vælg en [værdi](connections.md) på rullelisten. Kontakt en administrator, hvis der ikke er nogen tilgængelig Azure Maps-forbindelse. Hvis du er en administrator, kan du [konfigurere forbindelsen til Azure Maps](#configure-the-connection-for-azure-maps). 

1. Vælg **Næste** for at bekræfte markeringen.

1. Vælg den **Kundedatasæt**, du vil forbedre med lokationsdata fra Azure Maps. Du kan vælge objektet **Kunde** for at forbedre alle dine ensartede kundeprofiler, eller du kan vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Skærmbillede, når du vælger den kundedatasæt.":::

1. Vælg, om du vil knytte felter til den primære og/eller sekundære adresse. Du kan angive en felttilknytning for begge adresser og forbedre profilerne for begge adresser separat&mdash;f.eks.for en privatadresse og en forretningsadresse. Vælg **Næste**.

1. Definér, hvilke felter fra dine ensartede profiler der skal bruges til at søge efter tilsvarende lokationsdata fra Azure Maps. Felterne **Gade 1** og **Postnummer** kræves for den valgte primære eller sekundære adresse. Du kan opnå en mere nøjagtig overensstemmelse ved at tilføje flere felter.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Azure Maps-forbedret konfigurationsside.":::

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Evaluere, om du vil redigere **Avancerede indstillinger**. Disse funktioner giver maksimal fleksibilitet til håndtering af avancerede brugssager, men standardværdierne vil være passende i de fleste tilfælde:
   - **Adressetype**: Standardfunktionsmåden er, at adressen returnerer det bedste adresseoverensstemmelse, selvom den ikke er komplet. Hvis du kun vil have fuldstændige adresser, f.eks. adresser, der indeholder husnummeret, skal alle afkrydsningsfelterne undtagen **Punktadresser** ryddes. 
   - **Sprog**: Adresser returneres som standard på det sprog, som adressen er bestemt til at tilhøre. Hvis du vil anvende et standardiseret adressesprog, skal du vælge sproget i rullemenuen. Hvis du f.eks. vælger **engelsk**, returneres **Copenhagen, Denmark** i stedet for **København, Danmark**.

1. Angiv et Navn til forbedringen.

1. Gennemse indstillingerne, og vælg derefter **Gem forbedringer**.

## <a name="configure-the-connection-for-azure-maps"></a>Konfiguration af forbindelsen til Azure Maps

Du skal være administrator i målgruppeindsigt for at kunne konfigurere forbindelser. Vælg **Tilføj forbindelse**, når du konfigurerer en forbedring, eller gå til **Administration** > **Forbindelser**, og vælg **Konfigurer** i feltet Azure Maps.

1. Angiv et **visningsnavn** til forbindelsen i feltet visningsnavn.

1. Angiv en gyldig API-nøgle til Azure Maps.

1. Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**

1. Vælg **Kontroller** for at validere konfigurationen.

1. Vælg **Gem**, når verifikationen er fuldført.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Maps-forbindelseskonfigurationsside.":::

## <a name="enrichment-results"></a>Forbedringsresultater

Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen. Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab). Behandlingstiden afhænger af størrelsen på dine kundedata og API-svartider.

Når processen til forbedring af kundeoplevelsen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**. Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.

Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.

## <a name="next-steps"></a>Næste trin

Byg oven over dine forbedrede kundedata. Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du gør det muligt for Dynamics 365 Customer Insights at overfører data til Azure Maps, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personlige data. Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at Azure Maps overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have. Du kan finde flere oplysninger i [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
