---
title: Kundeaktiviteter
description: Definer kundeaktiviteter, og få vist dem på kundetidslinjen.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304919"
---
# <a name="customer-activities"></a><span data-ttu-id="656ec-103">Kundeaktiviteter</span><span class="sxs-lookup"><span data-stu-id="656ec-103">Customer activities</span></span>

<span data-ttu-id="656ec-104">Kombiner kundeaktiviteter fra [forskellige datakilder](data-sources.md) i Dynamics 365 Customer Insights for at oprette en tidslinje, der viser aktiviteterne kronologisk.</span><span class="sxs-lookup"><span data-stu-id="656ec-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="656ec-105">Inkluder tidslinjen i Dynamics 365-apps med [tilføjelsesprogrammet Kundekortløsning](customer-card-add-in.md) eller i et Power BI-dashboard.</span><span class="sxs-lookup"><span data-stu-id="656ec-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="656ec-106">Definere en aktivitet</span><span class="sxs-lookup"><span data-stu-id="656ec-106">Define an activity</span></span>

<span data-ttu-id="656ec-107">Datakilderne kan inkludere objekter med transaktions- og aktivitetsdata fra flere datakilder.</span><span class="sxs-lookup"><span data-stu-id="656ec-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="656ec-108">Identificer disse objekter, og vælg de aktiviteter, du vil have vist på kundens tidslinje.</span><span class="sxs-lookup"><span data-stu-id="656ec-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="656ec-109">Vælg det objekt, der indeholder målaktiviteten eller -aktiviteterne.</span><span class="sxs-lookup"><span data-stu-id="656ec-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="656ec-110">Et objekt skal have mindst én attribut af typen **Dato** for at blive medtaget på en kundes tidslinje, og du kan ikke tilføje objekter uden **Dato**-felter.</span><span class="sxs-lookup"><span data-stu-id="656ec-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="656ec-111">Kontrolelementet **Tilføj aktivitet** deaktiveres, hvis der ikke findes et sådant objekt.</span><span class="sxs-lookup"><span data-stu-id="656ec-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="656ec-112">Gå til **Data** > **Aktiviteter** i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="656ec-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="656ec-113">Vælg **Tilføj aktivitet** for at starte den styrede oplevelse af aktivitetskonfigurationsprocessen.</span><span class="sxs-lookup"><span data-stu-id="656ec-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="656ec-114">Angiv værdier for følgende felter i datatrinnet **Aktivitetsdata**:</span><span class="sxs-lookup"><span data-stu-id="656ec-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="656ec-115">**Aktivitetsnavn**: Vælg et navn til aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="656ec-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="656ec-116">**Objekt**: Vælg et objekt, der indeholder transaktions- eller aktivitetsdata.</span><span class="sxs-lookup"><span data-stu-id="656ec-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="656ec-117">**Primær nøgle**: Vælg det felt, der entydigt identificerer en post.</span><span class="sxs-lookup"><span data-stu-id="656ec-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="656ec-118">Den må ikke indeholde dublerede værdier, tomme værdier eller manglende værdier.</span><span class="sxs-lookup"><span data-stu-id="656ec-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Konfigurer aktivitetsdataene med navn, objekt og primær nøgle.":::

1. <span data-ttu-id="656ec-120">Vælg **Næste** for at gå til næste trin.</span><span class="sxs-lookup"><span data-stu-id="656ec-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="656ec-121">I **relationstrinnet** skal du konfigurere detaljerne for at knytte dine aktivitetsdata til den tilhørende kunde.</span><span class="sxs-lookup"><span data-stu-id="656ec-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="656ec-122">I dette trin visualiseres forbindelsen mellem objekter.</span><span class="sxs-lookup"><span data-stu-id="656ec-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="656ec-123">**Først**: Fremmed felt i aktivitetsobjektet, der bruges til at oprette en relation til et andet objekt.</span><span class="sxs-lookup"><span data-stu-id="656ec-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="656ec-124">**Andet**: Det tilsvarende kildekundeobjekt, som aktivitetsobjektet er i relation til.</span><span class="sxs-lookup"><span data-stu-id="656ec-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="656ec-125">Du kan kun relatere til kildekundeobjekter, der bruges i processen til dataenheder.</span><span class="sxs-lookup"><span data-stu-id="656ec-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="656ec-126">**Tredje**: Hvis der allerede findes en relation mellem dette aktivitetsobjekt og det valgte kildekundeobjekt, er relationsnavnet skrivebeskyttet.</span><span class="sxs-lookup"><span data-stu-id="656ec-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="656ec-127">Hvis der ikke findes en sådan relation, oprettes der en ny relation med det navn, du angiver i denne boks.</span><span class="sxs-lookup"><span data-stu-id="656ec-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definere objektrelationen.":::

1. <span data-ttu-id="656ec-129">Vælg **Næste** for at gå til næste trin.</span><span class="sxs-lookup"><span data-stu-id="656ec-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="656ec-130">I **Aktivitetsenhed**-trinnet skal du vælge aktivitetshændelsen og starttiden for aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="656ec-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="656ec-131">**Obligatoriske felter**</span><span class="sxs-lookup"><span data-stu-id="656ec-131">**Required fields**</span></span>
      - <span data-ttu-id="656ec-132">**Hændelsesaktivitet**: Det felt, der er begivenheden for denne aktivitet.</span><span class="sxs-lookup"><span data-stu-id="656ec-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="656ec-133">**Tidsstempel**: Felt, der repræsenterer starttiderne for aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="656ec-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="656ec-134">**Valgfrie felter**</span><span class="sxs-lookup"><span data-stu-id="656ec-134">**Optional fields**</span></span>
      - <span data-ttu-id="656ec-135">**Flere detaljer**: Felt med relevante oplysninger om aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="656ec-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="656ec-136">**Ikon**: Det ikon, der bedst repræsenterer denne aktivitetstype.</span><span class="sxs-lookup"><span data-stu-id="656ec-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="656ec-137">**Webadresse**: Felt, der indeholder en URL-adresse med oplysninger om aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="656ec-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="656ec-138">For eksempel det transaktionssystem, der er kilde til aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="656ec-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="656ec-139">Denne URL-adresse kan være et hvilket som helst felt fra datakilden, eller den kan konstrueres som et nyt felt ved hjælp af en Power Query-transformation.</span><span class="sxs-lookup"><span data-stu-id="656ec-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="656ec-140">URL-dataene gemmes i objektet *Unified Activity*, som kan forbruges downstream ved hjælp af [API'er](apis.md).</span><span class="sxs-lookup"><span data-stu-id="656ec-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Angiv kundeaktivitetsdata i et Unified Activity-objekt.":::

1. <span data-ttu-id="656ec-142">Vælg **Næste** for at gå til næste trin.</span><span class="sxs-lookup"><span data-stu-id="656ec-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="656ec-143">Du kan vælge **Afslut og gennemse** for at gemme aktiviteten nu, hvor aktivitetstypen er angivet til **Andet**.</span><span class="sxs-lookup"><span data-stu-id="656ec-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="656ec-144">Vælg aktivitetstypen i trinnet **Aktivitetstype**, og vælg eventuelt, om du vil tilknytte nogle af aktivitetstyperne til brug i andre områder af Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="656ec-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="656ec-145">I øjeblikket kan aktivitetstyperne *Abonnement* og *Salgsordrelinje* tilknyttes semantisk, når du har accepteret at tilknytte felterne.</span><span class="sxs-lookup"><span data-stu-id="656ec-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="656ec-146">Hvis en aktivitetstype ikke er relevant for den nye aktivitet, kan du vælge *Andet* eller *Opret nyt* for en brugerdefineret aktivitetstype.</span><span class="sxs-lookup"><span data-stu-id="656ec-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="656ec-147">Vælg **Næste** for at gå til næste trin.</span><span class="sxs-lookup"><span data-stu-id="656ec-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="656ec-148">Kontrollér de indstillinger, du har godkendt i **Gennemse**.</span><span class="sxs-lookup"><span data-stu-id="656ec-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="656ec-149">Gå tilbage til et af de forrige trin, og opdater oplysningerne, hvis det er nødvendigt.</span><span class="sxs-lookup"><span data-stu-id="656ec-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Gennemse de angivne felter for en aktivitet.":::
   
1. <span data-ttu-id="656ec-151">Vælg **Gem aktivitet** for at anvende ændringerne, og vælg **Udført** for at gå tilbage til **Data** > **Aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="656ec-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="656ec-152">Her kan du se, hvilke aktiviteter der er angivet til at blive vist på tidslinjen.</span><span class="sxs-lookup"><span data-stu-id="656ec-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="656ec-153">Vælg **Kør** på siden **Aktiviteter** for at behandle aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="656ec-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="656ec-154">Opgaver og processer indeholder [seks typer status](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="656ec-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="656ec-155">De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="656ec-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="656ec-156">Du kan vælge status for en proces for at se statusdetaljer for hele jobbet.</span><span class="sxs-lookup"><span data-stu-id="656ec-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="656ec-157">Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.</span><span class="sxs-lookup"><span data-stu-id="656ec-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="656ec-158">Administrer eksisterende aktiviteter</span><span class="sxs-lookup"><span data-stu-id="656ec-158">Manage existing activities</span></span>

<span data-ttu-id="656ec-159">I **Data** > **Aktiviteter** kan du få vist alle de gemte aktiviteter og administrere dem.</span><span class="sxs-lookup"><span data-stu-id="656ec-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="656ec-160">De enkelte aktiviteter repræsenteres af en række, der også indeholder oplysninger om kilden, objektet og aktivitetstypen.</span><span class="sxs-lookup"><span data-stu-id="656ec-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="656ec-161">Følgende handlinger er tilgængelige, når du vælger en aktivitet.</span><span class="sxs-lookup"><span data-stu-id="656ec-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="656ec-162">**Rediger**: Åbner aktivitetskonfigurationen i gennemsynstrinnet.</span><span class="sxs-lookup"><span data-stu-id="656ec-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="656ec-163">Du kan ændre en eller alle de aktuelle konfigurationer fra dette trin.</span><span class="sxs-lookup"><span data-stu-id="656ec-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="656ec-164">Når du har ændret konfigurationen, skal du vælge **Gem aktivitet** og derefter vælge **Kør** for at behandle ændringerne.</span><span class="sxs-lookup"><span data-stu-id="656ec-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="656ec-165">**Omdøb**: Åbner en dialogboks, hvor du kan angive et andet navn til den valgte aktivitet.</span><span class="sxs-lookup"><span data-stu-id="656ec-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="656ec-166">Vælg **Gem** for at anvende dine ændringer.</span><span class="sxs-lookup"><span data-stu-id="656ec-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="656ec-167">**Slet**: Åbner en dialogboks for at bekræfte sletningen af den valgte aktivitet.</span><span class="sxs-lookup"><span data-stu-id="656ec-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="656ec-168">Du kan også slette mere end én aktivitet på én gang ved at markere aktiviteterne og derefter vælge sletteikonet.</span><span class="sxs-lookup"><span data-stu-id="656ec-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="656ec-169">Bekræft sletningen ved at vælge **Slet**.</span><span class="sxs-lookup"><span data-stu-id="656ec-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
