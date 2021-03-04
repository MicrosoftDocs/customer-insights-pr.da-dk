---
title: Tilknyt objekter til datasamling
description: Tilknyt data for at oprette samlede kundeprofiler.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267028"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="9d4d0-103">Tilknyt objekter og attributter</span><span class="sxs-lookup"><span data-stu-id="9d4d0-103">Map entities and attributes</span></span>

<span data-ttu-id="9d4d0-104">**Tilknyt** er det første trin i datasamlingsprocessen for målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="9d4d0-105">Tilknytning består af tre faser:</span><span class="sxs-lookup"><span data-stu-id="9d4d0-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="9d4d0-106">*Objektvalg*: Identificer de kombinerbare enheder, som fører til et datasæt med mere komplette oplysninger om dine kunder.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="9d4d0-107">*Attributvalg*: Identificerer for hvert objekt de kolonner, du vil kombinere og afstemme i faserne *match* og *flet*.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="9d4d0-108">Disse kolonner kaldes *Attributter*.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="9d4d0-109">*Primær nøgle og semantisk valg*: For hvert objekt skal du identificere en attribut, som du vil definere som den primære nøgle for det pågældende objekt, og for hver attribut skal du identificere en semantisk type, der bedst beskriver den pågældende attribut.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="9d4d0-110">Du kan finde flere oplysninger om det generelle flow af datasamling under [Samle](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9d4d0-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="9d4d0-111">Vælge de første objekter</span><span class="sxs-lookup"><span data-stu-id="9d4d0-111">Select the first entities</span></span>

1. <span data-ttu-id="9d4d0-112">Gå til **Data** > **Saml** > **Tilknyt** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="9d4d0-113">Start tilknytningsfasen ved at vælge **Vælg objekter**.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="9d4d0-114">Vælg de objekter og attributter, du vil bruge i faserne *Afstem* og *Flet*.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="9d4d0-115">Du kan vælge de krævede attributter individuelt for et objekt eller inkludere alle attributter fra et objekt ved at markere afkrydsningsfeltet **Medtag alle felter** på objektniveauet.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="9d4d0-116">Det anbefales, at du vælger mindst to objekter for at drage fordel af datasamlingsprocessen.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9d4d0-117">![Eksempel på tilføjelse af objekter](media/data-manager-configure-map-add-entities-example.png "Eksempel på tilføjelse af objekter")</span><span class="sxs-lookup"><span data-stu-id="9d4d0-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="9d4d0-118">I dette eksempel tilføjer vi objekterne **eCommerceContacts** og **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="9d4d0-119">Hvis du vælger disse objekter, kan du få indsigt i, hvilke online virksomhedskunder der er medlemmer af loyalitetsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="9d4d0-120">Du kan søge efter nøgleord på tværs af alle attributter og objekter for at vælge de nødvendige attributter, du vil tilknytte.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9d4d0-121">![Eksempel på feltet Søg](media/data-manager-configure-map-search-fields-example.png "Eksempel på feltet Søg")</span><span class="sxs-lookup"><span data-stu-id="9d4d0-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="9d4d0-122">Vælg **Anvend** for at bekræfte de valgte indstillinger.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="9d4d0-123">Vælg primær nøgle og semantisk type for attributter</span><span class="sxs-lookup"><span data-stu-id="9d4d0-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="9d4d0-124">Når du har valgt objekterne , viser siden **Tilknyt** de valgte objekter for anmeldelsen.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="9d4d0-125">Definer den primære nøgle for et objekt, og identificer den semantiske type for en attribut i objektet.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="9d4d0-126">**Primær nøgle**: Vælg en attribut som primær nøgle for hvert af objekterne.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="9d4d0-127">Hvis en attribut skal være en gyldig primær nøgle, må den ikke indeholde dubletværdier, manglende værdier eller null-værdier.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="9d4d0-128">Datatypeattributter for streng, heltal og GUID understøttes som primære nøgler, og de vises i et felt, hvor du kan vælge dem.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="9d4d0-129">**Semantisk attributtype**: Kategorier af attributter, f.eks. mailadresse eller navn.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="9d4d0-130">Hvis du vil bruge AI-modeller til smart forudsigelse af semantik og spare tid og øge præcisionen, skal du indstille **Intelligent tilknytning** til **TIL**.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="9d4d0-131">Intelligent tilknytning fremhæver den AI-baserede semantikanbefaling i feltet **Type**.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="9d4d0-132">Hvis du indstiller den til **FRA**, kan du se vores almindelige tilknytningsanbefalinger.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="9d4d0-133">Du kan vælge en hvilken som helst semantisk type på den tilgængelige liste over indstillinger og tilsidesætte den foreslåede markering.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9d4d0-134">![Attributtype og semantisk forudsigelse](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attributtype og semantisk forudsigelse")</span><span class="sxs-lookup"><span data-stu-id="9d4d0-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="9d4d0-135">Det er også muligt at tilføje en brugerdefineret semantisk type.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="9d4d0-136">Vælg typefeltet for en attribut, og skriv navnet på den brugerdefinerede semantiske type.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="9d4d0-137">På denne måde kan du også ændre de attributtyper, der er identificeret automatisk af systemet.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="9d4d0-138">Alle attributter, hvor der automatisk identificeres en semantisk type, grupperes i sektionen **Gennemse tilknyttede felter**.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="9d4d0-139">Gennemse disse attributter og deres semantiske typer, da de bruges til at kombinere objekterne i fletningen i forbindelse med dataensretning.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="9d4d0-140">Attributter, der ikke automatisk knyttes til en semantisk type, grupperes i sektionen **Definer data i ikke-tilknyttede felter**.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="9d4d0-141">Vælg feltet for semantisk type for de ikke-tilknyttede attributter, eller angiv navnet på den brugerdefinerede attributtype.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9d4d0-142">![Primær nøgle og attributtype](media/data-manager-configure-map-add-attributes.png "Primær nøgle og attributtype")</span><span class="sxs-lookup"><span data-stu-id="9d4d0-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="9d4d0-143">Et enkelt felt skal knyttes til den semantiske type Person.FullName for at udfylde kundenavnet på debitorkortet.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="9d4d0-144">Ellers vises kundekortene uden navn.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="9d4d0-145">Tilføje og fjerne attributter og objekter</span><span class="sxs-lookup"><span data-stu-id="9d4d0-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="9d4d0-146">Vælg **Rediger felter** under **Saml** > **Tilknyt**.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="9d4d0-147">Tilføj eller fjern attributter og objekter i ruden **Rediger felter**.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="9d4d0-148">Brug søgning eller rulning til at søge efter og vælge de ønskede attributter og objekter.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="9d4d0-149">Du kan ikke fjerne en attribut eller et objekt, hvis det allerede er tilknyttet.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9d4d0-150">![Tilføje eller fjerne attributter](media/configure-data-map-edit.png "Tilføje eller fjerne attributter")</span><span class="sxs-lookup"><span data-stu-id="9d4d0-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="9d4d0-151">Vælg **Anvend**.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="9d4d0-152">Føje billeder til profiler</span><span class="sxs-lookup"><span data-stu-id="9d4d0-152">Add images to profiles</span></span>

<span data-ttu-id="9d4d0-153">Hvis et objekt indeholder URL-adresser til offentligt tilgængelige profilbilleder eller logoer, kan du føje dem til den samlede kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="9d4d0-154">Vælg objektet, og find det felt, der indeholder URL-adressen til profilbilledet.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="9d4d0-155">Angiv manuelt følgende værdi i inputfeltet **Type**.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="9d4d0-156">For en person: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="9d4d0-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="9d4d0-157">For en organisation: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="9d4d0-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="9d4d0-158">Fortsæt med fremgangsmåden for ensartethed, og kontrollér, at den attribut, der indeholder URL-adressen for billedet, også tilføjes i trinnet [Flet](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="9d4d0-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="9d4d0-159">Angive attributter for organisationer</span><span class="sxs-lookup"><span data-stu-id="9d4d0-159">Set attributes for organizations</span></span>

<span data-ttu-id="9d4d0-160">For organisationer (prøveversion) skal attributtypen knyttes til "Organization.Name".</span><span class="sxs-lookup"><span data-stu-id="9d4d0-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="9d4d0-161">![Primær nøgle og attributtype B2B](media/configure-data-map-edit-b2b.png "Primær nøgle og attributtype B2B")</span><span class="sxs-lookup"><span data-stu-id="9d4d0-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="9d4d0-162">Næste trin</span><span class="sxs-lookup"><span data-stu-id="9d4d0-162">Next step</span></span>

<span data-ttu-id="9d4d0-163">Gå til siden **Match** som en del af datasamlingsprocessen.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="9d4d0-164">Besøg [**Match**](match-entities.md) for at få mere at vide om denne fase.</span><span class="sxs-lookup"><span data-stu-id="9d4d0-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="9d4d0-165">Se følgende video: [Introduktion: oprettelse af en samlet kundeprofil](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="9d4d0-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]