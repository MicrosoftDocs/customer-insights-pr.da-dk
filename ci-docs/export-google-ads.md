---
title: Eksport af segmenter til Google Ads (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b7f08936d7d90322cb4e62396a2961fe06273b76
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081173"
---
# <a name="export-segments-to-google-ads-preview"></a>Eksport af segmenter til Google Ads (forhåndsversion)

Eksporter segmenter af samlede kundeprofiler til en Liste over Google Ads-målgruppe, og brug dem til at annoncere på Google Søgning, Gmail, YouTube og Google Display Network. 


## <a name="prerequisites-for-connection"></a>Forudsætninger for forbindelse

-   Du har en [Google Ads-konto](https://ads.google.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Du opfylder kravene i [Politik for kundematch](https://support.google.com/adspolicy/answer/6299717).
-   Du opfylder kravene til [listestørrelser for re-marketing](https://support.google.com/google-ads/answer/7558048).
-   Du har [konfigureret segmenter](segments.md).
-   Ensartede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en mailadresse, en telefon, et mobil annoncør-id, et tredjepartsbruger-id eller en adresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Eksport til Google Ads er begrænset til segmenter.
- Eksport af segmenter med i alt 1 million kundeprofiler kan tage op til 30 minutter på grund af begrænsninger på udbydersiden. 
- Det kan tage op til 48 timer at foretage match ingen i Google Ads.

## <a name="set-up-connection-to-google-ads"></a>Konfigurer forbindelse til Google Ads

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Google Ads** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv din **[Google Ads-kunde-id](https://support.google.com/google-ads/answer/1704344)**.

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Godkendelse med Google Ads**, og angiv dine Google Ads-legitimationsoplysninger.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen. 

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen Google Ads i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen tilgængelige forbindelser af denne type.

1. Hvis du vil oprette en ny målgruppe, skal du lade Google Målgruppe-id være tomt. Vi opretter automatisk en ny målgruppe i din Google Ads-konto og bruger navnet på det eksporterede segment. Hvis du vil opdatere en eksisterende Google Ads-målgruppe, skal du angive dit [Google Ads-målgruppe-id](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. Vælg et eller flere datafelter, du vil eksportere, i sektionen **Datatilpasning**, og vælg det felt, der repræsenterer de tilsvarende datafelter i Customer Insights.

1. Vælg de segmenter, du vil eksportere. 

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). 

Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Google Ads, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Google Ads overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE [footer-include](includes/footer-banner.md)]
