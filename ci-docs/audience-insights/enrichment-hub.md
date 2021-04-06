---
title: Forbedring af samlede kundeprofiler
description: Du kan bruge egenskaber til at forbedre dine kundedata.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597688"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="2dfe8-103">Forbedring af kundeprofiler (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="2dfe8-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="2dfe8-104">Brug data fra kilder som f.eks. Microsoft og andre partnere til at forbedre kundedataene.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Hubside for forbedring":::

<span data-ttu-id="2dfe8-106">Hvis du målgruppeindsigt, kan du gå til **Data** > **Forbedring** for at arbejde sammen med forbedringsmuligheder.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="2dfe8-107">Du skal have bidragyder- eller administratortilladelser for at kunne oprette eller redigere forbedringer.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="2dfe8-108">Du kan finde flere oplysninger under [Tilladelser](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2dfe8-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="2dfe8-109">Under fanen **Opdag** kan du se følgende forbedringer:</span><span class="sxs-lookup"><span data-stu-id="2dfe8-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="2dfe8-110">[Varemærker](enrichment-microsoft-graph.md) leveret af Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="2dfe8-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="2dfe8-111">[Interesser](enrichment-microsoft-graph.md) leveret af Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="2dfe8-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="2dfe8-112">[Firmadata](enrichment-leadspace.md) leveret af Leadspace</span><span class="sxs-lookup"><span data-stu-id="2dfe8-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="2dfe8-113">[Demografi](enrichment-experian.md) leveret af Experian</span><span class="sxs-lookup"><span data-stu-id="2dfe8-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="2dfe8-114">[Lokationsdata](enrichment-here.md) leveret af HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="2dfe8-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="2dfe8-115">[Brugerdefineret data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="2dfe8-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="2dfe8-116">Under fanen **Mine forbedringer** kan du se de forbedringer, du har konfigureret, og redigere deres egenskaber.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="2dfe8-117">Administrer eksisterende forbedringer</span><span class="sxs-lookup"><span data-stu-id="2dfe8-117">Manage existing enrichments</span></span>

<span data-ttu-id="2dfe8-118">Gå til **Mine forbedringer** for at få vist alle konfigurerede forbedringer.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="2dfe8-119">Hver forbedring repræsenteres som en række, der indeholder yderligere oplysninger om forbedringen.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="2dfe8-120">Vælg en forbedring for at få vist de tilgængelige indstillinger.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="2dfe8-121">Du kan også vælge ellipsen (...) på et listeelement for at få vist indstillingerne.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Indstillinger til administration af forbedringer på listen over forbedringer":::

- <span data-ttu-id="2dfe8-123">**Vis** oplysninger om forbedringer med antallet af forbedrede kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="2dfe8-124">**Rediger** konfigurationen af forbedringen.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="2dfe8-125">**Kør** forbedringen for at opdatere kundeprofiler med de nyeste data.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="2dfe8-126">**Deaktiver** en eksisterende forbedring for at forhindre, at den opdateres automatisk i alle planlagte opdateringer.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="2dfe8-127">Data fra den seneste vellykkede opdatering vil fortsat være tilgængelige.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="2dfe8-128">**Aktivér** en inaktiv forbedring, hvis du vil genstarte automatisk opdatering for hver planlagt opdatering.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="2dfe8-129">Vil du **slette** en forbedring?</span><span class="sxs-lookup"><span data-stu-id="2dfe8-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="2dfe8-130">Du kan køre eller deaktivere flere forbedringer på én gang ved at vælge dem på listen.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="2dfe8-131">Indstillingerne Vis og Rediger er ikke tilgængelige som massehandlinger og kan kun bruges med én forbedring ad gangen.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]