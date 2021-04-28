---
title: Eksport af Customer Insights-data til RollWorks
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760503"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="3a254-103">Eksport af segmentlister til RollWorks (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="3a254-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="3a254-104">Eksportér segmenter med ensartede kundeprofiler til RollWorks, og brug dem til marketing.</span><span class="sxs-lookup"><span data-stu-id="3a254-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="3a254-105">Forudsætninger for en forbindelse</span><span class="sxs-lookup"><span data-stu-id="3a254-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="3a254-106">Du har en [RollWorks-konto](https://www.rollworks.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="3a254-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3a254-107">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="3a254-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3a254-108">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="3a254-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3a254-109">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="3a254-109">Known limitations</span></span>

- <span data-ttu-id="3a254-110">Du kan eksportere op til 250.000 profiler pr. eksport til RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3a254-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="3a254-111">Du kan ikke eksportere segmenter med færre end 100 profiler til RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3a254-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="3a254-112">Eksport til RollWorks er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="3a254-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="3a254-113">Det kan tage op til 10 minutter at eksportere op til 250.000 profiler til RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3a254-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="3a254-114">Det antal profiler, du kan eksportere til RollWorks, er afhængigt af og begrænset af kontrakten med RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3a254-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="3a254-115">Konfigurer forbindelsen til RollWorks</span><span class="sxs-lookup"><span data-stu-id="3a254-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="3a254-116">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="3a254-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3a254-117">Vælg **Tilføj forbindelse**, og vælg **RollWorks** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="3a254-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="3a254-118">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="3a254-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3a254-119">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="3a254-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3a254-120">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="3a254-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3a254-121">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="3a254-121">Choose who can use this connection.</span></span> <span data-ttu-id="3a254-122">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="3a254-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3a254-123">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3a254-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3a254-124">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="3a254-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3a254-125">Vælg **Opret forbindelse** for at initialisere forbindelsen til RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3a254-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="3a254-126">Vælg **Autentificer med RollWorks**, og angiv administratoroplysningerne for RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3a254-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="3a254-127">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="3a254-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3a254-128">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="3a254-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3a254-129">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="3a254-129">Configure an export</span></span>

<span data-ttu-id="3a254-130">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="3a254-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3a254-131">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3a254-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3a254-132">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="3a254-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3a254-133">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="3a254-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3a254-134">Vælg en forbindelse i sektionen RollWorks i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="3a254-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="3a254-135">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="3a254-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3a254-136">Angiv dit **RollWorks Advertiser-id** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="3a254-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="3a254-137">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="3a254-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3a254-138">Det er obligatorisk at eksportere segmenter til RollWorks.</span><span class="sxs-lookup"><span data-stu-id="3a254-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="3a254-139">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="3a254-139">Select the segments you want to export.</span></span> <span data-ttu-id="3a254-140">Vælg et segment med mindst 100 medlemmer.</span><span class="sxs-lookup"><span data-stu-id="3a254-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="3a254-141">Du kan ikke eksportere mindre segmenter.</span><span class="sxs-lookup"><span data-stu-id="3a254-141">You can't export smaller segments.</span></span> <span data-ttu-id="3a254-142">Derudover er maksimumstørrelsen på et segment, der skal eksporteres, 250.000 medlemmer pr. eksport.</span><span class="sxs-lookup"><span data-stu-id="3a254-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="3a254-143">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="3a254-143">Select **Save**.</span></span>

<span data-ttu-id="3a254-144">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="3a254-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3a254-145">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3a254-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3a254-146">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3a254-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3a254-147">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="3a254-147">Data privacy and compliance</span></span>

<span data-ttu-id="3a254-148">Når du gør det muligt for Dynamics 365 Customer Insights at overføre data til RollWorks, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder følsomme data som f.eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="3a254-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3a254-149">Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at RollWorks overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have.</span><span class="sxs-lookup"><span data-stu-id="3a254-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3a254-150">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3a254-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="3a254-151">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="3a254-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
