---
title: Eksportér Customer Insights-data til Google Ads
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Google Ads.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d9a25af3913e755cccec745c532b35aef3cccf9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598240"
---
# <a name="connector-for-google-ads-preview"></a>Connector til Google Ads (prøveversion)

Eksportér segmenter af samlede kundeprofiler til Google Ads-målgruppelisten, og brug dem til at annoncere på Google Search, Gmail og YouTube og Google Display Network. 

## <a name="prerequisites"></a>Forudsætninger

-   Du har en [Google Ads-konto](https://ads.google.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Der findes eksisterende målgrupper i Google Ads og de tilsvarende id'er. Du kan finde flere oplysninger i [Google ads-målgrupper](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Du har [konfigureret segmenter](segments.md)
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse, fornavn og efternavn

## <a name="connect-to-google-ads"></a>Opret forbindelse til Google Ads

1. Gå til **Adminstration** > **Eksportdestinationer**.

1. Under **Google Ads** skal du vælge **Konfigurer**.

1. Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.

1. Angiv din **[Google Ads-kunde-id](https://support.google.com/google-ads/answer/1704344)**.

1. Angiv din **[Google Ads-godkendte udvikler-token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Angiv dit **[Google Ads-målgruppe-id](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**, og vælg **Opret forbindelse** for at initialisere forbindelsen til Google Ads.

1. Vælg **Godkendelse med Google Ads**, og angiv dine Google Ads-legitimationsoplysninger.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Eksportér skærmbilleder til Google Ads-forbindelse":::

1. Vælg **Næste** for at konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurer connectoren

1. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. Gentag de samme trin for felterne **Fornavn** og **Efternavn**.

1. Vælg de segmenter, du vil eksportere. Du kan eksportere op til 1000000 kundeprofiler i alt til Google Ads.

1. Vælg **Gem**.

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab). I Google Ads kan du nu finde dine segmenter under [Google Ads-målgrupper](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 1000000 profiler pr. eksport til Google Ads.
- Eksport til Google Ads er begrænset til segmenter.
- Eksport af segmenter med det samlede antal 1000000-profiler kan tage op til 5 minutter på grund af begrænsninger på udbydersiden. 
- Det kan tage op til 48 timer at foretage match ingen i Google Ads.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Google Ads, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Google Ads overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]