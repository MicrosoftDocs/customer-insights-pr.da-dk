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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895998"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="3e666-103">Forbedring af kundeprofiler (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="3e666-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="3e666-104">Brug data fra kilder som f.eks. Microsoft og andre partnere til at forbedre kundedataene.</span><span class="sxs-lookup"><span data-stu-id="3e666-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Hubside for forbedring":::

<span data-ttu-id="3e666-106">Hvis du målgruppeindsigt, kan du gå til **Data** > **Forbedring** for at arbejde sammen med forbedringsmuligheder.</span><span class="sxs-lookup"><span data-stu-id="3e666-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="3e666-107">Du skal have bidragyder- eller administratortilladelser for at kunne oprette eller redigere forbedringer.</span><span class="sxs-lookup"><span data-stu-id="3e666-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="3e666-108">Du kan finde flere oplysninger under [Tilladelser](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3e666-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="3e666-109">Under fanen **Opdag** kan du se følgende forbedringer:</span><span class="sxs-lookup"><span data-stu-id="3e666-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="3e666-110">[Varemærker](enrichment-microsoft.md) leveret af Microsoft</span><span class="sxs-lookup"><span data-stu-id="3e666-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="3e666-111">[Interesser](enrichment-microsoft.md) leveret af Microsoft</span><span class="sxs-lookup"><span data-stu-id="3e666-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="3e666-112">[Firmadata](enrichment-leadspace.md) leveret af Leadspace</span><span class="sxs-lookup"><span data-stu-id="3e666-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="3e666-113">[Demografi](enrichment-experian.md) leveret af Experian</span><span class="sxs-lookup"><span data-stu-id="3e666-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="3e666-114">[Lokationsdata](enrichment-here.md) leveret af HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="3e666-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="3e666-115">[Brugerdefineret data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="3e666-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="3e666-116">Under fanen **Mine forbedringer** kan du se de forbedringer, du har konfigureret, og redigere deres egenskaber.</span><span class="sxs-lookup"><span data-stu-id="3e666-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="3e666-117">Administrer eksisterende forbedringer</span><span class="sxs-lookup"><span data-stu-id="3e666-117">Manage existing enrichments</span></span>

<span data-ttu-id="3e666-118">Gå til **Mine forbedringer** for at få vist alle konfigurerede forbedringer.</span><span class="sxs-lookup"><span data-stu-id="3e666-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="3e666-119">Hver forbedring repræsenteres som en række, der indeholder yderligere oplysninger om forbedringen.</span><span class="sxs-lookup"><span data-stu-id="3e666-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="3e666-120">Vælg en forbedring for at få vist de tilgængelige indstillinger.</span><span class="sxs-lookup"><span data-stu-id="3e666-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="3e666-121">Du kan også vælge ellipsen (...) på et listeelement for at se indstillingerne.</span><span class="sxs-lookup"><span data-stu-id="3e666-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Indstillinger til administration af forbedringer på listen over forbedringer":::

- <span data-ttu-id="3e666-123">**Vis** oplysninger om forbedringer med antallet af forbedrede kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="3e666-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="3e666-124">**Rediger** konfigurationen af forbedringen.</span><span class="sxs-lookup"><span data-stu-id="3e666-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="3e666-125">**Kør** forbedringen for at opdatere kundeprofiler med de nyeste data.</span><span class="sxs-lookup"><span data-stu-id="3e666-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="3e666-126">**Deaktiver** en eksisterende forbedring for at forhindre, at den opdateres automatisk i alle planlagte opdateringer.</span><span class="sxs-lookup"><span data-stu-id="3e666-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="3e666-127">Data fra den seneste vellykkede opdatering vil fortsat være tilgængelige.</span><span class="sxs-lookup"><span data-stu-id="3e666-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="3e666-128">**Aktivér** en inaktiv forbedring, hvis du vil genstarte automatisk opdatering for hver planlagt opdatering.</span><span class="sxs-lookup"><span data-stu-id="3e666-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="3e666-129">Vil du **slette** en forbedring?</span><span class="sxs-lookup"><span data-stu-id="3e666-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="3e666-130">Du kan køre eller deaktivere flere forbedringer på én gang ved at vælge dem på listen.</span><span class="sxs-lookup"><span data-stu-id="3e666-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="3e666-131">Indstillingerne Vis og Rediger er ikke tilgængelige som massehandlinger og kan kun bruges med én forbedring ad gangen.</span><span class="sxs-lookup"><span data-stu-id="3e666-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="3e666-132">Forbedringer og forbindelser</span><span class="sxs-lookup"><span data-stu-id="3e666-132">Enrichments and connections</span></span>

<span data-ttu-id="3e666-133">Konfigurationer fra tredjeparter konfigureres ved hjælp af [forbindelser](connections.md), som en administrator konfigurerer med legitimationsoplysninger og giver samtykke til dataoverførsler.</span><span class="sxs-lookup"><span data-stu-id="3e666-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="3e666-134">Forbindelsen kan derefter bruges af både administratorer og bidragydere til at konfigurere forbedringer.</span><span class="sxs-lookup"><span data-stu-id="3e666-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="3e666-135">Flere forbedringer af samme type</span><span class="sxs-lookup"><span data-stu-id="3e666-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="3e666-136">Det objekt, der skal forbedres, angives under forbedringskonfigurationen med mulighed for forbedring, som gør det muligt kun at forbedre et undersæt af dine profiler.</span><span class="sxs-lookup"><span data-stu-id="3e666-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="3e666-137">Du kan for eksempel forbedre data for et bestemt segment.</span><span class="sxs-lookup"><span data-stu-id="3e666-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="3e666-138">Du kan konfigurere flere forbedringer af samme type og genbruge den samme forbindelse.</span><span class="sxs-lookup"><span data-stu-id="3e666-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="3e666-139">Nogle forbedringer har grænser for antallet af forbedringer af samme type, der kan oprettes.</span><span class="sxs-lookup"><span data-stu-id="3e666-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="3e666-140">Grænseværdierne og den aktuelle brug kan ses på siden **Forbedring**.</span><span class="sxs-lookup"><span data-stu-id="3e666-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
