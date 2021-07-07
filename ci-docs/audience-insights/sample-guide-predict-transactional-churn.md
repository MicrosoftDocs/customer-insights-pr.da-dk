---
title: Eksempelvejledning til transaktionsrelateret forudsigelse af afgang
description: Brug denne eksempelvejledning til at afprøve transaktionsrelateret standardafgang i en forudsigelsesmodel.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306113"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="b443e-103">Eksempelvejledning til forudsigelse af transaktionsrelateret afgang (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="b443e-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="b443e-104">Denne vejledning vil gennemgå et eksempel på forudsigelse af transaktionsrelateret afgang i Customer Insights fra start til slut ved hjælp af de data, der er angivet nedenfor.</span><span class="sxs-lookup"><span data-stu-id="b443e-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="b443e-105">Alle data, der bruges i denne vejledning, er ikke rigtige kundedata og er en del af de Contoso-datasæt, der findes i *Demo*-miljøet i dit customer insights-abonnement.</span><span class="sxs-lookup"><span data-stu-id="b443e-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="b443e-106">Scenarie</span><span class="sxs-lookup"><span data-stu-id="b443e-106">Scenario</span></span>

<span data-ttu-id="b443e-107">Contoso er en virksomhed, der producerer kaffemaskiner af høj kvalitet, som de sælger via deres Contoso Coffee-websted.</span><span class="sxs-lookup"><span data-stu-id="b443e-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="b443e-108">Deres mål er at vide, hvilke kunder der jævnligt køber deres produkter, men som holder op med at være aktive kunder i de næste 60 dage.</span><span class="sxs-lookup"><span data-stu-id="b443e-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="b443e-109">Det kan være en god hjælp at vide, hvilke af deres kunder der evt. **afgår**, ved at spare marketingkræfter og fokusere på at holde på dem.</span><span class="sxs-lookup"><span data-stu-id="b443e-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b443e-110">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="b443e-110">Prerequisites</span></span>

- <span data-ttu-id="b443e-111">Mindst [bidragydertilladelser](permissions.md) i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b443e-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="b443e-112">Vi anbefaler, at du implementerer følgende trin [i et nyt miljø](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="b443e-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="b443e-113">Opgave 1 - Indsættelse af data</span><span class="sxs-lookup"><span data-stu-id="b443e-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="b443e-114">Gennemgå artiklerne [om indsættelse af data](data-sources.md) og [import af datakilder ved hjælp af Power Query-connectors](connect-power-query.md) specifikt.</span><span class="sxs-lookup"><span data-stu-id="b443e-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="b443e-115">I følgende oplysninger antages det, at du har generelt kendskab til indsættelse af data.</span><span class="sxs-lookup"><span data-stu-id="b443e-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="b443e-116">Indsættelse af kundedata fra eCommerce-platform</span><span class="sxs-lookup"><span data-stu-id="b443e-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="b443e-117">Opret en datakilde med navnet **eCommerce**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="b443e-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b443e-118">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="b443e-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="b443e-119">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="b443e-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b443e-120">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="b443e-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="b443e-121">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="b443e-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="b443e-122">**CreatedOn**: Dato/Klokkeslæt/Zone</span><span class="sxs-lookup"><span data-stu-id="b443e-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="b443e-123">![Omdan DoB til dato](media/ecommerce-dob-date.PNG "transformer fødselsdato til dato")</span><span class="sxs-lookup"><span data-stu-id="b443e-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="b443e-124">Omdøb datakilde fra **Forespørgsel** til **eCommerceContactsQuery** i feltet **Navn** i ruden til højre</span><span class="sxs-lookup"><span data-stu-id="b443e-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="b443e-125">Gem datakilden.</span><span class="sxs-lookup"><span data-stu-id="b443e-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="b443e-126">Indsættelse af online købsdata</span><span class="sxs-lookup"><span data-stu-id="b443e-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="b443e-127">Tilføj et andet datasæt til samme **eCommerce**-datakilde.</span><span class="sxs-lookup"><span data-stu-id="b443e-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="b443e-128">Vælg **Tekst/CSV**-connector igen.</span><span class="sxs-lookup"><span data-stu-id="b443e-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="b443e-129">Angiv URL-adressen til **onlinekøb**-data https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="b443e-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="b443e-130">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="b443e-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b443e-131">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="b443e-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="b443e-132">**PurchasedOn**: Dato/Klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="b443e-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="b443e-133">**TotalPrice**: Valuta</span><span class="sxs-lookup"><span data-stu-id="b443e-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="b443e-134">Omdøb datakilde fra **Forespørgsel** til **eCommercePurchases** i feltet **Navn** i ruden til højre.</span><span class="sxs-lookup"><span data-stu-id="b443e-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="b443e-135">Gem datakilden.</span><span class="sxs-lookup"><span data-stu-id="b443e-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="b443e-136">Indsæt kundedata fra loyalitetsskemaet</span><span class="sxs-lookup"><span data-stu-id="b443e-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="b443e-137">Opret en datakilde med navnet **LoyaltyScheme**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="b443e-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b443e-138">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="b443e-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="b443e-139">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="b443e-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="b443e-140">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="b443e-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="b443e-141">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="b443e-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="b443e-142">**RewardsPoints**: Heltal</span><span class="sxs-lookup"><span data-stu-id="b443e-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="b443e-143">**CreatedOn**: Dato/Klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="b443e-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="b443e-144">Omdøb datakilde fra **Forespørgsel** til **loyCustomers** i feltet **Navn** i ruden til højre.</span><span class="sxs-lookup"><span data-stu-id="b443e-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="b443e-145">Gem datakilden.</span><span class="sxs-lookup"><span data-stu-id="b443e-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="b443e-146">Opgave 2 - Datasamling</span><span class="sxs-lookup"><span data-stu-id="b443e-146">Task 2 - Data unification</span></span>

<span data-ttu-id="b443e-147">Når dataene er indsat, skal du nu starte **Tilknyt, Match, Flet**-processen for at oprette en samlet kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="b443e-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="b443e-148">Du kan finde flere oplysninger i [Datasamling](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="b443e-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="b443e-149">Tilknytning</span><span class="sxs-lookup"><span data-stu-id="b443e-149">Map</span></span>

1. <span data-ttu-id="b443e-150">Når du har indsat dataene, skal du knytte kontakterne fra eCommerce- og Loyalty-data til almindelige datatyper.</span><span class="sxs-lookup"><span data-stu-id="b443e-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="b443e-151">Go to **Data** > **Saml** > **Tilknyt**.</span><span class="sxs-lookup"><span data-stu-id="b443e-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="b443e-152">Vælg de objekter, der repræsenterer kundeprofilen - **eCommerceContacts** og **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="b443e-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="samle eCommerce- og loyalty-datakilder.":::

1. <span data-ttu-id="b443e-154">Vælg **ContactId** som primær nøgle for **eCommerceContacts** og **LoyaltyID** som primær nøgle for **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="b443e-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Saml LoyaltyId som primær nøgle.":::

### <a name="match"></a><span data-ttu-id="b443e-156">Resultat</span><span class="sxs-lookup"><span data-stu-id="b443e-156">Match</span></span>

1. <span data-ttu-id="b443e-157">Gå til fanen **Match**, og vælg **Angiv rækkefølge**.</span><span class="sxs-lookup"><span data-stu-id="b443e-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="b443e-158">På rullelisten **Primær** skal du vælge **eCommerceContacts: e-handel** som den primære kilde og inkludere alle poster.</span><span class="sxs-lookup"><span data-stu-id="b443e-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="b443e-159">På rullelisten **Entity 2** skal du vælge **loyCustomers: LoyaltyScheme** og medtage alle poster.</span><span class="sxs-lookup"><span data-stu-id="b443e-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Saml og match eCommerce og Loyalty.":::

1. <span data-ttu-id="b443e-161">Vælg **Opret en ny regel**</span><span class="sxs-lookup"><span data-stu-id="b443e-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="b443e-162">Tilføj din første betingelse ved hjælp af FullName.</span><span class="sxs-lookup"><span data-stu-id="b443e-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="b443e-163">I forbindelse med eCommerceContacts skal du vælge **Fuldt navn** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="b443e-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="b443e-164">I forbindelse med loyCustomers skal du vælge **Fuldt navn** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="b443e-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="b443e-165">Vælg **Normaliser**-rullelisten, og vælg **Type (telefon, navn, adresse ...)**.</span><span class="sxs-lookup"><span data-stu-id="b443e-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="b443e-166">Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.</span><span class="sxs-lookup"><span data-stu-id="b443e-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="b443e-167">Angiv navnet **FullName, e-mail** til den nye regel.</span><span class="sxs-lookup"><span data-stu-id="b443e-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="b443e-168">Tilføj endnu en betingelse for e-mailadressen ved at vælge **Tilføj betingelse**</span><span class="sxs-lookup"><span data-stu-id="b443e-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="b443e-169">For enhed eCommerceContacts skal du vælge **E-mail** i rullelisten.</span><span class="sxs-lookup"><span data-stu-id="b443e-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="b443e-170">For enhed loyCustomers skal du vælge **E-mail** i rullelisten.</span><span class="sxs-lookup"><span data-stu-id="b443e-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="b443e-171">Lad Normaliser være tom.</span><span class="sxs-lookup"><span data-stu-id="b443e-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="b443e-172">Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.</span><span class="sxs-lookup"><span data-stu-id="b443e-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Saml og match regel for navn og e-mail.":::

7. <span data-ttu-id="b443e-174">Vælg **Gem** og **Kør**.</span><span class="sxs-lookup"><span data-stu-id="b443e-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="b443e-175">Fletning</span><span class="sxs-lookup"><span data-stu-id="b443e-175">Merge</span></span>

1. <span data-ttu-id="b443e-176">Gå til fanen **Flet**.</span><span class="sxs-lookup"><span data-stu-id="b443e-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="b443e-177">I **ContactId** for **loyCustomers** skal du ændre visningsnavn til **ContactIdLOYALTY** for at skelne mellem dem og andre id'er, der indsættes.</span><span class="sxs-lookup"><span data-stu-id="b443e-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="omdøb contactid fra loyalty-id.":::

1. <span data-ttu-id="b443e-179">Vælg **Gem** og **Kør** for at starte fletningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="b443e-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="b443e-180">Opgave 3 - Konfiguration af transaktion af forudsigelse af afgang</span><span class="sxs-lookup"><span data-stu-id="b443e-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="b443e-181">Når du har samlet kundeprofiler på plads, kan vi nu køre forudsigelse af abonnementsafgang.</span><span class="sxs-lookup"><span data-stu-id="b443e-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="b443e-182">Du kan se de detaljerede trin i artiklen [Forudsigelse af abonnementsafgang (prøveversion)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="b443e-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="b443e-183">Gå til **Intelligens** > **Find**, og vælg at bruge **Model for kundeafgang**.</span><span class="sxs-lookup"><span data-stu-id="b443e-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="b443e-184">Vælg indstillingen **Transaktionsrelateret**, og vælg **Start her**.</span><span class="sxs-lookup"><span data-stu-id="b443e-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="b443e-185">Navngiv modellen **Forudsigelse af afgang af OOB eCommerce-transaktion** og outputobjektets **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="b443e-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="b443e-186">Definer to betingelser for afgangsmodellen:</span><span class="sxs-lookup"><span data-stu-id="b443e-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="b443e-187">**Forudsigelsesvindue**: **mindst 60** dage.</span><span class="sxs-lookup"><span data-stu-id="b443e-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="b443e-188">Brug denne indstilling til at definere, hvor langt ud i fremtiden du vil forudsige kundeafgang.</span><span class="sxs-lookup"><span data-stu-id="b443e-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="b443e-189">**Definition af afgang**: **mindst 60** dage.</span><span class="sxs-lookup"><span data-stu-id="b443e-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="b443e-190">Varigheden uden køb, hvorefter en kunde anses for at være tabt.</span><span class="sxs-lookup"><span data-stu-id="b443e-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Vælg den model, der udnytter et forudsigelsesvindue og definition af afgang.":::

1. <span data-ttu-id="b443e-192">Vælg **Købshistorik (påkrævet)**, og vælg **Tilføj data** til købshistorik.</span><span class="sxs-lookup"><span data-stu-id="b443e-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="b443e-193">Tilføj **eCommercePurchases: eCommerce**-objektet, og tilknyt felterne fra eCommerce til de tilsvarende felter, der kræves af modellen.</span><span class="sxs-lookup"><span data-stu-id="b443e-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="b443e-194">Deltag i objektet **eCommercePurchases: eCommerce** med **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="b443e-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Forbind eCommerce-objekter.":::

1. <span data-ttu-id="b443e-196">Vælg **Næste** for at angive modelplanen.</span><span class="sxs-lookup"><span data-stu-id="b443e-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="b443e-197">Modellen skal trænes regelmæssigt for at lære nye mønstre, når der er nye data, der indtages.</span><span class="sxs-lookup"><span data-stu-id="b443e-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="b443e-198">I dette eksempel skal du vælge **Månedlig**.</span><span class="sxs-lookup"><span data-stu-id="b443e-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="b443e-199">Vælg **Gem og Kør**, når du har gennemgået alle detaljer.</span><span class="sxs-lookup"><span data-stu-id="b443e-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="b443e-200">Opgave 4 - Gennemse modelresultater og forklaringer</span><span class="sxs-lookup"><span data-stu-id="b443e-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="b443e-201">Lad modellen fuldføre med at få oplæring og resultaterne af dataene.</span><span class="sxs-lookup"><span data-stu-id="b443e-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="b443e-202">Du kan nu gennemgå forklaringer på afgang af abonnementsmodellen.</span><span class="sxs-lookup"><span data-stu-id="b443e-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="b443e-203">Du kan finde flere oplysninger under [Gennemse en forudsigelsesstatus og resultater](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="b443e-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="b443e-204">Opgave 5 - Opret et segment med kunder med risiko for afgang</span><span class="sxs-lookup"><span data-stu-id="b443e-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="b443e-205">Når produktionsmodellen køres, oprettes der et nyt objekt, som du kan se i **Data** > **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="b443e-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="b443e-206">Du kan oprette et nyt segment baseret på det objekt, der er oprettet af modellen.</span><span class="sxs-lookup"><span data-stu-id="b443e-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="b443e-207">Gå til **Segmenter**</span><span class="sxs-lookup"><span data-stu-id="b443e-207">Go to **Segments**.</span></span> <span data-ttu-id="b443e-208">Vælg **Ny**, og vælg **Opret fra** > **Intelligens**.</span><span class="sxs-lookup"><span data-stu-id="b443e-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Oprettelse af et segment ved hjælp af model-output.":::

1. <span data-ttu-id="b443e-210">Vælg den **OOBSubscriptionChurnPrediction**-slutpunkt, og definer segmentet:</span><span class="sxs-lookup"><span data-stu-id="b443e-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="b443e-211">Felt: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="b443e-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="b443e-212">Operatør: større end</span><span class="sxs-lookup"><span data-stu-id="b443e-212">Operator: greater than</span></span>
   - <span data-ttu-id="b443e-213">Værdi: 0,6</span><span class="sxs-lookup"><span data-stu-id="b443e-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Opsætning af abonnementsafgang-segment.":::

<span data-ttu-id="b443e-215">Du har nu et segment, der opdateres dynamisk, og som identificerer de mange kunder med høj risiko for afgang til denne abonnementsforretning.</span><span class="sxs-lookup"><span data-stu-id="b443e-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="b443e-216">Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b443e-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]