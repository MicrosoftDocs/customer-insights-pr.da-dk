---
title: Forhold mellem objekter og objektstier
description: Opret og administrer forhold mellem objekter fra flere datakilder.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405454"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="305ed-103">Relationer mellem objekter</span><span class="sxs-lookup"><span data-stu-id="305ed-103">Relationships between entities</span></span>

<span data-ttu-id="305ed-104">Relationer hjælper dig med at oprette forbindelse mellem objekter og oprette en graf over dine data, når objekter deler en fælles identifikator (fremmed nøgle), der kan henvises til fra et objekt til et andet.</span><span class="sxs-lookup"><span data-stu-id="305ed-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="305ed-105">Forbundne objekter giver dig mulighed for at definere segmenter og målinger, der er baseret på flere datakilder.</span><span class="sxs-lookup"><span data-stu-id="305ed-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="305ed-106">Der findes to typer relationer.</span><span class="sxs-lookup"><span data-stu-id="305ed-106">There are two types of relationships.</span></span> <span data-ttu-id="305ed-107">ikke-redigerbare systemrelationer, der oprettes automatisk, og brugerdefinerede relationer, som oprettes og konfigureres af brugere.</span><span class="sxs-lookup"><span data-stu-id="305ed-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="305ed-108">Under match- og fletteprocesserne oprettes systemrelationer i baggrunden baseret på intelligent matchning.</span><span class="sxs-lookup"><span data-stu-id="305ed-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="305ed-109">Disse relationer hjælper med at relatere kundeprofilposter til andre tilsvarende objekters poster.</span><span class="sxs-lookup"><span data-stu-id="305ed-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="305ed-110">I følgende diagram illustreres oprettelsen af tre systemrelationer, når kundeobjektet matches med flere objekter for at producere det endelige kundeprofilobjekt.</span><span class="sxs-lookup"><span data-stu-id="305ed-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="305ed-111">![Oprettelse af relation](media/relationships-entities-merge.png "Oprettelse af relation")</span><span class="sxs-lookup"><span data-stu-id="305ed-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="305ed-112">\***CustomerToContact\*-relationen** blev oprettet mellem kundeobjektet og kontaktobjektet.</span><span class="sxs-lookup"><span data-stu-id="305ed-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="305ed-113">Kundeobjektet får nøglefeltet **Contact_contactId** til at relatere til nøglefeltet **contactId** for kontaktobjektet.</span><span class="sxs-lookup"><span data-stu-id="305ed-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="305ed-114">**_CustomerToAccount_-relationen** blev oprettet mellem kundeobjektet og kontoobjektet.</span><span class="sxs-lookup"><span data-stu-id="305ed-114">**_CustomerToAccount_ relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="305ed-115">Kundeobjektet får nøglefeltet **Account_accountId** til at relatere til nøglefeltet **accountId** for kontoobjektet.</span><span class="sxs-lookup"><span data-stu-id="305ed-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="305ed-116">**_CustomerToWebAccount_-relationen** blev oprettet mellem kundeobjektet og webkontoobjektet.</span><span class="sxs-lookup"><span data-stu-id="305ed-116">**_CustomerToWebAccount_ relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="305ed-117">Kundeobjektet får nøglefeltet **WebAccount_webaccountId** til at relatere til nøglefeltet **webaccountId** for webkontoobjektet.</span><span class="sxs-lookup"><span data-stu-id="305ed-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="305ed-118">Oprette en relation</span><span class="sxs-lookup"><span data-stu-id="305ed-118">Create a relationship</span></span>

<span data-ttu-id="305ed-119">Definer tilpassede relationer på siden **Relationer**.</span><span class="sxs-lookup"><span data-stu-id="305ed-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="305ed-120">Hver relation består af et kildeobjekt (det objekt, der indeholder den fremmede nøgle) og et målobjekt (det objekt, som kildeobjektets fremmede nøgle peger på).</span><span class="sxs-lookup"><span data-stu-id="305ed-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="305ed-121">Gå til **Data** > **Forhold** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="305ed-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="305ed-122">Vælg **Ny relation**.</span><span class="sxs-lookup"><span data-stu-id="305ed-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="305ed-123">Angiv følgende oplysninger i ruden **Tilføj relation**:</span><span class="sxs-lookup"><span data-stu-id="305ed-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="305ed-124">![Angive relationsdetaljer](media/relationships-add.png "Angive relationsdetaljer")</span><span class="sxs-lookup"><span data-stu-id="305ed-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="305ed-125">**Navn på relation**: Navn, der afspejler formålet med relationen (f.eks. **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="305ed-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="305ed-126">**Beskrivelse**: Beskrivelsen af relationen.</span><span class="sxs-lookup"><span data-stu-id="305ed-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="305ed-127">**Kildeobjekt**: Vælg det objekt, der bruges som kilde i relationen (f.eks. WebLog).</span><span class="sxs-lookup"><span data-stu-id="305ed-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="305ed-128">**Kardinalitet**: Vælg kardinaliteten for kildeobjektposterne.</span><span class="sxs-lookup"><span data-stu-id="305ed-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="305ed-129">F.eks. betyder "mange", at flere weblogposter er relateret til én webkonto.</span><span class="sxs-lookup"><span data-stu-id="305ed-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="305ed-130">**Kildenøglefelt**: Det repræsenterer den fremmede nøgle i kildeobjektet.</span><span class="sxs-lookup"><span data-stu-id="305ed-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="305ed-131">WebLog indeholder f.eks. feltet **accountId** som fremmed nøgle.</span><span class="sxs-lookup"><span data-stu-id="305ed-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="305ed-132">**Målobjekt**: Vælg det objekt, der bruges som mål i relationen (f.eks. WebAccount).</span><span class="sxs-lookup"><span data-stu-id="305ed-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="305ed-133">**Målkardinalitet**: Vælg kardinaliteten for målobjektposterne.</span><span class="sxs-lookup"><span data-stu-id="305ed-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="305ed-134">F.eks. betyder "én", at flere weblogposter er relateret til én webkonto.</span><span class="sxs-lookup"><span data-stu-id="305ed-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="305ed-135">**Målnøglefelt**: Dette felt repræsenterer nøglefeltet for målobjektet.</span><span class="sxs-lookup"><span data-stu-id="305ed-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="305ed-136">WebAccount indeholder f.eks. nøglefeltet **accountId**.</span><span class="sxs-lookup"><span data-stu-id="305ed-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="305ed-137">Det er kun mange-til-én- og én-til-én-relationer, der understøttes.</span><span class="sxs-lookup"><span data-stu-id="305ed-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="305ed-138">Mange-til-mange-relationer kan oprettes ved hjælp af to mange til én-relationer og et linkobjekt (et objekt, der bruges til at oprette forbindelse mellem kildeobjektet og målobjektet).</span><span class="sxs-lookup"><span data-stu-id="305ed-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="305ed-139">Slette en relation</span><span class="sxs-lookup"><span data-stu-id="305ed-139">Delete a relationship</span></span>

1. <span data-ttu-id="305ed-140">Gå til **Data** > **Forhold** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="305ed-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="305ed-141">Markér afkrydsningsfelterne ud for de relationer, der skal slettes.</span><span class="sxs-lookup"><span data-stu-id="305ed-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="305ed-142">Vælg **Slet** øverst i **Relationer**-tabellen.</span><span class="sxs-lookup"><span data-stu-id="305ed-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="305ed-143">Bekræft sletningen.</span><span class="sxs-lookup"><span data-stu-id="305ed-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="305ed-144">Næste trin</span><span class="sxs-lookup"><span data-stu-id="305ed-144">Next step</span></span>

<span data-ttu-id="305ed-145">System- og brugerdefinerede relationer bruges til at oprette segmenter baseret på flere datakilder, der ikke længere er i silo.</span><span class="sxs-lookup"><span data-stu-id="305ed-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="305ed-146">Du kan finde flere oplysninger under [Segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="305ed-146">For more information, see [Segments](segments.md).</span></span>
