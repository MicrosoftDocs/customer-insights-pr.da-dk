---
title: Eksportér Customer Insights-data til Google Ads
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976311"
---
# <a name="export-segments-to-google-ads-preview"></a>Eksport af segmenter til Google Ads (forhåndsversion)

Eksportér segmenter af samlede kundeprofiler til Google Ads-målgruppelisten, og brug dem til at annoncere på Google Search, Gmail og YouTube og Google Display Network. 

## <a name="prerequisites-for-connection"></a>Forudsætninger for forbindelse

-   Du har en [Google Ads-konto](https://ads.google.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Du har et [godkendt Google Ads-udviklertoken](https://developers.google.com/google-ads/api/docs/first-call/dev-token) 
-   Du opfylder kravene i [politikken for kundeoverensstemmelse](https://support.google.com/adspolicy/answer/6299717)
-   Du opfylder kravene til [listestørrelser for re-marketing](https://support.google.com/google-ads/answer/7558048) 

-   Der findes eksisterende målgrupper i Google Ads og de tilsvarende id'er. Du kan finde flere oplysninger i [Google ads-målgrupper](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Du har [konfigureret segmenter](segments.md)
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse, fornavn og efternavn

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 1000000 profiler pr. eksport til Google Ads.
- Eksport til Google Ads er begrænset til segmenter.
- Eksport af segmenter med det samlede antal 1000000-profiler kan tage op til 5 minutter på grund af begrænsninger på udbydersiden. 
- Det kan tage op til 48 timer at foretage match ingen i Google Ads.

## <a name="set-up-connection-to-google-ads"></a>Konfigurer forbindelse til Google Ads

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Google Ads** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv din **[Google Ads-kunde-id](https://support.google.com/google-ads/answer/1704344)**.

1. Angiv din **[Google Ads-godkendte udvikler-token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Godkendelse med Google Ads**, og angiv dine Google Ads-legitimationsoplysninger.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen. 

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen Google Ads i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Angiv dit **[Google Ads-målgruppe-id](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**, og vælg **Opret forbindelse** for at initialisere forbindelsen til Google Ads.

1. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. Gentag de samme trin for felterne **Fornavn** og **Efternavn**.

1. Vælg de segmenter, du vil eksportere. Du kan eksportere op til 1000000 kundeprofiler i alt til Google Ads.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Google Ads, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Google Ads overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
