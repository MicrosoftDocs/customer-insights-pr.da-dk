---
title: Forhold mellem objekter og objektstier
description: Opret og administrer forhold mellem objekter fra flere datakilder.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171157"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="7f6e8-103">Relationer mellem objekter</span><span class="sxs-lookup"><span data-stu-id="7f6e8-103">Relationships between entities</span></span>

<span data-ttu-id="7f6e8-104">Relationer forbinde objekter og definere en graf over dine data, når objekter deler et fælles id, en fremmednøgle.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="7f6e8-105">Der kan refereres til denne fremmednøgle fra et objekt til et andet.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="7f6e8-106">Forbundne objekter giver dig mulighed for at definere segmenter og målinger, der er baseret på flere datakilder.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="7f6e8-107">Der findes tre typer relationer:</span><span class="sxs-lookup"><span data-stu-id="7f6e8-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="7f6e8-108">Systemrelationer, som ikke kan redigeres. Disse oprettes af systemet som del af datasamlingen</span><span class="sxs-lookup"><span data-stu-id="7f6e8-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="7f6e8-109">Nedarvede relationer, som ikke kan redigeres. Disse oprettes automatisk ud fra indtagelse af datakilder</span><span class="sxs-lookup"><span data-stu-id="7f6e8-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="7f6e8-110">Brugerdefinerede relationer, der kan redigeres. Disse oprettes og konfigureres af brugere</span><span class="sxs-lookup"><span data-stu-id="7f6e8-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="7f6e8-111">Systemrelationer, der ikke kan redigeres</span><span class="sxs-lookup"><span data-stu-id="7f6e8-111">Non-editable system relationships</span></span>

<span data-ttu-id="7f6e8-112">Under datasamling oprettes systemrelationer automatisk baseret på intelligent matchning.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="7f6e8-113">Disse relationer hjælper med at relatere kundeprofilposter til tilsvarende poster.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="7f6e8-114">I følgende diagram illustreres oprettelsen af tre systembaserede relationer.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="7f6e8-115">Kundeobjektet matches med andre enheder for at producere den samlede *kundeenhed*.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram med relationsstier for kundeobjektet med tre 1-n-relationer.":::

- <span data-ttu-id="7f6e8-117">\***CustomerToContact\*-relationen** blev oprettet mellem objektet *Kunde* og objektet *Kontakt*.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="7f6e8-118">Objektet *Kunde* får nøglefeltet **Contact_contactID** til at relatere til nøglefeltet *contactID* for objektet **Kontakt**.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="7f6e8-119">\***CustomerToAccount\*-relationen** blev oprettet mellem objektet *Kunde* og objektet *Konto*.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="7f6e8-120">Objektet *Kunde* får nøglefeltet **Account_accountID** til at relatere til nøglefeltet *accountID* for objektet **Konto**.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="7f6e8-121">\***CustomerToWebAccount\*-relationen** blev oprettet mellem objektet *Kunde* og objektet *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="7f6e8-122">Objektet *Kunde* får nøglefeltet **WebAccount_webaccountID** til at relatere til nøglefeltet *webaccountID* for **WebAccount**.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="7f6e8-123">Nedarvede relationer, der ikke kan redigeres</span><span class="sxs-lookup"><span data-stu-id="7f6e8-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="7f6e8-124">Under dataindtagelsesprocessen kontrollerer systemet datakilder for eksisterende relationer.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="7f6e8-125">Hvis der ikke findes relationer, opretter systemet dem automatisk.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="7f6e8-126">Disse relationer anvendes også i downstream-processer.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="7f6e8-127">Oprette en brugerdefineret relation</span><span class="sxs-lookup"><span data-stu-id="7f6e8-127">Create a custom relationship</span></span>

<span data-ttu-id="7f6e8-128">Relationen består af et *kildeobjekt*, der indeholder fremmednøglen, og et *destinationsobjekt*, som kildeobjektets fremmednøgle peger på.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="7f6e8-129">Gå til **Data** > **Forhold** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="7f6e8-130">Vælg **Ny relation**.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="7f6e8-131">Angiv følgende oplysninger i ruden **Ny relation**:</span><span class="sxs-lookup"><span data-stu-id="7f6e8-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Rude på siden Ny relation med tomme inputfelter.":::

   - <span data-ttu-id="7f6e8-133">**Relationsnavn**: Navn, der afspejler relationens formål.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="7f6e8-134">Eksempel: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="7f6e8-135">**Beskrivelse**: Beskrivelsen af relationen.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="7f6e8-136">**Kildeobjekt**: Objekt, der bruges som kilde i relationen.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="7f6e8-137">Eksempel: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="7f6e8-138">**Målobjekt**: Objekt, der bruges som målet i relationen.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="7f6e8-139">Eksempel: Kunde.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-139">Example: Customer.</span></span>
   - <span data-ttu-id="7f6e8-140">**Kildekardinalitet**: Angiv kardinaliteten for kildeobjektet.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="7f6e8-141">Kardinalitet beskriver antallet af mulige elementer i et sæt.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="7f6e8-142">Det vedrører altid målets kardinalitet.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="7f6e8-143">Du kan vælge mellem **En** og **Mange**.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="7f6e8-144">Det er kun mange-til-én- og én-til-én-relationer, der understøttes.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="7f6e8-145">Mange-til-en: Flere kildeposter kan relateres til én målpost.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="7f6e8-146">Eksempel: Flere supportsager fra en enkelt kunde.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="7f6e8-147">En-til-en: En enkelt kildepost vedrører én målpost.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="7f6e8-148">Eksempel: Ét loyalitets-id for en enkelt kunde.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="7f6e8-149">Mange-til-mange-relationer kan oprettes ved hjælp af to mange-til-en-relationer og et sammenkædningsobjekt, der forbinder kildeobjektet og destinationsobjektet.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="7f6e8-150">**Målkardinalitet**: Vælg kardinaliteten for målobjektposterne.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="7f6e8-151">**Kildenøglefelt**: Feltet med fremmednøglen i kildeobjektet.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="7f6e8-152">Eksempel: SupportCase kan bruge CaseID som et fremmednøgle-felt.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="7f6e8-153">**Målnøglefelt**: Nøglefeltet for målobjektet.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="7f6e8-154">Eksempel: Kunde kan bruge nøglefeltet **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="7f6e8-155">Vælg **Gem** for at oprette den brugerdefinerede relation.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="7f6e8-156">Vise relationer</span><span class="sxs-lookup"><span data-stu-id="7f6e8-156">View relationships</span></span>

<span data-ttu-id="7f6e8-157">På siden Relationer vises alle de relationer, der er oprettet.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="7f6e8-158">Hver række repræsenterer en relation, som også indeholder oplysninger om kildeobjektet, målobjektet og kardinaliteten.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Liste over relationer og indstillinger på handlingslinjen på siden Relationer.":::

<span data-ttu-id="7f6e8-160">Denne side indeholder et sæt indstillinger for eksisterende og nye relationer:</span><span class="sxs-lookup"><span data-stu-id="7f6e8-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="7f6e8-161">**Ny relation**: [Opret en brugerdefineret relation](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="7f6e8-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="7f6e8-162">**Visualisering**: [Udforsk relationens visualiseringsfunktion](#explore-the-relationship-visualizer) for at få vist et netværksdiagram over de eksisterende relationer og deres kardinalitet.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="7f6e8-163">**Filtrer efter**: Vælg den type relationer, der skal vises på listen.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="7f6e8-164">**Søg efter relationer**: Brug en tekstbaseret søgning på egenskaberne for relationerne.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="7f6e8-165">Udforsk relationens visualiseringsfunktion</span><span class="sxs-lookup"><span data-stu-id="7f6e8-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="7f6e8-166">Relationens visualiseringsfunktion viser et netværksdiagram over de eksisterende relationer mellem tilsluttede objekter og deres kardinalitet.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="7f6e8-167">Hvis du vil tilpasse visningen, kan du ændre felternes placering ved at trække dem på lærredet.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Skærmbillede af netværksdiagrammet for relationens visualiseringsfunktion med forbindelser mellem relaterede objekter.":::

<span data-ttu-id="7f6e8-169">Tilgængelige indstillinger:</span><span class="sxs-lookup"><span data-stu-id="7f6e8-169">Available options:</span></span> 
- <span data-ttu-id="7f6e8-170">**Eksporter som billede**: Gem den aktuelle visning som en billedfil.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="7f6e8-171">**Skift til vandret/lodret layout**: Skift justering af enhederne og relationer.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="7f6e8-172">**Rediger**: Opdater egenskaber for brugerdefinerede relationer i redigeringsruden, og gem ændringerne.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="7f6e8-173">Administrer eksisterende relationer</span><span class="sxs-lookup"><span data-stu-id="7f6e8-173">Manage existing relationships</span></span> 

<span data-ttu-id="7f6e8-174">På siden Relationer repræsenteres hver relation af en række.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="7f6e8-175">Vælg en relation, og vælg en af følgende indstillinger:</span><span class="sxs-lookup"><span data-stu-id="7f6e8-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="7f6e8-176">**Rediger**: Opdater egenskaber for brugerdefinerede relationer i redigeringsruden, og gem ændringerne.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="7f6e8-177">**Slet**: Slet brugerdefinerede relationer.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="7f6e8-178">**Vis**: Få vist systemoprettede og nedarvede relationer.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="7f6e8-179">Næste trin</span><span class="sxs-lookup"><span data-stu-id="7f6e8-179">Next step</span></span>

<span data-ttu-id="7f6e8-180">System- og brugerdefinerede relationer bruges til at [oprette segmenter](segments.md) baseret på flere datakilder, der ikke længere er i en silo.</span><span class="sxs-lookup"><span data-stu-id="7f6e8-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
