---
title: Eksportere Customer Insights-data til Azure Data Lake Storage Gen2
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596630"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Connector til Azure Data Lake Storage Gen2

Gem dine Customer Insights-data i Azure Data Lake Storage Gen2, eller brug dem til at overføre dine data til andre programmer.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Konfiguration af connectoren til Azure Data Lake Storage Gen2

1. Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.

1. Under **Azure Data Lake Storage Gen2** skal du vælge **Konfigurer**.

1. Giv din destination et genkendeligt navn i feltet **Vist navn**.

1. Angiv **Firmanavn**, **Firmanøgle** og **Beholder** til Din Azure Data Lake Storage Gen2.
    - Du kan få mere at vide om, hvordan du opretter en lagerkonto, der skal bruges sammen med Azure Data Lake Storage Gen2, under [Oprette lagerkonto](/azure/storage/blobs/create-data-lake-storage-account). 
    - Du kan få mere at vide om, hvordan du finder Azure Data Lake Gen2-lagerkontonavnet og kontonøglen, under [Administrere indstillinger for lagerkonti i Azure-portalen](/azure/storage/common/storage-account-manage).

1. Vælg **Næste**.

1. Markér afkrydsningsfeltet ud for hvert af de objekter, du vil eksportere til denne destination.

1. Vælg **Gem**.

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md#export-data-on-demand). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).