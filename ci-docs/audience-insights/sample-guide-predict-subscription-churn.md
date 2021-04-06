---
title: Eksempelvejledning til forudsigelse af abonnementsafgang
description: Brug denne eksempelvejledning til at afprøve abonnementet i en forudsigelsesmodel for afgang af standard-abonnement.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 324e5c19778230dd978b2f4e9156a2dd82b3d2bd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595511"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="40828-103">Eksempelvejledning til forudsigelse af abonnementsafgang (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="40828-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="40828-104">Vi gennemgår fra start til slut et eksempel på forudsigelse af abonnementsafgang ved hjælp af de eksempeldata, der er angivet nedenfor.</span><span class="sxs-lookup"><span data-stu-id="40828-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="40828-105">Scenarie</span><span class="sxs-lookup"><span data-stu-id="40828-105">Scenario</span></span>

<span data-ttu-id="40828-106">Contoso er et firma, der fremstiller kaffe og kaffemaskiner i høj kvalitet, som de sælger via deres Contoso Coffee-websted.</span><span class="sxs-lookup"><span data-stu-id="40828-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="40828-107">De har for nylig startet en abonnementsforretning for kunderne for at få kaffe på normal basis.</span><span class="sxs-lookup"><span data-stu-id="40828-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="40828-108">Deres målsætning er at forstå, hvilke abonnementskunder kan opsige deres abonnement i løbet af de næste par måneder.</span><span class="sxs-lookup"><span data-stu-id="40828-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="40828-109">Det kan være en god hjælp at vide, hvilke af deres kunder der evt. **afgår**, ved at spare marketingkræfter og fokusere på at holde på dem.</span><span class="sxs-lookup"><span data-stu-id="40828-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="40828-110">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="40828-110">Prerequisites</span></span>

- <span data-ttu-id="40828-111">Mindst [bidragydertilladelser](permissions.md) i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="40828-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="40828-112">Vi anbefaler, at du implementerer følgende trin [i et nyt miljø](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="40828-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="40828-113">Opgave 1 - Indsættelse af data</span><span class="sxs-lookup"><span data-stu-id="40828-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="40828-114">Gennemgå artiklerne [om indsættelse af data](data-sources.md) og [import af datakilder ved hjælp af Power Query-connectors](connect-power-query.md) specifikt.</span><span class="sxs-lookup"><span data-stu-id="40828-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="40828-115">I følgende oplysninger antages det, at du har generelt kendskab til indsættelse af data.</span><span class="sxs-lookup"><span data-stu-id="40828-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="40828-116">Indsættelse af kundedata fra eCommerce-platform</span><span class="sxs-lookup"><span data-stu-id="40828-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="40828-117">Opret en datakilde med navnet **eCommerce**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="40828-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="40828-118">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="40828-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="40828-119">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="40828-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="40828-120">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="40828-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="40828-121">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="40828-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="40828-122">**CreatedOn**: Dato/Klokkeslæt/Zone</span><span class="sxs-lookup"><span data-stu-id="40828-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformere fødselsdato til dato.":::

1. <span data-ttu-id="40828-124">Omdøb datakilde fra **Forespørgsel** til **eCommerceContactsQuery** i feltet **Navn** i ruden til højre</span><span class="sxs-lookup"><span data-stu-id="40828-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="40828-125">Gem datakilden.</span><span class="sxs-lookup"><span data-stu-id="40828-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="40828-126">Indsæt kundedata fra loyalitetsskemaet</span><span class="sxs-lookup"><span data-stu-id="40828-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="40828-127">Opret en datakilde med navnet **LoyaltyScheme**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="40828-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="40828-128">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="40828-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="40828-129">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="40828-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="40828-130">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="40828-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="40828-131">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="40828-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="40828-132">**RewardsPoints**: Heltal</span><span class="sxs-lookup"><span data-stu-id="40828-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="40828-133">**CreatedOn**: Dato/Klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="40828-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="40828-134">Omdøb datakilde fra **Forespørgsel** til **loyCustomers** i feltet **Navn** i ruden til højre.</span><span class="sxs-lookup"><span data-stu-id="40828-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="40828-135">Gem datakilden.</span><span class="sxs-lookup"><span data-stu-id="40828-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="40828-136">Indsæt oplysninger om abonnement</span><span class="sxs-lookup"><span data-stu-id="40828-136">Ingest subscription information</span></span>

1. <span data-ttu-id="40828-137">Opret en datakilde med navnet **SubscriptionHistory**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="40828-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="40828-138">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="40828-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="40828-139">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="40828-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="40828-140">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="40828-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="40828-141">**SubscriptioID**: Heltal</span><span class="sxs-lookup"><span data-stu-id="40828-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="40828-142">**SubscriptionAmount**: Valuta</span><span class="sxs-lookup"><span data-stu-id="40828-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="40828-143">**SubscriptionEndDate** : Dato/klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="40828-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="40828-144">**SubscriptionEndDate** : Dato/Klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="40828-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="40828-145">**TransactionDate**: Dato/Klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="40828-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="40828-146">**IsRecurring**: Sand/Falsk</span><span class="sxs-lookup"><span data-stu-id="40828-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="40828-147">**Is_auto_renew**: Sand/Falsk</span><span class="sxs-lookup"><span data-stu-id="40828-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="40828-148">**RecurringFrequencyInMonths**: Heltal</span><span class="sxs-lookup"><span data-stu-id="40828-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="40828-149">Omdøb datakilde fra **Forespørgsel** til **SubscriptionHistory** i feltet **Navn** i ruden til højre.</span><span class="sxs-lookup"><span data-stu-id="40828-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="40828-150">Gem datakilden.</span><span class="sxs-lookup"><span data-stu-id="40828-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="40828-151">Indsættelse af kundedata fra gennemsyn af websted</span><span class="sxs-lookup"><span data-stu-id="40828-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="40828-152">Opret en datakilde med navnet **Website**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="40828-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="40828-153">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="40828-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="40828-154">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="40828-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="40828-155">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="40828-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="40828-156">**ReviewRating**: Heltal</span><span class="sxs-lookup"><span data-stu-id="40828-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="40828-157">**ReviewDate**: Dato</span><span class="sxs-lookup"><span data-stu-id="40828-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="40828-158">Omdøb datakilde fra **Forespørgsel** til **webReviews** i feltet 'Navn' i ruden til højre.</span><span class="sxs-lookup"><span data-stu-id="40828-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="40828-159">Opgave 2 - Datasamling</span><span class="sxs-lookup"><span data-stu-id="40828-159">Task 2 - Data unification</span></span>

<span data-ttu-id="40828-160">Når dataene er indsat, skal du nu starte **Tilknyt, Match, Flet**-processen for at oprette en samlet kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="40828-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="40828-161">Du kan finde flere oplysninger i [Datasamling](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="40828-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="40828-162">Tilknytning</span><span class="sxs-lookup"><span data-stu-id="40828-162">Map</span></span>

1. <span data-ttu-id="40828-163">Når du har indsat dataene, skal du knytte kontakterne fra eCommerce- og Loyalty-data til almindelige datatyper.</span><span class="sxs-lookup"><span data-stu-id="40828-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="40828-164">Go to **Data** > **Saml** > **Tilknyt**.</span><span class="sxs-lookup"><span data-stu-id="40828-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="40828-165">Vælg de objekter, der repræsenterer kundeprofilen - **eCommerceContacts** og **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="40828-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="samle eCommerce- og loyalty-datakilder.":::

1. <span data-ttu-id="40828-167">Vælg **ContactId** som primær nøgle for **eCommerceContacts** og **LoyaltyID** som primær nøgle for **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="40828-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Saml LoyaltyId som primær nøgle.":::

### <a name="match"></a><span data-ttu-id="40828-169">Resultat</span><span class="sxs-lookup"><span data-stu-id="40828-169">Match</span></span>

1. <span data-ttu-id="40828-170">Gå til fanen **Match**, og vælg **Angiv rækkefølge**.</span><span class="sxs-lookup"><span data-stu-id="40828-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="40828-171">Vælg **eCommerceContacts: eCommerce** som den primære kilde, og medtag alle poster i rullelisten **Primær**.</span><span class="sxs-lookup"><span data-stu-id="40828-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="40828-172">På rullelisten **Objekt 2** skal du vælge **loyCustomers: LoyaltyScheme** og inkludere alle poster.</span><span class="sxs-lookup"><span data-stu-id="40828-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Saml og match eCommerce og Loyalty.":::

1. <span data-ttu-id="40828-174">Vælg **Opret en ny regel**</span><span class="sxs-lookup"><span data-stu-id="40828-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="40828-175">Tilføj din første betingelse ved hjælp af FullName.</span><span class="sxs-lookup"><span data-stu-id="40828-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="40828-176">For eCommerceContacts skal du vælge **FullName** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="40828-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="40828-177">For loyCustomers skal du vælge **FullName** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="40828-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="40828-178">Vælg **Normaliser**-rullelisten, og vælg **Type (telefon, navn, adresse ...)**.</span><span class="sxs-lookup"><span data-stu-id="40828-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="40828-179">Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.</span><span class="sxs-lookup"><span data-stu-id="40828-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="40828-180">Angiv navnet **FullName, e-mail** til den nye regel.</span><span class="sxs-lookup"><span data-stu-id="40828-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="40828-181">Tilføj endnu en betingelse for e-mailadressen ved at vælge **Tilføj betingelse**</span><span class="sxs-lookup"><span data-stu-id="40828-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="40828-182">Vælg **E-mail** i rullelisten for objektet eCommerceContacts.</span><span class="sxs-lookup"><span data-stu-id="40828-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="40828-183">Vælg **E-mail** i rullelisten for objektet loyCustomers.</span><span class="sxs-lookup"><span data-stu-id="40828-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="40828-184">Lad Normaliser være tom.</span><span class="sxs-lookup"><span data-stu-id="40828-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="40828-185">Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.</span><span class="sxs-lookup"><span data-stu-id="40828-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Saml og match regel for navn og e-mail.":::

7. <span data-ttu-id="40828-187">Vælg **Gem** og **Kør**.</span><span class="sxs-lookup"><span data-stu-id="40828-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="40828-188">Fletning</span><span class="sxs-lookup"><span data-stu-id="40828-188">Merge</span></span>

1. <span data-ttu-id="40828-189">Gå til fanen **Flet**.</span><span class="sxs-lookup"><span data-stu-id="40828-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="40828-190">I **ContactId** for **loyCustomers** skal du ændre visningsnavn til **ContactIdLOYALTY** for at skelne mellem dem og andre id'er, der indsættes.</span><span class="sxs-lookup"><span data-stu-id="40828-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="omdøb contactid fra loyalty-id.":::

1. <span data-ttu-id="40828-192">Vælg **Gem** og **Kør** for at starte fletningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="40828-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="40828-193">Opgave 3 - Konfiguration af forudsigelse af abonnementsafgang</span><span class="sxs-lookup"><span data-stu-id="40828-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="40828-194">Når du har samlet kundeprofiler på plads, kan vi nu køre forudsigelse af abonnementsafgang.</span><span class="sxs-lookup"><span data-stu-id="40828-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="40828-195">Du kan se de detaljerede trin i artiklen [Forudsigelse af abonnementsafgang (prøveversion)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="40828-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="40828-196">Gå til **Intelligens** > **Find**, og vælg at bruge **Model for kundeafgang**.</span><span class="sxs-lookup"><span data-stu-id="40828-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="40828-197">Vælg indstillingen **Abonnement**, og vælg **Start her**.</span><span class="sxs-lookup"><span data-stu-id="40828-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="40828-198">Navngiv modellen **Forudsigelse af afgang af OOB-abonnement** og outputobjektets **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="40828-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="40828-199">Definer to betingelser for afgangsmodellen:</span><span class="sxs-lookup"><span data-stu-id="40828-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="40828-200">**Antal dage siden abonnement er afsluttet**: **mindst 60** dage.</span><span class="sxs-lookup"><span data-stu-id="40828-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="40828-201">Hvis en kunde ikke har fornyet sit abonnement inden for dette tidsrum, efter at abonnementet er udløbet, betragtes vedkommende som tabt</span><span class="sxs-lookup"><span data-stu-id="40828-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="40828-202">**Definition af afgang**: **mindst 93** dage.</span><span class="sxs-lookup"><span data-stu-id="40828-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="40828-203">Den varighed, modellen forudsiger, hvilke kunder der afgår.</span><span class="sxs-lookup"><span data-stu-id="40828-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="40828-204">Jo længere i fremtidsvisningen du er, jo mindre præcis er resultaterne.</span><span class="sxs-lookup"><span data-stu-id="40828-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Vælg den model, der udnytter et forudsigelsesvindue og definition af afgang.":::

1. <span data-ttu-id="40828-206">Vælg **Tilføj påkrævede data**, og vælg **Tilføj data** til abonnementsoversigt.</span><span class="sxs-lookup"><span data-stu-id="40828-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="40828-207">Tilføj **Abonnementet: SubscriptionHistory**-objektet, og tilknyt felterne fra eCommerce til de tilsvarende felter, der kræves af modellen.</span><span class="sxs-lookup"><span data-stu-id="40828-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="40828-208">Deltag i **Abonnement: SubscriptionHistory**-objekt med **eCommerceContacts: eCommerce**, navngiv relationen **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="40828-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Forbind eCommerce-objekter.":::

1. <span data-ttu-id="40828-210">Tilføj **webReviews: Websted**-objektet under kundeaktiviteter, og tilknyt felterne fra webReviews til de tilsvarende felter, der kræves af modellen.</span><span class="sxs-lookup"><span data-stu-id="40828-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="40828-211">Primær nøgle: ReviewId</span><span class="sxs-lookup"><span data-stu-id="40828-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="40828-212">Tidsstempel: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="40828-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="40828-213">Hændelse: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="40828-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="40828-214">Konfigurer en aktivitet til webstedets gennemgang.</span><span class="sxs-lookup"><span data-stu-id="40828-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="40828-215">Vælg aktiviteten **Gennemse**, og deltag i **webReviews: Websted**-objekt med **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="40828-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="40828-216">Vælg **Næste** for at angive modelplanen.</span><span class="sxs-lookup"><span data-stu-id="40828-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="40828-217">Modellen skal trænes regelmæssigt for at lære nye mønstre, når der er nye data, der indtages.</span><span class="sxs-lookup"><span data-stu-id="40828-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="40828-218">I dette eksempel skal du vælge **Månedlig**.</span><span class="sxs-lookup"><span data-stu-id="40828-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="40828-219">Vælg **Gem og Kør**, når du har gennemgået alle detaljer.</span><span class="sxs-lookup"><span data-stu-id="40828-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="40828-220">Opgave 4 - Gennemse modelresultater og forklaringer</span><span class="sxs-lookup"><span data-stu-id="40828-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="40828-221">Lad modellen fuldføre med at få oplæring og resultaterne af dataene.</span><span class="sxs-lookup"><span data-stu-id="40828-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="40828-222">Du kan nu gennemgå forklaringer på afgang af abonnementsmodellen.</span><span class="sxs-lookup"><span data-stu-id="40828-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="40828-223">Du kan finde flere oplysninger under [Gennemse en forudsigelsesstatus og resultater](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="40828-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="40828-224">Opgave 5 - Opret et segment med kunder med risiko for afgang</span><span class="sxs-lookup"><span data-stu-id="40828-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="40828-225">Når produktionsmodellen køres, oprettes der et nyt objekt, som du kan se i **Data** > **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="40828-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="40828-226">Du kan oprette et nyt segment baseret på det objekt, der er oprettet af modellen.</span><span class="sxs-lookup"><span data-stu-id="40828-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="40828-227">Gå til **Segmenter**</span><span class="sxs-lookup"><span data-stu-id="40828-227">Go to **Segments**.</span></span> <span data-ttu-id="40828-228">Vælg **Ny**, og vælg **Opret fra** > **Intelligens**.</span><span class="sxs-lookup"><span data-stu-id="40828-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Oprettelse af et segment ved hjælp af model-output.":::

1. <span data-ttu-id="40828-230">Vælg den **OOBSubscriptionChurnPrediction**-slutpunkt, og definer segmentet:</span><span class="sxs-lookup"><span data-stu-id="40828-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="40828-231">Felt: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="40828-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="40828-232">Operatør: større end</span><span class="sxs-lookup"><span data-stu-id="40828-232">Operator: greater than</span></span>
   - <span data-ttu-id="40828-233">Værdi: 0,6</span><span class="sxs-lookup"><span data-stu-id="40828-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Opsætning af abonnementsafgang-segment.":::

<span data-ttu-id="40828-235">Du har nu et segment, der opdateres dynamisk, og som identificerer de mange kunder med høj risiko for afgang til denne abonnementsforretning.</span><span class="sxs-lookup"><span data-stu-id="40828-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="40828-236">Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="40828-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]