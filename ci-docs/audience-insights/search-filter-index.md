---
title: Søg og filtrér kundeprofiler
description: Find hurtigt oplysninger om samlede kundeprofiler, og filtrer efter angivne attributter.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270059"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="de1d9-103">Kundeprofiler: Indeks for søgning og filtrering</span><span class="sxs-lookup"><span data-stu-id="de1d9-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="de1d9-104">Resultatet af at samle dine kundedata er et kundeprofilobjekt, der giver en fælles visning af den samlede kundebase.</span><span class="sxs-lookup"><span data-stu-id="de1d9-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="de1d9-105">Hvis du hurtigt vil [finde oplysninger om en bestemt kunde eller gruppe af kunder](customer-profiles.md), kan du konfigurere **Søg**- og **Filter**-funktionerne på siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="de1d9-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="de1d9-106">Læs videre for at få mere at vide om, hvordan administratorer kan redigere attributterne på siden **Indeks for søgning og filtrering**, som er tilgængelig for brugere i forbindelse med søgning og filtrering.</span><span class="sxs-lookup"><span data-stu-id="de1d9-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="de1d9-107">![Søgefilter](media/search-filter.png "Søgefilter")</span><span class="sxs-lookup"><span data-stu-id="de1d9-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="de1d9-108">Tilføje felter og angive attributter</span><span class="sxs-lookup"><span data-stu-id="de1d9-108">Add fields and specify attributes</span></span>

<span data-ttu-id="de1d9-109">Hvis det er første gang, du definerer attributter, der kan søges efter, som administrator, skal du definere indekserede felter først.</span><span class="sxs-lookup"><span data-stu-id="de1d9-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="de1d9-110">Det anbefales, at du vælger alle attributterne, som brugerne kan benytte til at søge efter og filtrere kunder på siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="de1d9-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="de1d9-111">Du kan kun angive attributter, der findes i det kundeprofilobjekt, du har oprettet under datasamlingsprocessen.</span><span class="sxs-lookup"><span data-stu-id="de1d9-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="de1d9-112">Åbn siden **Kunder**, og vælg **Indeks for søgning og filtrering**.</span><span class="sxs-lookup"><span data-stu-id="de1d9-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="de1d9-113">Vælg **+ Tilføj** for at angive de indekserede felter.</span><span class="sxs-lookup"><span data-stu-id="de1d9-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="de1d9-114">På listen skal du vælge de attributter, du vil tilføje som indekserede felter.</span><span class="sxs-lookup"><span data-stu-id="de1d9-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="de1d9-115">Du kan altid tilføje flere attributter ved at vælge **Tilføj**.</span><span class="sxs-lookup"><span data-stu-id="de1d9-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="de1d9-116">Du kan også fjerne valgte attributter ved at vælge **Fjern**-symbolet.</span><span class="sxs-lookup"><span data-stu-id="de1d9-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="de1d9-117">Undersøge tabellen med indekserede kundefelter</span><span class="sxs-lookup"><span data-stu-id="de1d9-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="de1d9-118">Følgende oplysninger vises i tabellen.</span><span class="sxs-lookup"><span data-stu-id="de1d9-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="de1d9-119">**Navn**: Repræsenterer attributtens navn, som det vises i objektet Kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="de1d9-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="de1d9-120">**Datatype**: Angiver, om datatypen er en streng, et tal eller en dato.</span><span class="sxs-lookup"><span data-stu-id="de1d9-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="de1d9-121">**Inkluderet i søgning**: Angiver, om denne attribut kan bruges til at søge efter kunder på siden **Kunder** ved hjælp af feltet **Søg**.</span><span class="sxs-lookup"><span data-stu-id="de1d9-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="de1d9-122">**Tilføj filter**: Kontrolelement for at definere, hvordan denne attribut kan bruges til filtrering på siden **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="de1d9-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="de1d9-123">Redigering af filtreringsindstillinger for en given attribut</span><span class="sxs-lookup"><span data-stu-id="de1d9-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="de1d9-124">Menuen **Filter** på siden **Kunder** kan indeholde et varierende antal attributniveauer (f.eks. forskellige aldersgrupper til filtrering af kunder).</span><span class="sxs-lookup"><span data-stu-id="de1d9-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="de1d9-125">Vælg **Tilføj filter** for en bestemt attribut på siden **Indeks for søgning og filtrering**.</span><span class="sxs-lookup"><span data-stu-id="de1d9-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="de1d9-126">Du kan definere antallet af resultater og den rækkefølge, de skal organiseres i.</span><span class="sxs-lookup"><span data-stu-id="de1d9-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="de1d9-127">Afhængig af attributtens datatype vises en af følgende ruder.</span><span class="sxs-lookup"><span data-stu-id="de1d9-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="de1d9-128">Attributter for strengtype: Angiv antallet af ønskede resultater i ruden **Indstillinger for strengfilter** og den rækkefølgepolitik, de skal være organiseret efter.</span><span class="sxs-lookup"><span data-stu-id="de1d9-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="de1d9-129">Numeriske attributter: Angiv intervallerne i ruden **Indstillinger for antalsfilter** og den rækkefølgepolitik, de skal være organiseret efter.</span><span class="sxs-lookup"><span data-stu-id="de1d9-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="de1d9-130">Datotypeattributter: Angiv intervallerne i ruden **Indstillinger for datofilter** og den rækkefølgepolitik, de skal være organiseret efter.</span><span class="sxs-lookup"><span data-stu-id="de1d9-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="de1d9-131">Vælg **Gem** for at anvende dine ændringer.</span><span class="sxs-lookup"><span data-stu-id="de1d9-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="de1d9-132">Vælg **Kør**, når du er klar til at anvende dine indstillinger.</span><span class="sxs-lookup"><span data-stu-id="de1d9-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="de1d9-133">Næste trin</span><span class="sxs-lookup"><span data-stu-id="de1d9-133">Next steps</span></span>

<span data-ttu-id="de1d9-134">Gå til siden **Kunder** for at søge efter kundeprofiler eller bruge de indekserede felter til at se et undersæt af alle kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="de1d9-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]