---
title: Eksempelvejledning til forudsigelse til produktanbefaling
description: Brug denne eksempelvejledning til at afprøve den indbyggede forudsigelsesmodel til produktanbefaling.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b136084316da5ae17a8428236381f69e5c21f9ea
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129892"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="80956-103">Eksempelvejledning til forudsigelse til produktanbefaling (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="80956-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="80956-104">Vi gennemgår fra start til slut et eksempel på forudsigelse af produktanbefaling ved hjælp af de eksempeldata, der er angivet nedenfor.</span><span class="sxs-lookup"><span data-stu-id="80956-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="80956-105">Scenarie</span><span class="sxs-lookup"><span data-stu-id="80956-105">Scenario</span></span>

<span data-ttu-id="80956-106">Contoso er en virksomhed, der producerer kaffemaskiner af høj kvalitet, som de sælger via deres Contoso Coffee-websted.</span><span class="sxs-lookup"><span data-stu-id="80956-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="80956-107">Deres mål er at forstå, hvilke produkter der skal anbefales til tilbagevendende kunder.</span><span class="sxs-lookup"><span data-stu-id="80956-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="80956-108">Hvis du ved, hvilke kunder der er **større sandsynlighed for at købe**, kan du hjælpe dem med at spare marketingindsatsen ved at fokusere på bestemte elementer.</span><span class="sxs-lookup"><span data-stu-id="80956-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80956-109">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="80956-109">Prerequisites</span></span>

- <span data-ttu-id="80956-110">Mindst [bidragydertilladelser](permissions.md) i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="80956-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="80956-111">Vi anbefaler, at du implementerer følgende trin [i et nyt miljø](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="80956-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="80956-112">Opgave 1 - Indsættelse af data</span><span class="sxs-lookup"><span data-stu-id="80956-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="80956-113">Gennemgå artiklerne [om indsættelse af data](data-sources.md) og [import af datakilder ved hjælp af Power Query-connectors](connect-power-query.md) specifikt.</span><span class="sxs-lookup"><span data-stu-id="80956-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="80956-114">I følgende oplysninger antages det, at du har generelt kendskab til indsættelse af data.</span><span class="sxs-lookup"><span data-stu-id="80956-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="80956-115">Indsættelse af kundedata fra eCommerce-platform</span><span class="sxs-lookup"><span data-stu-id="80956-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="80956-116">Opret en datakilde med navnet **eCommerce**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="80956-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="80956-117">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="80956-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="80956-118">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="80956-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="80956-119">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="80956-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="80956-120">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="80956-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="80956-121">**CreatedOn**: Dato/Klokkeslæt/Zone</span><span class="sxs-lookup"><span data-stu-id="80956-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformere fødselsdato til dato.":::

5. <span data-ttu-id="80956-123">Omdøb datakilde fra **Forespørgsel** til **eCommerceContacts** i feltet 'Navn' i ruden til højre.</span><span class="sxs-lookup"><span data-stu-id="80956-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="80956-124">**Gem** datakilden.</span><span class="sxs-lookup"><span data-stu-id="80956-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="80956-125">Indsættelse af online købsdata</span><span class="sxs-lookup"><span data-stu-id="80956-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="80956-126">Tilføj et andet datasæt til samme **eCommerce**-datakilde.</span><span class="sxs-lookup"><span data-stu-id="80956-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="80956-127">Vælg **Tekst/CSV**-connector igen.</span><span class="sxs-lookup"><span data-stu-id="80956-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="80956-128">Angiv URL-adressen til **onlinekøb**-data https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="80956-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="80956-129">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="80956-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="80956-130">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="80956-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="80956-131">**PurchasedOn**: Dato/Klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="80956-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="80956-132">**TotalPrice**: Valuta</span><span class="sxs-lookup"><span data-stu-id="80956-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="80956-133">Omdøb datakilde fra **Forespørgsel** til **eCommercePurchases** i feltet **Navn** i sideruden.</span><span class="sxs-lookup"><span data-stu-id="80956-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="80956-134">**Gem** datakilden.</span><span class="sxs-lookup"><span data-stu-id="80956-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="80956-135">Indsæt kundedata fra loyalitetsskemaet</span><span class="sxs-lookup"><span data-stu-id="80956-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="80956-136">Opret en datakilde med navnet **LoyaltyScheme**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="80956-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="80956-137">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="80956-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="80956-138">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="80956-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="80956-139">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="80956-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="80956-140">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="80956-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="80956-141">**RewardsPoints**: Heltal</span><span class="sxs-lookup"><span data-stu-id="80956-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="80956-142">**CreatedOn**: Dato/Klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="80956-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="80956-143">Omdøb datakilde fra **Forespørgsel** til **loyCustomers** i feltet **Navn** i ruden til højre.</span><span class="sxs-lookup"><span data-stu-id="80956-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="80956-144">**Gem** datakilden.</span><span class="sxs-lookup"><span data-stu-id="80956-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="80956-145">Opgave 2 - Datasamling</span><span class="sxs-lookup"><span data-stu-id="80956-145">Task 2 - Data unification</span></span>

<span data-ttu-id="80956-146">Når vi har indtaget dataene, begynder vi nu datasamlingen for at oprette en samlet kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="80956-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="80956-147">Du kan finde flere oplysninger i [Datasamling](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="80956-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="80956-148">Tilknytning</span><span class="sxs-lookup"><span data-stu-id="80956-148">Map</span></span>

1. <span data-ttu-id="80956-149">Når du har indsat dataene, skal du knytte kontakterne fra eCommerce- og Loyalty-data til almindelige datatyper.</span><span class="sxs-lookup"><span data-stu-id="80956-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="80956-150">Go to **Data** > **Saml** > **Tilknyt**.</span><span class="sxs-lookup"><span data-stu-id="80956-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="80956-151">Vælg de objekter, der repræsenterer kundeprofilen - **eCommerceContacts** og **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="80956-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![samle eCommerce- og loyalty-datakilder.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="80956-153">Vælg **ContactId** som primær nøgle for **eCommerceContacts** og **LoyaltyID** som primær nøgle for **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="80956-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Saml LoyaltyId som primær nøgle.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="80956-155">Resultat</span><span class="sxs-lookup"><span data-stu-id="80956-155">Match</span></span>

1. <span data-ttu-id="80956-156">Gå til fanen **Match**, og vælg **Angiv rækkefølge**.</span><span class="sxs-lookup"><span data-stu-id="80956-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="80956-157">Vælg **eCommerceContacts: eCommerce** som den primære kilde, og medtag alle poster i rullelisten **Primær**.</span><span class="sxs-lookup"><span data-stu-id="80956-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="80956-158">På rullelisten **Objekt 2** skal du vælge **loyCustomers: LoyaltyScheme** og inkludere alle poster.</span><span class="sxs-lookup"><span data-stu-id="80956-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Saml og match eCommerce og Loyalty.](media/unify-match-order.png)

4. <span data-ttu-id="80956-160">Vælg **Opret en ny regel**</span><span class="sxs-lookup"><span data-stu-id="80956-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="80956-161">Tilføj din første betingelse ved hjælp af FullName.</span><span class="sxs-lookup"><span data-stu-id="80956-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="80956-162">For eCommerceContacts skal du vælge **FullName** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="80956-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="80956-163">For loyCustomers skal du vælge **FullName** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="80956-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="80956-164">Vælg **Normaliser**-rullelisten, og vælg **Type (telefon, navn, adresse ...)**.</span><span class="sxs-lookup"><span data-stu-id="80956-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="80956-165">Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.</span><span class="sxs-lookup"><span data-stu-id="80956-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="80956-166">Angiv navnet **FullName, e-mail** til den nye regel.</span><span class="sxs-lookup"><span data-stu-id="80956-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="80956-167">Tilføj endnu en betingelse for e-mailadressen ved at vælge **Tilføj betingelse**</span><span class="sxs-lookup"><span data-stu-id="80956-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="80956-168">Vælg **E-mail** i rullelisten for objektet eCommerceContacts.</span><span class="sxs-lookup"><span data-stu-id="80956-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="80956-169">Vælg **E-mail** i rullelisten for objektet loyCustomers.</span><span class="sxs-lookup"><span data-stu-id="80956-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="80956-170">Lad Normaliser være tom.</span><span class="sxs-lookup"><span data-stu-id="80956-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="80956-171">Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.</span><span class="sxs-lookup"><span data-stu-id="80956-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Saml og match regel for navn og e-mail.](media/unify-match-rule.png)

7. <span data-ttu-id="80956-173">Vælg **Gem** og **Kør**.</span><span class="sxs-lookup"><span data-stu-id="80956-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="80956-174">Fletning</span><span class="sxs-lookup"><span data-stu-id="80956-174">Merge</span></span>

1. <span data-ttu-id="80956-175">Gå til fanen **Flet**.</span><span class="sxs-lookup"><span data-stu-id="80956-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="80956-176">I **ContactId** for **loyCustomers** skal du ændre visningsnavn til **ContactIdLOYALTY** for at skelne mellem dem og andre id'er, der indsættes.</span><span class="sxs-lookup"><span data-stu-id="80956-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![omdøb contactid fra loyalty-id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="80956-178">Vælg **Gem** og **Kør** for at starte fletningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="80956-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="80956-179">Opgave 3 – Konfigurere forudsigelse af produktanbefaling</span><span class="sxs-lookup"><span data-stu-id="80956-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="80956-180">Når du har samlet kundeprofiler på plads, kan vi nu køre forudsigelse af abonnementsafgang.</span><span class="sxs-lookup"><span data-stu-id="80956-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="80956-181">Gå til **Intelligens** > **Forudsigelse** vælg **Produktanbefaling**.</span><span class="sxs-lookup"><span data-stu-id="80956-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="80956-182">Vælg **Introduktion**.</span><span class="sxs-lookup"><span data-stu-id="80956-182">Select **Get started**.</span></span>

1. <span data-ttu-id="80956-183">Navngiv modellen **Forudsigelse til OOB-produktanbefalingsmodel** og outputobjektet **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="80956-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="80956-184">Definer tre betingelser for modellen:</span><span class="sxs-lookup"><span data-stu-id="80956-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="80956-185">**Antal produkter**: Angiv denne værdi til **5**.</span><span class="sxs-lookup"><span data-stu-id="80956-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="80956-186">Denne indstilling definerer, hvor mange produkter du vil anbefale til dine kunder.</span><span class="sxs-lookup"><span data-stu-id="80956-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="80956-187">**Forventede gentagne køb**: Vælg **Ja** for at angive, at du vil medtage produkter i den anbefaling, som dine kunder tidligere har købt.</span><span class="sxs-lookup"><span data-stu-id="80956-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="80956-188">**Kig tilbage-vinduet:** Vælg mindst **365 dage**.</span><span class="sxs-lookup"><span data-stu-id="80956-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="80956-189">Denne indstilling definerer, hvor langt tilbage modellen tjekker en kundens aktivitet som input til deres anbefalinger.</span><span class="sxs-lookup"><span data-stu-id="80956-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelindstillinger for produktanbefalingsmodellen":::.

1. <span data-ttu-id="80956-191">Vælg **Påkrævede data**, og vælg **Tilføj data** til købshistorik.</span><span class="sxs-lookup"><span data-stu-id="80956-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="80956-192">Tilføj **eCommercePurchases: eCommerce**-objektet, og tilknyt felterne fra eCommerce til de tilsvarende felter, der kræves af modellen.</span><span class="sxs-lookup"><span data-stu-id="80956-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="80956-193">Deltag i objektet **eCommercePurchases: eCommerce** med **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="80956-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Forbind eCommerce-objekter.](media/model-purchase-join.png)

1. <span data-ttu-id="80956-195">Vælg **Næste** for at angive modelplanen.</span><span class="sxs-lookup"><span data-stu-id="80956-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="80956-196">Modellen skal trænes regelmæssigt for at lære nye mønstre, når der er nye data, der indtages.</span><span class="sxs-lookup"><span data-stu-id="80956-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="80956-197">I dette eksempel skal du vælge **Månedlig**.</span><span class="sxs-lookup"><span data-stu-id="80956-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="80956-198">Vælg **Gem og Kør**, når du har gennemgået alle detaljer.</span><span class="sxs-lookup"><span data-stu-id="80956-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="80956-199">Opgave 4 - Gennemse modelresultater og forklaringer</span><span class="sxs-lookup"><span data-stu-id="80956-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="80956-200">Lad modellen fuldføre med at få oplæring og resultaterne af dataene.</span><span class="sxs-lookup"><span data-stu-id="80956-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="80956-201">Du kan nu gennemgå produktanbefalinger til modelforklaringer.</span><span class="sxs-lookup"><span data-stu-id="80956-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="80956-202">Du kan finde flere oplysninger under [Gennemse en forudsigelsesstatus og resultater](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="80956-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="80956-203">Opgave 5 – Oprettelse af et segment med højt købte produkter</span><span class="sxs-lookup"><span data-stu-id="80956-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="80956-204">Når produktionsmodellen køres, oprettes der et nyt objekt, som du kan se i **Data** > **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="80956-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="80956-205">Du kan oprette et nyt segment baseret på det objekt, der er oprettet af modellen.</span><span class="sxs-lookup"><span data-stu-id="80956-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="80956-206">Gå til **Segmenter**</span><span class="sxs-lookup"><span data-stu-id="80956-206">Go to **Segments**.</span></span> <span data-ttu-id="80956-207">Vælg **Ny**, og vælg **Opret fra** > **Intelligens**.</span><span class="sxs-lookup"><span data-stu-id="80956-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Oprettelse af et segment ved hjælp af model-output.](media/segment-intelligence.png)

1. <span data-ttu-id="80956-209">Vælg det **OOBProductRecommendationModelPrediction**-slutpunkt, og definer segmentet:</span><span class="sxs-lookup"><span data-stu-id="80956-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="80956-210">Felt: Produktid</span><span class="sxs-lookup"><span data-stu-id="80956-210">Field: ProductID</span></span>
   - <span data-ttu-id="80956-211">Operator: Værdi</span><span class="sxs-lookup"><span data-stu-id="80956-211">Operator: Value</span></span>
   - <span data-ttu-id="80956-212">Værdi: Vælg de øverste tre produkt-id'er</span><span class="sxs-lookup"><span data-stu-id="80956-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Opret et segment ud fra modelresultaterne.":::

<span data-ttu-id="80956-214">Du har nu et segment, der opdateres dynamisk, og som identificerer de kunder, der er mere villige til at købe de tre mest anbefalede produkter</span><span class="sxs-lookup"><span data-stu-id="80956-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="80956-215">Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="80956-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
