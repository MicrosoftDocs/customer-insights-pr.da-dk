---
title: Oprette og administrere målinger
description: Definer foranstaltninger, der skal analysere og afspejle ydeevnen i virksomheden.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654725"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="15c75-103">Definere og administrere målinger</span><span class="sxs-lookup"><span data-stu-id="15c75-103">Define and manage measures</span></span>

<span data-ttu-id="15c75-104">Foranstaltninger hjælper dig med at få en bedre forståelse af kundeadfærd og virksomhedens ydeevne ved at hente relevante værdier fra [ensartede profiler](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="15c75-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="15c75-105">En virksomhed vil f.eks. se det *samlede forbrug pr. kunde* for at forstå den enkelte kundes købshistorik.</span><span class="sxs-lookup"><span data-stu-id="15c75-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="15c75-106">Du kan også måle *firmaets samlede* salg for at få en forståelse af den samlede omsætning i hele virksomheden.</span><span class="sxs-lookup"><span data-stu-id="15c75-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="15c75-107">Målinger oprettes ved hjælp af målegeneratoren, en platform til dataforespørgsel med forskellige operatorer og simple tilknytningsindstillinger.</span><span class="sxs-lookup"><span data-stu-id="15c75-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="15c75-108">Du kan filtrere dataene, gruppere resultater, registrere [objektrelationsstier](relationships.md) og gennemse outputtet.</span><span class="sxs-lookup"><span data-stu-id="15c75-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="15c75-109">Brug målegeneratoren til at planlægge forretningsaktiviteter ved at forespørge om kundedata og udtrække indsigt.</span><span class="sxs-lookup"><span data-stu-id="15c75-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="15c75-110">Hvis du f.eks. opretter et mål for det *samlede forbrug pr. kunde* og det *samlede afkast pr. kunde*, kan du identificere en gruppe kunder med et højt forbrug, men et højt afkast.</span><span class="sxs-lookup"><span data-stu-id="15c75-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="15c75-111">Du kan [oprette et segment](segments.md) for at opnå de bedste handlinger.</span><span class="sxs-lookup"><span data-stu-id="15c75-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="15c75-112">Oprette en måling</span><span class="sxs-lookup"><span data-stu-id="15c75-112">Create a measure</span></span>

<span data-ttu-id="15c75-113">Dette afsnit indeholder en gennemgang af, hvordan du opretter en ny måling fra bunden.</span><span class="sxs-lookup"><span data-stu-id="15c75-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="15c75-114">Du kan oprette en måling med dataattributter fra dataobjekter, der har en relation konfigureret til at oprette forbindelse til objektet Kunde.</span><span class="sxs-lookup"><span data-stu-id="15c75-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="15c75-115">Gå til **Målinger** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="15c75-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="15c75-116">Vælg **Ny**.</span><span class="sxs-lookup"><span data-stu-id="15c75-116">Select **New**.</span></span>

1. <span data-ttu-id="15c75-117">Vælg **Rediger navn**, og angiv et **Navn** til målingen.</span><span class="sxs-lookup"><span data-stu-id="15c75-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="15c75-118">Hvis konfigurationen af den nye måleenhed kun indeholder to felter, f.eks. CustomerID og én beregning, føjes outputtet som en ny kolonne til det systemgenererede objekt, der kaldes Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="15c75-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="15c75-119">Du kan også se målingens værdi i den samlede kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="15c75-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="15c75-120">Andre foranstaltninger opretter deres egne objekter.</span><span class="sxs-lookup"><span data-stu-id="15c75-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="15c75-121">Vælg aggregeringsfunktionen i rullemenuen **Vælg funktion** i konfigurationsområdet.</span><span class="sxs-lookup"><span data-stu-id="15c75-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="15c75-122">Aggregeringsfunktionerne omfatter:</span><span class="sxs-lookup"><span data-stu-id="15c75-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="15c75-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="15c75-123">**Sum**</span></span>
   - <span data-ttu-id="15c75-124">**Gennemsnitlig**</span><span class="sxs-lookup"><span data-stu-id="15c75-124">**Average**</span></span>
   - <span data-ttu-id="15c75-125">**Tælling**</span><span class="sxs-lookup"><span data-stu-id="15c75-125">**Count**</span></span>
   - <span data-ttu-id="15c75-126">**Antal entydige**</span><span class="sxs-lookup"><span data-stu-id="15c75-126">**Count Unique**</span></span>
   - <span data-ttu-id="15c75-127">**Maks.**</span><span class="sxs-lookup"><span data-stu-id="15c75-127">**Max**</span></span>
   - <span data-ttu-id="15c75-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="15c75-128">**Min**</span></span>
   - <span data-ttu-id="15c75-129">**Først**: Tager den første værdi af dataposten</span><span class="sxs-lookup"><span data-stu-id="15c75-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="15c75-130">**Sidste**: Tager den sidste værdi, der er tilføjet dataposten</span><span class="sxs-lookup"><span data-stu-id="15c75-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatorer til måleberegninger.":::

1. <span data-ttu-id="15c75-132">Vælg **Tilføj attribut** for at vælge de data, du skal bruge for at oprette denne måling.</span><span class="sxs-lookup"><span data-stu-id="15c75-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="15c75-133">Vælg fanen **Attributter**.</span><span class="sxs-lookup"><span data-stu-id="15c75-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="15c75-134">Dataobjekt: Vælg det objekt, der indeholder den attribut, du vil måle.</span><span class="sxs-lookup"><span data-stu-id="15c75-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="15c75-135">Dataattribut: Vælg den attribut, du vil bruge i aggregeringsfunktionen for at beregne målingen.</span><span class="sxs-lookup"><span data-stu-id="15c75-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="15c75-136">Du kan kun vælge én attribut ad gangen.</span><span class="sxs-lookup"><span data-stu-id="15c75-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="15c75-137">Du kan også vælge en dataattribut fra en eksisterende måleenhed ved at vælge fanen **Mål**. Du kan også søge efter navnet på et objekt eller en måleenhed.</span><span class="sxs-lookup"><span data-stu-id="15c75-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="15c75-138">Vælg **Tilføj** for at føje den valgte attribut til målingen.</span><span class="sxs-lookup"><span data-stu-id="15c75-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Vælg en attribut, der skal bruges i beregninger.":::

1. <span data-ttu-id="15c75-140">Hvis du vil oprette mere komplekse målinger, kan du tilføje flere attributter eller bruge matematikoperatorer på målfunktionen.</span><span class="sxs-lookup"><span data-stu-id="15c75-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Opret en kompleks måling med matematikoperatorer.":::

1. <span data-ttu-id="15c75-142">Hvis du vil tilføje filtre, skal du vælge **Filter** i konfigurationsområdet.</span><span class="sxs-lookup"><span data-stu-id="15c75-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="15c75-143">Vælg den attribut, du vil bruge til at oprette filtre, i sektionen **Tilføj attribut** i ruden **Filtre**.</span><span class="sxs-lookup"><span data-stu-id="15c75-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="15c75-144">Angiv filteroperatørerne for at definere filteret for alle valgte attributter.</span><span class="sxs-lookup"><span data-stu-id="15c75-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="15c75-145">Vælg **Tilføj** for at tilføje filtrene til målingen.</span><span class="sxs-lookup"><span data-stu-id="15c75-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="15c75-146">Hvis du vil tilføje dimensioner, skal du vælge **Dimension** i konfigurationsområdet.</span><span class="sxs-lookup"><span data-stu-id="15c75-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="15c75-147">Dimensionerne vises som kolonner i objektet til måling af output.</span><span class="sxs-lookup"><span data-stu-id="15c75-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="15c75-148">Vælg **Rediger dimensioner** for at tilføje dataattributter, som du vil gruppere måleværdierne efter.</span><span class="sxs-lookup"><span data-stu-id="15c75-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="15c75-149">Det kan f.eks. være by eller køn.</span><span class="sxs-lookup"><span data-stu-id="15c75-149">For example, city or gender.</span></span> <span data-ttu-id="15c75-150">Som standard vælges dimensionen *CustomerID* for at oprette *mål på kundeniveau*.</span><span class="sxs-lookup"><span data-stu-id="15c75-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="15c75-151">Du kan fjerne standarddimensionen, hvis du vil oprette *mål på virksomhedsniveau*.</span><span class="sxs-lookup"><span data-stu-id="15c75-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="15c75-152">Vælg **Gennemført** for at tilføje dimensioner til målingen.</span><span class="sxs-lookup"><span data-stu-id="15c75-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="15c75-153">Hvis der er flere stier mellem det dataobjekt, du har tilknyttet, og objektet *Kunde*, skal du vælge en af de identificerede [objektrelationsstier](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="15c75-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="15c75-154">Måleresultater kan variere, afhængigt af den valgte sti.</span><span class="sxs-lookup"><span data-stu-id="15c75-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="15c75-155">Vælg **Dataindstillinger**, og vælg den objektsti, der skal bruges til at identificere din måling.</span><span class="sxs-lookup"><span data-stu-id="15c75-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="15c75-156">Hvis der kun er en enkelt sti til objektet *Kunde*, vises dette kontrolelement ikke.</span><span class="sxs-lookup"><span data-stu-id="15c75-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="15c75-157">Vælg **Udført** for at anvende det valgte.</span><span class="sxs-lookup"><span data-stu-id="15c75-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Vælg objektsti til målingen.":::

1. <span data-ttu-id="15c75-159">Hvis du vil tilføje flere beregninger for målingen, skal du vælge **Ny beregning**.</span><span class="sxs-lookup"><span data-stu-id="15c75-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="15c75-160">Du kan kun bruge objekter på samme objektsti til nye beregninger.</span><span class="sxs-lookup"><span data-stu-id="15c75-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="15c75-161">Flere beregninger vises som nye kolonner i objektet til måling af output.</span><span class="sxs-lookup"><span data-stu-id="15c75-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="15c75-162">Vælg **...** i beregningen at **Dupliker**, **Omdøb** eller **Fjern** for en beregning fra en måleenhed.</span><span class="sxs-lookup"><span data-stu-id="15c75-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="15c75-163">I området **Prøveversion** kan du se dataskemaet for outputobjektet for måleenheden, herunder filtre og dimensioner.</span><span class="sxs-lookup"><span data-stu-id="15c75-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="15c75-164">Prøveversionen reagerer dynamisk på ændringer i konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="15c75-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="15c75-165">Vælg **Kør** for at beregne resultaterne for det konfigurerede mål.</span><span class="sxs-lookup"><span data-stu-id="15c75-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="15c75-166">Vælg **Gem og luk**, hvis du vil bevare den aktuelle konfiguration og køre målingen senere.</span><span class="sxs-lookup"><span data-stu-id="15c75-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="15c75-167">Gå til **Målinger** for at se den måling, du netop har oprettet, på listen.</span><span class="sxs-lookup"><span data-stu-id="15c75-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="15c75-168">Administrere dine målinger</span><span class="sxs-lookup"><span data-stu-id="15c75-168">Manage your measures</span></span>

<span data-ttu-id="15c75-169">Efter at [oprette en måling](#create-a-measure) vises en liste over målinger på siden **Målinger**.</span><span class="sxs-lookup"><span data-stu-id="15c75-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="15c75-170">Du kan finde oplysninger om målingstype, oprettelsesdato, status og tilstand.</span><span class="sxs-lookup"><span data-stu-id="15c75-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="15c75-171">Når du vælger en måling på listen, kan du gennemse outputtet og hente en .CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="15c75-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="15c75-172">Hvis du vil opdatere alle dine målinger på én gang, skal du vælge **Opdater alle** uden at vælge en bestemt måling.</span><span class="sxs-lookup"><span data-stu-id="15c75-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="15c75-173">![Handlinger til administration af enkelte målinger](media/measure-actions.png "Handlinger til administration af enkelte målinger")</span><span class="sxs-lookup"><span data-stu-id="15c75-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="15c75-174">Vælg en måling på listen for følgende indstillinger:</span><span class="sxs-lookup"><span data-stu-id="15c75-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="15c75-175">Vælg målingens navn for at se detaljer om den.</span><span class="sxs-lookup"><span data-stu-id="15c75-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="15c75-176">**Rediger** konfigurationen af målingen.</span><span class="sxs-lookup"><span data-stu-id="15c75-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="15c75-177">**Opdater** målingen på baggrund af de seneste data.</span><span class="sxs-lookup"><span data-stu-id="15c75-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="15c75-178">**Omdøb** målingen.</span><span class="sxs-lookup"><span data-stu-id="15c75-178">**Rename** the measure.</span></span>
- <span data-ttu-id="15c75-179">**Slet** målingen.</span><span class="sxs-lookup"><span data-stu-id="15c75-179">**Delete** the measure.</span></span>
- <span data-ttu-id="15c75-180">**Aktivere** eller **deaktivere**.</span><span class="sxs-lookup"><span data-stu-id="15c75-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="15c75-181">Inaktive målinger opdateres ikke under en [planlagt opdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="15c75-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="15c75-182">Opgaver og processer indeholder [seks typer status](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="15c75-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="15c75-183">De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="15c75-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="15c75-184">Du kan vælge status for en proces for at se statusdetaljer for hele jobbet.</span><span class="sxs-lookup"><span data-stu-id="15c75-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="15c75-185">Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.</span><span class="sxs-lookup"><span data-stu-id="15c75-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="15c75-186">Næste trin</span><span class="sxs-lookup"><span data-stu-id="15c75-186">Next step</span></span>

<span data-ttu-id="15c75-187">Du kan benytte eksisterende foranstaltninger til at oprette [et kundesegment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="15c75-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]