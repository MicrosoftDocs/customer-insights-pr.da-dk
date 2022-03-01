---
title: Robot til Microsoft Teams
description: Søg efter samlede kundeprofiler i Microsoft Teams ved hjælp af en robot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405441"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams-robot til Dynamics 365 Customer Insights (prøveversion)

Opret forbindelse Microsoft Teams for at lade en robot søge efter samlede kundeprofiler i Teams-kanaler.

> [!div class="mx-imgBorder"]
> ![Teams-bot viser en kundepost](media/teams-bot.png "Teams-bot viser en kundepost")

## <a name="prerequisites"></a>Forudsætninger

For at installere og konfigurere denne bot, skal følgende forudsætninger være opfyldt:

- Der er tilføjet mindst én [datakilde](data-sources.md).
- [Samlingsprocessen](data-unification.md) er fuldført.
- Der tilføjet felter til [søge- og filtreringsindekset](search-filter-index.md).
- Customer Insights og Teams er i samme organisation.

## <a name="configure-the-bot"></a>Konfiguration af botten

1. Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.
1. På Microsoft Teams-feltet vælges **Konfigurer**.
1. Du omdirigeres til området **Apps** Teams. Du kan også åbne Teams og vælge **Apps** i nederste venstre hjørne eller [hente direkte fra AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Søg efter **Customer Insights**, og vælg appen.
1. Vælg **Tilføj**.
1. Når du har logget på Customer Insights i Teams, kan du se en velkomstmeddelelse og komme i gang.

## <a name="things-you-can-do-with-the-bot"></a>Ting du kan gøre med botten

Botten leverer opslagsmuligheder for samlede kundeprofiler.

- Skriv **search** efterfulgt af et navn, en mailadresse eller et andet felt i den samlede kundeprofil, der er føjet til søge- og filtreringsindekset.

  Du får et kort med op til 15 felter fra den resulterende kundeprofil. Flere forekomster returnerer en liste med resultater, hvor du kan vælge en profil. Du kan tilføje søgeudtryk i dobbelte anførselstegn for at søge efter et nøjagtigt match.

- Hvis din organisation vedligeholder flere Customer Insights-miljøer i samme organisation, kan du angive **switchinstance** for at vælge, hvilket miljø en robot skal knyttes til.

- Skriv **Hjælp** for at få vist en liste over tilgængelige kommandoer for botten.  
