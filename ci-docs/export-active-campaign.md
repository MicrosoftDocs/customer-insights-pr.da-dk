---
title: Eksportér segmenter til ActiveCampaign
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725393"
---
# <a name="export-segments-to-activecampaign-preview"></a>Eksporter segmenter til ActiveCampaign (forhåndsversion)

Eksporter segmenter af samlede kundeprofiler til ActiveCampaign, og brug dem til marketingaktiviteter.

## <a name="prerequisites"></a>Forudsætninger

- En [ActiveCampaign-konto](https://www.activecampaign.com/) og tilsvarende administratorlegitimationsoplysninger.
- En [ActiveCampaign-liste id](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- En [ActiveCampaign API-nøgle](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) og REST slutpunkt Hostname.
- [Konfigurerede segmenter](segments.md) i Customer Insights.
- Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Private Link i kombination med BYOS (Bring your own storage) understøttes ikke.
- Du kan eksportere op til 1 million kundeprofiler pr. eksport til ActiveCampaign, og det kan tage op til 90 minutter at fuldføre den. Antallet af kundeprofiler, du kan eksportere til ActiveCampaign, afhænger af din kontrakt med ActiveCampaign.
- Kun segmenter.

## <a name="set-up-connection-to-activecampaign"></a>Konfigurer forbindelsen til ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **ActiveCampaign**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv din ActiveCampaign API-nøgle og REST slutpunkt Hostname. Værtsnavn for REST-slutpunkt er kun værtsnavnet uden https://.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen ActiveCampaign i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Angiv din **ActiveCampaign List ID**.

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**.

1. Du kan også eksportere **Fornavn**, **Efternavn** og **Telefon** for at oprette mere personlige e-mails. Vælg **Tilføj attribut** for at tilknytte disse felter.

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
