---
title: Tilsætning af tredjeparts forbedringer fra HERE Technologies
description: Generelle oplysninger om HERE Technologies-forbedringer.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597734"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="36c1c-103">Tilsætning af kundeprofiler ved hjælp af HERE Technologies (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="36c1c-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="36c1c-104">HERE Technologies er en lokationsplatformsvirksomhed, der leverer geografiske data og tjenester, der er centreret.</span><span class="sxs-lookup"><span data-stu-id="36c1c-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="36c1c-105">Med dataforbedringstjenester i HERE Technologies kan du oprette en mere præcis placering for dine kunder med normalisering af adresser, bredde- og længdegrader og meget mere.</span><span class="sxs-lookup"><span data-stu-id="36c1c-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36c1c-106">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="36c1c-106">Prerequisites</span></span>

<span data-ttu-id="36c1c-107">Følgende forudsætninger skal være opfyldt, hvis du vil konfigurere HERE Technologies-forbedringer:</span><span class="sxs-lookup"><span data-stu-id="36c1c-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="36c1c-108">Du skal have et aktivt HERE Technologies-abonnement.</span><span class="sxs-lookup"><span data-stu-id="36c1c-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="36c1c-109">Hvis du vil have et abonnement, kan du [tilmelde dig her](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkte.</span><span class="sxs-lookup"><span data-stu-id="36c1c-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="36c1c-110">Få mere at vide om HERE Technologies Forbedring af placeringsdata.</span><span class="sxs-lookup"><span data-stu-id="36c1c-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="36c1c-111">Du har API-nøglen til HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="36c1c-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="36c1c-112">Du har [Administrator](permissions.md#administrator)-tilladelser.</span><span class="sxs-lookup"><span data-stu-id="36c1c-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="36c1c-113">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="36c1c-113">Configuration</span></span>

1. <span data-ttu-id="36c1c-114">Gå til **Data** > **Forbedring**.</span><span class="sxs-lookup"><span data-stu-id="36c1c-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="36c1c-115">Vælg **Forbedring af dine data** på feltet HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="36c1c-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="36c1c-116">![HERE Technologies-felt](media/HERE-tile.png "HERE Technologies-felt")</span><span class="sxs-lookup"><span data-stu-id="36c1c-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="36c1c-117">Angiv en aktiv **HERE Technologies-API-nøgle**.</span><span class="sxs-lookup"><span data-stu-id="36c1c-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="36c1c-118">Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**.</span><span class="sxs-lookup"><span data-stu-id="36c1c-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="36c1c-119">Bekræft begge input ved at vælge **Opret forbindelse til HERE**.</span><span class="sxs-lookup"><span data-stu-id="36c1c-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="36c1c-120">Vælg **Tilføj data**, og vælg det **kundedatasæt**, du vil forbedre med lokationsdata fra HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="36c1c-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="36c1c-121">Du kan vælge objektet **Kunde** for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.</span><span class="sxs-lookup"><span data-stu-id="36c1c-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Skærmbillede, når du vælger kundedatasættet.":::

1. <span data-ttu-id="36c1c-123">Vælg, om du vil knytte felter til den primære og/eller sekundære adresse.</span><span class="sxs-lookup"><span data-stu-id="36c1c-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="36c1c-124">Du kan angive en felttilknytning for begge adresser (f. eks. privat-og firmaadresse) og forbedre profilerne for begge adresser separat.</span><span class="sxs-lookup"><span data-stu-id="36c1c-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="36c1c-125">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="36c1c-125">Select **Next**.</span></span>

1. <span data-ttu-id="36c1c-126">Definér, hvilke felter fra dine samlede profiler der skal bruges til at søge efter de tilsvarende placeringsdata fra HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="36c1c-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="36c1c-127">Felterne **Gade 1** og **postnummer** er obligatoriske for den valgte primære og/eller sekundære adresse.</span><span class="sxs-lookup"><span data-stu-id="36c1c-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="36c1c-128">Hvis du vil opnå en større overensstemmelse, kan du tilføje flere felter.</span><span class="sxs-lookup"><span data-stu-id="36c1c-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="36c1c-129">![HERE Technologies forbedret konfigurationsside](media/enrichment-HERE-configuration.png "HERE Technologies forbedret konfigurationsside")</span><span class="sxs-lookup"><span data-stu-id="36c1c-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="36c1c-130">Vælg **Anvend** for at fuldføre felttilknytningen.</span><span class="sxs-lookup"><span data-stu-id="36c1c-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="36c1c-131">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="36c1c-131">Enrichment results</span></span>

<span data-ttu-id="36c1c-132">Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="36c1c-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="36c1c-133">Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="36c1c-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="36c1c-134">Behandlingstiden afhænger af størrelsen på dine kundedata og de API-svartider, der er knyttet til HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="36c1c-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="36c1c-135">Når forbedringsprocessen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**.</span><span class="sxs-lookup"><span data-stu-id="36c1c-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="36c1c-136">Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.</span><span class="sxs-lookup"><span data-stu-id="36c1c-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="36c1c-137">Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.</span><span class="sxs-lookup"><span data-stu-id="36c1c-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="36c1c-138">Næste trin</span><span class="sxs-lookup"><span data-stu-id="36c1c-138">Next steps</span></span>

<span data-ttu-id="36c1c-139">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="36c1c-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="36c1c-140">Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.</span><span class="sxs-lookup"><span data-stu-id="36c1c-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="36c1c-141">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="36c1c-141">Data privacy and compliance</span></span>

<span data-ttu-id="36c1c-142">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til HERE Technologies, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="36c1c-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="36c1c-143">Microsoft overfører sådanne data under din instruktion, men du er ansvarlig for at sikre, at HERE Technologies overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="36c1c-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="36c1c-144">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="36c1c-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="36c1c-145">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="36c1c-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]