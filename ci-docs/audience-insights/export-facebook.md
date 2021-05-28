---
title: Eksportér Customer Insights-data til Facebook Ads Manager
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976035"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Eksport af segmentliste til Facebook Ads Manager (forhåndsversion)

Eksportér segmenter af samlede kundeprofiler til Facebook Annonceadministrator for at oprette kampagner på Facebook og Instagram.

## <a name="prerequisites-for-connection"></a>Forudsætninger for forbindelse

- Du skal have en [**Facebook-reklamekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), der omfatter en [**Facebook-forretningskonto**](https://business.facebook.com/).
- Du skal være administrator for [**Facebook-reklamekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 10 millioner kundeprofiler pr. eksport til Facebook Ads Manager.
- Eksport til Facebook Ads Manager er begrænset til segmenter.
- Opret eller opdater kun brugerdefinerede målgrupper Facebook af typen *kundeliste*.
- Eksport af segmenter med i alt 10 millioner profiler kan tage op til 90 minutter at fuldføre.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Konfigurer forbindelse til Facebook Ads Manager

Før brugere kan oprette en eksport, skal administrator konfigurere forbindelsen til tjenesten og tillade bidragydere at bruge forbindelsen.

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Facebook Ads Manager** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden **Administratorer**. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Godkend med Facebook Ads: 

   1. Vælg **Fortsæt med Facebook** for at logge på din Facebook-annoncekonto.

   1. Tillad **ads_management**-tilladelsen, efter at de er godkendt i Facebook.

   1. Vælg den **Facebook-annoncekonto**, du vil arbejde med.

   1. Vælg en **Eksisterende brugerdefineret målgruppe** på rullelisten, eller opret en **Ny brugerdefineret målgruppe**. Du kan finde flere oplysninger under [**Målgrupper i Facebook Annonceadministrator**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Du kan kun oprette eller opdatere brugerdefinerede målgrupper for Facebook med typen *kundeliste*, der har denne eksport. I visse tilfælde kan du se brugerdefinerede målgrupper af forskellige typer på rullelisten. Hvis du vælger en anden type *kundeliste*, lykkes eksporten ikke. 

1. Gennemse **Beskyttelse af personlige data og overholdelse af angivne standarder**, og vælg **Jeg accepterer**.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport. 

1. Vælg i **Forbindelse til eksport** en forbindelse i sektionen **Facebook Ads Manager**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Brug feltet **Vælg din nøgleidentifikator** til at vælge **Mail**, **Navn og adresse** eller **Telefon**, du vil sende til Facebook Annonceadministrator. 

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.

1. Tilknyt de tilsvarende attributter fra det samlede kundeobjekt til den valgte nøgle-identifikator.
   > [TIP] De bedste chancer for et match sker, hvis du vælger **Mail** som nøgleidentifikator. Tilføjelse af flere identifikatorer kan forbedre matchningen.

1. Vælg **Tilføj attribut** for at tilknytte flere attributter, der skal sendes til Facebook Ads Manager. Attributter fra Facebook Ads Manager tilknyttes følgende brugervenlige navne: **FN** = **Fornavn**, **LN** = **Efternavn**, **FI** = **Første initial**, **PHONE** = **Telefon**, **GEN** = **Køn**, **DOB** = **Fødselsdato**, **ST** = **Stat**, **CT** = **By**, **ZIP** = **Postnummer**, **COUNTRY** = **Land/område**

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Facebook Ads Manager, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Facebook-reklamer overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
