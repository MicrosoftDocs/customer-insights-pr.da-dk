---
title: Administrer brugertilladelser
description: Få mere at vide om tilladelser og brugerroller.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760366"
---
# <a name="user-permissions"></a><span data-ttu-id="287ad-103">Brugertilladelser</span><span class="sxs-lookup"><span data-stu-id="287ad-103">User permissions</span></span>

<span data-ttu-id="287ad-104">Siden **Tilladelser** er det sted, hvor du skal konfigurere roller og tilladelser til at bruge målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="287ad-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="287ad-105">Du skal have administratortilladelser for at kunne se siden.</span><span class="sxs-lookup"><span data-stu-id="287ad-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="287ad-106">Du kan få adgang til siden med tilladelser i målgruppen Insights ved at gå til **Admin** > **Tilladelser**.</span><span class="sxs-lookup"><span data-stu-id="287ad-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="287ad-107">Der findes tre typer roller:</span><span class="sxs-lookup"><span data-stu-id="287ad-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="287ad-108">Seer</span><span class="sxs-lookup"><span data-stu-id="287ad-108">Viewer</span></span>

- <span data-ttu-id="287ad-109">Udforsk indsigt og segmenter på siderne **Start** og **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="287ad-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="287ad-110">Søg og filtrer kundeprofiler ved hjælp af siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="287ad-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="287ad-111">Felter skal være søgbare.</span><span class="sxs-lookup"><span data-stu-id="287ad-111">Fields must be searchable.</span></span>
- <span data-ttu-id="287ad-112">Åbn og undersøg siden **Forbedring**.</span><span class="sxs-lookup"><span data-stu-id="287ad-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="287ad-113">Udforsk og eksportér objekter ved hjælp af siden **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="287ad-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="287ad-114">Se status for systemprocesser ved hjælp af siden **System**.</span><span class="sxs-lookup"><span data-stu-id="287ad-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="287ad-115">Vis eksporter på siden **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="287ad-115">View exports in **Exports** page.</span></span>
- <span data-ttu-id="287ad-116">Installer og brug dashboard **Power BI Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="287ad-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="287ad-117">Bidragyder</span><span class="sxs-lookup"><span data-stu-id="287ad-117">Contributor</span></span>

- <span data-ttu-id="287ad-118">Alle tilladelser, der er tilgængelige for seeren.</span><span class="sxs-lookup"><span data-stu-id="287ad-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="287ad-119">Indlæs og transformer data ved hjælp af siden **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="287ad-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="287ad-120">Udfyld sektionere *Datasamling* (**Tilknyt**, **Match** og **Flet**), som resulterer i det samlede kundeprofilobjekt.</span><span class="sxs-lookup"><span data-stu-id="287ad-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="287ad-121">Definer **Relationer** og **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="287ad-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="287ad-122">Opret segmenter ved hjælp af siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="287ad-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="287ad-123">Opret målinger på siden **Målinger**.</span><span class="sxs-lookup"><span data-stu-id="287ad-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="287ad-124">Administrer konfiguration og forbedring af kundeprofiler på siden **Forbedring** (kun førstepartsforbedringer).</span><span class="sxs-lookup"><span data-stu-id="287ad-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>
- <span data-ttu-id="287ad-125">Administrer og opret eksporter på baggrund af forbindelser, der deles med bidragydere.</span><span class="sxs-lookup"><span data-stu-id="287ad-125">Manage and create exports based on connections shared with contributors.</span></span> <span data-ttu-id="287ad-126">[Få mere at vide om, hvordan administratorer tillader bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="287ad-126">[Learn more about how administrators allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

## <a name="administrator"></a><span data-ttu-id="287ad-127">Administrator</span><span class="sxs-lookup"><span data-stu-id="287ad-127">Administrator</span></span>

- <span data-ttu-id="287ad-128">Alle tilladelser, der er tilgængelige for bidragyderen.</span><span class="sxs-lookup"><span data-stu-id="287ad-128">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="287ad-129">Rediger indstillingerne på siden **System**, herunder arbejdssproget og opdateringsplanerne for systemprocesserne.</span><span class="sxs-lookup"><span data-stu-id="287ad-129">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="287ad-130">Se og tilføj tilladelser på siden **Tilladelser**.</span><span class="sxs-lookup"><span data-stu-id="287ad-130">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="287ad-131">Angiv søge- og filterdefinitioner for siden Kunder ved hjælp af siden **Indeks for søgning og filtrering** (tilgængelig via siden **Kunder**).</span><span class="sxs-lookup"><span data-stu-id="287ad-131">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="287ad-132">Administrer forbindelser, og tillad dem for andre brugerroller på siden **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="287ad-132">Manage connections and allow them for other user roles on **Connections** page.</span></span>
- <span data-ttu-id="287ad-133">Administrer konfiguration og forbedring af kundeprofiler på siden **Forbedring** (for alle forbedringer).</span><span class="sxs-lookup"><span data-stu-id="287ad-133">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="287ad-134">Administrere og oprette eksporter på siden **Eksporter**.</span><span class="sxs-lookup"><span data-stu-id="287ad-134">Manage and create exports on **Exports** page.</span></span>
- <span data-ttu-id="287ad-135">Installer og brug **tilføjelsesprogrammet Kundekort**.</span><span class="sxs-lookup"><span data-stu-id="287ad-135">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="287ad-136">Tilføj og brug **Power Apps-connector**.</span><span class="sxs-lookup"><span data-stu-id="287ad-136">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="287ad-137">Aktiver brug af [Customer Insights API'er](apis.md).</span><span class="sxs-lookup"><span data-stu-id="287ad-137">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="287ad-138">Tildele roller og tilladelser</span><span class="sxs-lookup"><span data-stu-id="287ad-138">Assign roles and permissions</span></span>

1. <span data-ttu-id="287ad-139">Gå til **Adm** > **Tilladelser** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="287ad-139">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="287ad-140">Vælg **Tilføj brugere** for at åbne ruden **Tilføj/Rediger tilladelser**.</span><span class="sxs-lookup"><span data-stu-id="287ad-140">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="287ad-141">Brug feltet **Søg** til at finde den Azure Active Directory-bruger eller -gruppe, du vil justere tilladelser for.</span><span class="sxs-lookup"><span data-stu-id="287ad-141">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="287ad-142">Vælg en **Rolle**, der skal tildeles den pågældende bruger eller gruppe.</span><span class="sxs-lookup"><span data-stu-id="287ad-142">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="287ad-143">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="287ad-143">Select **Save**.</span></span> <span data-ttu-id="287ad-144">Det aktuelle miljø deles automatisk med brugeren eller medlemmerne af den gruppe, hvis tilladelser du har ændret.</span><span class="sxs-lookup"><span data-stu-id="287ad-144">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="287ad-145">Brugerne kan få adgang til appen Customer Insights og arbejde i henhold til deres angivne rolle.</span><span class="sxs-lookup"><span data-stu-id="287ad-145">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="287ad-146">Se aktuelle tilladelser</span><span class="sxs-lookup"><span data-stu-id="287ad-146">View current permissions</span></span>

<span data-ttu-id="287ad-147">Gå til **Admin** > **Tilladelser** i målgruppen Insights for at se, hvilke rolletildelinger der er aktive i øjeblikket.</span><span class="sxs-lookup"><span data-stu-id="287ad-147">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="287ad-148">Kolonnen **Type** angiver en enkelt bruger, en gruppe eller et program.</span><span class="sxs-lookup"><span data-stu-id="287ad-148">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="287ad-149">Systemet understøtter individuelle brugere og grupper.</span><span class="sxs-lookup"><span data-stu-id="287ad-149">The system supports individual users and groups.</span></span>
- <span data-ttu-id="287ad-150">Roller angives i kolonnen **Rolle**.</span><span class="sxs-lookup"><span data-stu-id="287ad-150">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="287ad-151">Vælg en vilkårlig kolonnetitel for at sortere resultaterne efter den pågældende kolonnes værdi.</span><span class="sxs-lookup"><span data-stu-id="287ad-151">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="287ad-152">Brug feltet **Søg** øverst på siden til at finde bestemte brugere.</span><span class="sxs-lookup"><span data-stu-id="287ad-152">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
