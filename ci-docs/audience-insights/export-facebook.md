---
title: Eksportér Customer Insights-data til Facebook Ads Manager
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Facebook Annonceadministrator.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269967"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Connector til Facebook Annonceadministrator (prøveversion)

Eksportér segmenter af samlede kundeprofiler til Facebook Annonceadministrator for at oprette kampagner på Facebook og Instagram.

## <a name="prerequisites"></a>Forudsætninger

- Du skal have en [**Facebook-reklamekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), der indeholder en [**Facebook-forretningskonto**](https://business.facebook.com/).
- Du skal være administrator for [**Facebook-reklamekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Opret forbindelse til Facebook Annonceadministrator

1. Gå til **Adminstration** > **Eksportdestinationer**.

1. Vælg **Konfigurer** under **Facebook Annonceadministrator**.

1. Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.

1. Vælg **Fortsæt med Facebook** for at logge på din Facebook-annoncekonto.

1. Tillad **ads_management**-tilladelsen, efter at de er godkendt i Facebook.

1. Vælg den **Facebook-annoncekonto**, du vil arbejde med.

1. Vælg en **Eksisterende brugerdefineret målgruppe** på rullelisten, eller opret en **Ny brugerdefineret målgruppe**. Du kan finde flere oplysninger under [**Målgrupper i Facebook Annonceadministrator**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Næste** for at konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurer connectoren

1. Brug feltet **Vælg din nøgleidentifikator** til at vælge **Mail**, **Navn og adresse** eller **Telefon**, du vil sende til Facebook Annonceadministrator.

1. Tilknyt de tilsvarende attributter fra det samlede kundeobjekt til den valgte nøgle-identifikator.
   > [TIP] De bedste chancer for et match sker, hvis du vælger **Mail** som nøgleidentifikator. Tilføjelse af flere identifikatorer kan forbedre matchningen.

1. Vælg **Tilføj attribut** for at tilknytte flere attributter, der skal sendes til Facebook Annonceadministrator. Attributter fra Facebook Annonceadministrator tilknyttes følgende brugervenlige navne: **FN** = **Fornavn**, **LN** = **Efternavn**, **FI** = **Første initial**, **PHONE** = **Telefon**, **GEN** = **Køn**, **DOB** = **Fødselsdato**, **ST** = **Stat**, **CT** = **By**, **ZIP** = **Postnummer**, **COUNTRY** = **Land/område**

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 10 millioner kundeprofiler pr. eksport til Facebook Ads Manager 
- Eksport til Facebook Ads Manager er begrænset til segmenter.
- Eksport af segmenter med i alt 10 millioner profiler kan tage op til 90 minutter at fuldføre

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Facebook Ads Manager, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Facebook-reklamer overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]