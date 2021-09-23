---
title: Start her med funktioner i engagementsindsigt
description: En oversigt over hjælperessourcer til hurtig start.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494587"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Start her med Dynamics 365 Customer Insights funktioner i engagementsindsigt (offentlig forhåndsversion)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Med engagementsindsigt kan du indsamle og måle kundefunktionsmåder på dit websted. Den integreres med målgruppeindsigtsfunktionalitet, så du kan se avancerede adfærdsanalyser i realtid sammen med rapporter over kundeprofiler. Linkene i denne artikel hjælper dig med hurtigt at konfigurere og konfigurere miljøet.

## <a name="step-1-review-prerequisites"></a>Trin 1: Gennemse forudsætninger

Du skal først have en aktiv Microsoft Azure Active Directory-brugerkonto (AAD). Læs derefter følgende artikler, før du konfigurerer arbejdsområdet engagementsindsigt.

- Gennemse og acceptere [Servicebetingelser](terms-of-service.md) med Microsoft.  
- Læs artiklen [Administration af cookies og brugernes samtykke](user-consent-storage.md). Derefter skal du vurdere, om du skal opdatere din meddelelse om brugerens samtykke. Hvis du ikke tidligere har haft "ikke-vigtige" cookies, skal du sandsynligvis opdatere din webstedspolitik.
- Gennemgå [ordlisten](glossary.md) for at få en hurtig introduktion til nøgleord og koncepter.

## <a name="step-2-explore-engagement-insights"></a>Trin 2: Undersøge indsigt i engagement

Første gang du logger på for at få engagementsindsigt, kan du konfigurere indstillingerne, gennemse politikker og undersøge produktet.

1. Log på [portal til engagementsindsigt](https://home.ci.ai.dynamics.com/app/engagement-insights) ved hjælp af din Microsoft AAD-bruger (skole- eller arbejdskonto).

1. Vælg dit område, og markér afkrydsningsfeltet, hvis du vil vælge, om du vil modtage e-mailopdateringer og tilbud.

1. Gennemse **engagementsindsigt (forhåndsversion) vilkårene for anvendelse** og **erklæringen om beskyttelse af personlige oplysninger**, og vælg derefter **Undersøg demo** for at acceptere disse indstillinger.

1. Undersøg produktet ved hjælp af et sæt eksempeldata.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Trin 3: Konfigurer et arbejdsområde, og føj kode til webstedet

Et arbejdsområde er det sted, hvor du kan få vist brugeraktivitet i realtid og gemme og administrere rapporter. Føj kode til webstedet for at starte indsamlingen af *hændelser*, de aktivitetsdata, der kommer fra brugere.

1. [Opret et arbejdsområde](create-workspace.md), og tilføj medlemmer.

1. [Føj kode til dit websted](instrument-website.md) eller [mobilappen](developer-resources.md#capture-events-from-mobile-apps) for at se brugeraktiviteten i dit arbejdsområde.

1. Få vist en [rapport i realtid](view-reports.md), der viser aktive brugere efter browser, enhed, operativsystem, placering og sprog. Du kan også oprette [brugerdefinerede rapporter](custom-reports.md) for at oprette dine egne visualiseringer.
    
## <a name="step-4-export-data-to-other-channels"></a>Trin 4: Eksport af data til andre kanaler

Du kan oprette *forfinede hændelser* (en virtuel visning) med dine webanalysedata. Filtrer og eksporter derefter dataene til Azure Data Lake Storage. Du kan oprette de eksporterede data som en datakilde. Flere oplysninger: [Opret et link mellem målgruppeindsigt og engagementsindsigt](integrate-audience-insights-engagement-insights.md).

1. [Oprette forfinede hændelser](refined-events.md) til eksport.

1. [Eksportér data](export-events.md) til Data Lake Storage.

1. [Opret et link mellem målgruppeindsigt og engagementsindsigt](integrate-audience-insights-engagement-insights.md) for at dele data mellem de to funktioner.

1. Flere oplysninger om at [slette og eksportere hændelsesdata, der indeholder personlige oplysninger](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Trin 5: Bevar forbindelsen

Vi værdsætter din aktive deltagelse og overvejer al relevant feedback i forbindelse med udvikling af kommende udgivelser. Du kan dele din feedback og rapportere problemer via en af disse kanaler:
- [Community](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Sende feedback](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Anmode om support](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]