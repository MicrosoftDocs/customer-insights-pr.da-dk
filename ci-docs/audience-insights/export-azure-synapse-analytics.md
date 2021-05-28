---
title: Eksportere Customer Insights-data til Azure Synapse Analytics
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977370"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="1a26f-103">Eksportere data til Azure Synapse Analytics (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="1a26f-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="1a26f-104">Azure Synapse er en analysetjeneste, der accelererer tiden til at få indsigt på tværs af data warehouses og big data-systemer.</span><span class="sxs-lookup"><span data-stu-id="1a26f-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="1a26f-105">Du kan indtage og bruge dine Customer Insights-data i [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="1a26f-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1a26f-106">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="1a26f-106">Prerequisites</span></span>

<span data-ttu-id="1a26f-107">Følgende forudsætninger skal være opfyldt for at konfigurere forbindelsen fra Customer Insights til Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="1a26f-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="1a26f-108">Sørg for at angive alle **rolletildelinger** som beskrevet.</span><span class="sxs-lookup"><span data-stu-id="1a26f-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="1a26f-109">Forudsætninger i Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1a26f-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="1a26f-110">Du har rollen som **Administrator** i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="1a26f-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="1a26f-111">Få mere at vide om [at angive brugertilladelser i målgruppeindsigt](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="1a26f-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="1a26f-112">I Azure:</span><span class="sxs-lookup"><span data-stu-id="1a26f-112">In Azure:</span></span> 

- <span data-ttu-id="1a26f-113">Et aktivt Azure-abonnement.</span><span class="sxs-lookup"><span data-stu-id="1a26f-113">An active Azure subscription.</span></span>

- <span data-ttu-id="1a26f-114">Hvis du bruger en ny Azure Data Lake Storage Gen2-konto, skal *tjenesteprincipal for målgruppeindsigt* have **Bidragyder til Storage Blob-data**-tilladelser.</span><span class="sxs-lookup"><span data-stu-id="1a26f-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="1a26f-115">Få mere at vide om [at oprette forbindelse til en Azure Data Lake Storage Gen2-konto med Azure-tjenesteprincipal for målgruppeindsigt](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="1a26f-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="1a26f-116">Data Lake Storage Gen2 **skal have** [hierarkisk navneområde](/azure/storage/blobs/data-lake-storage-namespace) aktiveret.</span><span class="sxs-lookup"><span data-stu-id="1a26f-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="1a26f-117">I ressourcegruppen er Azure Synapse-arbejdsområdet placeret, *tjenesteprincipalen* og *brugeren til målgruppeindsigt* skal tildeles mindst **Læser-** tilladelser.</span><span class="sxs-lookup"><span data-stu-id="1a26f-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="1a26f-118">Du kan finde flere oplysninger under [Tildele Azure-roller ved hjælp af Azure-portalen](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="1a26f-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="1a26f-119">*Brugeren* skal have **Bidragyder til Storage Blob-data**-tilladelser til den Azure Data Lake Storage Gen2-konto, hvor dataene er placeret og sammenkædet med Azure Synapse-arbejdsområdet.</span><span class="sxs-lookup"><span data-stu-id="1a26f-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="1a26f-120">Få mere at vide om at [bruge Azure-portalen til at tildele en Azure-rolle for at få adgang til BLOB- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [Bidragyder til Storage Blob-data-tilladelser](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="1a26f-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="1a26f-121">Den *[Azure Synapse-arbejdsområdestyrede identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* skal have **Bidragyder til Storage Blob-data**-tilladelser til den Azure Data Lake Storage Gen2-konto, hvor dataene er placeret og sammenkædet med Azure Synapse-arbejdsområdet.</span><span class="sxs-lookup"><span data-stu-id="1a26f-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="1a26f-122">Få mere at vide om at [bruge Azure-portalen til at tildele en Azure-rolle for at få adgang til BLOB- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [Bidragyder til Storage Blob-data-tilladelser](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="1a26f-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="1a26f-123">I Azure Synapse-arbejdsområdet skal *tjenesteprincipal for målgruppeindsigt* have tildelt en **Synapse-administrator**-rolle.</span><span class="sxs-lookup"><span data-stu-id="1a26f-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="1a26f-124">Du kan finde flere oplysninger i [Sådan konfigurerer du adgangskontrol til dit Synapse-arbejdsområde](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="1a26f-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="1a26f-125">Konfigurere forbindelsen og eksportere til Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="1a26f-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="1a26f-126">Konfiguration af en forbindelse</span><span class="sxs-lookup"><span data-stu-id="1a26f-126">Configure a connection</span></span>

1. <span data-ttu-id="1a26f-127">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="1a26f-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1a26f-128">Vælg **Tilføj forbindelse**, og vælg **Azure Synapse Analytics**, eller vælg **Konfigurer** i feltet **Azure Synapse Analytics** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="1a26f-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="1a26f-129">Giv din forbindelse et genkendeligt navn i feltet Vist navn.</span><span class="sxs-lookup"><span data-stu-id="1a26f-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="1a26f-130">Navnet og forbindelsestypen beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="1a26f-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="1a26f-131">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="1a26f-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1a26f-132">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="1a26f-132">Choose who can use this connection.</span></span> <span data-ttu-id="1a26f-133">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="1a26f-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1a26f-134">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1a26f-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1a26f-135">Vælg eller søg efter det abonnement, hvor du vil bruge Customer Insights-dataene.</span><span class="sxs-lookup"><span data-stu-id="1a26f-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="1a26f-136">Så snart et abonnement er valgt, kan du også vælge **Arbejdsområde**, **Lagerkonto** og **Container**.</span><span class="sxs-lookup"><span data-stu-id="1a26f-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="1a26f-137">Vælg **Gem** for at gemme forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="1a26f-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="1a26f-138">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="1a26f-138">Configure an export</span></span>

<span data-ttu-id="1a26f-139">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="1a26f-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1a26f-140">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1a26f-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1a26f-141">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="1a26f-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1a26f-142">Hvis du vil oprette en ny eksport, skal du vælge **Tilføj eksport**.</span><span class="sxs-lookup"><span data-stu-id="1a26f-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="1a26f-143">Vælg en forbindelse i feltet **Forbindelse til eksport** i sektionen **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="1a26f-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="1a26f-144">Hvis du ikke kan se dette sektionsnavn, er der ingen [forbindelser](connections.md) af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="1a26f-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="1a26f-145">Angiv et genkendeligt **Vist navn** til eksport og et **Databasenavn**.</span><span class="sxs-lookup"><span data-stu-id="1a26f-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="1a26f-146">Vælg, hvilke objekter du vil eksportere til Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="1a26f-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="1a26f-147">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="1a26f-147">Select **Save**.</span></span>

<span data-ttu-id="1a26f-148">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="1a26f-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1a26f-149">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1a26f-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1a26f-150">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1a26f-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="1a26f-151">Opdatere en eksport</span><span class="sxs-lookup"><span data-stu-id="1a26f-151">Update an export</span></span>

1. <span data-ttu-id="1a26f-152">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="1a26f-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1a26f-153">Vælg **Rediger** på den eksport, du vil opdatere.</span><span class="sxs-lookup"><span data-stu-id="1a26f-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="1a26f-154">**Tilføj** eller **Fjern** objekter fra valget.</span><span class="sxs-lookup"><span data-stu-id="1a26f-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="1a26f-155">Hvis objekter fjernes fra markeringen, slettes de ikke fra Synapse Analytics-databasen.</span><span class="sxs-lookup"><span data-stu-id="1a26f-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="1a26f-156">Fremtidige dataopdateringer opdaterer dog ikke de fjernede objekter i den pågældende database.</span><span class="sxs-lookup"><span data-stu-id="1a26f-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="1a26f-157">**Hvis du ændrer databasenavnet**, oprettes der en ny Synapse Analytics-database.</span><span class="sxs-lookup"><span data-stu-id="1a26f-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="1a26f-158">Databasen med det navn, der tidligere er konfigureret, modtager ingen opdateringer fremover.</span><span class="sxs-lookup"><span data-stu-id="1a26f-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
