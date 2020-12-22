---
title: Opret forbindelse til en Azure Data Lake Storage Gen2-konto med en tjenestekonto
description: Brug en Azure-tjenestekonto til at få målgruppeindsigt for at oprette forbindelse til dine egen Data Lake, når du vedhæfter den til målgruppeindsigt.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644081"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="d79b5-103">Opret forbindelse til en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekonto for at få målgruppeindsigt</span><span class="sxs-lookup"><span data-stu-id="d79b5-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="d79b5-104">Automatiserede værktøjer, der bruger Azure-tjenester, bør altid have begrænsede tilladelser.</span><span class="sxs-lookup"><span data-stu-id="d79b5-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="d79b5-105">I stedet for at have programmer til at logge på som bruger med fuld administratorrettigheder, tilbyder Azure tjenestekonti.</span><span class="sxs-lookup"><span data-stu-id="d79b5-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="d79b5-106">Læs videre for at få mere at vide om, hvordan du opretter forbindelse til målgruppeindsigt med en Azure Data Lake Storage Gen2-konto ved hjælp af en Azure-tjenestekonto i stedet for lagerkontonøgler.</span><span class="sxs-lookup"><span data-stu-id="d79b5-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="d79b5-107">Du kan bruge tjenestekontoen til at [tilføje eller redigere en Common Data Model-mappe på en sikker måde som datakilde](connect-common-data-model.md) eller [oprette nye eller opdatere et eksisterende miljø](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="d79b5-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="d79b5-108">Du skal have administratorrettigheder til dit Azure-abonnement for at oprette tjenestekonto.</span><span class="sxs-lookup"><span data-stu-id="d79b5-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="d79b5-109">Opret Azure-tjenestekonto til målgruppeindsigt</span><span class="sxs-lookup"><span data-stu-id="d79b5-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="d79b5-110">Før du opretter en ny tjenestekonto til målgruppeindsigt, skal du kontrollere, om den allerede findes i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d79b5-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="d79b5-111">Søge efter en eksisterende tjenestekonto</span><span class="sxs-lookup"><span data-stu-id="d79b5-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="d79b5-112">Gå til [Azure Admin-portalen](https://portal.azure.com), og log på organisationen.</span><span class="sxs-lookup"><span data-stu-id="d79b5-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="d79b5-113">Vælg **Azure Active Directory** mellem Azure-tjenesterne.</span><span class="sxs-lookup"><span data-stu-id="d79b5-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="d79b5-114">Vælg **Administrer** under **Virksomhedsprogrammer**.</span><span class="sxs-lookup"><span data-stu-id="d79b5-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="d79b5-115">Søg efter målgruppeindsigt i program-ID for første part `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` eller navn `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="d79b5-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="d79b5-116">Hvis du finder en tilsvarende post, betyder det, at der findes en tjenestekonto til målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="d79b5-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="d79b5-117">Du behøver ikke at oprette igen.</span><span class="sxs-lookup"><span data-stu-id="d79b5-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skærmbillede, der viser den eksisterende tjenestekonto.":::
   
6. <span data-ttu-id="d79b5-119">Hvis der ikke returneres resultater, skal du oprette en ny tjenestekonto.</span><span class="sxs-lookup"><span data-stu-id="d79b5-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="d79b5-120">Opret en ny tjenestekonto</span><span class="sxs-lookup"><span data-stu-id="d79b5-120">Create a new service principal</span></span>

1. <span data-ttu-id="d79b5-121">Installer den nyeste version af **Azure Active Directory PowerShell til Graph**.</span><span class="sxs-lookup"><span data-stu-id="d79b5-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="d79b5-122">Du kan finde flere oplysninger i [Installation af Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="d79b5-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="d79b5-123">Vælg Windows-tasten på tastaturet i din PC, og søg efter **Windows PowerShell**, og **Kør som administrator**.</span><span class="sxs-lookup"><span data-stu-id="d79b5-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="d79b5-124">I det PowerShell-vindue, der åbnes, skal du skrive `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="d79b5-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="d79b5-125">Opret tjenestekonto til målgruppeindsigt i Azure AD PowerShell-modulet.</span><span class="sxs-lookup"><span data-stu-id="d79b5-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="d79b5-126">I det PowerShell-vindue, der åbnes, skal du skrive `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="d79b5-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="d79b5-127">Erstat "dit lejer-ID" med det faktiske ID for din lejer, hvor du vil oprette tjenestekonto.</span><span class="sxs-lookup"><span data-stu-id="d79b5-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="d79b5-128">Valgfrit navn for miljøet `AzureEnvironmentName`.</span><span class="sxs-lookup"><span data-stu-id="d79b5-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="d79b5-129">Angiv `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="d79b5-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="d79b5-130">Denne kommando opretter tjenestekontoen for at få målgruppeindsigt i den valgte lejer.</span><span class="sxs-lookup"><span data-stu-id="d79b5-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="d79b5-131">Giv tilladelser til den pågældende tjenestekonto for at få adgang til lagerkontoen</span><span class="sxs-lookup"><span data-stu-id="d79b5-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="d79b5-132">Gå til Azure-portalen for at give tilladelser til tjenestekontoen for den lagerkonto, du vil bruge i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="d79b5-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="d79b5-133">Gå til [Azure Admin-portalen](https://portal.azure.com), og log på organisationen.</span><span class="sxs-lookup"><span data-stu-id="d79b5-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="d79b5-134">Åbn den lagerkonto, som du vil have målgruppeindsigt i for at få adgang.</span><span class="sxs-lookup"><span data-stu-id="d79b5-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="d79b5-135">Vælg **Adgangskontrol (IAM)** i navigationsruden, og vælg **Tilføj** > **Tilføj rolletildeling**.</span><span class="sxs-lookup"><span data-stu-id="d79b5-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skærmbillede, der viser Azure-portalen under tilføjelse af en rolletildeling.":::
   
1. <span data-ttu-id="d79b5-137">I ruden **Tilføj rolletildeling** skal du angive følgende egenskaber:</span><span class="sxs-lookup"><span data-stu-id="d79b5-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="d79b5-138">Rolle: *Storage Blob Data-bidragyder*</span><span class="sxs-lookup"><span data-stu-id="d79b5-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="d79b5-139">Tildel adgang til: *bruger, gruppe eller tjenestekonto*</span><span class="sxs-lookup"><span data-stu-id="d79b5-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="d79b5-140">Vælg: *Dynamics 365 AI for Customer Insights* (den [tjenestekonto, du har oprettet](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="d79b5-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="d79b5-141">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="d79b5-141">Select **Save**.</span></span>

<span data-ttu-id="d79b5-142">Det kan tage op til 15 minutter at overføre ændringerne.</span><span class="sxs-lookup"><span data-stu-id="d79b5-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="d79b5-143">Angiv Azure Resource-id eller Azure-abonnementsoplysningerne i lagerkontoen for den vedhæftede målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="d79b5-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="d79b5-144">Vedhæft en Azure Data Lake-lagerkonto i målgruppeindsigter for at [gemme outputdata](manage-environments.md) eller [bruge det som en datakilde](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="d79b5-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="d79b5-145">Hvis du vælger indstillingen Azure Data Lake, kan du vælge mellem en ressourcebaseret eller en abonnementsbaseret metode.</span><span class="sxs-lookup"><span data-stu-id="d79b5-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="d79b5-146">Følg nedenstående fremgangsmåde for at angive de nødvendige oplysninger om den valgte fremgangsmåde.</span><span class="sxs-lookup"><span data-stu-id="d79b5-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="d79b5-147">Resourcebaseret forbindelse til lagerkonto</span><span class="sxs-lookup"><span data-stu-id="d79b5-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="d79b5-148">Gå til [Azure Admin-portalen](https://portal.azure.com), log på dit abonnement, og åbn lagerkontoen.</span><span class="sxs-lookup"><span data-stu-id="d79b5-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="d79b5-149">Gå til **Indstillinger** > **Egenskaber** i navigationsrude.</span><span class="sxs-lookup"><span data-stu-id="d79b5-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="d79b5-150">Kopiér værdien for ressource-ID for lagerkontoen.</span><span class="sxs-lookup"><span data-stu-id="d79b5-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopiér ressource-ID for lagerkontoen.":::

1. <span data-ttu-id="d79b5-152">I målgruppeindsigt skal du indsætte ressource-id i det ressourcefelt, der vises på skærmen med lagerkontoforbindelsen.</span><span class="sxs-lookup"><span data-stu-id="d79b5-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Angiv oplysninger om ressource-ID for lagerkontoen.":::   
   
1. <span data-ttu-id="d79b5-154">Fortsæt med de resterende trin i målgruppeindsigt for at tilknytte lagerkontoen.</span><span class="sxs-lookup"><span data-stu-id="d79b5-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="d79b5-155">Abonnementbaseret forbindelse til lagerkonto</span><span class="sxs-lookup"><span data-stu-id="d79b5-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="d79b5-156">Gå til [Azure Admin-portalen](https://portal.azure.com), log på dit abonnement, og åbn lagerkontoen.</span><span class="sxs-lookup"><span data-stu-id="d79b5-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="d79b5-157">Gå til **Indstillinger** > **Egenskaber** i navigationsrude.</span><span class="sxs-lookup"><span data-stu-id="d79b5-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="d79b5-158">Gennemse **Abonnement**, **Ressourcegruppe** og **Navn** på lagerkontoen for at sikre dig, at du vælger de rigtige værdier i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="d79b5-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="d79b5-159">I målgruppeindsigt kan du vælge værdier eller for de tilsvarende felter, når du tilknytter lagerkontoen.</span><span class="sxs-lookup"><span data-stu-id="d79b5-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Angiv oplysninger om ressource-ID for lagerkontoen.":::
   
1. <span data-ttu-id="d79b5-161">Fortsæt med de resterende trin i målgruppeindsigt for at tilknytte lagerkontoen.</span><span class="sxs-lookup"><span data-stu-id="d79b5-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
