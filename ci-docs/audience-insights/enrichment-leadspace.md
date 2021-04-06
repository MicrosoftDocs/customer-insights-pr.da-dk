---
title: Forhøjelse af virksomhedsprofiler med tredjeparts Leadspace
description: Generelle oplysninger om Leadspace-tilsætning af tredjepart.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597642"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="dd6f7-103">Forbedring af virksomhedsprofiler med Leadspace (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="dd6f7-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="dd6f7-104">Leadspace er en videnskabelig datavirksomhed, der leverer en B2B-kundedataplatform.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="dd6f7-105">Den gør det muligt for kunder, der har en samlet kundeprofil for virksomheder, at forbedre deres data.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="dd6f7-106">Forbedringer omfatter yderligere attributter som f.eks. firmastørrelse, lokation, branche og meget mere.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dd6f7-107">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="dd6f7-107">Prerequisites</span></span>

<span data-ttu-id="dd6f7-108">Hvis du vil konfigurere Leadspace, skal følgende forudsætninger være opfyldt:</span><span class="sxs-lookup"><span data-stu-id="dd6f7-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="dd6f7-109">Du har en aktiv Leadspace-licens og den "permanente nøgle" (kaldes **Leadspace token**).</span><span class="sxs-lookup"><span data-stu-id="dd6f7-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="dd6f7-110">Kontakt direkte [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for at få oplysninger om deres produkt.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="dd6f7-111">Du har [Administrator](permissions.md#administrator)-tilladelser.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="dd6f7-112">Du har [samlede kundeprofiler](customer-profiles.md) til virksomheder.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="dd6f7-113">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="dd6f7-113">Configuration</span></span>

1. <span data-ttu-id="dd6f7-114">Gå til **Data** > **Forbedring** i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="dd6f7-115">Vælg **Forbedr mine data** på Leadspace-feltet.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Skærmbillede af Leadspace-feltet.":::

1. <span data-ttu-id="dd6f7-117">Vælg **Start her**, og angiv derefter et aktivt **Leadspace-token** (permanent nøgle).</span><span class="sxs-lookup"><span data-stu-id="dd6f7-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="dd6f7-118">Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="dd6f7-119">Bekræft begge input ved at vælge **Opret forbindelse til Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="dd6f7-120">Vælg **Tilknyt data** , og vælg det datasæt, du vil forbedre med firmadata fra Leadspace.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="dd6f7-121">Du kan vælge objektet *Kunde* for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Vælg mellem kundeprofil og forbedring af segment.":::

1. <span data-ttu-id="dd6f7-123">Klik på **Næste**, og definer, hvilke felter fra dine samlede profiler der skal bruges til at søge efter de tilsvarende virksomhedsdata fra Leadspace.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="dd6f7-124">Feltet **Firmanavn** er obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-124">The **Name of company** field is required.</span></span> <span data-ttu-id="dd6f7-125">Hvis du vil opnå en større overensstemmelse, kan du tilføje op til to andre felter, **Virksomheds-websteder** og **Virksomhedsplacering**.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace-felttilknytningsruden.":::
   
1. <span data-ttu-id="dd6f7-127">Vælg **Anvend** for at fuldføre felttilknytningen.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="dd6f7-128">Vælg **Kør** for at forbedre firmaprofilerne.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="dd6f7-129">Hvor længe en forbedring tager, afhænger af antallet af samlede kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="dd6f7-130">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="dd6f7-130">Enrichment results</span></span>

<span data-ttu-id="dd6f7-131">Når du har opdateret forbedring, kan du gennemse de netop forbedrede virksomhedsdata under [Mine forbedringer](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="dd6f7-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="dd6f7-132">Du kan se tidspunktet for den seneste opdatering og antallet af forbedrede profiler.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="dd6f7-133">Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="dd6f7-134">Du kan finde flere oplysninger under [Leadspace-API'er](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="dd6f7-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="dd6f7-135">Næste trin</span><span class="sxs-lookup"><span data-stu-id="dd6f7-135">Next steps</span></span>

<span data-ttu-id="dd6f7-136">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dd6f7-137">Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dd6f7-138">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="dd6f7-138">Data privacy and compliance</span></span>

<span data-ttu-id="dd6f7-139">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Leadspace, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dd6f7-140">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Leadspace overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dd6f7-141">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dd6f7-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dd6f7-142">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="dd6f7-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]