---
title: Vejledning til eksempel på forudsigelse af kundens levetidsværdi
description: Brug denne eksempelvejledning til at afprøve forudsigelsesmodellen for kundens levetidsværdi.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306342"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="1eb2f-103">Vejledning til eksempel på forudsigelse af kundens levetidsværdi (CLV)</span><span class="sxs-lookup"><span data-stu-id="1eb2f-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="1eb2f-104">Denne vejledning indeholder et komplet eksempel på CLV-forudsigelse (Customer Lifetime Value) i Customer Insights ved hjælp af eksempeldata.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="1eb2f-105">Scenarie</span><span class="sxs-lookup"><span data-stu-id="1eb2f-105">Scenario</span></span>

<span data-ttu-id="1eb2f-106">Contoso er en virksomhed, der producerer kaffemaskiner af høj kvalitet.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="1eb2f-107">De sælger produkterne via deres Contoso Coffee-hjemmeside.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="1eb2f-108">Virksomheden ønsker at forstå den værdi (omsætning), som deres kunder kan generere i de næste 12 måneder.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="1eb2f-109">At kende den forventede værdi af deres kunder i de næste 12 måneder vil hjælpe dem med at styre deres marketingindsats på kunder af høj værdi.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1eb2f-110">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="1eb2f-110">Prerequisites</span></span>

- <span data-ttu-id="1eb2f-111">Mindst [bidragydertilladelser](permissions.md) i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="1eb2f-112">Vi anbefaler, at du implementerer følgende trin [i et nyt miljø](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="1eb2f-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="1eb2f-113">Opgave 1 - Indsættelse af data</span><span class="sxs-lookup"><span data-stu-id="1eb2f-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="1eb2f-114">Gennemse artiklerne om [dataindtagelse](data-sources.md) og import af [datakilder ved hjælp af Power Query forbindelser](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="1eb2f-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="1eb2f-115">I følgende oplysninger antages det, at du har generelt kendskab til indsættelse af data.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="1eb2f-116">Indsættelse af kundedata fra eCommerce-platform</span><span class="sxs-lookup"><span data-stu-id="1eb2f-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="1eb2f-117">Opret en datakilde med navnet **eCommerce**, vælg importindstilling og **Text/CSV**-connectoren.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1eb2f-118">Angiv URL-adressen til eCommerce-kontakter [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="1eb2f-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="1eb2f-119">Når du redigerer dataene, skal du vælge **Transformer** og derefter **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1eb2f-120">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="1eb2f-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="1eb2f-121">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="1eb2f-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="1eb2f-122">**CreatedOn**: Dato/Klokkeslæt/Zone</span><span class="sxs-lookup"><span data-stu-id="1eb2f-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformere fødselsdato til dato.":::

1. <span data-ttu-id="1eb2f-124">Omdøb datakilde fra **Forespørgsel** til **eCommerceContacts** i feltet 'Navn' i ruden til højre.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="1eb2f-125">**Gem** datakilden.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="1eb2f-126">Indsættelse af online købsdata</span><span class="sxs-lookup"><span data-stu-id="1eb2f-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="1eb2f-127">Tilføj et andet datasæt til samme **eCommerce**-datakilde.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="1eb2f-128">Vælg **Tekst/CSV**-connector igen.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="1eb2f-129">Angiv URL-adressen til **onlinekøb**-data https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="1eb2f-130">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1eb2f-131">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="1eb2f-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="1eb2f-132">**PurchasedOn**: Dato/Klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="1eb2f-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="1eb2f-133">**TotalPrice**: Valuta</span><span class="sxs-lookup"><span data-stu-id="1eb2f-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="1eb2f-134">Omdøb datakilde fra **Forespørgsel** til **eCommercePurchases** i feltet **Navn** i sideruden.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="1eb2f-135">**Gem** datakilden.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="1eb2f-136">Indsæt kundedata fra loyalitetsskemaet</span><span class="sxs-lookup"><span data-stu-id="1eb2f-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="1eb2f-137">Opret en datakilde med navnet **LoyaltyScheme**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1eb2f-138">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="1eb2f-139">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1eb2f-140">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="1eb2f-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="1eb2f-141">**DateOfBirth**: Dato</span><span class="sxs-lookup"><span data-stu-id="1eb2f-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1eb2f-142">**RewardsPoints**: Heltal</span><span class="sxs-lookup"><span data-stu-id="1eb2f-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="1eb2f-143">**CreatedOn**: Dato/Klokkeslæt</span><span class="sxs-lookup"><span data-stu-id="1eb2f-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="1eb2f-144">Omdøb datakilde fra **Forespørgsel** til **loyCustomers** i feltet **Navn** i ruden til højre.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="1eb2f-145">**Gem** datakilden.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="1eb2f-146">Indsættelse af kundedata fra gennemsyn af websted</span><span class="sxs-lookup"><span data-stu-id="1eb2f-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="1eb2f-147">Opret en datakilde med navnet **Website**, vælg importindstilling og **Text/CSV**-connector.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1eb2f-148">Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="1eb2f-149">Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1eb2f-150">Opdater datatypen for de kolonner, der er angivet nedenfor:</span><span class="sxs-lookup"><span data-stu-id="1eb2f-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1eb2f-151">**ReviewRating**: Decimaltal</span><span class="sxs-lookup"><span data-stu-id="1eb2f-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="1eb2f-152">**ReviewDate**: Dato</span><span class="sxs-lookup"><span data-stu-id="1eb2f-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="1eb2f-153">Omdøb dine datakilde fra **Forespørgsel** til **Korrektur** i feltet "Navn" i øverste, højre rude.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="1eb2f-154">**Gem** datakilden.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="1eb2f-155">Opgave 2 - Datasamling</span><span class="sxs-lookup"><span data-stu-id="1eb2f-155">Task 2 - Data unification</span></span>

<span data-ttu-id="1eb2f-156">Når vi har indtaget dataene, begynder vi nu datasamlingen for at oprette en samlet kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="1eb2f-157">Du kan finde flere oplysninger i [Datasamling](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="1eb2f-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="1eb2f-158">Tilknytning</span><span class="sxs-lookup"><span data-stu-id="1eb2f-158">Map</span></span>

1. <span data-ttu-id="1eb2f-159">Når du har indsat dataene, skal du knytte kontakterne fra eCommerce- og Loyalty-data til almindelige datatyper.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="1eb2f-160">Go to **Data** > **Saml** > **Tilknyt**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="1eb2f-161">Vælg de objekter, der repræsenterer kundeprofilen - **eCommerceContacts** og **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="1eb2f-162">Vælg derefter **Anvend**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-162">Then, select **Apply**.</span></span>

   ![samle eCommerce- og loyalty-datakilder.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="1eb2f-164">Vælg **ContactId** som primær nøgle for **eCommerceContacts** og **LoyaltyID** som primær nøgle for **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Saml LoyaltyId som primær nøgle.](media/unify-loyaltyid.png)

1. <span data-ttu-id="1eb2f-166">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="1eb2f-167">Resultat</span><span class="sxs-lookup"><span data-stu-id="1eb2f-167">Match</span></span>

1. <span data-ttu-id="1eb2f-168">Gå til fanen **Match**, og vælg **Angiv rækkefølge**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="1eb2f-169">På rullelisten **Primær** skal du vælge **eCommerceContacts: e-handel** som den primære kilde og inkludere alle poster.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="1eb2f-170">På rullelisten **Entity 2** skal du vælge **loyCustomers: LoyaltyScheme** og medtage alle poster.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Saml og match eCommerce og Loyalty.](media/unify-match-order.png)

1. <span data-ttu-id="1eb2f-172">Vælg **Tilføj regel**</span><span class="sxs-lookup"><span data-stu-id="1eb2f-172">Select **Add rule**</span></span>

1. <span data-ttu-id="1eb2f-173">Tilføj din første betingelse ved hjælp af FullName.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="1eb2f-174">I forbindelse med eCommerceContacts skal du vælge **Fuldt navn** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="1eb2f-175">I forbindelse med loyCustomers skal du vælge **Fuldt navn** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="1eb2f-176">Vælg rullelisten **Normaliser**, og vælg **Type (Telefon, Navn, Adresse, ...)**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="1eb2f-177">Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="1eb2f-178">Angiv navnet **FullName, e-mail** til den nye regel.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="1eb2f-179">Tilføj endnu en betingelse for e-mailadressen ved at vælge **Tilføj betingelse**</span><span class="sxs-lookup"><span data-stu-id="1eb2f-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="1eb2f-180">For enhed eCommerceContacts skal du vælge **E-mail** i rullelisten.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="1eb2f-181">For enhed loyCustomers skal du vælge **E-mail** i rullelisten.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="1eb2f-182">Lad Normaliser være tom.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="1eb2f-183">Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Saml og match regel for navn og e-mail.](media/unify-match-rule.png)

1. <span data-ttu-id="1eb2f-185">Vælg **Udført**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-185">Select **Done**.</span></span>

1. <span data-ttu-id="1eb2f-186">Vælg **Gem** og **Kør**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="1eb2f-187">Fletning</span><span class="sxs-lookup"><span data-stu-id="1eb2f-187">Merge</span></span>

1. <span data-ttu-id="1eb2f-188">Gå til fanen **Flet**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="1eb2f-189">I **ContactId** for **loyCustomers** skal du ændre visningsnavn til **ContactIdLOYALTY** for at skelne mellem dem og andre id'er, der indsættes.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![omdøb contactid fra loyalty-id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="1eb2f-191">Vælg **Gem** og **Kør flettede og downstream-processer**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="1eb2f-192">Opgave 3 – Konfigurer værdien for forudsigelse af kundens levetidsværdi</span><span class="sxs-lookup"><span data-stu-id="1eb2f-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="1eb2f-193">Med de samlede kundeprofiler på plads kan vi nu køre forudsigelsen af kundens levetidsværdi.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="1eb2f-194">Du kan finde detaljerede trin i [Forudsigelse af kundens levetidsværdi (forhåndsversion)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="1eb2f-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="1eb2f-195">Gå til **Intelligens**  > **Forudsigelser**, og vælg **Model for kundens levetidsværdi**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="1eb2f-196">Gå gennem oplysningerne i sideruden, og vælg **Introduktion**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="1eb2f-197">Navngiv modellen **OOB eCommerce CLV-forudsigelse** og outputobjektet **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="1eb2f-198">Definer modelindstillinger for CLV-modellen:</span><span class="sxs-lookup"><span data-stu-id="1eb2f-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="1eb2f-199">**Forudsigelsesperiode**: **12 måneder eller 1 år**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="1eb2f-200">Denne indstilling definerer, hvor langt ind i fremtiden der kundens levetidsværdi skal forudsiges.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="1eb2f-201">**Aktive kunder**: Angiv, hvad aktive kunder betyder for din virksomhed.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="1eb2f-202">Angiv den historiske tidsramme, hvor en kunde skal have haft mindst én transaktion for at blive betragtet som aktiv.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="1eb2f-203">Modellen ønsker kun at bruge CLV til aktive kunder.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="1eb2f-204">Vælg mellem at lade modellen beregne tidsperioden baseret på historiske transaktionsdata, eller angiv en bestemt tidsramme.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="1eb2f-205">I denne eksempelvejledning lader vi **modellen beregne købsintervallet**, som er standardindstillingen.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="1eb2f-206">**Kunder af høj værdi**: Definer kunder af høj værdi som en fraktil af topbetalende kunder.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="1eb2f-207">Modellen bruger dette input til at levere resultater, der passer til din virksomhedsdefinition af kunder af høj værdi.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="1eb2f-208">Du kan vælge at lade modellen definere kunder med høj værdi.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="1eb2f-209">Den bruger en heuristisk regel, der udleder percentilen.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="1eb2f-210">Du kan også definere kunder af høj værdi som en percentil af fremtidige topbetalende kunder.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="1eb2f-211">I denne eksempelguide definerer vi manuelt kunder af høj værdi som **top 30 % af aktive betalende kunder** og vælger **Næste**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Præferencertrin i den guidede oplevelse for CLV-modellen.":::

1. <span data-ttu-id="1eb2f-213">I trinnet **Obligatoriske data** skal du vælge **Tilføj data** for at angive transaktionshistorikdataene.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="1eb2f-214">Tilføj objektet **eCommercePurchases: eCommerce**, og tilknyt de attributter, der kræves af modellen:</span><span class="sxs-lookup"><span data-stu-id="1eb2f-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="1eb2f-215">Transaktions-id: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="1eb2f-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="1eb2f-216">Transaktionsdato: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="1eb2f-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="1eb2f-217">Transaktionsbeløb: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="1eb2f-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="1eb2f-218">Produkt-id: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="1eb2f-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="1eb2f-219">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-219">Select **Next**.</span></span>

1. <span data-ttu-id="1eb2f-220">Konfigurer relationen mellem objektet **eCommercePurchases : eCommerce** og **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="1eb2f-221">Trinnet **Yderligere data (valgfrit)** giver dig mulighed for at tilføje flere kundeaktivitetsdata.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="1eb2f-222">Disse data kan hjælpe med at få mere indsigt i kundeinteraktioner med din virksomhed, hvilket kan bidrage til CLV.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="1eb2f-223">Tilføjelse af vigtige kundeinteraktioner som weblogfiler, kundeservicelogfiler eller belønningsprogramhistorik kan forbedre nøjagtigheden af forudsigelser.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="1eb2f-224">Vælg **Tilføj data** for at medtage flere kundeaktivitetsdata.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="1eb2f-225">Tilføj kundeaktivitetsobjektet, og knyt feltnavnene til de tilsvarende felter, der kræves af modellen:</span><span class="sxs-lookup"><span data-stu-id="1eb2f-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="1eb2f-226">Kundeaktivitetsobjekt: Anmeldelser:Websted</span><span class="sxs-lookup"><span data-stu-id="1eb2f-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="1eb2f-227">Primær nøgle: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="1eb2f-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="1eb2f-228">Tidsstempel: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="1eb2f-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="1eb2f-229">Hændelse (aktivitetsnavn): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="1eb2f-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="1eb2f-230">Detaljer (beløb eller værdi): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="1eb2f-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="1eb2f-231">Vælg **Næste**, og konfigurer aktiviteten og relationen mellem transaktionsdataene og kundedataene:</span><span class="sxs-lookup"><span data-stu-id="1eb2f-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="1eb2f-232">Aktivitetstype: Vælg eksisterende</span><span class="sxs-lookup"><span data-stu-id="1eb2f-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="1eb2f-233">Aktivitetsnavn: Anmeldelse</span><span class="sxs-lookup"><span data-stu-id="1eb2f-233">Activity label: Review</span></span>
   - <span data-ttu-id="1eb2f-234">Tilsvarende navn: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="1eb2f-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="1eb2f-235">Kundeobjekt: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="1eb2f-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="1eb2f-236">Relation: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="1eb2f-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="1eb2f-237">Vælg **Næste** for at angive modelplanen.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="1eb2f-238">Modellen skal træne regelmæssigt for at lære nye mønstre, når der er nye data indtaget.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="1eb2f-239">I dette eksempel skal du vælge **Månedlig**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="1eb2f-240">Vælg **Gem og Kør**, når du har gennemgået alle detaljer.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="1eb2f-241">Opgave 4 - Gennemse modelresultater og forklaringer</span><span class="sxs-lookup"><span data-stu-id="1eb2f-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="1eb2f-242">Lad modellen fuldføre med at få oplæring og resultaterne af dataene.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="1eb2f-243">Dernæst kan du gennemgå CLV-modellens resultater og forklaringer.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="1eb2f-244">Du kan finde flere oplysninger under [Gennemse en forudsigelsesstatus og resultater](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="1eb2f-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="1eb2f-245">Opgave 5 – Opret et segment af kunder af høj værdi</span><span class="sxs-lookup"><span data-stu-id="1eb2f-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="1eb2f-246">Når du kører modellen, oprettes der et nyt objekt, som vises i **Data** > **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="1eb2f-247">Du kan oprette en ny kundesegment baseret på det objekt, der er oprettet af modellen.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="1eb2f-248">Gå til **Segmenter**</span><span class="sxs-lookup"><span data-stu-id="1eb2f-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="1eb2f-249">Vælg **Ny**, og vælg **Opret fra** > **Intelligens**.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Oprettelse af et segment ved hjælp af model-output.](media/segment-intelligence.png)

1. <span data-ttu-id="1eb2f-251">Vælg enheden **OOBeCommerceCLVPrediction**, og definer segmentet:</span><span class="sxs-lookup"><span data-stu-id="1eb2f-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="1eb2f-252">Felt: CLVScore</span><span class="sxs-lookup"><span data-stu-id="1eb2f-252">Field: CLVScore</span></span>
  - <span data-ttu-id="1eb2f-253">Operatør: større end</span><span class="sxs-lookup"><span data-stu-id="1eb2f-253">Operator: greater than</span></span>
  - <span data-ttu-id="1eb2f-254">Værdi: 1500</span><span class="sxs-lookup"><span data-stu-id="1eb2f-254">Value: 1500</span></span>

1. <span data-ttu-id="1eb2f-255">Vælg **Gennemse** og **Gem** segmentet.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="1eb2f-256">Du har nu et segment, der identificerer kunder, der forventes at generere mere end $1500 i omsætning inden for de næste 12 måneder.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="1eb2f-257">Dette segment opdateres dynamisk, hvis der indtages flere data.</span><span class="sxs-lookup"><span data-stu-id="1eb2f-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="1eb2f-258">Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1eb2f-258">For more information, see [Create and manage segments](segments.md).</span></span>
