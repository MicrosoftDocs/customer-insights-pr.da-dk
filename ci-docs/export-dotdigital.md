---
title: Eksporter segmenter til DotDigital (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724979"
---
# <a name="export-segments-to-dotdigital-preview"></a>Eksporter segmenter til DotDigital (forhåndsversion)

Eksportér segmenter af Unified-kundeprofiler til DotDigital-adressekartotekerne, og brug dem til kampagner, e-mailmarketing og til at oprette kundesegmenter med DotDigital.

## <a name="prerequisites"></a>Forudsætninger

- En [DotDigital-konto](https://dotdigital.com/) og har oprettet en [API-bruger](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Et DotDigital-id fra et [nyt](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) eller eksisterende adressekartotek i DotDigital. Id kan findes i URL-adressen, når du vælger og åbner et adressekartotek.
- [Konfigurerede segmenter](segments.md) i Customer Insights.
- Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Private Link i kombination med BYOS (Bring your own storage) understøttes ikke.
- Op til 1 millioner kundeprofiler pr. eksport til DotDigital, som kan tage op til tre timer at fuldføre på grund af begrænsninger på udbydersiden. Antallet af kundeprofiler, du kan eksportere til DotDigital, afhænger af din kontrakt med DotDigital.
- Kun segmenter.

## <a name="set-up-connection-to-dotdigital"></a>Konfigurer forbindelsen til DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **DotDigital**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv **DotDigital API-brugernavn og -adgangskode**.

1. Angiv dit **DotDigital-adressekartoteks-id**.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen DotDigital i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**.

1. Du kan også eksportere **Fornavn**, **Efternavn**, **Fulde navn**, **Køn** og **Postnummer**.

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

I DotDigital kan du finde dine segmenter i [DotDigital-adressekartoteker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
