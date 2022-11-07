---
title: Eksportér segmenter til SendGrid (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724841"
---
# <a name="export-segments-to-sendgrid-preview"></a>Eksportér segmenter til SendGrid (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til SendGrid-kontaktlister, og brug dem til kampagner og mailmarketing i SendGrid.

## <a name="prerequisites"></a>Forudsætninger

- En [SendGrid-konto](https://sendgrid.com/) og tilsvarende administratorlegitimationsoplysninger.
- [Eksisterende kontaktlister i SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) og tilhørende id'er.
- En [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Konfigurerede segmenter](segments.md) i Customer Insights.
- Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Private Link i kombination med BYOS (Bring your own storage) understøttes ikke.
- Det kan tage op til et par timer at eksportere op til 100.000 kundeprofiler til SendGrid. Antallet af kundeprofiler, du kan eksportere til SendGrid, afhænger af din kontrakt med SendGrid.
- Kun segmenter.

## <a name="set-up-connection-to-sendgrid"></a>Konfigurer forbindelsen til SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **SendGrid**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv **SendGrid-API-nøglen**.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen SendGrid i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Angiv dit **SendGrid liste-ID**.

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**.

1. Du kan også vælge felter, f.eks.. **Fornavn**, **Efternavn**, **Land/Område**, **Stat**, **By** og **Postnummer**.

1. Vælg de segmenter, der skal eksporteres med følgende kendte begrænsninger.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
