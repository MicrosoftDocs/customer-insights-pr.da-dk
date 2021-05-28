---
title: Eksportér Customer Insights-data til et Azure Blob Storage
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Blob Storage.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976127"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="0fb99-103">Eksport af segmentliste og andre data til Azure Blob Storage (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="0fb99-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="0fb99-104">Gem dine Customer Insights-data i Blob Storage, eller brug dem til at overføre dine data til andre programmer.</span><span class="sxs-lookup"><span data-stu-id="0fb99-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="0fb99-105">Konfigurer forbindelsen til Blob Storage</span><span class="sxs-lookup"><span data-stu-id="0fb99-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="0fb99-106">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="0fb99-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0fb99-107">Vælg **Tilføj forbindelse**, og vælg **Azure Blob Storage** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="0fb99-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="0fb99-108">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="0fb99-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0fb99-109">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="0fb99-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0fb99-110">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="0fb99-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0fb99-111">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="0fb99-111">Choose who can use this connection.</span></span> <span data-ttu-id="0fb99-112">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="0fb99-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0fb99-113">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0fb99-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0fb99-114">Angiv **Kontonavn**, **Kontonøgle** og **Beholder** for Blob Storage-kontoen.</span><span class="sxs-lookup"><span data-stu-id="0fb99-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="0fb99-115">Du kan få mere at vide om, hvordan du finder Blob storage-kontonavnet og kontonøglen, under [Administration af indstillinger for lagerkonti i Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="0fb99-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="0fb99-116">Du kan få mere at vide om, hvordan du opretter en objektbeholder, i [Oprette en objektbeholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="0fb99-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="0fb99-117">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="0fb99-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="0fb99-118">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="0fb99-118">Configure an export</span></span>

<span data-ttu-id="0fb99-119">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="0fb99-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0fb99-120">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0fb99-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0fb99-121">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="0fb99-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0fb99-122">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="0fb99-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0fb99-123">Vælg en forbindelse i sektionen Azure Blob Storage i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="0fb99-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="0fb99-124">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="0fb99-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0fb99-125">Markér afkrydsningsfeltet ud for hvert af de objekter, du vil eksportere til denne destination.</span><span class="sxs-lookup"><span data-stu-id="0fb99-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="0fb99-126">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="0fb99-126">Select **Save**.</span></span>

<span data-ttu-id="0fb99-127">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="0fb99-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0fb99-128">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0fb99-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="0fb99-129">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0fb99-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="0fb99-130">Eksporterede data lagres i den Blob Storage-beholder, du har konfigureret.</span><span class="sxs-lookup"><span data-stu-id="0fb99-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="0fb99-131">Følgende mappestier oprettes automatisk i objektbeholderen:</span><span class="sxs-lookup"><span data-stu-id="0fb99-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="0fb99-132">For kildeobjekter og objekter, der er oprettet af systemet: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="0fb99-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="0fb99-133">Eksempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="0fb99-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="0fb99-134">Model.json for de eksporterede objekter vil være på niveau med %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="0fb99-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="0fb99-135">Eksempel: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="0fb99-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
