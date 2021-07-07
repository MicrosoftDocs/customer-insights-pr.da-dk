---
title: Forhøjelse af virksomhedsprofiler med tredjeparts Leadspace
description: Generelle oplysninger om Leadspace-tilsætning af tredjepart.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305195"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="c1a47-103">Forbedring af virksomhedsprofiler med Leadspace (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="c1a47-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="c1a47-104">Leadspace er en videnskabelig datavirksomhed, der leverer en B2B-kundedataplatform.</span><span class="sxs-lookup"><span data-stu-id="c1a47-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="c1a47-105">Den gør det muligt for kunder, der har en samlet kundeprofil for virksomheder, at forbedre deres data.</span><span class="sxs-lookup"><span data-stu-id="c1a47-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="c1a47-106">Forbedringer omfatter flere attributter, herunder firmastørrelse, lokation, branche og meget mere.</span><span class="sxs-lookup"><span data-stu-id="c1a47-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c1a47-107">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="c1a47-107">Prerequisites</span></span>

<span data-ttu-id="c1a47-108">Hvis du vil konfigurere Leadspace, skal følgende forudsætninger være opfyldt:</span><span class="sxs-lookup"><span data-stu-id="c1a47-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c1a47-109">Du har en aktiv Leadspace-licens.</span><span class="sxs-lookup"><span data-stu-id="c1a47-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="c1a47-110">Du har [samlede kundeprofiler](customer-profiles.md) til virksomheder.</span><span class="sxs-lookup"><span data-stu-id="c1a47-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="c1a47-111">En Leadspace-forbindelse er allerede konfigureret af en administrator, eller du har [administrator](permissions.md#administrator)-tilladelser og den "permanente nøgle" (kaldes også **Leadspace-token**).</span><span class="sxs-lookup"><span data-stu-id="c1a47-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="c1a47-112">Kontakt [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) direkte for at få oplysninger om produktet.</span><span class="sxs-lookup"><span data-stu-id="c1a47-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="c1a47-113">Konfiguration af forbedring</span><span class="sxs-lookup"><span data-stu-id="c1a47-113">Configure the enrichment</span></span>

1. <span data-ttu-id="c1a47-114">Gå til **Data** > **Forbedring** i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="c1a47-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="c1a47-115">Vælg **Forbedr mine data** i feltet Leadspace, og vælg **Start her**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skærmbillede af Leadspace-feltet.":::

1. <span data-ttu-id="c1a47-117">Vælg en [værdi](connections.md) på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="c1a47-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="c1a47-118">Kontakt en administrator, hvis der ikke er nogen forbindelse.</span><span class="sxs-lookup"><span data-stu-id="c1a47-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="c1a47-119">Hvis du er administrator, kan du oprette en forbindelse ved at vælge **Tilføj forbindelse** og vælge **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="c1a47-120">Vælg **Opret forbindelse til Leadspace** for at bekræfte den valgte forbindelse.</span><span class="sxs-lookup"><span data-stu-id="c1a47-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="c1a47-121">Vælg **Næste**, og angiv de **Kundedatasæt**, du vil forbedre med firmadata fra Leadspace.</span><span class="sxs-lookup"><span data-stu-id="c1a47-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="c1a47-122">Du kan vælge objektet **Kunde** for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.</span><span class="sxs-lookup"><span data-stu-id="c1a47-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Skærmbillede, når du vælger kundedatasættet.":::

1. <span data-ttu-id="c1a47-124">Vælg **Næste**, og definer, hvilke felter fra dine samlede profiler der bruges til at søge efter tilsvarende virksomhedsdata fra Leadspace.</span><span class="sxs-lookup"><span data-stu-id="c1a47-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="c1a47-125">Feltet **Firmanavn** er obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="c1a47-125">The **Name of company** field is required.</span></span> <span data-ttu-id="c1a47-126">Hvis du vil opnå en større overensstemmelse, kan du tilføje op til to andre felter, **Virksomheds-websteder** og **Virksomhedsplacering**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-felttilknytningsruden.":::

1. <span data-ttu-id="c1a47-128">Når du har fuldført felttilknytningen, skal du vælge **Næste**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="c1a47-129">Angiv et navn til den forbedring, du udvælger, og angiv **Vælg forbedring**, når du har gennemset dine valg.</span><span class="sxs-lookup"><span data-stu-id="c1a47-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="c1a47-130">Konfiguration af forbindelsen til Leadspace</span><span class="sxs-lookup"><span data-stu-id="c1a47-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="c1a47-131">Du skal være en administrator for at konfigurere forbindelser.</span><span class="sxs-lookup"><span data-stu-id="c1a47-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="c1a47-132">Vælg **Tilføj forbindelse**, når du konfigurerer en konfiguration, *eller* gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i feltet Leadspace.</span><span class="sxs-lookup"><span data-stu-id="c1a47-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="c1a47-133">Vælg **Introduktion**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="c1a47-134">Angiv et navn til forbindelsen i feltet **Vis navn**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="c1a47-135">Angiv dit Leadspace-token</span><span class="sxs-lookup"><span data-stu-id="c1a47-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="c1a47-136">Gennemse og giv dit samtykke til **Beskyttelse af personlige oplysninger og overholdelse af data** ved at vælge **Jeg accepterer**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="c1a47-137">Vælg **Kontroller** for at validere konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="c1a47-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="c1a47-138">Vælg **Gem**, når verifikationen er fuldført.</span><span class="sxs-lookup"><span data-stu-id="c1a47-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace-forbindelsens konfigurationsside.":::

## <a name="enrichment-results"></a><span data-ttu-id="c1a47-140">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="c1a47-140">Enrichment results</span></span>

<span data-ttu-id="c1a47-141">Når du har opdateret forbedring, kan du gennemse de netop forbedrede virksomhedsdata under [Mine forbedringer](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="c1a47-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="c1a47-142">Du kan se tidspunktet for den seneste opdatering og antallet af forbedrede profiler.</span><span class="sxs-lookup"><span data-stu-id="c1a47-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c1a47-143">Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.</span><span class="sxs-lookup"><span data-stu-id="c1a47-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="c1a47-144">Du kan finde flere oplysninger under [Leadspace-API'er](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="c1a47-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c1a47-145">Næste trin</span><span class="sxs-lookup"><span data-stu-id="c1a47-145">Next steps</span></span>

<span data-ttu-id="c1a47-146">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="c1a47-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c1a47-147">Opret [segmenter](segments.md) og [målpunkter](measures.md), og [eksporter endda dataene](export-destinations.md) for at levere personlige oplevelser til dine kunder.</span><span class="sxs-lookup"><span data-stu-id="c1a47-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c1a47-148">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="c1a47-148">Data privacy and compliance</span></span>

<span data-ttu-id="c1a47-149">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Leadspace, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="c1a47-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c1a47-150">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Leadspace overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="c1a47-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c1a47-151">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c1a47-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c1a47-152">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="c1a47-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
