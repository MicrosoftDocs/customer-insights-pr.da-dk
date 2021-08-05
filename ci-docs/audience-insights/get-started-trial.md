---
title: Oprette og konfigurere en prøveversion af Customer Insights
description: Trin til at få et prøveversions-abonnement på Dynamics 365 Customer Insights og konfigurere det.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f80654f03252142ce08241ff3ca3606be4595740
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650457"
---
# <a name="set-up-a-trial-environment"></a>Konfiguration af et prøveversionsmiljø 

Med en prøveversion af Dynamics 365 Customer Insights kan du gennemse nøglefunktioner og få mere at vide om de forskellige funktioner. Et prøveabonnement slettes efter udløb. Prøveversionsmiljøer oprettes af individuelle brugere, der bliver administrator i deres prøveversionsmiljø. De kan invitere flere brugere til deres prøveversion og konfigurere de forskellige funktioner.

## <a name="create-a-trial-environment"></a>Oprette et prøvemiljø

Du kan tilmelde dig en prøveversion på [prøveabonnementssiden](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Vælg indstillingen **Tilmeld dig en gratis prøveversion**, og vælg **Tilmeld nu**.

1. Angiv din arbejds- eller skole-mailadresse, fortæl os lidt mere om dig selv, og vælg **Introduktion**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogboks, hvor du kan tilmelde dig for at få en gratis prøveversion":::

1. Gennemse vilkårene og betingelserne, og vælg derefter **Fortsæt** for at bekræfte.

1. Angiv et **Navn** til dit nye miljø. 

1. Angiv **miljøtypen** som **prøveversion**.

1. I feltet **Vælg en branchedemonstration** kan du vælge et branchespecifikt datasæt. Du kan også [skifte til en branchedemonstration](#use-industry-specific-demo-data-sets-in-audience-insights) senere og starte med standarddatasættet.

1. Vælg et **Område** for dit miljø.

1. Hvis du er administrator af en Dynamics 365-organisation, kan du vælge **Avancerede indstillinger** og angive webadressen for din organisation til at bruge forudsigelse-funktioner som kundeafskærmede forudsigelse. 

1. Vælg **Opret**. 

Det tager et par minutter at udføre miljøkonfigurationen. Når du er færdig, omdirigeres du til demomiljøet eller den branchedemonstration, du vælger i trinnet ovenfor. Du kan nu udforske appen med skrivebeskyttet demodata. Hvis du vil føje dine egne data til miljøet, skal du se [Oprettelse af scenariespecifikke demodata i dit eget miljø](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Skærmbillede af et netop oprettet prøvemiljø.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Brug branchespecifikke demodatasæt i målgruppeindsigt

Oprettelse af forbindelse mellem virkelige datakilder er et af de vigtigste trin i brugen af Customer Insights. Hvis du vil prøve funktioner uden at forstyrre dine egne data, kan du vælge at bruge branchespecifikke demodata. Der findes et par demonstrationsdatasæt til følgende brancher: 

-   Biler
-   Bankvæsen
-   Forbrugsvarer
-   Offentlige myndigheder
-   Sundhedssektor
-   Beværtning
-   Forsikring
-   Fremstilling
-   Professionelle serviceydelser
-   Detail

### <a name="see-industry-specific-demo-data-in-trials"></a>Se branchespecifikke demodata i prøveversioner

Hvis du vil have en skrivebeskyttet version af Customer Insights, der er skræddersyet til en bestemt branche eller et bestemt scenario, skal du starte i demomiljøet. 
 
1.  Vælg **demomiljøet** i miljøvælgeren for målgruppeindsigt.

2.  Vælg en indstilling på rullelisten Vælg en branchedemonstration på **Startside**.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Vælg en branche til prøvemiljøet.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Oprettelse af scenariespecifikke demodata i dit eget miljø

Som en administrator skal du vælge miljøvælgeren i appoverskriften for at oprette et nyt miljø. I det nye miljø kan du konfigurere dine egne datakilder og konfigurere appen efter dine behov. 

1.  Gå til **Data** > **Datakilder** i målgruppen Insights.

2.  Hvis du vil importere dine egne datakilder, skal du gå til [vejledningen om dataimport](data-sources.md).     
   Hvis du foretrækker at arbejde med eksempeldata, hvor du kan afprøve data, kan du vælge at bruge branchedemonstrationsdataene i miljøet. Vælg indstillingen **Importér fra Datahub**, og følg trinnene nedenfor.

3.  Vælg det branchekort, der passer til dit scenario. 

4.  Gennemse og opdater eventuelt det foreslåede navn på datakilde. 

5.  Vælg **Næste** for at udvælge eksempeldataene. 

Du kan nu bruge de tilpassede data til at tilpasse Customer Insights til dit scenario. Hvis du vil se et miljø, der er specifikt for de indtagne demodata, skal du vælge **<Industry> Demo**-indstillingen i miljøvælgeren.

## <a name="limitations-in-trials"></a>Begrænsninger i prøveversioner

- Prøveversioner er som standard aktive i 30 dage. Du kan dog udvide dem efter dag 23, når du logger på prøveperioden.
- Du kan ikke bruge din egen Azure Data Lake Storage-konto til at gemme outputdata i løbet af en prøveversion. Du kan dog oprette data fra en Data Lake Storage-konto.
- Du kan gemme op til 3 GB data i Dataverse-miljøet, der automatisk bliver klargjort, når du starter en Customer Insights-prøveversion.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Kopiere data fra en prøveversion til et betalingsabonnement

Som regel anbefales det, at du starter med dine egne data, når du opgraderer til den betalte version af Customer Insights. 

Du kan også kopiere dataene fra et prøvemiljø, hvis du køber Customer Insights. Du skal være administrator i Customer Insights-prøveversionen og global administrator af din Microsoft 365-lejer eller Dynamics 365-administrator i organisationen for at overføre indstillingerne fra et prøvemiljø til et betalingsmiljø. 

Når du har logget på den betalte forekomst af Customer Insights for første gang, bliver du bedt om at oprette et nyt miljø. I denne proces kan du vælge at kopiere konfigurationen fra et eksisterende miljø og overføre de fleste indstillinger. Hvis du har ovennævnte tilladelser, vises prøveversionsmiljøet på denne liste. Du kan finde flere oplysninger under [Kopiere miljøkonfigurationen](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Næste trin

Gennemgå følgende artikler for at hjælpe dig med at komme i gang med at konfigurere Customer Insights. 

- [Tilføj flere brugere, og tildel tilladelser](permissions.md).
- [Gennemgå datakilderne](data-sources.md) og kør dem gennem [processen til enhed af data](data-unification.md) for at få [ensartede kundeprofiler](customer-profiles.md).
- [Forbedr de ensartede kundeprofiler](enrichment-hub.md) eller [kør intelligente modeller](predictions-overview.md).
- Opret [segmenter](segments.md) for at gruppere kunder og [målgennemgang](measures.md) af nøgletal.
- Opret [forbindelser](connections.md) og [eksporter](export-destinations.md) for at behandle undersæt af dataene i andre programmer.