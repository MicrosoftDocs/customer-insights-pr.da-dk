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
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="055f6-103">Connector til Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="055f6-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="055f6-104">Gem dine Customer Insights-data i Azure Data Lake Storage Gen2, eller brug dem til at overføre dine data til andre programmer.</span><span class="sxs-lookup"><span data-stu-id="055f6-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="055f6-105">Konfiguration af connectoren til Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="055f6-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="055f6-106">Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="055f6-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="055f6-107">Under **Azure Data Lake Storage Gen2** skal du vælge **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="055f6-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="055f6-108">Giv din destination et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="055f6-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="055f6-109">Angiv **Firmanavn**, **Firmanøgle** og **Beholder** til Din Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="055f6-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="055f6-110">Du kan få mere at vide om, hvordan du opretter en lagerkonto, der skal bruges sammen med Azure Data Lake Storage Gen2, under [Oprette lagerkonto](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="055f6-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="055f6-111">Du kan få mere at vide om, hvordan du finder Azure Data Lake Gen2-lagerkontonavnet og kontonøglen, under [Administrere indstillinger for lagerkonti i Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="055f6-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="055f6-112">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="055f6-112">Select **Next**.</span></span>

1. <span data-ttu-id="055f6-113">Markér afkrydsningsfeltet ud for hvert af de objekter, du vil eksportere til denne destination.</span><span class="sxs-lookup"><span data-stu-id="055f6-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="055f6-114">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="055f6-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="055f6-115">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="055f6-115">Export the data</span></span>

<span data-ttu-id="055f6-116">Du kan [eksportere data efter behov](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="055f6-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="055f6-117">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="055f6-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>