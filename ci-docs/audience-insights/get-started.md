---
title: Start her med funktionen målgruppeindsigt i Dynamics 365 Customer Insights
description: En oversigt over målgruppeindsigt kan hjælpe ressourcer med at komme hurtigt i gang.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5e8545bc9bf0d953150248fa859c6ca71a12f9cf
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645257"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Start her med funktionen målgruppeindsigt i Dynamics 365 Customer Insights

Målgruppeindsigt kan hjælpe med at opbygge en større forståelse af kunderne. Forbind data fra forskellige transaktions-, adfærds- og overvågningskilder for at få en 360-graders kundevisning. Brug disse indsigter til at skabe kundebaserede oplevelser og processer. Du kan samle og forstå kundedata og udnytte dem til intelligent indsigt og handlinger.

## <a name="step-1-create-an-environment"></a>Trin 1: Oprette et miljø

Du skal først oprette et miljø, du kan arbejde i. Hvis din organisation allerede har købt en licens, skal du se [Oprette et miljø](create-environment.md). Hvis du vil starte en forhåndsversion til målgruppeindsigt, skal du se [Konfigurere et prøvemiljø](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>Trin 2: Udforsk målgruppeindsigt

Første gang du logger på for at få målgruppeindsigt, kan du konfigurere indstillingerne og undersøge produktet.

1. [Log på målgruppeindsigt](https://home.ci.ai.dynamics.com) ved hjælp af din Microsoft Azure Active Directory-brugerkonto (AAD).

1. [Rediger miljøet](manage-environments.md#switch-environments) for at få vist demonstrationsdata, og [udforske målgruppeindsigt](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Trin 3: Indtage, samle og konfigurere relationer til dataene

Fælles profiler er grundlaget for at få indsigt og handle ud fra dataene. Hent data ind fra forskellige kilder, og kør processen til samling af data for at kombinere ensartede profiler. Angiv relationer mellem de aktiverede objekter ved hjælp af funktioner til lige muligheder for at føje oplysninger til profilerne. 

1. Indtag data ved at oprette datakilder fra flere indstillinger. Vælg mellem [Power Query](connect-power-query.md)-connectors, [mappen Common Data Model](connect-common-data-model.md) eller [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. Kør [datasamlingsprocessen](data-unification.md) ved at gennemgå [tilknytning](map-entities.md), [match](match-entities.md) og [fletning](merge-entities.md) af faser.

1. Bliv fortrolig med de [objekter, som systemet opretter](entities.md), og opret [relationer imellem angivne objekter](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Trin 4: Forbedring af ensartede profiler med forudsigelser, aktiviteter og mål

Med ensartede profiles konfigureret, kan du forbedre dine data og yderligere øge de oplysninger, de giver.

1. Vælg mellem et udvidet bibliotek med udbydere til forbedring for at [forbedre dine kundedata](enrichment-hub.md).

1. Brug [standardmodeller](predictions-overview.md) til at forudsige risikoen for afgang eller den forventede indtjening.

1. [Konfigurer aktiviteter](activities.md) på baggrund af data, og visualiser interaktioner med kunderne på en kronologisk tidslinje. 

1. [Opbyg mål](measures.md) for at registrere forretningsmål og KPI'er.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Trin 5: Oprettelse af segmenter og aktivering af data via forskellige eksportindstillinger

Nu, hvor dataene er fuldstændige og indeholder en lang række oplysninger om kunderne, er det tid til at finde måder, du kan udføre handlinger på de pågældende data på. 

1. [Opret segmenter](segments.md), undersæt af kundebasen for at sikre, at dine handlinger er relevante for målkunderne.

1. Gennemse det udvidende katalog med [eksportindstillinger](export-destinations.md), hvor du kan bruge kundedata. Du kan f.eks. bruge data til at administrere kampagner og skabe kontakt med digital marketing.

1. Gennemse integrationsindstillinger, f.eks. med den [direkte forbindelse til indsigt i engagement](../engagement-insights/integrate-audience-insights-engagement-insights.md) eller til andre Dynamics 365-apps med [tilføjelsesprogrammet Kundekort](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
