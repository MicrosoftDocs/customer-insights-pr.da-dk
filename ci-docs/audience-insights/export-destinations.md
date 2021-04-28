---
title: Eksportere data fra Customer Insights
description: Administrer dataeksport til at dele data.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896136"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="871fb-103">Eksportoversigt (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="871fb-103">Exports (preview) overview</span></span>

<span data-ttu-id="871fb-104">På siden **Eksport** vises alle de konfigurerede eksporter.</span><span class="sxs-lookup"><span data-stu-id="871fb-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="871fb-105">Eksporter deler specifikke data med forskellige programmer.</span><span class="sxs-lookup"><span data-stu-id="871fb-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="871fb-106">De kan omfatte kundeprofiler eller objekter, skemaer og tilknytningsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="871fb-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="871fb-107">Hver eksport kræver en [forbindelse, konfigureret af en administrator, til at administrere godkendelse og adgang](connections.md).</span><span class="sxs-lookup"><span data-stu-id="871fb-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="871fb-108">Indtil marts 2021 oprettede eksporten automatisk en forbindelse til den tilknyttede tjeneste.</span><span class="sxs-lookup"><span data-stu-id="871fb-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="871fb-109">Eksporter kræver nu en [forbindelse, der er oprettet og delt af en administrator](connections.md), før du kan oprette dem.</span><span class="sxs-lookup"><span data-stu-id="871fb-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="871fb-110">Gå til **Data** > **Eksport** for at få vist eksportsiden.</span><span class="sxs-lookup"><span data-stu-id="871fb-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="871fb-111">Alle brugerroller har adgang til at få vist konfigurerede eksporter.</span><span class="sxs-lookup"><span data-stu-id="871fb-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="871fb-112">Brug af søgefeltet på kommandolinjen til at søge efter eksporter efter navn, forbindelsesnavn eller forbindelsestype.</span><span class="sxs-lookup"><span data-stu-id="871fb-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="871fb-113">Konfigurer en ny eksport</span><span class="sxs-lookup"><span data-stu-id="871fb-113">Set up a new export</span></span>

<span data-ttu-id="871fb-114">Hvis du vil konfigurere eller redigere en eksport, skal du have tilgængelige forbindelser.</span><span class="sxs-lookup"><span data-stu-id="871fb-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="871fb-115">Forbindelser afhænger af [brugerrollen](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="871fb-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="871fb-116">Administratorer har adgang til alle forbindelser.</span><span class="sxs-lookup"><span data-stu-id="871fb-116">Administrators have access to all connections.</span></span> <span data-ttu-id="871fb-117">De kan også oprette nye forbindelser, når en eksport konfigureres.</span><span class="sxs-lookup"><span data-stu-id="871fb-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="871fb-118">Bidragydere kan have adgang til bestemte forbindelser.</span><span class="sxs-lookup"><span data-stu-id="871fb-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="871fb-119">De er afhængige af administratorer, når de skal konfigurere og dele forbindelser.</span><span class="sxs-lookup"><span data-stu-id="871fb-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="871fb-120">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="871fb-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="871fb-121">Fremvisere kan kun få vist eksisterende eksporter, men ikke oprette dem.</span><span class="sxs-lookup"><span data-stu-id="871fb-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="871fb-122">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="871fb-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="871fb-123">Vælg **Tilføj eksport** for at oprette en ny eksport destination.</span><span class="sxs-lookup"><span data-stu-id="871fb-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="871fb-124">Vælg, hvilken forbindelse du vil bruge, i ruden **Konfigurer eksport**.</span><span class="sxs-lookup"><span data-stu-id="871fb-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="871fb-125">[Forbindelser](connections.md) administreres af administratorer.</span><span class="sxs-lookup"><span data-stu-id="871fb-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="871fb-126">Angiv de nødvendige oplysninger, og vælg **Gem** for at oprette eksporten.</span><span class="sxs-lookup"><span data-stu-id="871fb-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="871fb-127">Rediger en eksport</span><span class="sxs-lookup"><span data-stu-id="871fb-127">Edit an export</span></span>

1. <span data-ttu-id="871fb-128">Vælg den lodrette ellipse for den eksportdestination, du vil redigere.</span><span class="sxs-lookup"><span data-stu-id="871fb-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="871fb-129">Vælg **Rediger** fra rullemenuen.</span><span class="sxs-lookup"><span data-stu-id="871fb-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="871fb-130">Opdatér de værdier, du vil opdatere, og vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="871fb-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="871fb-131">Få vist eksport- og eksportdetaljer</span><span class="sxs-lookup"><span data-stu-id="871fb-131">View Exports and export details</span></span>

<span data-ttu-id="871fb-132">Når du har oprettet eksportmål, vises de under **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="871fb-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="871fb-133">Alle brugere kan se, hvilke data der deles, og den seneste status.</span><span class="sxs-lookup"><span data-stu-id="871fb-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="871fb-134">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="871fb-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="871fb-135">Brugere uden redigeringstilladelser vælger **Vis** i stedet for **Rediger**, og se eksportdetaljerne.</span><span class="sxs-lookup"><span data-stu-id="871fb-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="871fb-136">I denne siderude vises opsætningen af denne eksport.</span><span class="sxs-lookup"><span data-stu-id="871fb-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="871fb-137">Uden redigeringstilladelser kan du ikke ændre værdier.</span><span class="sxs-lookup"><span data-stu-id="871fb-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="871fb-138">Vælg **Luk** for at vende tilbage til eksportsiden.</span><span class="sxs-lookup"><span data-stu-id="871fb-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="871fb-139">Kør eksporter efter behov</span><span class="sxs-lookup"><span data-stu-id="871fb-139">Run exports on demand</span></span>

<span data-ttu-id="871fb-140">Når du har konfigureret en eksport, køres den med alle [planlagte opdateringer](system.md#schedule-tab), så længe den har en arbejdsforbindelse.</span><span class="sxs-lookup"><span data-stu-id="871fb-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="871fb-141">Hvis du vil eksportere data uden at vente på en planlagt opdatering, skal du gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="871fb-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="871fb-142">Du har to muligheder:</span><span class="sxs-lookup"><span data-stu-id="871fb-142">You have two options:</span></span>

- <span data-ttu-id="871fb-143">Hvis du vil køre alle eksporter, skal du vælge **Kør alle** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="871fb-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="871fb-144">Hvis du vil køre en enkelt eksport, skal du vælge ellipsen (...) på et listeelement og derefter vælge **Kør**.</span><span class="sxs-lookup"><span data-stu-id="871fb-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="871fb-145">Fjerne en eksport</span><span class="sxs-lookup"><span data-stu-id="871fb-145">Remove an Export</span></span>

1. <span data-ttu-id="871fb-146">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="871fb-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="871fb-147">Vælg den lodrette ellipse for den eksportdestination, du vil fjerne.</span><span class="sxs-lookup"><span data-stu-id="871fb-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="871fb-148">Vælg **Fjern** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="871fb-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="871fb-149">Bekræft fjernelsen ved at vælge **Fjern** på bekræftelsesskærmen.</span><span class="sxs-lookup"><span data-stu-id="871fb-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
