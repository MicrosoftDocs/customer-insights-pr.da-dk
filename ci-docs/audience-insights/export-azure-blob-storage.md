---
title: Eksportér Customer Insights-data til et Azure Blob-lager
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Azure Blob Storage.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596170"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Connector til Azure Blob Storage (forhåndsvisning)

Gem dine Customer Insights-data i et Azure Blob-lager, eller brug dem til at overføre dine data til andre programmer.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfigurer connector til Azure Blob Storage

1. Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.

1. Under **Azure Blob Storage** vælg **Konfigurer**.

1. Angiv **Firmanavn**, **Kontonøgle** og **Beholder** til din Azure Blob Storage-konto.
    - Du kan få mere at vide om, hvordan du finder navnet på og kontonøglen til Azure Blob Storage-kontoen, under [Administrere indstillinger for lagerkonto i Azure-portalen](/azure/storage/common/storage-account-manage).
    - Du kan få mere at vide om, hvordan du opretter en objektbeholder, i [Oprette en objektbeholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Giv din destination et genkendeligt navn i feltet **Vist navn**.

1. Vælg **Næste**.

1. Markér afkrydsningsfeltet ud for hvert af de objekter, du vil eksportere til denne destination.

1. Vælg **Gem**.

Eksporterede data gemmes i den Azure Blob Storage-beholder, du har konfigureret. Følgende mappestier oprettes automatisk i objektbeholderen:

- For kildeobjekter og objekter, der er oprettet af systemet: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Eksempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Filen model.json for de eksporterede objekter findes på %ExportDestinationName%-niveau
  - Eksempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md#export-data-on-demand). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]