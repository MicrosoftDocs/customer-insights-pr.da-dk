---
title: Eksportere Customer Insights-data til LinkedIn Ads
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 948a7e980df5714034009c92282e78cf2bdcb231
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618284"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Eksportere segmenter til LinkedIn Ads (forhåndsversion)

Eksportere segmenter af samlede kundeprofiler til LinkedIn Ads for at oprette matchede målgrupper. Brug de matchede målgrupper til målretning af virksomheder og kontakter.

## <a name="prerequisites"></a>Forudsætninger

-   Du har en [LinkedIn Campaign Manager-konto](https://business.linkedin.com/marketing-solutions/ads) og tilsvarende administratorlegitimationsoplysninger.
-   Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.
-   Debitorprofiler i de udlæste målgrupper indeholder et felt med en mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Du kan eksportere op til 100.000 kundeprofiler pr. eksport til LinkedIn-annoncer.
- Eksport til LinkedIn Ads er begrænset til segmenter.
- Det kan tage op til 10 minutter at eksportere op til 100.000 kundeprofiler til LinkedIn-annoncer. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Konfigurer forbindelsen til LinkedIn Ads

1. I målgruppeindsigt skal du gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **LinkedIn Ads** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv dit [LinkedIn Campaign Manager-konto-id](https://www.linkedin.com/help/lms/answer/a424270).

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret** forbindelse for at initialisere forbindelsen til Kampagneovervågning.

1. Vælg **Godkend med LinkedIn**, og angiv administratoroplysningerne for LinkedIn Campaign Manager.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere en eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen LinkedIn Ads i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Vælg, om du vil eksportere data for at udføre [målretning efter kontakt](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) eller [målretning efter virksomheder](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) på LinkedIn. 

1. Vælg mindst ét felt, der repræsenterer en kundes mailadresse, Apple-annonce-id, Google-annonce-id, Google-bruger-id eller for- og efternavn, i sektionen **Datamatching** for kontaktmålretning. Hvis du vælger firmamålretning, skal du vælge mindst ét felt, der repræsenterer firmanavn, maildomæne, URL-adresse til LinkedIn-side, lagersymbol eller websted. Der kan vælges flere felter for at definere eksporten yderligere. 

1. Vælg de segmenter, du vil eksportere. De matchede målgrupper i LinkedIn Campaign Manager oprettes automatisk med navnet på de segmenter, du har valgt at eksportere. Hvert segment resulterer i en separat afstemt målgruppe. 

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights til at overføre data til LinkedIn Ads, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder følsomme data som f.eks. personlige data. Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at LinkedIn Ads overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at stoppe brugen af denne funktionalitet.
