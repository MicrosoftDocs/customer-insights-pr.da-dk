---
title: Startsiden i målgruppen Insights
description: Begynd at udforske appen på startsiden.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597228"
---
# <a name="create-a-new-environment"></a>Opret et miljø

## <a name="create-a-trial-environment"></a>Oprette et prøvemiljø

Du kan tilmelde dig en prøveversion på [prøveabonnementssiden](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Prøver udløber efter 30 dage.

1. Vælg indstillingen **Tilmeld dig en gratis prøveversion**, og vælg **Tilmeld nu**.

1. Angiv din arbejds- eller skolemailadresse, fortæl os mere om dig selv, og vælg **Næste**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogboks, hvor du kan tilmelde dig for at få en gratis prøveversion":::

1. Angiv et **Navn** til dit nye miljø. 

1. Vælg prøvetypen.

1. Vælg et **Område** for dit miljø.

1. Du kan også vælge til administratorer af en Dynamics 365-organisation: Vælg **Avancerede indstillinger**, og angiv URL-adressen til din organisation for at bruge forudsigelsesfunktioner som f.eks. kundeafgang.

1. Vælg **Opret**. 

Når miljøet er oprettet, kan du se **Demo**-miljøet, som giver dig mulighed for at udforske appen med fiktive data. Du kan ændre eksempeldataene, så de stemmer overens med din branche. Vælg ikonet **Indstillinger** i sidehovedet, og vælg **Demoindstillinger**. Derudover kan du ændre det visuelle tema. 

Du [skifter til det miljø](#switch-environments), du har oprettet under tilmeldingsprocessen, for at arbejde med dine egne data.

## <a name="create-a-new-production-or-sandbox-environment"></a>Oprette et produktions- eller sandkassemiljø

Vælg **Miljøer** i appoverskriften, og vælg **Ny** i dit miljø.

Følg trinnene, som om du [opretter et prøvemiljø](#create-a-trial-environment). Som standard gemmes data i den Customer Insights-styrede datasø. Du får en ekstra indstilling, når du vælger **Avancerede indstillinger**, for at gemme dine data i din egen Azure Data Lake. Angiv dit kontonavn og din kontonøgle for at oprette forbindelse til din Azure Data Lake. 

> [!IMPORTANT]
> Når du gemmer data i Azure Data Lake Storage, accepterer du, at data overføres til og gemmes på den relevante geografiske placering for den pågældende Azure-datalagerkonto, som kan være en anden placering end den, hvor data gemmes i Dynamics 365 Customer Insights. [Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Udforske startsiden

Du kan få [adgang til målgruppeindsigt fra Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) på følgende URL-adresse: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
På siden **Start** vises en oversigt over segmenter, mål og data til forbedring (hvis de er konfigureret) efter fuldførelse af [tilknyt](map-entities.md), [match](match-entities.md), og [flet](merge-entities.md)-faserne.

> [!div class="mx-imgBorder"] 
> ![Indsigt på startside](media/home-page-insights.png "Indsigt på startside")

Under **Seneste segmenter** kan du se grupper af kunder baseret på de attributter for demografi, adfærd eller transaktioner, som du har defineret. [Ved at oprette segmenter](segments.md) kan du gruppere kundebasen og målrette dine forretningsaktiviteter bedre.

**Seneste målinger** viser de felter med [nøgletalsindikatorer (KPI'er)](measures.md), du har defineret. Det kan f.eks. være den gennemsnitlige sandsynlighed for, at en kunde kommer i gang, eller det gennemsnitlige onlineforbrug pr. kunde.

I sektionen **Seneste forbedringer** vises resultaterne af de forbedringer, der er blevet kørt og fuldført for nylig. [Forbedringer](enrichment-hub.md) tilføjer oplysninger om kundebasen. Det sker f.eks. ved at forstå, hvilke interesser og mærker de har et tilhørsforhold til.

## <a name="switch-environments"></a>Skift miljøer

Vælg **Miljø**-kontrolelementet i øverste højre hjørne af siden for at skifte miljøer.

> [!div class="mx-imgBorder"] 
> ![Skift miljø](media/home-page-environment-switcher.png "Skift miljø")

Administratorer kan oprette og administrere [flere miljøer](manage-environments.md). Det kan være en god ide at vedligeholde mere end ét miljø, hvis organisationen f.eks. opererer i udlandet, og du har brug for at adskille data og indsigt på forskellige måder.

## <a name="next-step"></a>Næste trin

Hvis du vil se dine egne indsigter på startsiden, skal du først [tilføje datakilder](data-sources.md) og [samle](data-unification.md) dataene for at oprette kundeprofiler.


[!INCLUDE[footer-include](../includes/footer-banner.md)]