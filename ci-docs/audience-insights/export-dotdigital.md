---
title: Eksportér Customer Insights-data til DotDigital
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269093"
---
# <a name="connector-for-dotdigital-preview"></a>Connector til DotDigital (prøveversion)

Eksportér segmenter af Unified-kundeprofiler til DotDigital-adressekartotekerne, og brug dem til kampagner, e-mailmarketing og til at oprette kundesegmenter med DotDigital. 

## <a name="prerequisites"></a>Forudsætninger

-   Du har en [DotDigital-konto](https://dotdigital.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Der findes eksisterende adressekartoteker i DotDigital og de tilsvarende id'er. Id kan findes i URL-adressen, når du vælger og åbner et adressekartotek. Du kan finde flere oplysninger i [DotDigital-adressekartoteker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="connect-to-dotdigital"></a>Opret forbindelse til DotDigital

1. Gå til **Adminstration** > **Eksportdestinationer**.

1. Under **DotDigital** skal du vælge **Konfigurer**.

1. Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfigurationsrude til DotDigital-eksport.":::

1. Angiv **DotDigital-brugernavn og adgangskode**.

1. Angiv dit **[DotDigital-adressekartoteks-id](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til DotDigital.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Næste** for at konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurer connectoren

1. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. Gentag de samme trin for andre valgfrie felter, f. eks. **fornavn**, **Efternavn**, **Fulde navn**, **Køn** og **Postnummer**.

1. Vælg de segmenter, du vil eksportere. Du kan eksportere op til 1 million kundeprofiler i alt til DotDigital.

1. Vælg **Gem**.

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab). I DotDigital kan du nu finde dine segmenter i [DotDigital-adressekartoteker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 1 million profiler pr. eksport til DotDigital.
- Eksport til DotDigital er begrænset til segmenter.
- Eksport af segmenter med det samlede antal 1 million profiler kan tage op til tre timer på grund af begrænsninger på udbydersiden. 
- Antallet af profiler, du kan eksportere til DotDigital, er afhængige og begrænsede i kontrakten med DotDigital.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til DotDigital, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at DotDigital overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]