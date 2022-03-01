---
title: Eksporter Customer Insights-data til ActiveCampaign
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314596"
---
# <a name="export-segments-to-activecampaign-preview"></a>Eksporter segmenter til ActiveCampaign (forhåndsversion)

Eksporter segmenter af samlede kundeprofiler til ActiveCampaign, og brug dem til marketingaktiviteter.

## <a name="prerequisites"></a>Forudsætninger

-   Du har en [ActiveCampaign-konto](https://www.activecampaign.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.
-   Samlede debitorprofiler i de eksporterede segmenter indeholder et felt med en mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Du kan eksportere op til 1 million profiler pr. eksport til ActiveCampaign, og det kan tage op til 90 minutter at gennemføre.
- Eksport til ActiveCampaign er begrænset til segmenter.
- Antallet af profiler, du kan eksportere til ActiveCampaign, afhænger af kontrakten med ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Konfigurer forbindelsen til ActiveCampaign

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **ActiveCampaign** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv din [ActiveCampaign API-nøgle og REST slutpunkt Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Værtsnavn for REST-slutpunkt er kun værtsnavnet uden https://. 

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til ActiveCampaign.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere en eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen ActiveCampaign i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Angiv din [**Id for ActiveCampaign-liste**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

3. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. Det kræves, at der eksporteres segmenter til ActiveCampaign. Du kan også eksportere Fornavn, Efternavn og Telefon for at oprette mere personlige e-mails. Vælg Tilføj attribut for at tilknytte disse felter.

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du gør det muligt for Dynamics 365 Customer Insights at overfører data til ActiveCampaign, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personlige data. Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at ActiveCampaign overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.
