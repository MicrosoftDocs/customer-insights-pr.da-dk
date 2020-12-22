---
title: Forbedring af samlede kundeprofiler
description: Du kan bruge egenskaber til at forbedre dine kundedata.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667087"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="8557b-103">Forbedring af kundeprofiler (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="8557b-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="8557b-104">Brug data fra kilder som f.eks. Microsoft og andre partnere til at forbedre kundedataene.</span><span class="sxs-lookup"><span data-stu-id="8557b-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Hubside for forbedring":::

<span data-ttu-id="8557b-106">Hvis du målgruppeindsigt, kan du gå til **Data** > **Forbedring** for at arbejde sammen med forbedringsmuligheder.</span><span class="sxs-lookup"><span data-stu-id="8557b-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="8557b-107">Du skal have bidragyder- eller administratortilladelser for at kunne oprette eller redigere forbedringer.</span><span class="sxs-lookup"><span data-stu-id="8557b-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="8557b-108">Du kan finde flere oplysninger under [Tilladelser](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8557b-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="8557b-109">Under fanen **Opdag** kan du se følgende forbedringer:</span><span class="sxs-lookup"><span data-stu-id="8557b-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="8557b-110">[Varemærker](enrichment-microsoft-graph.md) leveret af Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="8557b-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="8557b-111">[Interesser](enrichment-microsoft-graph.md) leveret af Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="8557b-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="8557b-112">[Firmadata](enrichment-leadspace.md) leveret af Leadspace</span><span class="sxs-lookup"><span data-stu-id="8557b-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="8557b-113">[Demografi](enrichment-experian.md) leveret af Experian</span><span class="sxs-lookup"><span data-stu-id="8557b-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="8557b-114">[Lokationsdata](enrichment-here.md) leveret af HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="8557b-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="8557b-115">[Brugerdefineret data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="8557b-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="8557b-116">Under fanen **Mine forbedringer** kan du se de forbedringer, du har konfigureret, og redigere deres egenskaber.</span><span class="sxs-lookup"><span data-stu-id="8557b-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="8557b-117">Administrer eksisterende forbedringer</span><span class="sxs-lookup"><span data-stu-id="8557b-117">Manage existing enrichments</span></span>

<span data-ttu-id="8557b-118">Gå til **Mine forbedringer** for at få vist alle konfigurerede forbedringer.</span><span class="sxs-lookup"><span data-stu-id="8557b-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="8557b-119">Hver forbedring repræsenteres som en række, der indeholder yderligere oplysninger om forbedringen.</span><span class="sxs-lookup"><span data-stu-id="8557b-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="8557b-120">Vælg en forbedring for at få vist de tilgængelige indstillinger.</span><span class="sxs-lookup"><span data-stu-id="8557b-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="8557b-121">Du kan også vælge ellipsen (...) på et listeelement for at få vist indstillingerne.</span><span class="sxs-lookup"><span data-stu-id="8557b-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Indstillinger til administration af forbedringer på listen over forbedringer":::

- <span data-ttu-id="8557b-123">**Vis** oplysninger om forbedringer med antallet af forbedrede kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="8557b-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="8557b-124">**Rediger** konfigurationen af forbedringen.</span><span class="sxs-lookup"><span data-stu-id="8557b-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="8557b-125">**Kør** forbedringen for at opdatere kundeprofiler med de nyeste data.</span><span class="sxs-lookup"><span data-stu-id="8557b-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="8557b-126">**Deaktiver** en eksisterende forbedring for at forhindre, at den opdateres automatisk i alle planlagte opdateringer.</span><span class="sxs-lookup"><span data-stu-id="8557b-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="8557b-127">Data fra den seneste vellykkede opdatering vil fortsat være tilgængelige.</span><span class="sxs-lookup"><span data-stu-id="8557b-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="8557b-128">**Aktivér** en inaktiv forbedring, hvis du vil genstarte automatisk opdatering for hver planlagt opdatering.</span><span class="sxs-lookup"><span data-stu-id="8557b-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="8557b-129">Vil du **slette** en forbedring?</span><span class="sxs-lookup"><span data-stu-id="8557b-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="8557b-130">Du kan køre eller deaktivere flere forbedringer på én gang ved at vælge dem på listen.</span><span class="sxs-lookup"><span data-stu-id="8557b-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="8557b-131">Indstillingerne Vis og Rediger er ikke tilgængelige som massehandlinger og kan kun bruges med én forbedring ad gangen.</span><span class="sxs-lookup"><span data-stu-id="8557b-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>
