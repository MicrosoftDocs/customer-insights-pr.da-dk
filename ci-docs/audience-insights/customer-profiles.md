---
title: Vis kundeprofiler
description: Få en kombineret visning af dine samlede kundedata.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596860"
---
# <a name="customer-profiles"></a><span data-ttu-id="058ae-103">Kundeprofiler</span><span class="sxs-lookup"><span data-stu-id="058ae-103">Customer profiles</span></span>

<span data-ttu-id="058ae-104">På siden **Kunder** vises en kombineret visning af dine kunder baseret på de profildata, der er indsamlet fra [alle datakilder](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="058ae-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="058ae-105">Kundeprofiler er tilgængelige, når du [opretter det samlede kundeobjekt](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="058ae-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="058ae-106">Sørg for at fuldføre dataforeningsprocessen for at få mere detaljerede visninger af dine kunder.</span><span class="sxs-lookup"><span data-stu-id="058ae-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="058ae-107">På siden kan du også søge efter kunder.</span><span class="sxs-lookup"><span data-stu-id="058ae-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="058ae-108">Kunder kan være enkeltpersoner eller organisationer (prøveversion).</span><span class="sxs-lookup"><span data-stu-id="058ae-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="058ae-109">Hver enkelt kunde- eller organisationsprofil repræsenteres af et felt.</span><span class="sxs-lookup"><span data-stu-id="058ae-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="058ae-110">Vælg et felt for at få vist flere oplysninger om den pågældende kunde eller organisation.</span><span class="sxs-lookup"><span data-stu-id="058ae-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="058ae-111">Brug sideinddelingskontrolelementerne nederst på siden for at få vist flere poster.</span><span class="sxs-lookup"><span data-stu-id="058ae-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="058ae-112">![B2C-kundeprofiler](media/profiles-customers.png "B2C-kundeprofiler")</span><span class="sxs-lookup"><span data-stu-id="058ae-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="058ae-113">Organisationer (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="058ae-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="058ae-114">![B2B-kundeprofiler](media/profile-customers-b2b.png "B2B-kundeprofiler")</span><span class="sxs-lookup"><span data-stu-id="058ae-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="058ae-115">Hvis du ikke kan se felterne, når du vælger **Kunder** i navigationen, skal din administrator [definere mindst én søgbar attribut](search-filter-index.md) i **Indeks for søgning og filtrering**.</span><span class="sxs-lookup"><span data-stu-id="058ae-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="058ae-116">Søge efter kunder</span><span class="sxs-lookup"><span data-stu-id="058ae-116">Search for customers</span></span>

<span data-ttu-id="058ae-117">Søg efter kunder ved at angive et navn eller en anden attribut i søgefeltet.</span><span class="sxs-lookup"><span data-stu-id="058ae-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="058ae-118">Søgningen virker kun i det kundeprofilobjekt, der oprettes under dataforeningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="058ae-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="058ae-119">Som administrator kan du konfigurere søgbare attributter på siden **Indeks for søgning og filtrering**.</span><span class="sxs-lookup"><span data-stu-id="058ae-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="058ae-120">Du kan finde flere oplysninger under [Administrere indeks for søgning og filtrering](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="058ae-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="058ae-121">Filtrere kunder</span><span class="sxs-lookup"><span data-stu-id="058ae-121">Filter customers</span></span>

<span data-ttu-id="058ae-122">Du kan filtrere kunder efter objektfelterne for kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="058ae-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="058ae-123">På samme måde som for søgning skal administratoren først definere felterne som filtrerbare på siden **Indeks for søgning og filtrering**.</span><span class="sxs-lookup"><span data-stu-id="058ae-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="058ae-124">Vælg **Filter** på siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="058ae-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="058ae-125">Markér afkrydsningsfelterne ud for de attributter, som du vil filtrere kunder efter.</span><span class="sxs-lookup"><span data-stu-id="058ae-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="058ae-126">![Kundeprofiler](media/profiles-customers3.png "Kundeprofiler")</span><span class="sxs-lookup"><span data-stu-id="058ae-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="058ae-127">Fjern dine filtre ved at vælge **Ryd filtre** på siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="058ae-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="058ae-128">Siden Kundeoplysninger</span><span class="sxs-lookup"><span data-stu-id="058ae-128">Customer details page</span></span>

<span data-ttu-id="058ae-129">Vælg et af kundefelterne for at åbne siden **Kundeoplysninger**.</span><span class="sxs-lookup"><span data-stu-id="058ae-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="058ae-130">Denne visning indeholder en samlet oplysning for den valgte kunde.</span><span class="sxs-lookup"><span data-stu-id="058ae-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="058ae-131">Kundeoplysninger indeholder:</span><span class="sxs-lookup"><span data-stu-id="058ae-131">Customer details include:</span></span>

-   <span data-ttu-id="058ae-132">**Felt til kundeprofil:** Dette felt vises de forskellige værdier fra objektet Kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="058ae-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="058ae-133">Disse oplysninger kan være e-mailadresse, navn, by osv.</span><span class="sxs-lookup"><span data-stu-id="058ae-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="058ae-134">**Potentielle interesser, potentielle mærker:** Viser, om du har konfigureret en opgørelse fra en oprindeligt leverandør.</span><span class="sxs-lookup"><span data-stu-id="058ae-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="058ae-135">Den repræsenterer potentielle interesser og tilhørsforhold for mærker, som en kunde med en profil, der ligner denne kunde, kan have.</span><span class="sxs-lookup"><span data-stu-id="058ae-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="058ae-136">Du kan finde flere oplysninger i [Forbedre kundeprofiler med mærketilhørsforhold og interesser](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="058ae-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="058ae-137">**Mål:** Viser, hvis du har konfigureret et eller flere mål for en bestemt type: Målpunkter for kundeattribut.</span><span class="sxs-lookup"><span data-stu-id="058ae-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="058ae-138">De indeholder beregnede nøgletal omkring dine kunder på de enkelte kundeniveauer.</span><span class="sxs-lookup"><span data-stu-id="058ae-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="058ae-139">Du kan finde flere oplysninger under [Definér, og administrer målpunkter](measures.md).</span><span class="sxs-lookup"><span data-stu-id="058ae-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="058ae-140">**Tidslinje for aktivitet:** Viser, om du har konfigureret aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="058ae-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="058ae-141">Tidslinjevisningen indeholder de kronologiske sorteringsaktiviteter for denne kunde og starter med den seneste aktivitet.</span><span class="sxs-lookup"><span data-stu-id="058ae-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="058ae-142">Du kan finde flere oplysninger under [Kundeaktiviteter](activities.md).</span><span class="sxs-lookup"><span data-stu-id="058ae-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="058ae-143">Vælg **Tilbage til kunder** for at vende tilbage til kundens søgeside.</span><span class="sxs-lookup"><span data-stu-id="058ae-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="058ae-144">Næste trin</span><span class="sxs-lookup"><span data-stu-id="058ae-144">Next steps</span></span>

<span data-ttu-id="058ae-145">[Tilføj flere datakilder](data-sources.md), eller [opret kundesegmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="058ae-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]