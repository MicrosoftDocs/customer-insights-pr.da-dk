---
title: Kundeaktiviteter
description: Definer kundeaktiviteter, og få vist dem på kundetidslinjen.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596722"
---
# <a name="customer-activities"></a><span data-ttu-id="e6cb9-103">Kundeaktiviteter</span><span class="sxs-lookup"><span data-stu-id="e6cb9-103">Customer activities</span></span>

<span data-ttu-id="e6cb9-104">Du kan kombinere kundeaktiviteter fra [forskellige datakilder](data-sources.md) i Dynamics 365 Customer Insights for at oprette en kundetidslinje, der angiver aktiviteterne i kronologisk rækkefølge.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="e6cb9-105">Du kan medtage tidslinjen i kundeengagementsapps i Dynamics 365 via [tilføjelsesprogrammet Kundekort](customer-card-add-in.md) eller et Power BI-dashboard.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="e6cb9-106">Definere en aktivitet</span><span class="sxs-lookup"><span data-stu-id="e6cb9-106">Define an activity</span></span>

<span data-ttu-id="e6cb9-107">Datakilderne inkluderer objekter med transaktions- og aktivitetsdata fra flere datakilder.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="e6cb9-108">Identificer disse objekter, og vælg de aktiviteter, du vil have vist på kundens tidslinje.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="e6cb9-109">Vælg det objekt, der indeholder målaktiviteten eller -aktiviteterne.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="e6cb9-110">Gå til **Data** > **Aktiviteter** i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="e6cb9-111">Vælg **Tilføj aktivitet**.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e6cb9-112">Et objekt skal have mindst én attribut af typen **Dato** for at blive medtaget på en kundes tidslinje, og du kan ikke tilføje objekter uden **Dato**-felter.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="e6cb9-113">Kontrolelementet **Tilføj aktivitet** deaktiveres, hvis der ikke findes et sådant objekt.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="e6cb9-114">Angiv værdierne for følgende felter i ruden **Tilføj aktivitet**:</span><span class="sxs-lookup"><span data-stu-id="e6cb9-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="e6cb9-115">**Objekt**: Vælg et objekt, der indeholder transaktions- eller aktivitetsdata.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="e6cb9-116">**Primær nøgle**: Vælg det felt, der entydigt identificerer en post.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="e6cb9-117">Den må ikke indeholde dublerede værdier, tomme værdier eller manglende værdier.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="e6cb9-118">**Tidsstempel**: Markér det felt, der repræsenterer starttidspunktet for aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="e6cb9-119">**Hændelse**: Markér det felt, der er hændelsen for aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="e6cb9-120">**Webadresse**: Markér det felt, der repræsenterer en URL-adresse, som indeholder yderligere oplysninger om denne aktivitet.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="e6cb9-121">For eksempel det transaktionssystem, der er kilde til aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="e6cb9-122">Denne URL-adresse kan være et hvilket som helst felt fra datakilden, eller den kan konstrueres som et nyt felt ved hjælp af en Power Query-transformation.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="e6cb9-123">Disse URL-adressedata gemmes i objektet Samlet aktivitet, som kan forbruges downstream ved hjælp af API'er.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="e6cb9-124">**Detaljer**: Vælg eventuelt det felt, der tilføjes, for at få flere oplysninger.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="e6cb9-125">**Ikon**: Vælg eventuelt det ikon, der repræsenterer denne aktivitet.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="e6cb9-126">**Aktivitetstype**: Definer den reference til aktivitetstype i Common Data Model, der bedst beskriver den semantiske definition af aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="e6cb9-127">I sektionen **Konfigurer relation** skal du konfigurere detaljerne for at oprette forbindelse mellem aktivitetsdataene og den tilsvarende kunde.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="e6cb9-128">**Aktivitetsobjektfelt**: Vælg det felt i det aktivitetsobjekt, der skal bruges til at oprette en relation til et andet objekt.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="e6cb9-129">**Kundeobjekt**: Vælg det tilsvarende kildekundeobjekt, som aktivitetsobjektet skal have en relation til.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="e6cb9-130">Du kan kun oprette forbindelse til de kildekundeobjekter, der bruges i datasamlingsprocessen.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="e6cb9-131">**Kundeobjektfelt**: I dette felt vises den primære nøgle for kildekundeobjektet, som det er valgt i tilknytningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="e6cb9-132">Dette primære nøglefelt i kildekundeobjektet bruges til at oprette en relation til aktivitetsobjektet.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="e6cb9-133">**Navn**: Hvis der allerede findes en relation mellem dette aktivitetsobjekt og det valgte kildekundeobjekt, vil navnet på relationen være i skrivebeskyttet tilstand.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="e6cb9-134">Hvis der ikke findes en sådan relation, oprettes der en ny relation med det navn, der angives her.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6cb9-135">![Definere objektrelationen](media/activities-entities-define.png "Definere objektrelationen")</span><span class="sxs-lookup"><span data-stu-id="e6cb9-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="e6cb9-136">Vælg **Gem** for at anvende dine ændringer.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="e6cb9-137">Vælg **Kør** på siden **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="e6cb9-138">Opgaver og processer indeholder [seks typer status](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="e6cb9-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e6cb9-139">De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e6cb9-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e6cb9-140">Du kan vælge status for en proces for at se statusdetaljer for hele jobbet.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e6cb9-141">Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="e6cb9-142">Redigere en aktivitet</span><span class="sxs-lookup"><span data-stu-id="e6cb9-142">Edit an activity</span></span>

1. <span data-ttu-id="e6cb9-143">Gå til **Data** > **Aktiviteter** i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="e6cb9-144">Vælg det aktivitetsobjekt, du vil redigere, og vælg **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="e6cb9-145">Du kan også holde markøren over objektrækken og vælge ikonet **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="e6cb9-146">Klik på ikonet **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="e6cb9-147">Opdater værdierne i ruden **Rediger aktivitet**, og vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="e6cb9-148">Vælg **Kør** på siden **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="e6cb9-149">Slette en aktivitet</span><span class="sxs-lookup"><span data-stu-id="e6cb9-149">Delete an activity</span></span>

1. <span data-ttu-id="e6cb9-150">Gå til **Data** > **Aktiviteter** i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="e6cb9-151">Vælg det aktivitetsobjekt, du vil fjerne, og vælg **Slet**.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="e6cb9-152">Du kan også holde markøren over objektrækken og vælge ikonet **Slet**.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="e6cb9-153">Derudover kan du markere flere aktivitetsobjekter, der skal slettes på én gang.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6cb9-154">![Redigere eller slette objektrelationen](media/activities-entities-edit-delete.png "Redigere eller slette objektrelationen")</span><span class="sxs-lookup"><span data-stu-id="e6cb9-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="e6cb9-155">Vælg ikonet **Slet**.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="e6cb9-156">Bekræft sletningen.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]