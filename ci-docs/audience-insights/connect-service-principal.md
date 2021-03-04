---
title: Opret forbindelse til en Azure Data Lake Storage Gen2-konto med en tjenestekonto
description: Brug en Azure-tjenestekonto til at få målgruppeindsigt for at oprette forbindelse til dine egen Data Lake, når du vedhæfter den til målgruppeindsigt.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267715"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="d33d3-103">Opret forbindelse til en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekonto for at få målgruppeindsigt</span><span class="sxs-lookup"><span data-stu-id="d33d3-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="d33d3-104">Automatiserede værktøjer, der bruger Azure-tjenester, bør altid have begrænsede tilladelser.</span><span class="sxs-lookup"><span data-stu-id="d33d3-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="d33d3-105">I stedet for at have programmer til at logge på som bruger med fuld administratorrettigheder, tilbyder Azure tjenestekonti.</span><span class="sxs-lookup"><span data-stu-id="d33d3-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="d33d3-106">Læs videre for at få mere at vide om, hvordan du opretter forbindelse til målgruppeindsigt med en Azure Data Lake Storage Gen2-konto ved hjælp af en Azure-tjenestekonto i stedet for lagerkontonøgler.</span><span class="sxs-lookup"><span data-stu-id="d33d3-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="d33d3-107">Du kan bruge tjenestekontoen til at [tilføje eller redigere en Common Data Model-mappe på en sikker måde som datakilde](connect-common-data-model.md) eller [oprette nye eller opdatere et eksisterende miljø](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="d33d3-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="d33d3-108">Azure Data Lake Gen2-lagerkontoen, hvor tjenestens hovednavn skal bruges, skal have [aktiveret HNS (hierarkisk navneplads)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="d33d3-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="d33d3-109">Du skal have administratorrettigheder til dit Azure-abonnement for at oprette tjenestekonto.</span><span class="sxs-lookup"><span data-stu-id="d33d3-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="d33d3-110">Opret Azure-tjenestekonto til målgruppeindsigt</span><span class="sxs-lookup"><span data-stu-id="d33d3-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="d33d3-111">Før du opretter en ny tjenestekonto til målgruppeindsigt, skal du kontrollere, om den allerede findes i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d33d3-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="d33d3-112">Søge efter en eksisterende tjenestekonto</span><span class="sxs-lookup"><span data-stu-id="d33d3-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="d33d3-113">Gå til [Azure Admin-portalen](https://portal.azure.com), og log på organisationen.</span><span class="sxs-lookup"><span data-stu-id="d33d3-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="d33d3-114">Vælg **Azure Active Directory** mellem Azure-tjenesterne.</span><span class="sxs-lookup"><span data-stu-id="d33d3-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="d33d3-115">Vælg **Administrer** under **Virksomhedsprogrammer**.</span><span class="sxs-lookup"><span data-stu-id="d33d3-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="d33d3-116">Søg efter målgruppeindsigt i program-ID for første part `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` eller navn `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="d33d3-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="d33d3-117">Hvis du finder en tilsvarende post, betyder det, at der findes en tjenestekonto til målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="d33d3-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="d33d3-118">Du behøver ikke at oprette igen.</span><span class="sxs-lookup"><span data-stu-id="d33d3-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skærmbillede, der viser den eksisterende tjenestekonto.":::
   
6. <span data-ttu-id="d33d3-120">Hvis der ikke returneres resultater, skal du oprette en ny tjenestekonto.</span><span class="sxs-lookup"><span data-stu-id="d33d3-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="d33d3-121">Opret en ny tjenestekonto</span><span class="sxs-lookup"><span data-stu-id="d33d3-121">Create a new service principal</span></span>

1. <span data-ttu-id="d33d3-122">Installer den nyeste version af **Azure Active Directory PowerShell til Graph**.</span><span class="sxs-lookup"><span data-stu-id="d33d3-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="d33d3-123">Du kan finde flere oplysninger i [Installation af Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="d33d3-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="d33d3-124">Vælg Windows-tasten på tastaturet i din PC, og søg efter **Windows PowerShell**, og **Kør som administrator**.</span><span class="sxs-lookup"><span data-stu-id="d33d3-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="d33d3-125">I det PowerShell-vindue, der åbnes, skal du skrive `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="d33d3-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="d33d3-126">Opret tjenestekonto til målgruppeindsigt i Azure AD PowerShell-modulet.</span><span class="sxs-lookup"><span data-stu-id="d33d3-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="d33d3-127">I det PowerShell-vindue, der åbnes, skal du skrive `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="d33d3-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="d33d3-128">Erstat "dit lejer-ID" med det faktiske ID for din lejer, hvor du vil oprette tjenestekonto.</span><span class="sxs-lookup"><span data-stu-id="d33d3-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="d33d3-129">Valgfrit navn for miljøet `AzureEnvironmentName`.</span><span class="sxs-lookup"><span data-stu-id="d33d3-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="d33d3-130">Angiv `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="d33d3-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="d33d3-131">Denne kommando opretter tjenestekontoen for at få målgruppeindsigt i den valgte lejer.</span><span class="sxs-lookup"><span data-stu-id="d33d3-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="d33d3-132">Giv tilladelser til den pågældende tjenestekonto for at få adgang til lagerkontoen</span><span class="sxs-lookup"><span data-stu-id="d33d3-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="d33d3-133">Gå til Azure-portalen for at give tilladelser til tjenestekontoen for den lagerkonto, du vil bruge i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="d33d3-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="d33d3-134">Gå til [Azure Admin-portalen](https://portal.azure.com), og log på organisationen.</span><span class="sxs-lookup"><span data-stu-id="d33d3-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="d33d3-135">Åbn den lagerkonto, som du vil have målgruppeindsigt i for at få adgang.</span><span class="sxs-lookup"><span data-stu-id="d33d3-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="d33d3-136">Vælg **Adgangskontrol (IAM)** i navigationsruden, og vælg **Tilføj** > **Tilføj rolletildeling**.</span><span class="sxs-lookup"><span data-stu-id="d33d3-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skærmbillede, der viser Azure-portalen under tilføjelse af en rolletildeling.":::
   
1. <span data-ttu-id="d33d3-138">I ruden **Tilføj rolletildeling** skal du angive følgende egenskaber:</span><span class="sxs-lookup"><span data-stu-id="d33d3-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="d33d3-139">Rolle: *Storage Blob Data-bidragyder*</span><span class="sxs-lookup"><span data-stu-id="d33d3-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="d33d3-140">Tildel adgang til: *bruger, gruppe eller tjenestekonto*</span><span class="sxs-lookup"><span data-stu-id="d33d3-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="d33d3-141">Vælg: *Dynamics 365 AI for Customer Insights* (den [tjenestekonto, du har oprettet](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="d33d3-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="d33d3-142">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="d33d3-142">Select **Save**.</span></span>

<span data-ttu-id="d33d3-143">Det kan tage op til 15 minutter at overføre ændringerne.</span><span class="sxs-lookup"><span data-stu-id="d33d3-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="d33d3-144">Angiv Azure Resource-id eller Azure-abonnementsoplysningerne i lagerkontoen for den vedhæftede målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="d33d3-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="d33d3-145">Vedhæft en Azure Data Lake-lagerkonto i målgruppeindsigter for at [gemme outputdata](manage-environments.md) eller [bruge det som en datakilde](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="d33d3-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="d33d3-146">Hvis du vælger indstillingen Azure Data Lake, kan du vælge mellem en ressourcebaseret eller en abonnementsbaseret metode.</span><span class="sxs-lookup"><span data-stu-id="d33d3-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="d33d3-147">Følg nedenstående fremgangsmåde for at angive de nødvendige oplysninger om den valgte fremgangsmåde.</span><span class="sxs-lookup"><span data-stu-id="d33d3-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="d33d3-148">Ressourcebaseret forbindelse til lagerkonto</span><span class="sxs-lookup"><span data-stu-id="d33d3-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="d33d3-149">Gå til [Azure Admin-portalen](https://portal.azure.com), log på dit abonnement, og åbn lagerkontoen.</span><span class="sxs-lookup"><span data-stu-id="d33d3-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="d33d3-150">Gå til **Indstillinger** > **Egenskaber** i navigationsrude.</span><span class="sxs-lookup"><span data-stu-id="d33d3-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="d33d3-151">Kopiér værdien for ressource-ID for lagerkontoen.</span><span class="sxs-lookup"><span data-stu-id="d33d3-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopiér ressource-ID for lagerkontoen.":::

1. <span data-ttu-id="d33d3-153">I målgruppeindsigt skal du indsætte ressource-id i det ressourcefelt, der vises på skærmen med lagerkontoforbindelsen.</span><span class="sxs-lookup"><span data-stu-id="d33d3-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Angiv oplysninger om ressource-ID for lagerkontoen.":::   
   
1. <span data-ttu-id="d33d3-155">Fortsæt med de resterende trin i målgruppeindsigt for at tilknytte lagerkontoen.</span><span class="sxs-lookup"><span data-stu-id="d33d3-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="d33d3-156">Abonnementbaseret forbindelse til lagerkonto</span><span class="sxs-lookup"><span data-stu-id="d33d3-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="d33d3-157">Gå til [Azure Admin-portalen](https://portal.azure.com), log på dit abonnement, og åbn lagerkontoen.</span><span class="sxs-lookup"><span data-stu-id="d33d3-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="d33d3-158">Gå til **Indstillinger** > **Egenskaber** i navigationsrude.</span><span class="sxs-lookup"><span data-stu-id="d33d3-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="d33d3-159">Gennemse **Abonnement**, **Ressourcegruppe** og **Navn** på lagerkontoen for at sikre dig, at du vælger de rigtige værdier i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="d33d3-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="d33d3-160">I målgruppeindsigt kan du vælge værdier eller for de tilsvarende felter, når du tilknytter lagerkontoen.</span><span class="sxs-lookup"><span data-stu-id="d33d3-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="d33d3-161">Fortsæt med de resterende trin i målgruppeindsigt for at tilknytte lagerkontoen.</span><span class="sxs-lookup"><span data-stu-id="d33d3-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]