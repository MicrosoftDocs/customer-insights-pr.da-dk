---
title: Eksportere data fra Customer Insights
description: Administrer dataeksport til at dele data.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016607"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="c6c0b-103">Eksportoversigt (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="c6c0b-103">Exports (preview) overview</span></span>

<span data-ttu-id="c6c0b-104">På siden **Eksport** vises alle de konfigurerede eksporter.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="c6c0b-105">Eksporter deler specifikke data med forskellige programmer.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="c6c0b-106">De kan omfatte kundeprofiler eller objekter, skemaer og tilknytningsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="c6c0b-107">Hver eksport kræver en [forbindelse, konfigureret af en administrator, til at administrere godkendelse og adgang](connections.md).</span><span class="sxs-lookup"><span data-stu-id="c6c0b-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="c6c0b-108">Gå til **Data** > **Eksport** for at få vist eksportsiden.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="c6c0b-109">Alle brugerroller har adgang til at få vist konfigurerede eksporter.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="c6c0b-110">Brug af søgefeltet på kommandolinjen til at søge efter eksporter efter navn, forbindelsesnavn eller forbindelsestype.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="c6c0b-111">Konfigurer en ny eksport</span><span class="sxs-lookup"><span data-stu-id="c6c0b-111">Set up a new export</span></span>

<span data-ttu-id="c6c0b-112">Hvis du vil konfigurere eller redigere en eksport, skal du have tilgængelige forbindelser.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="c6c0b-113">Forbindelser afhænger af [brugerrollen](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="c6c0b-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="c6c0b-114">Administratorer har adgang til alle forbindelser.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-114">Administrators have access to all connections.</span></span> <span data-ttu-id="c6c0b-115">De kan også oprette nye forbindelser, når en eksport konfigureres.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="c6c0b-116">Bidragydere kan have adgang til bestemte forbindelser.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="c6c0b-117">De er afhængige af administratorer, når de skal konfigurere og dele forbindelser.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="c6c0b-118">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c6c0b-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="c6c0b-119">Fremvisere kan kun få vist eksisterende eksporter, men ikke oprette dem.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="c6c0b-120">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c6c0b-121">Vælg **Tilføj eksport** for at oprette en ny eksport destination.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="c6c0b-122">Vælg, hvilken forbindelse du vil bruge, i ruden **Konfigurer eksport**.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="c6c0b-123">[Forbindelser](connections.md) administreres af administratorer.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="c6c0b-124">Angiv de nødvendige oplysninger, og vælg **Gem** for at oprette eksporten.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="c6c0b-125">Rediger en eksport</span><span class="sxs-lookup"><span data-stu-id="c6c0b-125">Edit an export</span></span>

1. <span data-ttu-id="c6c0b-126">Vælg den lodrette ellipse for den eksportdestination, du vil redigere.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="c6c0b-127">Vælg **Rediger** fra rullemenuen.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="c6c0b-128">Opdatér de værdier, du vil opdatere, og vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="c6c0b-129">Få vist eksport- og eksportdetaljer</span><span class="sxs-lookup"><span data-stu-id="c6c0b-129">View Exports and export details</span></span>

<span data-ttu-id="c6c0b-130">Når du har oprettet eksportmål, vises de under **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="c6c0b-131">Alle brugere kan se, hvilke data der deles, og den seneste status.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="c6c0b-132">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c6c0b-133">Brugere uden redigeringstilladelser vælger **Vis** i stedet for **Rediger**, og se eksportdetaljerne.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="c6c0b-134">I denne siderude vises opsætningen af denne eksport.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="c6c0b-135">Uden redigeringstilladelser kan du ikke ændre værdier.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="c6c0b-136">Vælg **Luk** for at vende tilbage til eksportsiden.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="c6c0b-137">Kør eksporter efter behov</span><span class="sxs-lookup"><span data-stu-id="c6c0b-137">Run exports on demand</span></span>

<span data-ttu-id="c6c0b-138">Når du har konfigureret en eksport, køres den med alle [planlagte opdateringer](system.md#schedule-tab), så længe den har en arbejdsforbindelse.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="c6c0b-139">Hvis du vil eksportere data uden at vente på en planlagt opdatering, skal du gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="c6c0b-140">Du har to muligheder:</span><span class="sxs-lookup"><span data-stu-id="c6c0b-140">You have two options:</span></span>

- <span data-ttu-id="c6c0b-141">Hvis du vil køre alle eksporter, skal du vælge **Kør alle** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="c6c0b-142">Hvis du vil køre en enkelt eksport, skal du vælge ellipsen (...) på et listeelement og derefter vælge **Kør**.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="c6c0b-143">Fjerne en eksport</span><span class="sxs-lookup"><span data-stu-id="c6c0b-143">Remove an Export</span></span>

1. <span data-ttu-id="c6c0b-144">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c6c0b-145">Vælg den lodrette ellipse for den eksportdestination, du vil fjerne.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="c6c0b-146">Vælg **Fjern** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="c6c0b-147">Bekræft fjernelsen ved at vælge **Fjern** på bekræftelsesskærmen.</span><span class="sxs-lookup"><span data-stu-id="c6c0b-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
