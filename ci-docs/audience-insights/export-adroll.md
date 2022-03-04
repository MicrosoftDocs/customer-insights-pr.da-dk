---
title: Eksportere Customer Insights-data til AdRoll
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a318750077c71a17e5a47c40722f6153e6640f3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227613"
---
# <a name="export-segments-to-adroll-preview"></a>Eksporter segmentlister til AdRoll (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til AdRoll, og brug dem til reklamer. 

## <a name="prerequisites-for-a-connection"></a>Forudsætninger for en forbindelse

-   Du har en [AdRoll-konto](https://www.adroll.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Du kan eksportere op til 250.000 kundeprofiler ad gangen til AdRoll.
- Du kan ikke eksportere segmenter med færre end 100 kundeprofiler til AdRoll. 
- Eksport til AdRoll er begrænset til segmenter.
- Det kan tage op til 10 minutter at eksportere op til 250.000 kundeprofiler til AdRoll. 
- Antallet af kundeprofiler, du kan eksportere til AdRoll, afhænger af din kontrakt med AdRoll.

## <a name="set-up-connection-to-adroll"></a>Konfigurer forbindelsen til AdRoll

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **AdRoll** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til AdRoll.

1. Vælg **Godkendelse med AdRoll**, og angiv dine administratorlegitimationsoplysninger for AdRoll. 

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen AdRoll i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen tilgængelige forbindelser af denne type.

1. Angiv dit **AdRoll-annoncør-id**. Du kan finde flere oplysninger under [AdRoll-annoncørprofiler](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**. Den kræves for at eksportere segmenter til AdRoll.

1. Vælg de segmenter, du vil eksportere. Vælg et segment med mindst 100 medlemmer. Du kan ikke eksportere mindre segmenter. Derudover er maksimumstørrelsen på et segment, der skal eksporteres, 250.000 medlemmer pr. eksport. 

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). 

Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til AdRoll, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at AdRoll overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.
