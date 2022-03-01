---
title: Eksportere Customer Insights-data til Microsoft Advertising
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124471"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Eksportere segmenter til Microsoft Advertising (forhåndsversion)

Eksporter Customer Insights-segmenter til Microsoft Advertising for at oprette målgrupper for kundematch. Brug disse målgrupper til dine annoncekampagner.

## <a name="prerequisites"></a>Forudsætninger

-   En [Microsoft Advertising-konto](https://ads.microsoft.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Du har accepteret vilkårene for kundematch. 
-   [Konfigurerede segmenter](segments.md) i målgruppeindsigt.
-   Samlede debitorprofiler i de eksporterede segmenter indeholder et felt med en mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Du kan eksportere op til 500K profiler pr. eksport til Microsoft Advertising.
- Eksport til Microsoft Advertising er begrænset til segmenter.
- Det kan tage op til 10 minutter at eksportere op til 500K profiler til Microsoft Advertising. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Konfigurer forbindelsen til Microsoft Advertising

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Microsoft Advertising** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Standarden er administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til Microsoft Advertising.

1. Vælg **Godkend med Microsoft Advertising**, og angiv administratoroplysningerne for Microsoft Advertising.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen Microsoft Advertising i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Vælg de segmenter, du vil eksportere. Målgrupperne Kundematch i Microsoft Advertising oprettes automatisk med navnet på de segmenter, der er valgt til eksport. Hvert segment resulterer i en separat kundematchmålgruppe. 

1. Angiv dit **Microsoft Advertising-kunde-id og -konto-id**. Du kan finde kunde-id' et (`cid`) og konto-id'et (`aid`) i parametrene for URL-adressen, når du er logget på Microsoft Advertising.

1. Vælg det felt i din samlede kundeprofil med en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**. Det er obligatorisk at eksportere segmenter til Microsoft Advertising.

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du gør det muligt for Dynamics 365 Customer Insights at overføre data til Microsoft Advertising, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder følsomme data som f.eks. personlige data. Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at Microsoft Advertising overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at stoppe brugen af denne funktionalitet.
