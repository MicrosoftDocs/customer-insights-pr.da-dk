---
title: Teams-robot til Dynamics 365 Customer Insights (prøveversion)
description: Søg efter samlede kundeprofiler i Microsoft Teams ved hjælp af en robot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195835"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Teams-robot til Dynamics 365 Customer Insights (prøveversion)

Opret forbindelse Microsoft Teams for at lade en robot søge efter samlede kundeprofiler i Teams-kanaler.

:::image type="content" source="media/teams-bot.png" alt-text="Teams-bot viser en kundepost":::

## <a name="prerequisites"></a>Forudsætninger

- Der er tilføjet mindst én [datakilde](data-sources.md).
- [Samlingsprocessen](data-unification.md) er fuldført.
- Der tilføjet felter til [søge- og filtreringsindekset](search-filter-index.md).
- Customer Insights og Teams er i samme organisation.
- I miljøet er den primære målgruppe angivet til de enkelte kunder. Virksomhedskonti understøttes ikke.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Konfiguration af botten

1. Gå til **Administrator** > **Forbindelser**.
1. På Microsoft Teams-feltet vælges **Konfigurer**.
1. Du omdirigeres til området **Apps** Teams. Du kan også åbne Teams og vælge **Apps** i nederste venstre hjørne eller [hente direkte fra AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Søg efter **Customer Insights**, og vælg appen.
1. Vælg **Tilføj**.
1. Log på Customer Insights i Teams. En velkomstmeddelelse vises.

## <a name="things-you-can-do-with-the-bot"></a>Ting du kan gøre med botten

Botten leverer opslagsmuligheder for samlede kundeprofiler.

- Skriv **søg** efterfulgt af et navn, en mailadresse eller et andet felt i den samlede kundeprofil, der er føjet til søge- og filtreringsindekset.

  Du får et kort med op til 15 felter fra den resulterende kundeprofil. Flere forekomster returnerer en liste med resultater, hvor du kan vælge en profil. Du kan tilføje søgeudtryk i dobbelte anførselstegn for at søge efter et nøjagtigt match.

- Hvis din organisation vedligeholder flere Customer Insights-miljøer i samme organisation, kan du angive **switchinstance** for at vælge, hvilket miljø en robot skal knyttes til.

- Skriv **Hjælp** for at få vist en liste over tilgængelige kommandoer for botten.  

[!INCLUDE [footer-include](includes/footer-banner.md)]