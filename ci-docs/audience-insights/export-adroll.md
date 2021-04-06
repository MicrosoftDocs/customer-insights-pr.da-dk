---
title: Eksportere Customer Insights-data til AdRoll
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697067"
---
# <a name="connector-for-adroll-preview"></a>Connector til AdRoll (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til AdRoll, og brug dem til reklamer. 

## <a name="prerequisites"></a>Forudsætninger

-   Du har en [AdRoll-konto](https://www.adroll.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="connect-to-adroll"></a>Opret forbindelse til AdRoll

1. Gå til **Adminstration** > **Eksportdestinationer**.

1. Under **AdRoll** skal du vælge **Konfigurer**.

1. Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfigurationsrude til AdRoll-forbindelse.":::

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til AdRoll.

1. Vælg **Godkendelse med AdRoll**, og angiv dine administratorlegitimationsoplysninger for AdRoll. 

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Angiv dit **AdRoll-annoncør-id** [AdRoll-annoncering](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Vælg **Næste** for at konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurer connectoren

1. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. Den kræves for at eksportere segmenter til AdRoll.

1. Vælg de segmenter, du vil eksportere. Vælg et segment med mindst 100 medlemmer. Du kan ikke eksportere mindre segmenter. Derudover er maksimumstørrelsen på et segment, der skal eksporteres, 250.000 medlemmer pr. eksport. 

1. Vælg **Gem**.

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).

## <a name="known-limitations"></a>Kendte begrænsninger

- Du kan eksportere op til 250.000 profiler pr. eksport til AdRoll.
- Du kan ikke eksportere segmenter med færre end 100 profiler til AdRoll. 
- Eksport til AdRoll er begrænset til segmenter.
- Det kan tage op til 10 minutter at eksportere op til 250.000 profiler til AdRoll. 
- Antallet af profiler, du kan eksportere til AdRoll, er afhængige og begrænsede i kontrakten med AdRoll.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til AdRoll, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at AdRoll overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.
