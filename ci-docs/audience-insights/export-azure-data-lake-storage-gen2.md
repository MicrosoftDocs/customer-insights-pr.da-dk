---
title: Eksportere Customer Insights-data til Azure Data Lake Storage Gen2
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 934c396559d4c4be8e640917d2265805753eb62d
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605896"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Eksportere segmentliste og andre data til Azure Data Lake Storage Gen2 (forhåndsversion)

Gem dine Customer Insights-data i en Data Lake Storage Gen2-konto, eller brug den til at overføre dine data til andre programmer.

## <a name="known-limitations"></a>Kendte begrænsninger

1. Til Azure Data Lake Storage Gen2 kan du vælge mellem [Standardydeevne og Premium-ydeevne som niveau](/azure/storage/blobs/create-data-lake-storage-account), når du opretter en lagerkonto til din datasø. Hvis du vælger Premium-ydeevneniveau, skal du vælge Premium-blok-blobbe som kontotype. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Konfigurere forbindelsen til Azure Data Lake Storage Gen2 


1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Azure Data Lake Gen 2** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv **Firmanavn**, **Firmanøgle** og **Beholder** til Din Azure Data Lake Storage Gen2.
    - Du kan få mere at vide om, hvordan du opretter en lagerkonto, der skal bruges sammen med Azure Data Lake Storage Gen2, under [Oprette lagerkonto](/azure/storage/blobs/create-data-lake-storage-account). 
    - Du kan få mere at vide om Azure Data Lake Gen2-lagerkontonavnet og kontonøglen i [Administration af indstillinger for lagerkonti i Azure-portalen](/azure/storage/common/storage-account-manage).

1. Vælg **Gem** for at fuldføre forbindelsen. 

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Hvis du vil oprette en ny eksport, skal du vælge **Tilføj eksport**.

1. I feltet **Forbindelse til eksport** skal du vælge en forbindelse fra sektionen i sektionen **Azure Data Lake**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Markér afkrydsningsfeltet ud for hvert af de objekter, du vil eksportere til denne destination.

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 

Eksporterede data lagres i den Azure Data Lake Gen 2-lagerbeholder, du har konfigureret. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
