---
title: Eksport af Customer Insights til Kampagneovervågning
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til kampagneovervågning.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760502"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a>Eksport af segmentlister til kampagneovervågning (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til Kampagneovervågning, og brug dem til marketingaktiviteter.

## <a name="prerequisites"></a>Forudsætninger

-   Du har en [kampagneovervågningskonto](https://www.campaignmonitor.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Du kan eksportere op til 1 millioner profiler pr. eksport til Kampagneovervågning.
- Eksport til Kampagneovervågning er begrænset til segmenter.
- Det kan tage op til 20 minutter at eksportere op til 1 millioner profiler til Kampagneovervågning. 
- Det antal profiler, du kan eksportere til Kampagneovervågning, er afhængigt af og begrænset af kontrakten med Kampagneovervågning.

## <a name="set-up-connection-to-campaign-monitor"></a>Konfigurer forbindelse til Kampagneovervågning 

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Kampagneovervågning** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret** forbindelse for at initialisere forbindelsen til Kampagneovervågning.

1. Vælg **Autentificer** med kampagneovervågning, og angiv administratoroplysningerne for Kampagneovervågning.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen Kampagneovervågning i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Angiv din [**Kampagneovervågningsliste-id**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Opret første API-nøglen](https://www.campaignmonitor.com/api/getting-started/) fra **Kontoindstillinger** i Kampagneovervågning for at få vist API-liste-id.  

3. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. Det er obligatorisk at eksportere segmenter til Kampagneovervågning.

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du gør det muligt for Dynamics 365 Customer Insights at overføre data til Kampagneovervågning, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder følsomme data som f.eks. personlige data. Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at Kampagneovervågning overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.
