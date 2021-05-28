---
title: Håndtere udvidede forbedringer
description: Udvid og normaliser adresseoplysninger om kundeprofiler med Microsofts modeller.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965571"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="1129c-103">Udvidelse af kundeprofiler med forbedrede adresser</span><span class="sxs-lookup"><span data-stu-id="1129c-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="1129c-104">Adresser i dine data kan være ustrukturerede, ufuldstændige eller forkerte.</span><span class="sxs-lookup"><span data-stu-id="1129c-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="1129c-105">Brug Microsofts modeller til at normalisere og forbedre dine adresser i [Common Data Model-formatet](/common-data-model/schema/core/applicationcommon/address) for at opnå større nøjagtighed og indsigt.</span><span class="sxs-lookup"><span data-stu-id="1129c-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="1129c-106">Sådan forbedrer vi adresser</span><span class="sxs-lookup"><span data-stu-id="1129c-106">How we enhance addresses</span></span>

<span data-ttu-id="1129c-107">Vores model gennemgår en to-trinnet proces for at forbedre en adresse.</span><span class="sxs-lookup"><span data-stu-id="1129c-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="1129c-108">For det første analyserer den adressen for at identificere dens komponenter og sætter dem i et struktureret format.</span><span class="sxs-lookup"><span data-stu-id="1129c-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="1129c-109">Derefter bruger vi kunstig intelligens til at korrigere, fuldføre og standardisere værdierne i adressen.</span><span class="sxs-lookup"><span data-stu-id="1129c-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="1129c-110">Eksempel</span><span class="sxs-lookup"><span data-stu-id="1129c-110">Example</span></span>

<span data-ttu-id="1129c-111">Adresseoplysningerne kan være i et ikke-standardformat og indeholde stavefejl.</span><span class="sxs-lookup"><span data-stu-id="1129c-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="1129c-112">Modellen kan løse disse problemer og oprette ensartede adresser i samlede kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="1129c-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="1129c-113">Begrænsninger</span><span class="sxs-lookup"><span data-stu-id="1129c-113">Limitations</span></span>

<span data-ttu-id="1129c-114">Forbedrede adresser fungerer kun sammen med de værdier, der allerede findes i dine adressedata, der er indtaget.</span><span class="sxs-lookup"><span data-stu-id="1129c-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="1129c-115">Modellen gør ikke dette:</span><span class="sxs-lookup"><span data-stu-id="1129c-115">The model doesn't:</span></span> 

1. <span data-ttu-id="1129c-116">Kontrollerer, om adressen er en gyldig adresse.</span><span class="sxs-lookup"><span data-stu-id="1129c-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="1129c-117">Kontrollerer, om nogen af værdierne, f.eks. postnumre eller gadenavne, er gyldige.</span><span class="sxs-lookup"><span data-stu-id="1129c-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="1129c-118">Skifter værdier, der ikke genkendes.</span><span class="sxs-lookup"><span data-stu-id="1129c-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="1129c-119">Modellen bruger maskinel indlæringsbaserede teknikker til at forbedre adresser.</span><span class="sxs-lookup"><span data-stu-id="1129c-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="1129c-120">Selvom vi anvender en høj konfidenstærskel for, hvornår modellen ændrer en inputværdi, er 100 % nøjagtighed, som med enhver ML-baseret model, ikke garanteret.</span><span class="sxs-lookup"><span data-stu-id="1129c-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="1129c-121">Understøttede lande eller områder</span><span class="sxs-lookup"><span data-stu-id="1129c-121">Supported countries or regions</span></span>

<span data-ttu-id="1129c-122">Vi understøtter i øjeblikket forbedrede adresser i disse lande eller områder:</span><span class="sxs-lookup"><span data-stu-id="1129c-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="1129c-123">Australien</span><span class="sxs-lookup"><span data-stu-id="1129c-123">Australia</span></span>
- <span data-ttu-id="1129c-124">Canada</span><span class="sxs-lookup"><span data-stu-id="1129c-124">Canada</span></span>
- <span data-ttu-id="1129c-125">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="1129c-125">United Kingdom</span></span>
- <span data-ttu-id="1129c-126">USA</span><span class="sxs-lookup"><span data-stu-id="1129c-126">United States</span></span>

<span data-ttu-id="1129c-127">Adresser skal indeholde en værdi for land/område.</span><span class="sxs-lookup"><span data-stu-id="1129c-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="1129c-128">Vi behandler ikke adresser for lande eller områder, der ikke understøttes, og adresser, der ikke har angivet noget land eller område.</span><span class="sxs-lookup"><span data-stu-id="1129c-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="1129c-129">Konfiguration af forbedring</span><span class="sxs-lookup"><span data-stu-id="1129c-129">Configure the enrichment</span></span>

1. <span data-ttu-id="1129c-130">Gå til **Data** > **Forbedring**.</span><span class="sxs-lookup"><span data-stu-id="1129c-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="1129c-131">Vælg **Forbedr mine data** på feltet **Udvidede adresser**.</span><span class="sxs-lookup"><span data-stu-id="1129c-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Skærmbillede af feltet Udvidede adresser.":::

1. <span data-ttu-id="1129c-133">Vælg **Kundedatasæt**, og vælg det objekt, der indeholder de adresser, du vil forbedre.</span><span class="sxs-lookup"><span data-stu-id="1129c-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="1129c-134">Du kan vælge objektet *Kunde* for at forbedre adresser i alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre adresser i kundeprofiler, der er indeholdt i det pågældende segment.</span><span class="sxs-lookup"><span data-stu-id="1129c-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="1129c-135">Vælg, hvordan adresser formateres i dit datasæt.</span><span class="sxs-lookup"><span data-stu-id="1129c-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="1129c-136">Vælg **Adresse med en enkelt attribut**, hvis adresserne i dataene bruger et enkelt felt.</span><span class="sxs-lookup"><span data-stu-id="1129c-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="1129c-137">Vælg **Multiattributadresse**, hvis adresserne i dataene bruger mere end et enkelt datafelt.</span><span class="sxs-lookup"><span data-stu-id="1129c-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1129c-138">Land/område er obligatorisk i både enkeltattribut- og multiattributadresser.</span><span class="sxs-lookup"><span data-stu-id="1129c-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="1129c-139">Adresser, der ikke indeholder gyldige eller understøttede værdier for land/område, vil ikke blive forbedret</span><span class="sxs-lookup"><span data-stu-id="1129c-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="1129c-140">Tilknyt adressefelterne fra dit samlede kundeobjekt.</span><span class="sxs-lookup"><span data-stu-id="1129c-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Udvidet side til tilknytning af adressefelt.":::

1. <span data-ttu-id="1129c-142">Når du har fuldført felttilknytningen, skal du vælge **Næste**.</span><span class="sxs-lookup"><span data-stu-id="1129c-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="1129c-143">Angiv et navn til forbedringen og outputobjektet.</span><span class="sxs-lookup"><span data-stu-id="1129c-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="1129c-144">Vælg **Gem valgmuligheder**, når du har gennemset dine valg.</span><span class="sxs-lookup"><span data-stu-id="1129c-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="1129c-145">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="1129c-145">Enrichment results</span></span>

<span data-ttu-id="1129c-146">Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="1129c-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="1129c-147">Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1129c-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1129c-148">Behandlingstiden afhænger af størrelsen på dine kundedata.</span><span class="sxs-lookup"><span data-stu-id="1129c-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="1129c-149">Når forbedringsprocessen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**.</span><span class="sxs-lookup"><span data-stu-id="1129c-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="1129c-150">Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.</span><span class="sxs-lookup"><span data-stu-id="1129c-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="1129c-151">Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.</span><span class="sxs-lookup"><span data-stu-id="1129c-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1129c-152">Næste trin</span><span class="sxs-lookup"><span data-stu-id="1129c-152">Next steps</span></span>

<span data-ttu-id="1129c-153">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="1129c-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="1129c-154">Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.</span><span class="sxs-lookup"><span data-stu-id="1129c-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
