---
title: Tilsætning af tredjeparts forbedringer fra HERE Technologies
description: Generelle oplysninger om HERE Technologies-forbedringer.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896044"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="bd365-103">Tilsætning af kundeprofiler ved hjælp af HERE Technologies (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="bd365-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="bd365-104">HERE Technologies er en lokationsplatformsvirksomhed, der leverer geografiske data og tjenester, der er centreret.</span><span class="sxs-lookup"><span data-stu-id="bd365-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="bd365-105">Med dataforbedringstjenester i HERE Technologies kan du oprette en mere præcis placering for dine kunder med normalisering af adresser, bredde- og længdegrader og meget mere.</span><span class="sxs-lookup"><span data-stu-id="bd365-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bd365-106">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="bd365-106">Prerequisites</span></span>

<span data-ttu-id="bd365-107">Følgende forudsætninger skal være opfyldt, hvis du vil konfigurere HERE Technologies-forbedringer:</span><span class="sxs-lookup"><span data-stu-id="bd365-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="bd365-108">Du skal have et aktivt HERE Technologies-abonnement.</span><span class="sxs-lookup"><span data-stu-id="bd365-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="bd365-109">Hvis du vil have et abonnement, kan du [tilmelde dig her](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) eller [kontakte HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) direkte.</span><span class="sxs-lookup"><span data-stu-id="bd365-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="bd365-110">Få mere at vide om HERE Technologies Forbedring af placeringsdata.</span><span class="sxs-lookup"><span data-stu-id="bd365-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="bd365-111">Der er en HERE-[forbindelse](connections.md) tilgængelig *eller* du har [administrator](permissions.md#administrator)-tilladelser og HERE Technologies API-nøglen.</span><span class="sxs-lookup"><span data-stu-id="bd365-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="bd365-112">Konfiguration af forbedring</span><span class="sxs-lookup"><span data-stu-id="bd365-112">Configure the enrichment</span></span>

1. <span data-ttu-id="bd365-113">Gå til **Data** > **Forbedring**.</span><span class="sxs-lookup"><span data-stu-id="bd365-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="bd365-114">Vælg **Forbedr mine data** i feltet HERE Technologies, og vælg **Start her**.</span><span class="sxs-lookup"><span data-stu-id="bd365-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bd365-115">![HERE Technologies-felt](media/HERE-tile.png "HERE Technologies-felt")</span><span class="sxs-lookup"><span data-stu-id="bd365-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="bd365-116">Vælg en [forbindelse](connections.md) på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="bd365-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="bd365-117">Kontakt en administrator, hvis der ikke er nogen forbindelse.</span><span class="sxs-lookup"><span data-stu-id="bd365-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="bd365-118">Hvis du er administrator, kan du oprette en forbindelse ved at vælge **Tilføj forbindelse**.</span><span class="sxs-lookup"><span data-stu-id="bd365-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="bd365-119">Vælg **HERE Technologies** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="bd365-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="bd365-120">Vælg **Opret forbindelse til HERE Technologies** for at bekræfte valget.</span><span class="sxs-lookup"><span data-stu-id="bd365-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="bd365-121">Vælg **Næste**, og angiv de **Kundedatasæt**, du vil forbedre med lokationsdata fra HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bd365-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="bd365-122">Du kan vælge objektet **Kunde** for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.</span><span class="sxs-lookup"><span data-stu-id="bd365-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Skærmbillede, når du vælger kundedatasættet.":::

1. <span data-ttu-id="bd365-124">Vælg, om du vil knytte felter til den primære og/eller sekundære adresse.</span><span class="sxs-lookup"><span data-stu-id="bd365-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="bd365-125">Du kan angive en felttilknytning for begge adresser og forbedre profilerne for begge adresser separat.</span><span class="sxs-lookup"><span data-stu-id="bd365-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="bd365-126">Hvis der f.eks. er en privatadresse og en forretningsadresse.</span><span class="sxs-lookup"><span data-stu-id="bd365-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="bd365-127">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="bd365-127">Select **Next**.</span></span>

1. <span data-ttu-id="bd365-128">Definér, hvilke felter fra dine samlede profiler der skal bruges til at søge efter de tilsvarende placeringsdata fra HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bd365-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="bd365-129">Felterne **Gade 1** og **postnummer** er obligatoriske for den valgte primære og/eller sekundære adresse.</span><span class="sxs-lookup"><span data-stu-id="bd365-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="bd365-130">Hvis du vil opnå en større overensstemmelse, kan du tilføje flere felter.</span><span class="sxs-lookup"><span data-stu-id="bd365-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bd365-131">![HERE Technologies forbedret konfigurationsside](media/enrichment-HERE-configuration.png "HERE Technologies forbedret konfigurationsside")</span><span class="sxs-lookup"><span data-stu-id="bd365-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="bd365-132">Når du har fuldført felttilknytningen, skal du vælge **Næste**.</span><span class="sxs-lookup"><span data-stu-id="bd365-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="bd365-133">Angiv et Navn til forbedringen.</span><span class="sxs-lookup"><span data-stu-id="bd365-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="bd365-134">1.Vælg **Gem forbedring**, når du har gennemset dine valg.</span><span class="sxs-lookup"><span data-stu-id="bd365-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="bd365-135">Konfiguration af forbindelsen til HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="bd365-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="bd365-136">Du skal være en administrator for at konfigurere forbindelser.</span><span class="sxs-lookup"><span data-stu-id="bd365-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="bd365-137">Vælg **Tilføj forbindelse**, når du konfigurerer en konfiguration, *eller* gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i feltet HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bd365-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="bd365-138">Angiv et navn til forbindelsen i feltet **Vis navn**.</span><span class="sxs-lookup"><span data-stu-id="bd365-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="bd365-139">Angiv en gyldig API-nøgle til HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bd365-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="bd365-140">Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**</span><span class="sxs-lookup"><span data-stu-id="bd365-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="bd365-141">Vælg **Kontroller** for at validere konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="bd365-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="bd365-142">Vælg **Gem**, når verifikationen er fuldført.</span><span class="sxs-lookup"><span data-stu-id="bd365-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="bd365-143">![HERE Technologies-forbindelsens konfigurationsside](media/enrichment-HERE-connection.png "HERE Technologies-forbindelsens konfigurationsside")</span><span class="sxs-lookup"><span data-stu-id="bd365-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="bd365-144">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="bd365-144">Enrichment results</span></span>

<span data-ttu-id="bd365-145">Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="bd365-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="bd365-146">Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bd365-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bd365-147">Behandlingstiden afhænger af størrelsen på dine kundedata og de API-svartider, der er knyttet til HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bd365-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="bd365-148">Når forbedringsprocessen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**.</span><span class="sxs-lookup"><span data-stu-id="bd365-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="bd365-149">Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.</span><span class="sxs-lookup"><span data-stu-id="bd365-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="bd365-150">Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.</span><span class="sxs-lookup"><span data-stu-id="bd365-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bd365-151">Næste trin</span><span class="sxs-lookup"><span data-stu-id="bd365-151">Next steps</span></span>

<span data-ttu-id="bd365-152">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="bd365-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bd365-153">Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.</span><span class="sxs-lookup"><span data-stu-id="bd365-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bd365-154">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="bd365-154">Data privacy and compliance</span></span>

<span data-ttu-id="bd365-155">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til HERE Technologies, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="bd365-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bd365-156">Microsoft overfører sådanne data under din instruktion, men du er ansvarlig for at sikre, at HERE Technologies overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="bd365-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bd365-157">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bd365-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bd365-158">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="bd365-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
