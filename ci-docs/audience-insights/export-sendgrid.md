---
title: Eksportere Customer Insights-data til SendGrid
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268725"
---
# <a name="connector-for-sendgrid-preview"></a>Connector til SendGrid (prøveversion)

Eksportér segmenter med ensartede kundeprofiler til SendGrid-kontaktlister, og brug dem til kampagner og mailmarketing i SendGrid. 

## <a name="prerequisites"></a>Forudsætninger

-   Du har en [SendGrid-konto](https://sendgrid.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Der findes eksisterende kontaktlister i SendGrid og de tilsvarende id'er. Du kan finde flere oplysninger [i SendGrid – Administrere kontakter](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="connect-to-sendgrid"></a>Oprette forbindelse til SendGrid

1. Gå til **Adminstration** > **Eksportdestinationer**.

1. Under **SendGrid** skal du vælge **Konfigurer**.

1. Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Ruden SendGrid-eksportkonfiguration.":::

1. Angiv **SendGrid API-nøglen** [SendGrid API-nøgle](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Angiv dit **[SendGrid-liste-id](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til SendGrid.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Næste** for at konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurer connectoren

1. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. Gentag de samme trin for andre valgfrie felter, f.eks.. **Fornavn**, **Efternavn**, **Land/Område**, **Stat**, **By** og **Postnummer**.

1. Vælg de segmenter, du vil eksportere. Det **anbefales ikke at eksportere mere end 100.000 kundeprofiler i alt** til SendGrid. 

1. Vælg **Gem**.

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 100.000 profiler i alt til SendGrid.
- Eksport til SendGrid er begrænset til segmenter.
- Det kan tage op til et par timer at eksportere op til 100.000 profiler til SendGrid. 
- Antallet af profiler, du kan eksportere til SendGrid, er afhængige og begrænsede i kontrakten med SendGrid.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til SendGrid, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks.. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at SendGrid overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]