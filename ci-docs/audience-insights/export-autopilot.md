---
title: Eksportere Customer Insights-data til Autopilot
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596123"
---
# <a name="connector-for-autopilot-preview"></a>Connector til Autopilot (prøveversion)

Eksportér segmenter med ensartede kundeprofiler til Autopilot, og brug dem til mailmarketing i Autopilot. 

## <a name="prerequisites"></a>Forudsætninger

-   Du har en [Autopilot-konto](https://www.autopilothq.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="connect-to-autopilot"></a>Oprette forbindelse til Autopilot

1. Gå til **Adminstration** > **Eksportdestinationer**.

1. Under **Autopilot** skal du vælge **Konfigurer**.

1. Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfigurationsrude til Autopilot-forbindelse.":::

1. Angiv din **Autopilot API-nøgle** [Autopilot API-nøgle](https://autopilot.docs.apiary.io/#).

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til Autopilot.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Næste** for at konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurer connectoren

1. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. Gentag de samme trin for andre felter som **Fornavn**, **Efternavn**.

1. Vælg de segmenter, du vil eksportere. Det **anbefales ikke at eksportere mere end 100'000 kundeprofiler i alt** til Autopilot. 

1. Vælg **Gem**.

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).

## <a name="known-limitations"></a>Kendte begrænsninger

- Du kan eksportere op til 100.000 kundeprofiler i alt til Autopilot.
- Eksport til Autopilot er begrænset til segmenter.
- Det kan tage op til et par timer at eksportere op til 100.000 profiler til Autopilot. 
- Antallet af profiler, du kan eksportere til Autopilot, er afhængige og begrænsede i kontrakten med Autopilot.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Autopilot, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks.. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Autopilot overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]