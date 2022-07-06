---
title: Eksportere Customer Insights-data til InMobi
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056537"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Eksportere segmentliste og andre data til InMobi (forhåndsversion)

Eksportér segmentlister eller andre data fra din forekomst af Customer Insights til [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Forudsætninger

1. Du har en [InMobi-konto](https://www.inmobi.com/) og administratorlegitimationsoplysninger.
1. Du har navnet på en Azure Blob-lagerkonto og den tilsvarende kontonøgle. Du kan finde flere oplysninger i [Administrere lagerkontoindstillinger i Azure-portalen](/azure/storage/common/storage-account-manage). Der er en beholder i lagerkontoen, som der skal eksporteres inMobi-data til. Du kan finde flere oplysninger i [Oprette en beholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi opretter en direkte forbindelse til dit Blob Storage og konfigurerer en automatisk import af dataene til InMobi. Kontakt InMobi-repræsentanten for at få sat processen i gang.

## <a name="known-limitations"></a>Kendte begrænsninger

1. Til Azure Blob Storage kan du vælge mellem [Standardydeevne og Premium-ydeevne som niveau](/azure/storage/blobs/storage-blob-performance-tiers). Hvis du vælger Premium-ydeevneniveau, skal du vælge [Premium-blok-blobbe som kontotype](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Konfigurere forbindelsen til Azure Blob Storage og konfigurere en eksport

1. Følg instruktionerne i at [konfigurere en forbindelse til dit Azure Blob Storage](export-azure-blob-storage.md).
2. Følg instruktionerne i at [konfigurere en eksport](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
