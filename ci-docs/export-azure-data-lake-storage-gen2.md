---
title: Eksportere data til Azure Data Lake Storage Gen2 (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196433"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Eksportere data til Azure Data Lake Storage Gen2 (forhåndsversion)

Gem dine Customer Insights-data i en Data Lake Storage Gen2-konto, eller brug den til at overføre dine data til andre programmer.

## <a name="prerequisites"></a>Forudsætninger

- En [lagerkonto, der skal bruges sammen med Azure Data Lake Gen 2](/azure/storage/blobs/create-data-lake-storage-account). Du kan finde lagerkontonavn og nøgle i [Administrere lagerkontoindstillinger i Azure-portalen](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage-forbindelse](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Kendte begrænsninger

- Til Azure Data Lake Storage Gen2 kan du vælge mellem [Standardydeevne og Premium-ydeevne som niveau](/azure/storage/blobs/create-data-lake-storage-account). Hvis du vælger Premium-ydeevneniveau, skal du vælge [Premium-blok-blobbe som kontotype](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Konfigurere forbindelsen til Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Azure Data Lake Gen 2**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv **Firmanavn**, **Firmanøgle** og **Beholder** til Din Azure Data Lake Storage Gen2.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. I feltet **Forbindelse til eksport** skal du vælge en forbindelse fra sektionen i sektionen Azure Data Lake. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Angiv mappenavnet til Azure Data Lake Storage Gen2-lager.

1. Markér afkrydsningsfeltet ud for hvert af de objekter, du vil eksportere til denne destination.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Eksporterede data lagres i den Azure Data Lake Gen 2-lagerbeholder, du har konfigureret.

> [!TIP]
> Eksport af objekter, der indeholder en stor mængde data, kan føre til flere CSV-filer i den samme mappe for hver eksport. Opdeling af eksport sker af ydelseshensyn for at minimere den tid, det tager at udføre en eksport.

[!INCLUDE [footer-include](includes/footer-banner.md)]
