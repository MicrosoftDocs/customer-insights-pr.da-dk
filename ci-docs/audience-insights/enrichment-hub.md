---
title: Forbedring af samlede kundeprofiler
description: Du kan bruge egenskaber til at forbedre dine kundedata.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305241"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="7670a-103">Forbedring af kundeprofiler (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="7670a-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="7670a-104">Brug data fra kilder som f.eks. Microsoft og andre partnere til at forbedre kundedataene.</span><span class="sxs-lookup"><span data-stu-id="7670a-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Hubside for forbedring":::

<span data-ttu-id="7670a-106">Hvis du målgruppeindsigt, kan du gå til **Data** > **Forbedring** for at arbejde sammen med forbedringsmuligheder.</span><span class="sxs-lookup"><span data-stu-id="7670a-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="7670a-107">Du skal have bidragyder- eller administratortilladelser for at kunne oprette eller redigere forbedringer.</span><span class="sxs-lookup"><span data-stu-id="7670a-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="7670a-108">Du kan finde flere oplysninger under [Tilladelser](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="7670a-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="7670a-109">Under fanen **Opdag** kan du se følgende forbedringer:</span><span class="sxs-lookup"><span data-stu-id="7670a-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="7670a-110">[Varemærker](enrichment-microsoft.md) leveret af Microsoft</span><span class="sxs-lookup"><span data-stu-id="7670a-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="7670a-111">[Interesser](enrichment-microsoft.md) leveret af Microsoft</span><span class="sxs-lookup"><span data-stu-id="7670a-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="7670a-112">[Udvidede adresser](enrichment-enhanced-addresses.md) leveret af Microsoft</span><span class="sxs-lookup"><span data-stu-id="7670a-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="7670a-113">[Firmadata](enrichment-leadspace.md) leveret af Leadspace</span><span class="sxs-lookup"><span data-stu-id="7670a-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="7670a-114">[Demografiske oplysninger](enrichment-experian.md) leveret af Experian</span><span class="sxs-lookup"><span data-stu-id="7670a-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="7670a-115">[Lokationsdata](enrichment-here.md) leveret af HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="7670a-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="7670a-116">[Brugerdefineret data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="7670a-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="7670a-117">Under fanen **Mine forbedringer** kan du se de forbedringer, du har konfigureret, og redigere deres egenskaber.</span><span class="sxs-lookup"><span data-stu-id="7670a-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="7670a-118">Administrer eksisterende forbedringer</span><span class="sxs-lookup"><span data-stu-id="7670a-118">Manage existing enrichments</span></span>

<span data-ttu-id="7670a-119">Gå til fanen **Mine forbedringer** for at se alle konfigurerede forbedringer.</span><span class="sxs-lookup"><span data-stu-id="7670a-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="7670a-120">Hver forbedring repræsenteres som en række, der indeholder yderligere oplysninger om forbedringen.</span><span class="sxs-lookup"><span data-stu-id="7670a-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="7670a-121">Vælg en forbedring for at få vist de tilgængelige indstillinger.</span><span class="sxs-lookup"><span data-stu-id="7670a-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="7670a-122">Du kan også vælge ellipsen (...) på et listeelement for at se indstillingerne.</span><span class="sxs-lookup"><span data-stu-id="7670a-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Indstillinger til administration af forbedringer på listen over forbedringer":::

- <span data-ttu-id="7670a-124">**Vis** oplysninger om forbedringer med antallet af forbedrede kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="7670a-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="7670a-125">**Rediger** konfigurationen af forbedringen.</span><span class="sxs-lookup"><span data-stu-id="7670a-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="7670a-126">**Kør** forbedringen for at opdatere kundeprofiler med de nyeste data.</span><span class="sxs-lookup"><span data-stu-id="7670a-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="7670a-127">**Deaktiver** en eksisterende forbedring for at forhindre, at den opdateres automatisk i alle planlagte opdateringer.</span><span class="sxs-lookup"><span data-stu-id="7670a-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="7670a-128">Data fra den seneste vellykkede opdatering vil fortsat være tilgængelige.</span><span class="sxs-lookup"><span data-stu-id="7670a-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="7670a-129">**Aktivér** en inaktiv forbedring, hvis du vil genstarte automatisk opdatering for hver planlagt opdatering.</span><span class="sxs-lookup"><span data-stu-id="7670a-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="7670a-130">Vil du **slette** en forbedring?</span><span class="sxs-lookup"><span data-stu-id="7670a-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="7670a-131">Du kan køre eller deaktivere flere forbedringer på én gang ved at vælge dem på listen.</span><span class="sxs-lookup"><span data-stu-id="7670a-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="7670a-132">Indstillingerne Vis og Rediger er ikke tilgængelige som massehandlinger og kan kun bruges med én forbedring ad gangen.</span><span class="sxs-lookup"><span data-stu-id="7670a-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="7670a-133">Forbedringer og forbindelser</span><span class="sxs-lookup"><span data-stu-id="7670a-133">Enrichments and connections</span></span>

<span data-ttu-id="7670a-134">Konfigurationer fra tredjeparter konfigureres ved hjælp af [forbindelser](connections.md), som en administrator konfigurerer med legitimationsoplysninger og giver samtykke til dataoverførsler.</span><span class="sxs-lookup"><span data-stu-id="7670a-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="7670a-135">Forbindelsen kan derefter bruges af både administratorer og bidragydere til at konfigurere forbedringer.</span><span class="sxs-lookup"><span data-stu-id="7670a-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="7670a-136">Flere forbedringer af samme type</span><span class="sxs-lookup"><span data-stu-id="7670a-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="7670a-137">Det objekt, der skal forbedres, angives under forbedringskonfigurationen med mulighed for forbedring, som gør det muligt kun at forbedre et undersæt af dine profiler.</span><span class="sxs-lookup"><span data-stu-id="7670a-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="7670a-138">Du kan f.eks. kun forbedre data for et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="7670a-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="7670a-139">Du kan konfigurere flere forbedringer af samme type og genbruge den samme forbindelse.</span><span class="sxs-lookup"><span data-stu-id="7670a-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="7670a-140">Nogle forbedringer har grænser for antallet af forbedringer af samme type, der kan oprettes.</span><span class="sxs-lookup"><span data-stu-id="7670a-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="7670a-141">Grænseværdierne og den aktuelle brug kan ses på siden **Forbedring**.</span><span class="sxs-lookup"><span data-stu-id="7670a-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
