---
title: Power Apps-connector
description: Forbind Power Apps med Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405410"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="677fc-103">Microsoft Power Apps-connector (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="677fc-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="677fc-104">Anbring samlede kundeprofiler i dine personlige apps med Power Apps.</span><span class="sxs-lookup"><span data-stu-id="677fc-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="677fc-105">Opret forbindelse mellem Power Apps og Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="677fc-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="677fc-106">Customer Insights er en af de mange [tilgængelige kilder til data i Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="677fc-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="677fc-107">Se Power Apps-dokumentationen for at få mere at vide om, hvordan du [føjer en dataforbindelse til en app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="677fc-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="677fc-108">Det anbefales, at du også gennemgår, [hvordan Power Apps bruger delegering til at håndtere store datasæt i lærred-apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="677fc-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="677fc-109">Tilgængelige objekter</span><span class="sxs-lookup"><span data-stu-id="677fc-109">Available entities</span></span>

<span data-ttu-id="677fc-110">Når du har tilføjet Customer Insights som dataforbindelse, kan du vælge følgende objekter i Power Apps:</span><span class="sxs-lookup"><span data-stu-id="677fc-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="677fc-111">Kunde: Hvis du vil bruge data fra en [samlet kundeprofil](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="677fc-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="677fc-112">Samlet kundeaktivitet: Hvis du vil se [aktivitetstidslinjen](activities.md) i appen.</span><span class="sxs-lookup"><span data-stu-id="677fc-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="677fc-113">Begrænsninger</span><span class="sxs-lookup"><span data-stu-id="677fc-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="677fc-114">Objekter, der kan hentes</span><span class="sxs-lookup"><span data-stu-id="677fc-114">Retrievable entities</span></span>

<span data-ttu-id="677fc-115">Du kan kun hente objekterne **Kunde**, **UnifiedActivity** og **Segmenter** via Power Apps-connectoren.</span><span class="sxs-lookup"><span data-stu-id="677fc-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="677fc-116">Andre objekter vises, fordi den underliggende connector understøtter dem gennem udløsere i Power Automate.</span><span class="sxs-lookup"><span data-stu-id="677fc-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="677fc-117">Delegering</span><span class="sxs-lookup"><span data-stu-id="677fc-117">Delegation</span></span>

<span data-ttu-id="677fc-118">Delegering fungerer for Kunde-objektet og UnifiedActivity-objektet.</span><span class="sxs-lookup"><span data-stu-id="677fc-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="677fc-119">Uddelegering for **Kunde**-objekt: Hvis du vil bruge et uddelegering til dette objekt, skal felterne indekseres i [Søg og filtrér](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="677fc-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="677fc-120">Delegering for **UnifiedActivity**: Delegering for dette objekt fungerer kun for felterne **ActivityId** og **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="677fc-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="677fc-121">Du kan finde flere oplysninger om delegering under [Power Apps-funktioner og -handlinger, der kan uddelegeres](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="677fc-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="677fc-122">Eksempel på gallerikontrolelement</span><span class="sxs-lookup"><span data-stu-id="677fc-122">Example gallery control</span></span>

<span data-ttu-id="677fc-123">Du kan f. eks. føje kundeprofiler til et [gallerikontrolelement](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="677fc-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="677fc-124">Føj et **Galleri**-kontrolelement til en app, som du opretter.</span><span class="sxs-lookup"><span data-stu-id="677fc-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="677fc-125">![Tilføje et gallerielement](media/connector-powerapps9.png "Tilføje et gallerielement")</span><span class="sxs-lookup"><span data-stu-id="677fc-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="677fc-126">Vælg **Kunde** som datakilde for elementer.</span><span class="sxs-lookup"><span data-stu-id="677fc-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="677fc-127">![Vælge en datakilde](media/choose-datasource-powerapps.png "Vælge en datakilde")</span><span class="sxs-lookup"><span data-stu-id="677fc-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="677fc-128">Du kan ændre datapanelet til højre for at vælge, hvilket felt for kundeobjektet, der skal vises i galleriet.</span><span class="sxs-lookup"><span data-stu-id="677fc-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="677fc-129">Hvis du vil have vist et felt fra den valgte kunde i galleriet, skal du udfylde tekstegenskaben for et navn: **{Name_of_the_gallery}.Valgt.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="677fc-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="677fc-130">Eksempel: Galleri1.Valgt.adresse1_by</span><span class="sxs-lookup"><span data-stu-id="677fc-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="677fc-131">Hvis du vil have vist den samlede tidslinje for en kunde, skal du tilføje et gallerielement og tilføje egenskaben Elementer: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="677fc-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="677fc-132">Eksempel: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="677fc-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
