---
title: Administrer brugertilladelser
description: Få mere at vide om tilladelser og brugerroller.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689213"
---
# <a name="user-permissions"></a><span data-ttu-id="71135-103">Brugertilladelser</span><span class="sxs-lookup"><span data-stu-id="71135-103">User permissions</span></span>

<span data-ttu-id="71135-104">Siden **Tilladelser** er det sted, hvor du skal konfigurere roller og tilladelser til at bruge målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="71135-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="71135-105">Du skal have administratortilladelser for at kunne se siden.</span><span class="sxs-lookup"><span data-stu-id="71135-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="71135-106">Du kan få adgang til siden med tilladelser i målgruppen Insights ved at gå til **Admin** > **Tilladelser**.</span><span class="sxs-lookup"><span data-stu-id="71135-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="71135-107">Der findes tre typer roller:</span><span class="sxs-lookup"><span data-stu-id="71135-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="71135-108">Seer</span><span class="sxs-lookup"><span data-stu-id="71135-108">Viewer</span></span>

- <span data-ttu-id="71135-109">Udforsk indsigt og segmenter på siderne **Start** og **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="71135-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="71135-110">Søg og filtrer kundeprofiler ved hjælp af siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="71135-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="71135-111">Felter skal være søgbare.</span><span class="sxs-lookup"><span data-stu-id="71135-111">Fields must be searchable.</span></span>
- <span data-ttu-id="71135-112">Åbn og undersøg siden **Forbedring**.</span><span class="sxs-lookup"><span data-stu-id="71135-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="71135-113">Udforsk og eksportér objekter ved hjælp af siden **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="71135-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="71135-114">Se status for systemprocesser ved hjælp af siden **System**.</span><span class="sxs-lookup"><span data-stu-id="71135-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="71135-115">Eksporter segmenter fra siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="71135-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="71135-116">Installer og brug dashboard **Power BI Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="71135-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="71135-117">Bidragyder</span><span class="sxs-lookup"><span data-stu-id="71135-117">Contributor</span></span>

- <span data-ttu-id="71135-118">Alle tilladelser, der er tilgængelige for seeren.</span><span class="sxs-lookup"><span data-stu-id="71135-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="71135-119">Indlæs og transformer data ved hjælp af siden **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="71135-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="71135-120">Udfyld sektionere *Datasamling* (**Tilknyt**, **Match** og **Flet**), som resulterer i det samlede kundeprofilobjekt.</span><span class="sxs-lookup"><span data-stu-id="71135-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="71135-121">Definer **Relationer** og **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="71135-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="71135-122">Opret segmenter ved hjælp af siden **Segmenter**.</span><span class="sxs-lookup"><span data-stu-id="71135-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="71135-123">Opret målinger på siden **Målinger**.</span><span class="sxs-lookup"><span data-stu-id="71135-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="71135-124">Administrer konfiguration og forbedring af kundeprofiler på siden **Forbedring** (kun førstepartsforbedringer).</span><span class="sxs-lookup"><span data-stu-id="71135-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="71135-125">Administrator</span><span class="sxs-lookup"><span data-stu-id="71135-125">Administrator</span></span>

- <span data-ttu-id="71135-126">Alle tilladelser, der er tilgængelige for bidragyderen.</span><span class="sxs-lookup"><span data-stu-id="71135-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="71135-127">Rediger indstillingerne på siden **System**, herunder arbejdssproget og opdateringsplanerne for systemprocesserne.</span><span class="sxs-lookup"><span data-stu-id="71135-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="71135-128">Se og tilføj tilladelser på siden **Tilladelser**.</span><span class="sxs-lookup"><span data-stu-id="71135-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="71135-129">Angiv søge- og filterdefinitioner for siden Kunder ved hjælp af siden **Indeks for søgning og filtrering** (tilgængelig via siden **Kunder**).</span><span class="sxs-lookup"><span data-stu-id="71135-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="71135-130">Definer Dynamics 365 Sales-segmentdestinationer ved hjælp af siden **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="71135-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="71135-131">Administrer konfiguration og forbedring af kundeprofiler på siden **Forbedring** (for alle forbedringer).</span><span class="sxs-lookup"><span data-stu-id="71135-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="71135-132">Installer og brug **tilføjelsesprogrammet Kundekort**.</span><span class="sxs-lookup"><span data-stu-id="71135-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="71135-133">Tilføj og brug **Power Apps-connector**.</span><span class="sxs-lookup"><span data-stu-id="71135-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="71135-134">Aktiver brug af [Customer Insights API'er](apis.md).</span><span class="sxs-lookup"><span data-stu-id="71135-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="71135-135">Tildele roller og tilladelser</span><span class="sxs-lookup"><span data-stu-id="71135-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="71135-136">Gå til **Adm** > **Tilladelser** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="71135-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="71135-137">Vælg **Tilføj brugere** for at åbne ruden **Tilføj/Rediger tilladelser**.</span><span class="sxs-lookup"><span data-stu-id="71135-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="71135-138">Brug feltet **Søg** til at finde den Azure Active Directory-bruger eller -gruppe, du vil justere tilladelser for.</span><span class="sxs-lookup"><span data-stu-id="71135-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="71135-139">Vælg en **Rolle**, der skal tildeles den pågældende bruger eller gruppe.</span><span class="sxs-lookup"><span data-stu-id="71135-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="71135-140">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="71135-140">Select **Save**.</span></span> <span data-ttu-id="71135-141">Det aktuelle miljø deles automatisk med brugeren eller medlemmerne af den gruppe, hvis tilladelser du har ændret.</span><span class="sxs-lookup"><span data-stu-id="71135-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="71135-142">Brugerne kan få adgang til appen Customer Insights og arbejde i henhold til deres angivne rolle.</span><span class="sxs-lookup"><span data-stu-id="71135-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="71135-143">Se aktuelle tilladelser</span><span class="sxs-lookup"><span data-stu-id="71135-143">View current permissions</span></span>

<span data-ttu-id="71135-144">Gå til **Admin** > **Tilladelser** i målgruppen Insights for at se, hvilke rolletildelinger der er aktive i øjeblikket.</span><span class="sxs-lookup"><span data-stu-id="71135-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="71135-145">Kolonnen **Type** angiver en enkelt bruger, en gruppe eller et program.</span><span class="sxs-lookup"><span data-stu-id="71135-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="71135-146">Systemet understøtter individuelle brugere og grupper.</span><span class="sxs-lookup"><span data-stu-id="71135-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="71135-147">Roller angives i kolonnen **Rolle**.</span><span class="sxs-lookup"><span data-stu-id="71135-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="71135-148">Vælg en vilkårlig kolonnetitel for at sortere resultaterne efter den pågældende kolonnes værdi.</span><span class="sxs-lookup"><span data-stu-id="71135-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="71135-149">Brug feltet **Søg** øverst på siden til at finde bestemte brugere.</span><span class="sxs-lookup"><span data-stu-id="71135-149">Use the **Search** field at the top of the page to locate specific users.</span></span>
