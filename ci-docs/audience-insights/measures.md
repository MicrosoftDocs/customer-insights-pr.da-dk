---
title: Oprette og administrere målinger
description: Definer foranstaltninger, der skal analysere og afspejle ydeevnen i virksomheden.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304782"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="f2a08-103">Definere og administrere målinger</span><span class="sxs-lookup"><span data-stu-id="f2a08-103">Define and manage measures</span></span>

<span data-ttu-id="f2a08-104">Foranstaltninger hjælper dig med at få en bedre forståelse af kundernes adfærd og virksomhedens præstation.</span><span class="sxs-lookup"><span data-stu-id="f2a08-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="f2a08-105">De ser på relevante værdier fra [ensartede profiler](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="f2a08-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="f2a08-106">En virksomhed vil f.eks. se det *samlede forbrug pr. kunde* for at forstå en enkelt kundes købsoversigt eller måle firmaets samlede salg for at forstå den *samlede omsætning i hele virksomheden*.</span><span class="sxs-lookup"><span data-stu-id="f2a08-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="f2a08-107">Målinger oprettes ved hjælp af målegeneratoren, en platform til dataforespørgsel med forskellige operatorer og simple tilknytningsindstillinger.</span><span class="sxs-lookup"><span data-stu-id="f2a08-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="f2a08-108">Du kan filtrere dataene, gruppere resultater, registrere [objektrelationsstier](relationships.md) og gennemse outputtet.</span><span class="sxs-lookup"><span data-stu-id="f2a08-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="f2a08-109">Brug målegeneratoren til at planlægge forretningsaktiviteter ved at forespørge om kundedata og udtrække indsigt.</span><span class="sxs-lookup"><span data-stu-id="f2a08-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="f2a08-110">Hvis du f.eks. opretter et mål for det *samlede forbrug pr. kunde* og det *samlede afkast pr. kunde*, kan du identificere en gruppe kunder med et højt forbrug, men et højt afkast.</span><span class="sxs-lookup"><span data-stu-id="f2a08-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="f2a08-111">Du kan [oprette et segment](segments.md) for at opnå de bedste handlinger.</span><span class="sxs-lookup"><span data-stu-id="f2a08-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="f2a08-112">Opret din egen måling fra bunden</span><span class="sxs-lookup"><span data-stu-id="f2a08-112">Build your own measure from scratch</span></span>

<span data-ttu-id="f2a08-113">Dette afsnit indeholder en gennemgang af, hvordan du opretter en ny måling fra bunden.</span><span class="sxs-lookup"><span data-stu-id="f2a08-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="f2a08-114">Du kan oprette en måling med dataattributter fra dataobjekter, der har en relation konfigureret til at oprette forbindelse til objektet Kunde.</span><span class="sxs-lookup"><span data-stu-id="f2a08-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="f2a08-115">Gå til **Målinger** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="f2a08-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="f2a08-116">Vælg **Ny**, og vælg **Opret din egen**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="f2a08-117">Vælg **Rediger navn**, og angiv et **Navn** til målingen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="f2a08-118">Hvis konfigurationen af den nye måling kun indeholder to felter, f.eks. CustomerID og én beregning, tilføjes outputtet som en ny kolonne i det systemgenererede objekt, der kaldes Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="f2a08-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="f2a08-119">Du kan også se målingens værdi i den samlede kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="f2a08-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="f2a08-120">Andre foranstaltninger opretter deres egne objekter.</span><span class="sxs-lookup"><span data-stu-id="f2a08-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="f2a08-121">Vælg aggregeringsfunktionen i rullemenuen **Vælg funktion** i konfigurationsområdet.</span><span class="sxs-lookup"><span data-stu-id="f2a08-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="f2a08-122">Aggregeringsfunktionerne omfatter:</span><span class="sxs-lookup"><span data-stu-id="f2a08-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="f2a08-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="f2a08-123">**Sum**</span></span>
   - <span data-ttu-id="f2a08-124">**Gennemsnitlig**</span><span class="sxs-lookup"><span data-stu-id="f2a08-124">**Average**</span></span>
   - <span data-ttu-id="f2a08-125">**Tælling**</span><span class="sxs-lookup"><span data-stu-id="f2a08-125">**Count**</span></span>
   - <span data-ttu-id="f2a08-126">**Antal entydige**</span><span class="sxs-lookup"><span data-stu-id="f2a08-126">**Count Unique**</span></span>
   - <span data-ttu-id="f2a08-127">**Maks.**</span><span class="sxs-lookup"><span data-stu-id="f2a08-127">**Max**</span></span>
   - <span data-ttu-id="f2a08-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="f2a08-128">**Min**</span></span>
   - <span data-ttu-id="f2a08-129">**Først**: Tager den første værdi af dataposten</span><span class="sxs-lookup"><span data-stu-id="f2a08-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="f2a08-130">**Sidste**: Tager den sidste værdi, der er tilføjet dataposten</span><span class="sxs-lookup"><span data-stu-id="f2a08-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operatorer til måleberegninger.":::

1. <span data-ttu-id="f2a08-132">Vælg **Tilføj attribut** for at vælge de data, du skal bruge for at oprette denne måling.</span><span class="sxs-lookup"><span data-stu-id="f2a08-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="f2a08-133">Vælg fanen **Attributter**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="f2a08-134">Dataobjekt: Vælg det objekt, der indeholder den attribut, du vil måle.</span><span class="sxs-lookup"><span data-stu-id="f2a08-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="f2a08-135">Dataattribut: Vælg den attribut, du vil bruge i aggregeringsfunktionen for at beregne målingen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="f2a08-136">Du kan kun vælge én attribut ad gangen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="f2a08-137">Du kan også vælge en dataattribut fra en eksisterende måleenhed ved at vælge fanen **Mål**. Du kan også søge efter navnet på et objekt eller en måleenhed.</span><span class="sxs-lookup"><span data-stu-id="f2a08-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="f2a08-138">Vælg **Tilføj** for at føje den valgte attribut til målingen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Vælg en attribut, der skal bruges i beregninger.":::

1. <span data-ttu-id="f2a08-140">Hvis du vil oprette mere komplekse målinger, kan du tilføje flere attributter eller bruge matematikoperatorer på målfunktionen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Opret en kompleks måling med matematikoperatorer.":::

1. <span data-ttu-id="f2a08-142">Hvis du vil tilføje filtre, skal du vælge **Filter** i konfigurationsområdet.</span><span class="sxs-lookup"><span data-stu-id="f2a08-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="f2a08-143">Vælg den attribut, du vil bruge til at oprette filtre, i sektionen **Tilføj attribut** i ruden **Filtre**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="f2a08-144">Angiv filteroperatørerne for at definere filteret for alle valgte attributter.</span><span class="sxs-lookup"><span data-stu-id="f2a08-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="f2a08-145">Vælg **Tilføj** for at tilføje filtrene til målingen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="f2a08-146">Hvis du vil tilføje dimensioner, skal du vælge **Dimension** i konfigurationsområdet.</span><span class="sxs-lookup"><span data-stu-id="f2a08-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="f2a08-147">Dimensionerne vises som kolonner i objektet til måling af output.</span><span class="sxs-lookup"><span data-stu-id="f2a08-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="f2a08-148">Vælg **Rediger dimensioner** for at tilføje dataattributter, som du vil gruppere måleværdierne efter.</span><span class="sxs-lookup"><span data-stu-id="f2a08-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="f2a08-149">Det kan f.eks. være by eller køn.</span><span class="sxs-lookup"><span data-stu-id="f2a08-149">For example, city or gender.</span></span> <span data-ttu-id="f2a08-150">Som standard vælges dimensionen *CustomerID* for at oprette *mål på kundeniveau*.</span><span class="sxs-lookup"><span data-stu-id="f2a08-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="f2a08-151">Du kan fjerne standarddimensionen, hvis du vil oprette *mål på virksomhedsniveau*.</span><span class="sxs-lookup"><span data-stu-id="f2a08-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="f2a08-152">Vælg **Gennemført** for at tilføje dimensioner til målingen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="f2a08-153">Hvis der er værdier i dataene, som skal erstattes af et heltal, f.eks. erstat *null* med *0*, skal du vælge **Regler**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="f2a08-154">Konfigurer reglen, og sørg for kun at vælge hele tal som erstatninger.</span><span class="sxs-lookup"><span data-stu-id="f2a08-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="f2a08-155">Hvis der er flere stier mellem det dataobjekt, du har tilknyttet, og objektet *Kunde*, skal du vælge en af de identificerede [objektrelationsstier](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="f2a08-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="f2a08-156">Måleresultater kan variere, afhængigt af den valgte sti.</span><span class="sxs-lookup"><span data-stu-id="f2a08-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="f2a08-157">Vælg **Dataindstillinger**, og vælg den objektsti, der skal bruges til at identificere din måling.</span><span class="sxs-lookup"><span data-stu-id="f2a08-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="f2a08-158">Hvis der kun er en enkelt sti til objektet *Kunde*, vises dette kontrolelement ikke.</span><span class="sxs-lookup"><span data-stu-id="f2a08-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="f2a08-159">Vælg **Udført** for at anvende det valgte.</span><span class="sxs-lookup"><span data-stu-id="f2a08-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Vælg objektsti til målingen.":::

1. <span data-ttu-id="f2a08-161">Hvis du vil tilføje flere beregninger for målingen, skal du vælge **Ny beregning**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="f2a08-162">Du kan kun bruge objekter på samme objektsti til nye beregninger.</span><span class="sxs-lookup"><span data-stu-id="f2a08-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="f2a08-163">Flere beregninger vises som nye kolonner i objektet til måling af output.</span><span class="sxs-lookup"><span data-stu-id="f2a08-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="f2a08-164">Vælg **...** i beregningen at **Dupliker**, **Omdøb** eller **Fjern** for en beregning fra en måleenhed.</span><span class="sxs-lookup"><span data-stu-id="f2a08-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="f2a08-165">I området **Prøveversion** kan du se dataskemaet for outputobjektet for måleenheden, herunder filtre og dimensioner.</span><span class="sxs-lookup"><span data-stu-id="f2a08-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="f2a08-166">Prøveversionen reagerer dynamisk på ændringer i konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="f2a08-167">Vælg **Kør** for at beregne resultaterne for det konfigurerede mål.</span><span class="sxs-lookup"><span data-stu-id="f2a08-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="f2a08-168">Vælg **Gem og luk**, hvis du vil bevare den aktuelle konfiguration og køre målingen senere.</span><span class="sxs-lookup"><span data-stu-id="f2a08-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="f2a08-169">Gå til **Målinger** for at se den måling, du netop har oprettet, på listen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="f2a08-170">Bruge en skabelon til at oprette en måleenhed</span><span class="sxs-lookup"><span data-stu-id="f2a08-170">Use a template to build a measure</span></span>

<span data-ttu-id="f2a08-171">Du kan bruge foruddefinerede skabeloner med almindeligt anvendte foranstaltninger til at oprette dem.</span><span class="sxs-lookup"><span data-stu-id="f2a08-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="f2a08-172">Detaljerede beskrivelser af skabelonerne og en styret oplevelse hjælper dig med at oprette effektive måleenheder.</span><span class="sxs-lookup"><span data-stu-id="f2a08-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="f2a08-173">Skabeloner bygger på tilknyttede data fra objektet *Unified Activity*.</span><span class="sxs-lookup"><span data-stu-id="f2a08-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="f2a08-174">Sørg derfor for, at du har konfigureret [kundeaktiviteter](activities.md), før du opretter en måleenhed ud fra en skabelon.</span><span class="sxs-lookup"><span data-stu-id="f2a08-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="f2a08-175">Tilgængelige måleskabeloner.</span><span class="sxs-lookup"><span data-stu-id="f2a08-175">Available measure templates:</span></span> 
- <span data-ttu-id="f2a08-176">Gennemsnitlig transaktionsværdi (ATV)</span><span class="sxs-lookup"><span data-stu-id="f2a08-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="f2a08-177">Samlet transaktionsværdi</span><span class="sxs-lookup"><span data-stu-id="f2a08-177">Total transaction value</span></span>
- <span data-ttu-id="f2a08-178">Gennemsnitlig dagsomsætning</span><span class="sxs-lookup"><span data-stu-id="f2a08-178">Average daily revenue</span></span>
- <span data-ttu-id="f2a08-179">Gennemsnitlig åromsætning</span><span class="sxs-lookup"><span data-stu-id="f2a08-179">Average yearly revenue</span></span>
- <span data-ttu-id="f2a08-180">Antal transaktioner</span><span class="sxs-lookup"><span data-stu-id="f2a08-180">Transaction count</span></span>
- <span data-ttu-id="f2a08-181">Optjente loyalitetspoint</span><span class="sxs-lookup"><span data-stu-id="f2a08-181">Loyalty points earned</span></span>
- <span data-ttu-id="f2a08-182">Indløste loyalitetspoint</span><span class="sxs-lookup"><span data-stu-id="f2a08-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="f2a08-183">Saldo for loyalitetspoint</span><span class="sxs-lookup"><span data-stu-id="f2a08-183">Loyalty points balance</span></span>
- <span data-ttu-id="f2a08-184">Aktiv kundelevetid</span><span class="sxs-lookup"><span data-stu-id="f2a08-184">Active customer lifespan</span></span>
- <span data-ttu-id="f2a08-185">Varighed af medlemskab for loyalitetskunde</span><span class="sxs-lookup"><span data-stu-id="f2a08-185">Loyalty membership duration</span></span>
- <span data-ttu-id="f2a08-186">Tid siden seneste køb</span><span class="sxs-lookup"><span data-stu-id="f2a08-186">Time since last purchase</span></span>

<span data-ttu-id="f2a08-187">I følgende procedure beskrives trinnene til opbygning af en ny måleenhed ved hjælp af en skabelon.</span><span class="sxs-lookup"><span data-stu-id="f2a08-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="f2a08-188">Gå til **Målinger** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="f2a08-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="f2a08-189">Vælg **Ny**, og vælg **Vælg en skabelon**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Skærmbillede af rullemenuen, når du opretter en ny måleenhed med fremhævning på skabelon.":::

1. <span data-ttu-id="f2a08-191">Find den skabelon, der passer til dine behov, og vælg **Vælg skabelon**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="f2a08-192">Gennemse de nødvendige data, og vælg **Start her**, hvis alle dataene er på plads.</span><span class="sxs-lookup"><span data-stu-id="f2a08-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="f2a08-193">Angiv navnet på målingen og outputobjektet i ruden **Rediger navn**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="f2a08-194">Vælg **Udført**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-194">Select **Done**.</span></span>

1. <span data-ttu-id="f2a08-195">Definer tidsrammen for de data, der skal bruges i **Angiv tidsperiode**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="f2a08-196">Vælg, om den nye måleenhed skal dække hele datasæt, ved at vælge **Alle tider**, eller hvis målingen skal fokusere på en **Bestemt tidsperiode**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Skærmbillede, der viser sektionen tidsperiode, når du konfigurerer en måling ud fra en skabelon.":::

1. <span data-ttu-id="f2a08-198">I næste afsnit skal du vælge **Tilføj data** for at vælge aktiviteterne og tilknytte de tilhørende data fra objektet *Unified Activity*.</span><span class="sxs-lookup"><span data-stu-id="f2a08-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="f2a08-199">Trin 1 af 2: Vælg den type objekt, du vil bruge under **Aktivitetstype**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="f2a08-200">I forbindelse med **Aktiviteter** skal du markere de objekter, du vil tilknytte.</span><span class="sxs-lookup"><span data-stu-id="f2a08-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="f2a08-201">Trin 2 af 2: Vælg attributten fra objektet *Unified Activity* for den komponent, der kræves af formlen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="f2a08-202">I forbindelse med gennemsnitlig transaktionsværdi er det f.eks. den attribut, der repræsenterer transaktionsværdien.</span><span class="sxs-lookup"><span data-stu-id="f2a08-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="f2a08-203">I forbindelse med **Aktivitetstidsstempel** skal du vælge attributten fra objektet Unified Activity, der repræsenterer dato og klokkeslæt for aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="f2a08-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="f2a08-204">Når datatilknytningen er vellykket, kan du se status som **Fuldført** og navnet på de tilknyttede aktiviteter og attributter.</span><span class="sxs-lookup"><span data-stu-id="f2a08-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Skærmbillede af konfigurationen af skabelonen til en fuldført måling.":::

1. <span data-ttu-id="f2a08-206">Du kan nu vælge **Kør** for at beregne resultaterne af målingen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="f2a08-207">Hvis du vil finjustere den senere, skal du vælge **Gem kladde**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="f2a08-208">Administrere dine målinger</span><span class="sxs-lookup"><span data-stu-id="f2a08-208">Manage your measures</span></span>

<span data-ttu-id="f2a08-209">Du kan finde listen over mål på siden **Målinger**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="f2a08-210">Du kan finde oplysninger om målingstype, oprettelsesdato, status og tilstand.</span><span class="sxs-lookup"><span data-stu-id="f2a08-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="f2a08-211">Når du vælger et mål på listen, kan du gennemse outputtet og hente en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="f2a08-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="f2a08-212">Hvis du vil opdatere alle dine målinger på én gang, skal du vælge **Opdater alle** uden at vælge en bestemt måling.</span><span class="sxs-lookup"><span data-stu-id="f2a08-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f2a08-213">![Handlinger til administration af enkelte målinger.](media/measure-actions.png "Handlinger til administration af enkelte målinger.")</span><span class="sxs-lookup"><span data-stu-id="f2a08-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="f2a08-214">Vælg en måling på listen for følgende indstillinger:</span><span class="sxs-lookup"><span data-stu-id="f2a08-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="f2a08-215">Vælg målingens navn for at se detaljer om den.</span><span class="sxs-lookup"><span data-stu-id="f2a08-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="f2a08-216">**Rediger** konfigurationen af målingen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="f2a08-217">**Opdater** målingen på baggrund af de seneste data.</span><span class="sxs-lookup"><span data-stu-id="f2a08-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="f2a08-218">**Omdøb** målingen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-218">**Rename** the measure.</span></span>
- <span data-ttu-id="f2a08-219">**Slet** målingen.</span><span class="sxs-lookup"><span data-stu-id="f2a08-219">**Delete** the measure.</span></span>
- <span data-ttu-id="f2a08-220">**Aktivere** eller **deaktivere**.</span><span class="sxs-lookup"><span data-stu-id="f2a08-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="f2a08-221">Inaktive målinger opdateres ikke under en [planlagt opdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f2a08-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="f2a08-222">Opgaver og processer indeholder [seks typer status](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="f2a08-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f2a08-223">De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f2a08-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f2a08-224">Du kan vælge status for en proces for at se statusdetaljer for hele jobbet.</span><span class="sxs-lookup"><span data-stu-id="f2a08-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f2a08-225">Når du har valgt **Se detaljer** for en af jobbets opgaver, finder du yderligere oplysninger: behandlingstid, sidste behandlingsdato og alle fejl og advarsler, der er knyttet til opgaven.</span><span class="sxs-lookup"><span data-stu-id="f2a08-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="f2a08-226">Næste trin</span><span class="sxs-lookup"><span data-stu-id="f2a08-226">Next step</span></span>

<span data-ttu-id="f2a08-227">Du kan bruge eksisterende mål til at oprette [et kundesegment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f2a08-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
