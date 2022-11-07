---
title: Eksportér segmenter til Marketo (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724933"
---
# <a name="export-segments-to-marketo-preview"></a>Eksportér segmenter til Marketo (forhåndsversion)

Eksportér segmenter fra de samlede brugerprofiler til at generere kampagner, levere e-mailmarketing og bruge bestemte grupper af kunder med Marketo.

## <a name="prerequisites"></a>Forudsætninger

- En [Marketo-konto](https://login.marketo.com/) og tilsvarende administratorlegitimationsoplysninger.
- En [Marketo-klient-ID, klientens hemmelige og REST værtsnavnsslutpunkt](https://developers.marketo.com/rest-api/authentication/).
- [Der findes eksisterende lister i Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) og de tilsvarende id'er.
- [Konfigurerede segmenter](segments.md).
- Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Private Link i kombination med BYOS (Bring your own storage) understøttes ikke.
- Op til 1 million kundeprofiler pr. eksport til Marketo, og det kan tage op til 3 timer at fuldføre den. Antallet af kundeprofiler, du kan eksportere til Marketo, afhænger af din kontrakt med Marketo.
- Kun segmenter.

## <a name="set-up-connection-to-marketo"></a>Konfigurer forbindelsen til Marketo.

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Marketo**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv dit **Marketo-klient-ID, klienthemmelighed og REST værtsnavnsslutpunkt**. Værtsnavn for REST-slutpunkt er kun værtsnavnet uden https://. Eksempel: xyz-abc-123.mktorest.com.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Marketo i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Angiv dit **Marketo list ID**. Liste-id'et er en rent numerisk værdi. Hvis f.eks. Marketo-liste-id'et er ST12345A7, skal du fjerne tegnet før og efter tallene og angive *12345*.

1. Vælg mindst et felt, der repræsenterer en kundes e-mail-adresse eller en kundes Marketo-id, i sektionen **Datamatchning**.

1. Du kan også eksportere **Fornavn**, **Efternavn**, **By**, **Land** og **Land/Område** for at oprette mere personlige mails. Vælg **Tilføj attribut** for at tilknytte disse felter.

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

I Marketo kan du nu finde dine segmenter under [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
