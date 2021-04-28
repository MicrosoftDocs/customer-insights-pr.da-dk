---
title: Eksportere Customer Insights-data til Azure Data Lake Storage Gen2
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760044"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="1940e-103">Konfigurer forbindelsen til Azure Data Lake Storage Gen 2 (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="1940e-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="1940e-104">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="1940e-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1940e-105">Vælg **Tilføj forbindelse**, og vælg **Azure Data Lake Gen 2** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="1940e-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="1940e-106">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="1940e-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1940e-107">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="1940e-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1940e-108">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="1940e-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1940e-109">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="1940e-109">Choose who can use this connection.</span></span> <span data-ttu-id="1940e-110">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="1940e-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1940e-111">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1940e-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1940e-112">Angiv **Firmanavn**, **Firmanøgle** og **Beholder** til Din Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="1940e-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="1940e-113">Du kan få mere at vide om, hvordan du opretter en lagerkonto, der skal bruges sammen med Azure Data Lake Storage Gen2, under [Oprette lagerkonto](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="1940e-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="1940e-114">Du kan få mere at vide om Azure Data Lake Gen2-lagerkontonavnet og kontonøglen i [Administration af indstillinger for lagerkonti i Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1940e-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="1940e-115">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="1940e-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="1940e-116">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="1940e-116">Configure an export</span></span>

<span data-ttu-id="1940e-117">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="1940e-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1940e-118">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1940e-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1940e-119">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="1940e-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1940e-120">Hvis du vil oprette en ny eksport, skal du vælge **Tilføj eksport**.</span><span class="sxs-lookup"><span data-stu-id="1940e-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="1940e-121">I feltet **Forbindelse til eksport** skal du vælge en forbindelse fra sektionen i sektionen **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="1940e-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="1940e-122">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="1940e-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1940e-123">Markér afkrydsningsfeltet ud for hvert af de objekter, du vil eksportere til denne destination.</span><span class="sxs-lookup"><span data-stu-id="1940e-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="1940e-124">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="1940e-124">Select **Save**.</span></span>

<span data-ttu-id="1940e-125">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="1940e-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1940e-126">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1940e-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1940e-127">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1940e-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="1940e-128">Eksporterede data lagres i den Azure Data Lake Gen 2-lagerbeholder, du har konfigureret.</span><span class="sxs-lookup"><span data-stu-id="1940e-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
