---
title: Dataindsættelse og begrænsninger i realtid
description: Generelle oplysninger om realtidsfunktioner i målgruppen Insights.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598562"
---
# <a name="real-time-data-ingestion-preview"></a>Dataindtagelse i realtid (prøveversion)

I næsten realtidsfunktionalitet kan du se i løbet af få sekunder de seneste interaktioner, som dine kunder har foretaget med dine produkter eller servicer.

[Planlagte opdateringer](system.md#schedule-tab) omfatter et stort antal poster og flere komplekse handlinger. For det første hentes data fra datakilden. Herefter bliver dataene samlet og derefter forbedret med yderligere oplysninger. Enhver kørsel af denne proces kan tage fra få minutter til flere timer.

Realtidsfunktionen leverer data med det samme til forbrug, indtil den efterfølgende planlagte opdatering henter disse data fra datakilden.

Opdateringerne i realtid har en udløbsdato, hvorefter de ikke længere overskriver værdien fra datakilden:

- Profilopdateringer gemmes i fire timer
- Aktiviteter gemmes i 30 dage

Disse værdier er parametre for API-kald, som du kan ændre. De skal sikre, at kildedataene forbliver din kilde til sandheden. Hvis der skal inkluderes realtidsopdateringer i længere tid, skal du føje dem til en datakilde så de bliver udtrukket under den næste planlagte opdatering.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Realtidsopdatering af felter med samlet kundeprofil

Opdaterede profiler vises i visningen kundekort eller en anden visualisering i løbet af få sekunder.

Da realtidsoperationer finder sted, efter at datasamlingen er sket, gælder de kun for de samlede kundeprofiler. Profilændringer i realtid vil derfor ikke opdatere målinger, segmentmedlemskab eller forbedringer.

### <a name="limitations"></a>Begrænsninger

- Kundeprofiler kan opdateres, men ikke oprettes eller slettes.
- Det er ikke muligt at eksportere opdateringer i realtid til eksterne som Power BI i øjeblikket.

## <a name="real-time-creation-of-activities"></a>Realtidsoprettelse af aktiviteter

I realtids-API kan du udgive en ny aktivitet fra kildesystemet (en enkelt kildepost) til en samlet kundeprofil. Den nye aktivitet bliver tilgængelig som en samlet aktivitet i den samlede kundeprofils tidslinje i løbet af få sekunder. Du kan se tidslinjen i visningen kundekort eller en anden tidslinjeintegration, du har konfigureret.

> [!NOTE]
>
> - Aktiviteter kan ikke ændres. De ændres ikke, når de er oprettet.
> - I øjeblikket opdateres segmenter og målinger ikke, afhængigt af den nye aktivitet.
> - Aktiviteter, der kun er tilføjet via realtids-API, er ikke en del af eksporter, og de vises ikke i Power BI.

Der er to måder at oprette forbindelse til en realtids-API på:

- [indirekte](#connect-via-the-dynamics-365-customer-insights-connector) ved hjælp af [Dynamics 365 Customer Insights-connectoren](/connectors/customerinsights/)
- [direkte](#connect-directly-to-the-real-time-api) med kode

Der gælder følgende forudsætninger for begge måder:

- Et Customer Insights-miljø
- Samlede kundeprofiler
- Aktiviteter er konfigureret og kører
- Bidragyder- eller administratortilladelser til at godkende din konto

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Forbindelse via Dynamics 365 Customer Insights-connectoren

I realtids-API kan du indtage data fra en dedikeret Power Platform-connector, [Dynamics 365 Customer Insights-connectoren](/connectors/customerinsights/) uden at skulle skrive og installere nogen kode.    
Connectoren kan udføre de samme realtidshandlinger som API'en. Du skal have en gyldig licens til premium connectorer. Du kan finde flere oplysninger under [Ofte stillede spørgsmål til Power Apps- og Power Automate-licenser](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps og/eller Power Automate](/connectors/)
- Azure [Logic Apps](/azure/connectors/apis-list)

Du kan finde flere oplysninger om oprettelse af flow i [dokumentationen til Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Oprette direkte forbindelse til API i realtid

Du kan bruge realtids-funktionerne ved at oprette din egen pipeline og oprette forbindelse direkte til API i realtid.    
Du kan bogføre en aktivitet i formatet af kildesystemet eller i UnifiedActivity-formatet. Hent formatet ved at foretage et API-kald til /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Du kan finde oplysninger om denne API, herunder parametre og svar, i afsnittet **EntityData** i [Customer Insights-API'er-reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Du kan finde flere oplysninger i afsnittet [Arbejde med Customer Insights-API'er](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Forstå dit realtidsforbrug med telemetri

Få et overblik over omfanget af anmodninger til API i realtid og oplysninger om de problemer, der kan opstå i systemet. Du kan få [adgang til telemetri i realtid](system.md#api-usage-tab). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]