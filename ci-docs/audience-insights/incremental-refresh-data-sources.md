---
title: Trinvis opdatering af Power Query-baserede datakilder
description: Opdater nye og opdaterede data for store datakilder baseret på Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405443"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="e1fa5-103">Trinvis opdatering af datakilder, der er baseret på Power Query</span><span class="sxs-lookup"><span data-stu-id="e1fa5-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="e1fa5-104">Den trinvise opdatering af datakilder giver følgende fordele:</span><span class="sxs-lookup"><span data-stu-id="e1fa5-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="e1fa5-105">**Hurtigere opdateringer** – Kun data, der er ændret, opdateres.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="e1fa5-106">Du kan f.eks. nøjes med at opdatere de seneste fem dage i et historisk datasæt.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="e1fa5-107">**Større pålidelighed** – Med mindre opdateringer har du ikke brug for at opretholde forbindelser til flygtige kildesystemer i så lang tid, hvilket mindsker risikoen for forbindelsesproblemer.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="e1fa5-108">**Reduceret ressourceforbrug** – Opdatering af et undersæt af dine samlede data giver mere effektiv brug af computerressourcer og reducerer det miljømæssige aftryk.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="e1fa5-109">Konfigurer trinvis opdatering</span><span class="sxs-lookup"><span data-stu-id="e1fa5-109">Configure incremental refresh</span></span>

<span data-ttu-id="e1fa5-110">Målgruppen Insights muliggør trinvis opdatering af datakilder, der importeres via Power Query, der understøtter den trinvise indsættelse.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="e1fa5-111">F.eks. Azure SQL-databaser med dato- og klokkeslætsfelter, som angiver, hvornår dataposterne sidst blev opdateret.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="e1fa5-112">[Oprette en ny datakilde, der er baseret på Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e1fa5-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="e1fa5-113">Angiv et navn til datakilden.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="e1fa5-114">Vælg en datakilde, der understøtter trinvis opdatering, f.eks. Azure SQL Database.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="e1fa5-115">Vælg de objekter eller tabeller, der skal indtages.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="e1fa5-116">Fuldfør transformationstrinnene, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="e1fa5-117">Vælg **Konfigurer** i dialogboksen **Konfigurer trinvis opdatering** for at åbne **Indstillinger for trinvis opdatering**.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="e1fa5-118">Hvis du vælger **Spring over**, vil datakilden opdatere hele datasættet.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="e1fa5-119">Du kan også anvende trinvis opdatering senere ved at redigere en eksisterende datakilde.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="e1fa5-120">I **Indstillinger for trinvis opdatering** konfigurerer du den trinvise opdatering for alle de objekter, du har valgt under oprettelsen af datakilden.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e1fa5-121">![Konfigurere objekter i en datakilde til trinvis opdatering](media/incremental-refresh-settings.png "Konfigurere objekter i en datakilde til trinvis opdatering")</span><span class="sxs-lookup"><span data-stu-id="e1fa5-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="e1fa5-122">Vælg et objekt, og angiv følgende oplysninger:</span><span class="sxs-lookup"><span data-stu-id="e1fa5-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="e1fa5-123">**Vælg primærnøglen**: Vælg en primærnøgle til objektet eller tabellen.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="e1fa5-124">**Definer feltet "sidst opdateret"**: I dette felt vises der kun attributter af typen dato eller klokkeslæt.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="e1fa5-125">Vælg en attribut, der angiver, hvornår posterne senest blev opdateret.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="e1fa5-126">Den bruges til at identificere de poster, der falder inden for den trinvise opdaterings tidsramme.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="e1fa5-127">**Søg efter opdateringer hver**: Angiv, hvor lang tid tidsrammen for den trinvise opdatering skal være.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="e1fa5-128">Vælg **Gem** for at fuldføre oprettelsen af datakilden.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="e1fa5-129">Den indledende dataopdatering vil være en fuld opdatering.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="e1fa5-130">Derefter sker den trinvise dataopdatering som konfigureret i forrige trin.</span><span class="sxs-lookup"><span data-stu-id="e1fa5-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>
