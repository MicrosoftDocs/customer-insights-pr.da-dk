---
title: Eksportere Customer Insights-data til Azure Data Lake Storage Gen2
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477172"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="fb036-103">Connector til Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="fb036-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="fb036-104">Gem dine Customer Insights-data i Azure Data Lake Storage Gen2, eller brug dem til at overføre dine data til andre programmer.</span><span class="sxs-lookup"><span data-stu-id="fb036-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="fb036-105">Konfiguration af connectoren til Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="fb036-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="fb036-106">Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="fb036-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fb036-107">Under **Azure Data Lake Storage Gen2** skal du vælge **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="fb036-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="fb036-108">Giv din destination et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="fb036-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="fb036-109">Angiv **Firmanavn**, **Firmanøgle** og **Beholder** til Din Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="fb036-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="fb036-110">Du kan få mere at vide om, hvordan du opretter en lagerkonto, der skal bruges sammen med Azure Data Lake Storage Gen2, under [Oprette lagerkonto](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="fb036-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="fb036-111">Du kan få mere at vide om, hvordan du finder Azure Data Lake Gen2-lagerkontonavnet og kontonøglen, under [Administrere indstillinger for lagerkonti i Azure-portalen](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="fb036-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="fb036-112">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="fb036-112">Select **Next**.</span></span>

1. <span data-ttu-id="fb036-113">Markér afkrydsningsfeltet ud for hvert af de objekter, du vil eksportere til denne destination.</span><span class="sxs-lookup"><span data-stu-id="fb036-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="fb036-114">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="fb036-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="fb036-115">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="fb036-115">Export the data</span></span>

<span data-ttu-id="fb036-116">Du kan [eksportere data efter behov](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fb036-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="fb036-117">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fb036-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
