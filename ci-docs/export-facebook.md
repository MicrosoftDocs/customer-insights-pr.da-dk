---
title: Eksportér segmenter til Facebook Ads Manager (forhåndsversion) (indeholder video)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195007"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Eksportér segmenter til Facebook Ads Manager (forhåndsversion)

Eksportér segmenter af samlede kundeprofiler til Facebook Annonceadministrator for at oprette kampagner på Facebook og Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Forudsætninger

- En [Facebook-reklamekonto](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), der omfatter en [Facebook -virksomhedskonto](https://business.facebook.com/).
- Administratorrettigheder til [Facebook-reklamekonto](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 10 million kundeprofiler pr. eksport til Facebook-reklameadministrator, og det kan tage op til 90 minutter at fuldføre den.
- Kun segmenter.
- Kun Facebook *‑kundelistetypen* i [brugerdefinerede](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) målgrupper.
  > [!NOTE]
  > I visse tilfælde kan du se brugerdefinerede målgrupper af forskellige typer på rullelisten. Hvis du vælger en anden type end *kundeliste*, lykkes eksporten ikke.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Konfigurer forbindelse til Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Facebook Ads Manager**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Godkend med Facebook Ads:

   1. Vælg **Fortsæt med Facebook** for at logge på din Facebook Ads-konto.

   1. Tillad **ads_management**-tilladelsen, efter at de er godkendt i Facebook.

   1. Vælg den **Facebook-annoncekonto**, du vil arbejde med.

   1. Vælg en **Eksisterende brugerdefineret målgruppe** på rullelisten, eller opret en **Ny brugerdefineret målgruppe**.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Facebook Ads Manager i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Brug feltet **Tilslut data** til at vælge **Mail**, **Navn og adresse** eller **Telefon**, du vil sende til Facebook Annonceadministrator.

1. Tilknyt de tilsvarende attributter fra det samlede kundeobjekt til den valgte nøgle-identifikator.
   > [!TIP]
   > De bedste chancer for et match sker, hvis du vælger **Mail** som nøgleidentifikator. Tilføjelse af flere identifikatorer kan forbedre matchningen.

1. Vælg **Tilføj attribut** for at tilknytte flere attributter, der skal sendes til Facebook Ads Manager. Attributter fra Facebook Ads Manager tilknyttes følgende brugervenlige navne: **FN** = **Fornavn**, **LN** = **Efternavn**, **FI** = **Første initial**, **PHONE** = **Telefon**, **GEN** = **Køn**, **DOB** = **Fødselsdato**, **ST** = **Stat**, **CT** = **By**, **ZIP** = **Postnummer**, **LAND** = **Land/område**

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
