---
title: Eksportér Customer Insights-data til DotDigital
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759952"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a>Eksport af segmentlister til DotDigital (forhåndsversion)

Eksportér segmenter af Unified-kundeprofiler til DotDigital-adressekartotekerne, og brug dem til kampagner, e-mailmarketing og til at oprette kundesegmenter med DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Forudsætninger for en forbindelse

-   Du har en [DotDigital-konto](https://dotdigital.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Der findes eksisterende adressekartoteker i DotDigital og de tilsvarende id'er. Id kan findes i URL-adressen, når du vælger og åbner et adressekartotek. Du kan finde flere oplysninger i [DotDigital-adressekartoteker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 1 million profiler pr. eksport til DotDigital.
- Eksport til DotDigital er begrænset til segmenter.
- Eksport af segmenter med det samlede antal 1 million profiler kan tage op til tre timer på grund af begrænsninger på udbydersiden. 
- Antallet af profiler, du kan eksportere til DotDigital, er afhængige og begrænsede i kontrakten med DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Konfigurer forbindelsen til DotDigital

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **DotDigital** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv **DotDigital-brugernavn og adgangskode**.

1. Angiv dit **[DotDigital-adressekartoteks-id](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til DotDigital.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen. 

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen DotDigital i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.


1. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. Gentag de samme trin for andre valgfrie felter, f. eks. **fornavn**, **Efternavn**, **Fulde navn**, **Køn** og **Postnummer**.

1. Vælg de segmenter, du vil eksportere. Du kan eksportere op til 1 million kundeprofiler i alt til DotDigital.

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 
 
I DotDigital kan du nu finde dine segmenter i [DotDigital-adressekartoteker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til DotDigital, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at DotDigital overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
