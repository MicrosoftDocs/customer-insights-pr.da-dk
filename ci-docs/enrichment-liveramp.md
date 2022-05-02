---
title: Forbedring af LiveRamp-identifikationsdata
description: Forbedre kundeprofiler med LiveRamp-data.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646086"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Forbedre kundeprofiler med identitetsdata fra LiveRamp (forhåndsversion) 

LiveRamp leverer deterministisk identitetsløsning til offline og en sammenlægning af kundedata. Du kan knytte personlige id'er i kundedataene til AbiliTec-identitetsgrafen og modtage AbiliTec-id'er. Du kan derefter bruge disse id'er til at opnå en bedre samling af kundedata. 

## <a name="prerequisites"></a>Forudsætninger 

Hvis du vil konfigurere forbedringen, skal følgende forudsætninger være opfyldt: 

- Du skal have et aktivt LiveRamp-abonnement. Hvis du vil have et abonnement, skal du kontakte dit LiveRamp-firmateam eller [dynamics@liveramp.com](mailto:dynamics@liveramp.com) for at få flere oplysninger.   

- Et aktivt AbiliTec-abonnement med et klient-id og en hemmelighed til at få adgang til API'en. Du kan finde flere oplysninger i [AbiliTec API Udvikler-hub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Understøttede lande/områder 

I øjeblikket understøtter vi kun forbedring af kundeprofiler med LiveRamp-data i USA. 

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring 

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**. 

1. Vælg **Forbedring af data** i feltet **Identitet**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identitetsfelt i oversigtssiden for forbedring. ":::

1. Vælg en [værdi](connections.md) på rullelisten. Kontakt en administrator, hvis der ikke er nogen forbindelse. Hvis du er en administrator, kan du oprette forbindelse ved at vælge **Tilføj forbindelse**. Vælg **LiveRamp** på rullelisten. 

1. Vælg **Næste**, og vælg det **Kundedatasæt**, du vil forbedre med identitetsdata fra LiveRamp. Du kan vælge objektet *Kunde* for at forbedre alle dine kundeprofiler eller vælge et *segment*-objekt for kun at forbedre de kundeprofiler, der findes i dette segment. 

1. Vælg **Næste**, og definer, hvilken type felter fra dine ensartede profiler der skal bruges til at søge efter tilsvarende identitetsdata fra LiveRamp. Mindst ét af felterne **Navn og adresse**, **Telefon** eller **E-mail** er obligatorisk. 

   > [!TIP]
   > Jo flere nøgle-id'er og felter, du tilknytter, jo større er sandsynligheden for en højere overensstemmelseshastighed 

1. Tilknyt felterne fra det unified *Customer*-objekt, der skal bruges til matchning, med LiveRamps AbiliTec-identitetsgraf. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Indstillinger for datatilknytning for LiveRamp-forbedring.":::

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**. 

1. Angiv et **Navn** til forbedringen og **outputobjektet**. 

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg. 

## <a name="configure-the-connection-for-liveramp"></a>Konfiguration af forbindelsen til LiveRamp 

Du skal være en administrator for at [konfigurere forbindelser](connections.md). Vælg **Tilføj forbindelse**, når du konfigurerer forbedringen, eller gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i feltet **LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Konfigurationsruden til at konfigurere forbindelsen til tjenesten LiveRamp AbiliTec. ":::

1. Ved **Visningsnavn** skal du angive navnet på forbindelsen. 

1. Angiv et gyldigt LiveRamp-klient-id og en hemmelighed. 

1. Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**. 

1. Vælg **Kontroller** for at validere konfigurationen. 

1. Vælg **Gem** for at fuldføre forbindelsen. 

## <a name="enrichment-results"></a>Forbedringsresultater 

Hvis du vil starte forbedringsprocessen, skal du vælge Kør fra kommandolinjen. Du kan også lade systemet køre forbedring automatisk som en del af en  [planlagt opdatering](system.md#schedule-tab). Behandlingstiden afhænger af størrelsen på dine kundedata. 

Når processen til forbedring af kundeoplevelsen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under  **Arbejde**. Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler. 

Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge  **Vis forbedrede** data. 

## <a name="next-steps"></a>Næste trin

Byg oven over dine forbedrede kundedata. Brug AbiliTec-id'er til at samle kundeprofiler i en personbaseret visning. 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder 

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til LiveRamp, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at LiveRamp overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have. Du kan finde yderligere oplysninger ved at gennemse [Erklæring om beskyttelse af personlige oplysninger i Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet. 


[!INCLUDE [footer-include](includes/footer-banner.md)]
