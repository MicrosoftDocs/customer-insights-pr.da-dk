---
title: Eksport af Customer Insights-data til RollWorks
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d8ce4d867835dcb7cf56c6fffff4e25d1f5c109af0e401fc0eb8b3a7427c1de4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034583"
---
# <a name="export-segments-to-rollworks-preview"></a>Eksportere segmenter til RollWorks (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til RollWorks, og brug dem til marketing. 

## <a name="prerequisites-for-a-connection"></a>Forudsætninger for en forbindelse

-   Du har en [RollWorks-konto](https://www.rollworks.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Du kan eksportere op til 250.000 profiler pr. eksport til RollWorks.
- Du kan ikke eksportere segmenter med færre end 100 profiler til RollWorks. 
- Eksport til RollWorks er begrænset til segmenter.
- Det kan tage op til 10 minutter at eksportere op til 250.000 profiler til RollWorks. 
- Det antal profiler, du kan eksportere til RollWorks, er afhængigt af og begrænset af kontrakten med RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Konfigurer forbindelsen til RollWorks

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **RollWorks** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til RollWorks.

1. Vælg **Autentificer med RollWorks**, og angiv administratoroplysningerne for RollWorks.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen RollWorks i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Angiv dit **RollWorks Advertiser-id** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. Det er obligatorisk at eksportere segmenter til RollWorks.

1. Vælg de segmenter, du vil eksportere. Vælg et segment med mindst 100 medlemmer. Du kan ikke eksportere mindre segmenter. Derudover er maksimumstørrelsen på et segment, der skal eksporteres, 250.000 medlemmer pr. eksport. 

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du gør det muligt for Dynamics 365 Customer Insights at overføre data til RollWorks, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder følsomme data som f.eks. personlige data. Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at RollWorks overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.
