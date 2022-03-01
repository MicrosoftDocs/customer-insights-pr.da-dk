---
title: Eksporter Customer Insights-data til Klaviyo
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Klaviyo.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7c1297fd5381c00c07d6501186c51fe4798773d1
ms.sourcegitcommit: 205f931ec671a0ab1850f2c1c94df3307ffb62c9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/13/2021
ms.locfileid: "7385781"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Eksport af segmentlister til Klaviyo (forhåndsversion)

Eksporter segmenter af samlede kundeprofiler til Klaviyo, og brug dem til marketingaktiviteter.

## <a name="prerequisites"></a>Forudsætninger

-   Du har en [Klaviyo-konto](https://www.klaviyo.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Du kan eksportere op til 100.000 profiler pr. eksport til Klaviyo.
- Eksport til Klaviyo er begrænset til segmenter.
- Det kan tage op til 20 minutter at eksportere op til 1 million profiler til Klaviyo. 
- Antallet af profiler, du kan eksportere til Klaviyo, afhænger af og er begrænset af din kontrakt med Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Konfigurer forbindelsen til Klaviyo.

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Klaviyo** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Giv din [Klaviyo API-nøgle](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) til fortsat at logge på. 

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til Klaviyo.

1. Vælg **Godkend med Klaviyo**, og angiv dine administratorlegitimationsoplysninger for Klaviyo.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen Klaviyo i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Angiv din [**Id for Klaviyo-liste**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. Det kræves, at der eksporteres segmenter til Klaviyo.

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du gør det muligt for Dynamics 365 Customer Insights at overfører data til Klaviyo, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personlige data. Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at Klaviyo overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.
