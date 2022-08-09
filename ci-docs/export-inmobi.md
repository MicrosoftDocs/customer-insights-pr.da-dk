---
title: Eksportere Customer Insights-data til InMobi
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195881"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Eksportere Customer Insights-data til InMobi (forhåndsversion)

Eksportér segmentlister eller andre data fra din forekomst af Customer Insights til [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Forudsætninger

- En [InMobi-konto](https://www.inmobi.com/) og administratorlegitimationsoplysninger.
- Et [Azure Blob Storage-kontonavn](/azure/storage/blobs/create-data-lake-storage-account) og en kontonøgle. Du kan finde flere oplysninger i [Administrere lagerkontoindstillinger i Azure-portalen](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage-beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) til eksport af InMobi-data.
- InMobi opretter en direkte forbindelse til dit Blob Storage og konfigurerer en automatisk import af dataene til InMobi. Kontakt InMobi-repræsentanten for at få sat processen i gang.

## <a name="known-limitations"></a>Kendte begrænsninger

- Til Azure Blob Storage kan du vælge mellem [Standardydeevne og Premium-ydeevne som niveau](/azure/storage/blobs/storage-blob-performance-tiers). Hvis du vælger Premium-ydeevneniveau, skal du vælge [Premium-blok-blobbe som kontotype](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Konfigurer forbindelsen til Azure Blob Storage

[Konfigurer forbindelsen til din Azure Blob Storage](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Konfigurere en eksport

[Konfigurere en eksport](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
