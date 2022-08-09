---
title: Eksportere data til en Azure Blob Storage (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Blob Storage.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195697"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Eksportere data til en Azure Blob Storage (forhåndsversion)

Gem dine Customer Insights-data i Blob Storage, eller brug dem til at overføre dine data til andre programmer.

## <a name="prerequisites"></a>Forudsætninger

- Et [Azure Blob Storage-kontonavn](/azure/storage/blobs/create-data-lake-storage-account) og en kontonøgle. Du kan finde flere oplysninger i [Administrere lagerkontoindstillinger i Azure-portalen](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage-forbindelse](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Kendte begrænsninger

- Til Azure Blob Storage kan du vælge mellem [Standardydeevne og Premium-ydeevne som niveau](/azure/storage/blobs/storage-blob-performance-tiers). Hvis du vælger Premium-ydeevneniveau, skal du vælge [Premium-blok-blobbe som kontotype](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Konfigurer forbindelsen til Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse,** og vælg **Azure Blob Storage**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv **Kontonavn**, **Kontonøgle** og **Beholder** for Blob Storage-kontoen.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Hvis du vil konfigurere denne eksport, skal du have [tilladelse](export-destinations.md#set-up-a-new-export) til denne forbindelsestype.

> [!IMPORTANT]
> Hvis du har aktiveret indstillingen for [blød sletning](/azure/storage/blobs/soft-delete-blob-enable) for Azure Blob Storage-kontoen, mislykkes eksporten. Slå blød sletning fra for at eksportere data til blobs.

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Azure Blob Storage i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Angiv mappenavnet til Blob Storage.

1. Markér afkrydsningsfeltet ud for hvert af de objekter, du vil eksportere til denne destination.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Eksporterede data lagres i den Blob Storage-beholder, du har konfigureret. Følgende mappestier oprettes automatisk i objektbeholderen:

- For kildeobjekter og objekter, der er oprettet af systemet:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Eksport af objekter, der indeholder en stor mængde data, kan føre til flere CSV-filer i den samme mappe for hver eksport. Opdeling af eksport sker af ydelseshensyn for at minimere den tid, det tager at udføre en eksport.

- Filen model.json for de eksporterede objekter findes på *%ExportDestinationName%*-niveau.  
  
  Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
