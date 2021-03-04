---
title: Eksempelvejledning til forudsigelse af abonnementsafgang
description: Brug denne eksempelvejledning til at afprøve abonnementet i en forudsigelsesmodel for afgang af standard-abonnement.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269829"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="8760b-103">Eksempelvejledning til forudsigelse af abonnementsafgang (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="8760b-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="8760b-104">Vi gennemgår fra start til slut et eksempel på forudsigelse af abonnementsafgang ved hjælp af de eksempeldata, der er angivet nedenfor.</span><span class="sxs-lookup"><span data-stu-id="8760b-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="8760b-105">Scenarie</span><span class="sxs-lookup"><span data-stu-id="8760b-105">Scenario</span></span>

<span data-ttu-id="8760b-106">Contoso er et firma, der fremstiller kaffe og kaffemaskiner i høj kvalitet, som de sælger via deres Contoso Coffee-websted.</span><span class="sxs-lookup"><span data-stu-id="8760b-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="8760b-107">De har for nylig startet en abonnementsforretning for kunderne for at få kaffe på normal basis.</span><span class="sxs-lookup"><span data-stu-id="8760b-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="8760b-108">Deres målsætning er at forstå, hvilke abonnementskunder kan opsige deres abonnement i løbet af de næste par måneder.</span><span class="sxs-lookup"><span data-stu-id="8760b-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="8760b-109">Det kan være en god hjælp at vide, hvilke af deres kunder der evt. **afgår**, ved at spare marketingkræfter og fokusere på at holde på dem.</span><span class="sxs-lookup"><span data-stu-id="8760b-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8760b-110">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="8760b-110">Prerequisites</span></span>

- <span data-ttu-id="8760b-111">Mindst [bidragydertilladelser](permissions.md) i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8760b-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="8760b-112">Vi anbefaler, at du implementerer følgende trin [i et nyt miljø](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="8760b-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="8760b-113">Opgave 1 - Indsættelse af data</span><span class="sxs-lookup"><span data-stu-id="8760b-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="8760b-114">Gennemgå artiklerne [om indsættelse af data](data-sources.md) og [import af datakilder ved hjælp af Power Query-connectors](connect-power-query.md) specifikt.</span><span class="sxs-lookup"><span data-stu-id="8760b-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="8760b-115">I følgende oplysninger antages det, at du har generelt kendskab til indsættelse af data.</span><span class="sxs-lookup"><span data-stu-id="8760b-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="8760b-116">Indsættelse af kundedata fra eCommerce-platform</span><span class="sxs-lookup"><span data-stu-id="8760b-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="8760b-117">Opret en datakilde med navnet **eCommerce**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="8760b-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="8760b-118">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="8760b-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="8760b-119">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="8760b-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="8760b-120">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="8760b-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="8760b-121">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="8760b-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="8760b-122">**CreatedOn**: Dato/Klokkeslæt/Zone</span><span class="sxs-lookup"><span data-stu-id="8760b-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformere fødselsdato til dato.":::

1. <span data-ttu-id="8760b-124">Omdøb datakilde fra **Forespørgsel** til **eCommerceContactsQuery** i feltet **Navn** i ruden til højre</span><span class="sxs-lookup"><span data-stu-id="8760b-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="8760b-125">Gem datakilden.</span><span class="sxs-lookup"><span data-stu-id="8760b-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="8760b-126">Indsæt kundedata fra loyalitetsskemaet</span><span class="sxs-lookup"><span data-stu-id="8760b-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="8760b-127">Opret en datakilde med navnet **LoyaltyScheme**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="8760b-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="8760b-128">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="8760b-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="8760b-129">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="8760b-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="8760b-130">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="8760b-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="8760b-131">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="8760b-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="8760b-132">**RewardsPoints**: Heltal</span><span class="sxs-lookup"><span data-stu-id="8760b-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="8760b-133">**CreatedOn**: Dato/Klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="8760b-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="8760b-134">Omdøb datakilde fra **Forespørgsel** til **loyCustomers** i feltet **Navn** i ruden til højre.</span><span class="sxs-lookup"><span data-stu-id="8760b-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="8760b-135">Gem datakilden.</span><span class="sxs-lookup"><span data-stu-id="8760b-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="8760b-136">Indsæt oplysninger om abonnement</span><span class="sxs-lookup"><span data-stu-id="8760b-136">Ingest subscription information</span></span>

1. <span data-ttu-id="8760b-137">Opret en datakilde med navnet **SubscriptionHistory**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="8760b-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="8760b-138">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="8760b-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="8760b-139">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="8760b-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="8760b-140">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="8760b-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="8760b-141">**SubscriptioID**: Heltal</span><span class="sxs-lookup"><span data-stu-id="8760b-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="8760b-142">**SubscriptionAmount**: Valuta</span><span class="sxs-lookup"><span data-stu-id="8760b-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="8760b-143">**SubscriptionEndDate** : Dato/klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="8760b-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="8760b-144">**SubscriptionEndDate** : Dato/Klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="8760b-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="8760b-145">**TransactionDate**: Dato/Klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="8760b-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="8760b-146">**IsRecurring**: Sand/Falsk</span><span class="sxs-lookup"><span data-stu-id="8760b-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="8760b-147">**Is_auto_renew**: Sand/Falsk</span><span class="sxs-lookup"><span data-stu-id="8760b-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="8760b-148">**RecurringFrequencyInMonths**: Heltal</span><span class="sxs-lookup"><span data-stu-id="8760b-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="8760b-149">Omdøb datakilde fra **Forespørgsel** til **SubscriptionHistory** i feltet **Navn** i ruden til højre.</span><span class="sxs-lookup"><span data-stu-id="8760b-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="8760b-150">Gem datakilden.</span><span class="sxs-lookup"><span data-stu-id="8760b-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="8760b-151">Indsættelse af kundedata fra gennemsyn af websted</span><span class="sxs-lookup"><span data-stu-id="8760b-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="8760b-152">Opret en datakilde med navnet **Website**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="8760b-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="8760b-153">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="8760b-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="8760b-154">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="8760b-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="8760b-155">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="8760b-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="8760b-156">**ReviewRating**: Heltal</span><span class="sxs-lookup"><span data-stu-id="8760b-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="8760b-157">**ReviewDate**: Dato</span><span class="sxs-lookup"><span data-stu-id="8760b-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="8760b-158">Omdøb datakilde fra **Forespørgsel** til **webReviews** i feltet 'Navn' i ruden til højre.</span><span class="sxs-lookup"><span data-stu-id="8760b-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="8760b-159">Opgave 2 - Datasamling</span><span class="sxs-lookup"><span data-stu-id="8760b-159">Task 2 - Data unification</span></span>

<span data-ttu-id="8760b-160">Når dataene er indsat, skal du nu starte **Tilknyt, Match, Flet**-processen for at oprette en samlet kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="8760b-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="8760b-161">Du kan finde flere oplysninger i [Datasamling](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="8760b-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="8760b-162">Tilknytning</span><span class="sxs-lookup"><span data-stu-id="8760b-162">Map</span></span>

1. <span data-ttu-id="8760b-163">Når du har indsat dataene, skal du knytte kontakterne fra eCommerce- og Loyalty-data til almindelige datatyper.</span><span class="sxs-lookup"><span data-stu-id="8760b-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="8760b-164">Go to **Data** > **Saml** > **Tilknyt**.</span><span class="sxs-lookup"><span data-stu-id="8760b-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="8760b-165">Vælg de objekter, der repræsenterer kundeprofilen - **eCommerceContacts** og **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="8760b-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="samle eCommerce- og loyalty-datakilder.":::

1. <span data-ttu-id="8760b-167">Vælg **ContactId** som primær nøgle for **eCommerceContacts** og **LoyaltyID** som primær nøgle for **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="8760b-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Saml LoyaltyId som primær nøgle.":::

### <a name="match"></a><span data-ttu-id="8760b-169">Resultat</span><span class="sxs-lookup"><span data-stu-id="8760b-169">Match</span></span>

1. <span data-ttu-id="8760b-170">Gå til fanen **Match**, og vælg **Angiv rækkefølge**.</span><span class="sxs-lookup"><span data-stu-id="8760b-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="8760b-171">Vælg **eCommerceContacts: eCommerce** som den primære kilde, og medtag alle poster i rullelisten **Primær**.</span><span class="sxs-lookup"><span data-stu-id="8760b-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="8760b-172">På rullelisten **Objekt 2** skal du vælge **loyCustomers: LoyaltyScheme** og inkludere alle poster.</span><span class="sxs-lookup"><span data-stu-id="8760b-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Saml og match eCommerce og Loyalty.":::

1. <span data-ttu-id="8760b-174">Vælg **Opret en ny regel**</span><span class="sxs-lookup"><span data-stu-id="8760b-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="8760b-175">Tilføj din første betingelse ved hjælp af FullName.</span><span class="sxs-lookup"><span data-stu-id="8760b-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="8760b-176">For eCommerceContacts skal du vælge **FullName** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="8760b-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="8760b-177">For loyCustomers skal du vælge **FullName** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="8760b-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="8760b-178">Vælg **Normaliser**-rullelisten, og vælg **Type (telefon, navn, adresse ...)**.</span><span class="sxs-lookup"><span data-stu-id="8760b-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="8760b-179">Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.</span><span class="sxs-lookup"><span data-stu-id="8760b-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="8760b-180">Angiv navnet **FullName, e-mail** til den nye regel.</span><span class="sxs-lookup"><span data-stu-id="8760b-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="8760b-181">Tilføj endnu en betingelse for e-mailadressen ved at vælge **Tilføj betingelse**</span><span class="sxs-lookup"><span data-stu-id="8760b-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="8760b-182">Vælg **E-mail** i rullelisten for objektet eCommerceContacts.</span><span class="sxs-lookup"><span data-stu-id="8760b-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="8760b-183">Vælg **E-mail** i rullelisten for objektet loyCustomers.</span><span class="sxs-lookup"><span data-stu-id="8760b-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="8760b-184">Lad Normaliser være tom.</span><span class="sxs-lookup"><span data-stu-id="8760b-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="8760b-185">Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.</span><span class="sxs-lookup"><span data-stu-id="8760b-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Saml og match regel for navn og e-mail.":::

7. <span data-ttu-id="8760b-187">Vælg **Gem** og **Kør**.</span><span class="sxs-lookup"><span data-stu-id="8760b-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="8760b-188">Fletning</span><span class="sxs-lookup"><span data-stu-id="8760b-188">Merge</span></span>

1. <span data-ttu-id="8760b-189">Gå til fanen **Flet**.</span><span class="sxs-lookup"><span data-stu-id="8760b-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="8760b-190">I **ContactId** for **loyCustomers** skal du ændre visningsnavn til **ContactIdLOYALTY** for at skelne mellem dem og andre id'er, der indsættes.</span><span class="sxs-lookup"><span data-stu-id="8760b-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="omdøb contactid fra loyalty-id.":::

1. <span data-ttu-id="8760b-192">Vælg **Gem** og **Kør** for at starte fletningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="8760b-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="8760b-193">Opgave 3 - Konfiguration af forudsigelse af abonnementsafgang</span><span class="sxs-lookup"><span data-stu-id="8760b-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="8760b-194">Når du har samlet kundeprofiler på plads, kan vi nu køre forudsigelse af abonnementsafgang.</span><span class="sxs-lookup"><span data-stu-id="8760b-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="8760b-195">Du kan se de detaljerede trin i artiklen [Forudsigelse af abonnementsafgang (prøveversion)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="8760b-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="8760b-196">Gå til **Intelligens** > **Find**, og vælg at bruge **Model for kundeafgang**.</span><span class="sxs-lookup"><span data-stu-id="8760b-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="8760b-197">Vælg indstillingen **Abonnement**, og vælg **Start her**.</span><span class="sxs-lookup"><span data-stu-id="8760b-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="8760b-198">Navngiv modellen **Forudsigelse af afgang af OOB-abonnement** og outputobjektets **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="8760b-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="8760b-199">Definer to betingelser for afgangsmodellen:</span><span class="sxs-lookup"><span data-stu-id="8760b-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="8760b-200">**Antal dage siden abonnement er afsluttet**: **mindst 60** dage.</span><span class="sxs-lookup"><span data-stu-id="8760b-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="8760b-201">Hvis en kunde ikke har fornyet sit abonnement inden for dette tidsrum, efter at abonnementet er udløbet, betragtes vedkommende som tabt</span><span class="sxs-lookup"><span data-stu-id="8760b-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="8760b-202">**Definition af afgang**: **mindst 93** dage.</span><span class="sxs-lookup"><span data-stu-id="8760b-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="8760b-203">Den varighed, modellen forudsiger, hvilke kunder der afgår.</span><span class="sxs-lookup"><span data-stu-id="8760b-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="8760b-204">Jo længere i fremtidsvisningen du er, jo mindre præcis er resultaterne.</span><span class="sxs-lookup"><span data-stu-id="8760b-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Vælg den model, der udnytter et forudsigelsesvindue og definition af afgang.":::

1. <span data-ttu-id="8760b-206">Vælg **Tilføj påkrævede data**, og vælg **Tilføj data** til abonnementsoversigt.</span><span class="sxs-lookup"><span data-stu-id="8760b-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="8760b-207">Tilføj **Abonnementet: SubscriptionHistory**-objektet, og tilknyt felterne fra eCommerce til de tilsvarende felter, der kræves af modellen.</span><span class="sxs-lookup"><span data-stu-id="8760b-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="8760b-208">Deltag i **Abonnement: SubscriptionHistory**-objekt med **eCommerceContacts: eCommerce**, navngiv relationen **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="8760b-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Forbind eCommerce-objekter.":::

1. <span data-ttu-id="8760b-210">Tilføj **webReviews: Websted**-objektet under kundeaktiviteter, og tilknyt felterne fra webReviews til de tilsvarende felter, der kræves af modellen.</span><span class="sxs-lookup"><span data-stu-id="8760b-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="8760b-211">Primær nøgle: ReviewId</span><span class="sxs-lookup"><span data-stu-id="8760b-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="8760b-212">Tidsstempel: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="8760b-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="8760b-213">Hændelse: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="8760b-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="8760b-214">Konfigurer en aktivitet til webstedets gennemgang.</span><span class="sxs-lookup"><span data-stu-id="8760b-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="8760b-215">Vælg aktiviteten **Gennemse**, og deltag i **webReviews: Websted**-objekt med **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="8760b-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="8760b-216">Vælg **Næste** for at angive modelplanen.</span><span class="sxs-lookup"><span data-stu-id="8760b-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="8760b-217">Modellen skal trænes regelmæssigt for at lære nye mønstre, når der er nye data, der indtages.</span><span class="sxs-lookup"><span data-stu-id="8760b-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="8760b-218">I dette eksempel skal du vælge **Månedlig**.</span><span class="sxs-lookup"><span data-stu-id="8760b-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="8760b-219">Vælg **Gem og Kør**, når du har gennemgået alle detaljer.</span><span class="sxs-lookup"><span data-stu-id="8760b-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="8760b-220">Opgave 4 - Gennemse modelresultater og forklaringer</span><span class="sxs-lookup"><span data-stu-id="8760b-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="8760b-221">Lad modellen fuldføre med at få oplæring og resultaterne af dataene.</span><span class="sxs-lookup"><span data-stu-id="8760b-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="8760b-222">Du kan nu gennemgå forklaringer på afgang af abonnementsmodellen.</span><span class="sxs-lookup"><span data-stu-id="8760b-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="8760b-223">Du kan finde flere oplysninger under [Gennemse en forudsigelsesstatus og resultater](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="8760b-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="8760b-224">Opgave 5 - Opret et segment med kunder med risiko for afgang</span><span class="sxs-lookup"><span data-stu-id="8760b-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="8760b-225">Når produktionsmodellen køres, oprettes der et nyt objekt, som du kan se i **Data** > **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="8760b-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="8760b-226">Du kan oprette et nyt segment baseret på det objekt, der er oprettet af modellen.</span><span class="sxs-lookup"><span data-stu-id="8760b-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="8760b-227">Gå til **Segmenter**</span><span class="sxs-lookup"><span data-stu-id="8760b-227">Go to **Segments**.</span></span> <span data-ttu-id="8760b-228">Vælg **Ny**, og vælg **Opret fra** > **Intelligens**.</span><span class="sxs-lookup"><span data-stu-id="8760b-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Oprettelse af et segment ved hjælp af model-output.":::

1. <span data-ttu-id="8760b-230">Vælg den **OOBSubscriptionChurnPrediction**-slutpunkt, og definer segmentet:</span><span class="sxs-lookup"><span data-stu-id="8760b-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="8760b-231">Felt: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="8760b-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="8760b-232">Operatør: større end</span><span class="sxs-lookup"><span data-stu-id="8760b-232">Operator: greater than</span></span>
   - <span data-ttu-id="8760b-233">Værdi: 0,6</span><span class="sxs-lookup"><span data-stu-id="8760b-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Opsætning af abonnementsafgang-segment.":::

<span data-ttu-id="8760b-235">Du har nu et segment, der opdateres dynamisk, og som identificerer de mange kunder med høj risiko for afgang til denne abonnementsforretning.</span><span class="sxs-lookup"><span data-stu-id="8760b-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="8760b-236">Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8760b-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]