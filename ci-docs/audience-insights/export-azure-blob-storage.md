---
title: Eksportér Customer Insights-data til et Azure Blob Storage
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Blob Storage.
ms.date: 06/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e38fc06a948178fcbc62c08a4cf4816e1d030e79
ms.sourcegitcommit: 656b1a6cdff37ba4f808311fd0327ab38e02ed13
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/30/2021
ms.locfileid: "6318292"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Eksport af segmentliste og andre data til Azure Blob Storage (forhåndsversion)

Gem dine Customer Insights-data i Blob Storage, eller brug dem til at overføre dine data til andre programmer.

## <a name="set-up-the-connection-to-blob-storage"></a>Konfigurer forbindelsen til Blob Storage

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Azure Blob Storage** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv **Kontonavn**, **Kontonøgle** og **Beholder** for Blob Storage-kontoen.
    - Du kan få mere at vide om, hvordan du finder Blob Storage-kontonavnet og kontonøglen, under [Administration af indstillinger for lagerkonti i Azure-portalen](/azure/storage/common/storage-account-manage).
    - Du kan få mere at vide om, hvordan du opretter en objektbeholder, i [Oprette en objektbeholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Vælg **Gem** for at fuldføre forbindelsen. 

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Hvis du har aktiveret indstillingen for blød sletning for Azure Blob Storage-kontoen, mislykkes eksporten. Slå blød sletning fra for at eksportere data til blobs. Yderligere oplysninger finder du i [Aktiver blød blob-sletning](/azure/storage/blobs/soft-delete-blob-enable.md)

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen Azure Blob Storage i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen tilgængelige forbindelser af denne type.

1. Markér afkrydsningsfeltet ud for hvert af de objekter, du vil eksportere til denne destination.

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).     

Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 

Eksporterede data lagres i den Blob Storage-beholder, du har konfigureret. Følgende mappestier oprettes automatisk i objektbeholderen:

- For kildeobjekter og objekter, der er oprettet af systemet:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Eksempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- Model.json for de eksporterede objekter vil være på niveau med %ExportDestinationName%.  
  - Eksempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
