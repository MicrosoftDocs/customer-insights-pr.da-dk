---
title: Objekter og datasæt
description: Få vist data på siden objekter.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049387"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="2c76b-103">Objekter i målgruppeindsigt</span><span class="sxs-lookup"><span data-stu-id="2c76b-103">Entities in audience insights</span></span>

<span data-ttu-id="2c76b-104">Når du har [konfigureret datakilderne](data-sources.md), skal du gå til siden **Objekter** for at vurdere kvaliteten af de data, der er indtaget.</span><span class="sxs-lookup"><span data-stu-id="2c76b-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="2c76b-105">Objekter anses for at være datasæt.</span><span class="sxs-lookup"><span data-stu-id="2c76b-105">Entities are considered datasets.</span></span> <span data-ttu-id="2c76b-106">Flere funktioner i Dynamics 365 Customer Insights er opbygget omkring disse objekter.</span><span class="sxs-lookup"><span data-stu-id="2c76b-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="2c76b-107">Hvis du gennemgår dem nøje, kan du bedre validere outputtet af disse funktioner.</span><span class="sxs-lookup"><span data-stu-id="2c76b-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="2c76b-108">På siden **Objekter** vises objekter, og der findes flere kolonner:</span><span class="sxs-lookup"><span data-stu-id="2c76b-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="2c76b-109">**Navn**: Navnet på dataobjektet.</span><span class="sxs-lookup"><span data-stu-id="2c76b-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="2c76b-110">Hvis du får vist et advarselssymbol ud for et objektnavn, betyder det, at dataene for det pågældende objekt ikke blev indlæst korrekt.</span><span class="sxs-lookup"><span data-stu-id="2c76b-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="2c76b-111">**Kilde**: Den type af datakilde, der har indtaget objektet</span><span class="sxs-lookup"><span data-stu-id="2c76b-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="2c76b-112">**Oprettet af**: Navnet på den person, der oprettede objektet</span><span class="sxs-lookup"><span data-stu-id="2c76b-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="2c76b-113">**Oprettet**: Dato og klokkeslæt for oprettelse af objektet</span><span class="sxs-lookup"><span data-stu-id="2c76b-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="2c76b-114">**Opdateret af**: Navnet på den person, der opdaterede objektet</span><span class="sxs-lookup"><span data-stu-id="2c76b-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="2c76b-115">**Senest opdateret**: Dato og klokkeslæt for seneste opdatering af objektet</span><span class="sxs-lookup"><span data-stu-id="2c76b-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="2c76b-116">**Seneste opdatering**: Dato og klokkeslæt for den seneste dataopdatering</span><span class="sxs-lookup"><span data-stu-id="2c76b-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="2c76b-117">Udforske et bestemt objekts data</span><span class="sxs-lookup"><span data-stu-id="2c76b-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="2c76b-118">Vælg et objekt for at udforske de forskellige felter og poster, der findes i det pågældende objekt.</span><span class="sxs-lookup"><span data-stu-id="2c76b-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2c76b-119">![Vælg et objekt](media/data-manager-entities-data.png "Vælge et objekt")</span><span class="sxs-lookup"><span data-stu-id="2c76b-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="2c76b-120">Under fanen **Data** vises en tabel med oplysninger om individuelle poster i objektet.</span><span class="sxs-lookup"><span data-stu-id="2c76b-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2c76b-121">![Tabellen Felter](media/data-manager-entities-fields.PNG "Tabellen Felter")</span><span class="sxs-lookup"><span data-stu-id="2c76b-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="2c76b-122">Fanen **Attributter** er valgt som standard, og der vises en tabel, hvor du kan gennemse detaljer om det valgte objekt, f.eks. feltnavne, datatyper og typer.</span><span class="sxs-lookup"><span data-stu-id="2c76b-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="2c76b-123">Kolonnen **Type** viser tilknyttede Common Data Model-typer, som enten identificeres automatisk af systemet eller [tilknyttes manuelt](map-entities.md) af brugere.</span><span class="sxs-lookup"><span data-stu-id="2c76b-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="2c76b-124">Disse er semantiske typer, der kan være forskellige fra datatyperne for attributter – f.eks. har feltet *Email* herunder datatypen *Tekst*, men dets (semantiske) Common Data Model -type kan f.eks. være *Email* eller *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="2c76b-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="2c76b-125">I begge tabeller vises der kun et eksempel på objektets data.</span><span class="sxs-lookup"><span data-stu-id="2c76b-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="2c76b-126">Hvis du vil have vist det komplette datasæt, skal du gå til siden **Datakilder**, vælge et objekt, vælge **Rediger** og derefter få vist dette objekts data med Power Query-editoren som forklaret under [Datakilder](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="2c76b-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="2c76b-127">Hvis du vil have mere at vide om de data, der indtages i objektet, kan du finde nogle vigtige karakteristika for dataene i kolonnen **Oversigt**, f.eks. null-værdier, manglende værdier, entydige værdier, antal og fordelinger, som det er relevant for dine data.</span><span class="sxs-lookup"><span data-stu-id="2c76b-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="2c76b-128">Vælg ikonet for diagrammet for at få vist en oversigt over dataene.</span><span class="sxs-lookup"><span data-stu-id="2c76b-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2c76b-129">![Symbol for oversigt](media/data-manager-entities-summary.png "Dataoversigtstabel")</span><span class="sxs-lookup"><span data-stu-id="2c76b-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="2c76b-130">Næste trin</span><span class="sxs-lookup"><span data-stu-id="2c76b-130">Next step</span></span>

<span data-ttu-id="2c76b-131">Se emnet [Samle](data-unification.md) for at lære at *tilknytte*, *matche* og *flette* de data, der er indtaget.</span><span class="sxs-lookup"><span data-stu-id="2c76b-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
