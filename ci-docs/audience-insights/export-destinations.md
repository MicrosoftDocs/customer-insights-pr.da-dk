---
title: Eksportere data fra Customer Insights
description: Administrer dataeksport til at dele data.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305471"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="a8956-103">Eksportoversigt (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="a8956-103">Exports (preview) overview</span></span>

<span data-ttu-id="a8956-104">På siden **Eksport** vises alle de konfigurerede eksporter.</span><span class="sxs-lookup"><span data-stu-id="a8956-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="a8956-105">Eksporter deler specifikke data med forskellige programmer.</span><span class="sxs-lookup"><span data-stu-id="a8956-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="a8956-106">De kan omfatte kundeprofiler eller objekter, skemaer og tilknytningsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="a8956-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="a8956-107">Hver eksport kræver en [forbindelse, konfigureret af en administrator, til at administrere godkendelse og adgang](connections.md).</span><span class="sxs-lookup"><span data-stu-id="a8956-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="a8956-108">Gå til **Data** > **Eksport** for at få vist eksportsiden.</span><span class="sxs-lookup"><span data-stu-id="a8956-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="a8956-109">Alle brugerroller kan få vist konfigurerede eksporter.</span><span class="sxs-lookup"><span data-stu-id="a8956-109">All user roles can view configured exports.</span></span> <span data-ttu-id="a8956-110">Brug søgefeltet på kommandolinjen til at finde eksporter efter navn, forbindelsesnavn eller forbindelsestype.</span><span class="sxs-lookup"><span data-stu-id="a8956-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="a8956-111">Konfigurer en ny eksport</span><span class="sxs-lookup"><span data-stu-id="a8956-111">Set up a new export</span></span>

<span data-ttu-id="a8956-112">Hvis du vil konfigurere eller redigere en eksport, skal du have tilgængelige forbindelser.</span><span class="sxs-lookup"><span data-stu-id="a8956-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="a8956-113">Forbindelser afhænger af [brugerrollen](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="a8956-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="a8956-114">Administratorer har adgang til alle forbindelser.</span><span class="sxs-lookup"><span data-stu-id="a8956-114">Administrators have access to all connections.</span></span> <span data-ttu-id="a8956-115">De kan også oprette nye forbindelser, når en eksport konfigureres.</span><span class="sxs-lookup"><span data-stu-id="a8956-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="a8956-116">Bidragydere kan have adgang til bestemte forbindelser.</span><span class="sxs-lookup"><span data-stu-id="a8956-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="a8956-117">De er afhængige af administratorer, når de skal konfigurere og dele forbindelser.</span><span class="sxs-lookup"><span data-stu-id="a8956-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="a8956-118">Eksportlisten viser bidragydere, om de kan redigere eller kun få vist en eksport i kolonnen **Dine tilladelser**.</span><span class="sxs-lookup"><span data-stu-id="a8956-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="a8956-119">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a8956-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="a8956-120">Fremvisere kan kun få vist eksisterende eksporter, men ikke oprette dem.</span><span class="sxs-lookup"><span data-stu-id="a8956-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="a8956-121">Definer en ny eksport</span><span class="sxs-lookup"><span data-stu-id="a8956-121">Define a new export</span></span>

1. <span data-ttu-id="a8956-122">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="a8956-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a8956-123">Vælg **Tilføj eksport** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="a8956-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="a8956-124">Vælg, hvilken forbindelse du vil bruge, i ruden **Konfigurer eksport**.</span><span class="sxs-lookup"><span data-stu-id="a8956-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="a8956-125">[Forbindelser](connections.md) administreres af administratorer.</span><span class="sxs-lookup"><span data-stu-id="a8956-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="a8956-126">Angiv de nødvendige oplysninger, og vælg **Gem** for at oprette eksporten.</span><span class="sxs-lookup"><span data-stu-id="a8956-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="a8956-127">Definer en ny eksport baseret på en eksisterende eksport</span><span class="sxs-lookup"><span data-stu-id="a8956-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="a8956-128">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="a8956-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a8956-129">Vælg den eksport, som du vil duplikere, på eksportlisten.</span><span class="sxs-lookup"><span data-stu-id="a8956-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="a8956-130">Vælg **Opret dublet** på kommandolinjen for at åbne ruden **Konfigurer eksport** med oplysninger om den valgte eksport.</span><span class="sxs-lookup"><span data-stu-id="a8956-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="a8956-131">Gennemse, og tilpas eksporten, og vælg **Gem** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="a8956-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="a8956-132">Rediger en eksport</span><span class="sxs-lookup"><span data-stu-id="a8956-132">Edit an export</span></span>

1. <span data-ttu-id="a8956-133">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="a8956-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a8956-134">Vælg den eksport, som du vil redigere, på eksportlisten.</span><span class="sxs-lookup"><span data-stu-id="a8956-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="a8956-135">Vælg **Rediger** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="a8956-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="a8956-136">Opdatér de værdier, du vil opdatere, og vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="a8956-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="a8956-137">Få vist eksport og eksportdetaljer</span><span class="sxs-lookup"><span data-stu-id="a8956-137">View exports and export details</span></span>

<span data-ttu-id="a8956-138">Når du har oprettet eksportmål, vises de under **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="a8956-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="a8956-139">Alle brugere kan se, hvilke data der deles, og den seneste status.</span><span class="sxs-lookup"><span data-stu-id="a8956-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="a8956-140">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="a8956-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a8956-141">Brugere uden redigeringstilladelser skal vælge **Vis** i stedet for **Rediger** for at få vist eksportoplysningerne.</span><span class="sxs-lookup"><span data-stu-id="a8956-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="a8956-142">I sideruden vises konfigurationen af en eksport.</span><span class="sxs-lookup"><span data-stu-id="a8956-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="a8956-143">Uden redigeringstilladelser kan du ikke ændre værdier.</span><span class="sxs-lookup"><span data-stu-id="a8956-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="a8956-144">Vælg **Luk** for at vende tilbage til eksportsiden.</span><span class="sxs-lookup"><span data-stu-id="a8956-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="a8956-145">Planlæg, og kør eksport</span><span class="sxs-lookup"><span data-stu-id="a8956-145">Schedule and run exports</span></span>

<span data-ttu-id="a8956-146">Hver eksport, du konfigurerer, har en opdateringsplan.</span><span class="sxs-lookup"><span data-stu-id="a8956-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="a8956-147">Under en opdatering søger systemet efter nye eller opdaterede data, der skal medtages i en eksport.</span><span class="sxs-lookup"><span data-stu-id="a8956-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="a8956-148">Eksport køres som standard som del af alle [planlagte systemopdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a8956-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a8956-149">Du kan tilpasse opdateringsplanen, eller slå den fra for at køre eksporten manuelt.</span><span class="sxs-lookup"><span data-stu-id="a8956-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="a8956-150">Eksportplaner afhænger af miljøets tilstand.</span><span class="sxs-lookup"><span data-stu-id="a8956-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="a8956-151">Hvis der er opdateringer i gang om [afhængigheder](system.md#refresh-policies), når en planlagt eksport skal starte, fuldfører systemet først opdateringerne og kører derefter eksporten.</span><span class="sxs-lookup"><span data-stu-id="a8956-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="a8956-152">Du kan få vist, hvornår en eksport sidst blev opdateret i kolonnen **Opdateret**.</span><span class="sxs-lookup"><span data-stu-id="a8956-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="a8956-153">Planlæg eksport</span><span class="sxs-lookup"><span data-stu-id="a8956-153">Schedule exports</span></span>

<span data-ttu-id="a8956-154">Du kan definere brugerdefinerede opdateringsplaner for individuelle eksporter eller flere eksporter på én gang.</span><span class="sxs-lookup"><span data-stu-id="a8956-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="a8956-155">Den aktuelt definerede tidsplan vises i kolonnen **Tidsplan** på eksportlisten.</span><span class="sxs-lookup"><span data-stu-id="a8956-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="a8956-156">Tilladelsen til at ændre tidsplanen er den samme som for [redigering og definition af eksporter](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a8956-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="a8956-157">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="a8956-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a8956-158">Vælg den eksport, du vil planlægge.</span><span class="sxs-lookup"><span data-stu-id="a8956-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="a8956-159">Vælg **Planlæg** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="a8956-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="a8956-160">Angiv **Planlæg kørsel** til **Til** i ruden **Planlæg eksport** for at køre eksporten automatisk.</span><span class="sxs-lookup"><span data-stu-id="a8956-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="a8956-161">Indstil den til **Fra** for at opdatere den manuelt.</span><span class="sxs-lookup"><span data-stu-id="a8956-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="a8956-162">Ved automatisk opdaterede eksporter skal du vælge en værdi for **Gentagelse** og angive detaljerne for den.</span><span class="sxs-lookup"><span data-stu-id="a8956-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="a8956-163">Den definerede tid gælder for alle forekomster af en gentagelse.</span><span class="sxs-lookup"><span data-stu-id="a8956-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="a8956-164">Det er det tidspunkt, hvor en eksport skal begynde at opdatere.</span><span class="sxs-lookup"><span data-stu-id="a8956-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="a8956-165">Anvend og aktivér ændringerne ved at vælge **Gem**.</span><span class="sxs-lookup"><span data-stu-id="a8956-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="a8956-166">Når du redigerer tidsplanen for flere eksporter, skal du foretage et valg under **Behold eller tilsidesætte tidsplaner**:</span><span class="sxs-lookup"><span data-stu-id="a8956-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="a8956-167">**Bevar individuelle tidsplaner**: Bevar den tidligere definerede tidsplan for de valgte eksporter, og deaktiver eller aktiver dem kun.</span><span class="sxs-lookup"><span data-stu-id="a8956-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="a8956-168">**Definer ny tidsplan for alle valgte eksporter**: Tilsidesæt de eksisterende tidsplaner for de valgte eksporter.</span><span class="sxs-lookup"><span data-stu-id="a8956-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="a8956-169">Kør eksporter efter behov</span><span class="sxs-lookup"><span data-stu-id="a8956-169">Run exports on demand</span></span>

<span data-ttu-id="a8956-170">Hvis du vil eksportere data uden at vente på en planlagt opdatering, skal du gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="a8956-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="a8956-171">Hvis du vil køre alle eksporter, skal du vælge **Kør alle** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="a8956-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="a8956-172">Denne handling kører kun eksporter, der har en aktiv tidsplan.</span><span class="sxs-lookup"><span data-stu-id="a8956-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="a8956-173">Hvis du vil køre en enkelt eksport, skal du markere den på listen og vælge **Kør** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="a8956-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="a8956-174">Det er sådan, du kører eksporter uden aktiv tidsplan.</span><span class="sxs-lookup"><span data-stu-id="a8956-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="a8956-175">Fjerne en eksport</span><span class="sxs-lookup"><span data-stu-id="a8956-175">Remove an Export</span></span>

1. <span data-ttu-id="a8956-176">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="a8956-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a8956-177">Markér den eksport, du vil fjerne.</span><span class="sxs-lookup"><span data-stu-id="a8956-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="a8956-178">Vælg **Fjern** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="a8956-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="a8956-179">Bekræft fjernelsen ved at vælge **Fjern** på bekræftelsesskærmen.</span><span class="sxs-lookup"><span data-stu-id="a8956-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
