---
title: Introduktion til Dynamics 365 Customer Insights
description: En oversigt over Customer Insights hjælper ressourcer med at komme hurtigt i gang.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1c925110f40319df77940d1c32f24a99504d6ec6
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011972"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Introduktion til Dynamics 365 Customer Insights

Customer Insights kan hjælpe dig med at få en større forståelse af dine kunder. Forbind data fra forskellige transaktions-, adfærds- og overvågningskilder for at få en 360-graders kundevisning. Brug disse indsigter til at skabe kundebaserede oplevelser og processer. Du kan samle og forstå kundedata og udnytte dem til intelligent indsigt og handlinger.

## <a name="step-1-create-an-environment"></a>Trin 1: Oprette et miljø

Opret først et miljø, du kan arbejde i. Hvis din organisation allerede har købt en licens, skal du se [Oprette et miljø](create-environment.md). Hvis du vil starte en prøveversion af Customer Insights, skal du se [Konfigurere et prøvemiljø](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Trin 2: Udforske Customer Insights

Første gang du logger på Customer Insights, kan du konfigurere indstillinger og undersøge produktet.

1. [Log på Customer Insights](https://home.ci.ai.dynamics.com) ved hjælp af din Microsoft Azure Active Directory (AAD) brugerkonto.

1. Rediger miljøet for at få vist demodata, og [udforsk Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Trin 3: Indtage, samle og konfigurere relationer til dataene

Fælles profiler er grundlaget for at få indsigt og handle ud fra dataene. Hent data ind fra forskellige kilder, og kør processen til samling af data for at kombinere ensartede profiler. Angiv relationer mellem de indtagede objekter, og brug forbedringsfunktioner til at føje oplysninger til profilerne.

1. Indtag data ved at oprette datakilder fra flere indstillinger. Vælg mellem [Azure Data Lake Storage, herunder Common Data Model](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), [Microsoft Dataverse](connect-dataverse-managed-lake.md) eller  [Power Query-connectorer](connect-power-query.md).

1. Kør [processen til oprettelse af data](data-unification.md) ved at identificere [kildefelterne](map-entities.md), fjerne [dubletter](remove-duplicates.md), [matche betingelser](match-entities.md) og [samle felter](merge-entities.md).

1. Bliv fortrolig med de [objekter, som systemet opretter](entities.md), og opret [relationer imellem angivne objekter](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Trin 4: Forbedring af ensartede profiler med forudsigelser, aktiviteter og mål

Hvis du har konfigureret samlede profiler, kan du forbedre dine data og øge mængden af oplysninger, de giver.

1. Vælg mellem et udvidet bibliotek med udbydere til forbedring for at [forbedre dine kundedata](enrichment-hub.md).

1. Brug [standardmodeller](predictions-overview.md) til at forudsige risikoen for afgang eller den forventede indtjening.

1. [Konfigurer aktiviteter](activities.md) på baggrund af data, og visualiser interaktioner med kunderne på en kronologisk tidslinje.

1. [Opbyg mål](measures.md) for at registrere forretningsmål og KPI'er.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Trin 5: Oprettelse af segmenter og aktivering af data via forskellige eksportindstillinger

Nu, hvor dataene er fuldstændige og indeholder en lang række oplysninger om kunderne, kan du finde ud af, hvordan du kan arbejde med de pågældende data.

1. [Opret segmenter](segments.md), undersæt af kundebasen for at sikre, at dine handlinger er relevante for målkunderne.

1. Gennemse det udvidende katalog med [eksportindstillinger](export-destinations.md), hvor du kan bruge kundedata. Du kan f.eks. bruge data til at administrere kampagner og skabe kontakt med digital marketing.

1. Gennemse integrationsindstillingerne, f.eks. til andre Dynamics 365-apps med [tilføjelsesprogrammet Kundekort](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
