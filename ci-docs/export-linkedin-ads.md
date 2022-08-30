---
title: Eksportere segmenter til LinkedIn Ads (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304696"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Eksportere segmenter til LinkedIn Ads (forhåndsversion)

Eksportere segmenter af samlede kundeprofiler til LinkedIn Ads for at oprette matchede målgrupper. Brug de matchede målgrupper til målretning af virksomheder og kontakter.

## <a name="prerequisites"></a>Forudsætninger

- En [LinkedIn Campaign Manager-konto](https://business.linkedin.com/marketing-solutions/ads) og tilhørende administratorlegitimationsoplysninger.
- En [LinkedIn Campaign Manager -konto-id](https://www.linkedin.com/help/lms/answer/a424270).
- [Konfigurerede segmenter](segments.md) i Customer Insights.
- De eksporterede segmenter skal bruge mindst ét specifikt felt, afhængigt af om du vælger [kontaktmålretning](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) eller [firmamålretning](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) på LinkedIn. De mulige felter vises i trinnet **Datamatching**, når [eksporten konfigureres](#configure-an-export).

## <a name="known-limitations"></a>Kendte begrænsninger

- Du kan eksportere op til 100.000 kundeprofiler pr. eksport til LinkedIn Ads, og det kan tage op til 10 minutter at fuldføre den.
- Kun segmenter. Et segment skal indeholde mindst 300 unikke profiler.

## <a name="set-up-connection-to-linkedin-ads"></a>Konfigurer forbindelsen til LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelseconnection**, og vælg **LinkedIn Ads**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv din LinkedIn Campaign Manager Konto-id.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen.

1. Vælg **Godkend med LinkedIn**, og angiv administratoroplysningerne for LinkedIn Campaign Manager.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen LinkedIn Ads i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Vælg, om du vil eksportere data for at udføre [målretning efter kontakt](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) eller [målretning efter virksomheder](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) på LinkedIn.

1. Vælg mindst ét felt, der repræsenterer en kundes mailadresse, Apple-annonce-id, Google-annonce-id, Google-bruger-id eller for- og efternavn, i sektionen **Datamatching** for kontaktmålretning. Hvis du vælger firmamålretning, skal du vælge mindst ét felt, der repræsenterer firmanavn, maildomæne, URL-adresse til LinkedIn-side, lagersymbol eller websted.

1. Der kan også vælges flere felter for at definere eksporten yderligere. Vælg **Tilføj attribut** for at tilknytte disse felter.

1. Vælg de segmenter, du vil eksportere. De matchede målgrupper i LinkedIn Campaign Manager oprettes automatisk med navnet på de segmenter, du har valgt at eksportere. Hvert segment resulterer i en separat afstemt målgruppe.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
