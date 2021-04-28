---
title: Eksport af Customer Insights til Kampagneovervågning
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til kampagneovervågning.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760502"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="49523-103">Eksport af segmentlister til kampagneovervågning (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="49523-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="49523-104">Eksportér segmenter med ensartede kundeprofiler til Kampagneovervågning, og brug dem til marketingaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="49523-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="49523-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="49523-105">Prerequisites</span></span>

-   <span data-ttu-id="49523-106">Du har en [kampagneovervågningskonto](https://www.campaignmonitor.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="49523-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="49523-107">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="49523-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="49523-108">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="49523-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="49523-109">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="49523-109">Known limitations</span></span>

- <span data-ttu-id="49523-110">Du kan eksportere op til 1 millioner profiler pr. eksport til Kampagneovervågning.</span><span class="sxs-lookup"><span data-stu-id="49523-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="49523-111">Eksport til Kampagneovervågning er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="49523-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="49523-112">Det kan tage op til 20 minutter at eksportere op til 1 millioner profiler til Kampagneovervågning.</span><span class="sxs-lookup"><span data-stu-id="49523-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="49523-113">Det antal profiler, du kan eksportere til Kampagneovervågning, er afhængigt af og begrænset af kontrakten med Kampagneovervågning.</span><span class="sxs-lookup"><span data-stu-id="49523-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="49523-114">Konfigurer forbindelse til Kampagneovervågning </span><span class="sxs-lookup"><span data-stu-id="49523-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="49523-115">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="49523-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="49523-116">Vælg **Tilføj forbindelse**, og vælg **Kampagneovervågning** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="49523-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="49523-117">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="49523-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="49523-118">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="49523-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="49523-119">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="49523-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="49523-120">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="49523-120">Choose who can use this connection.</span></span> <span data-ttu-id="49523-121">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="49523-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="49523-122">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="49523-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="49523-123">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="49523-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="49523-124">Vælg **Opret** forbindelse for at initialisere forbindelsen til Kampagneovervågning.</span><span class="sxs-lookup"><span data-stu-id="49523-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="49523-125">Vælg **Autentificer** med kampagneovervågning, og angiv administratoroplysningerne for Kampagneovervågning.</span><span class="sxs-lookup"><span data-stu-id="49523-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="49523-126">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="49523-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="49523-127">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="49523-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="49523-128">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="49523-128">Configure an export</span></span>

<span data-ttu-id="49523-129">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="49523-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="49523-130">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="49523-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="49523-131">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="49523-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="49523-132">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="49523-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="49523-133">Vælg en forbindelse i sektionen Kampagneovervågning i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="49523-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="49523-134">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="49523-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="49523-135">Angiv din [**Kampagneovervågningsliste-id**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="49523-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="49523-136">[Opret første API-nøglen](https://www.campaignmonitor.com/api/getting-started/) fra **Kontoindstillinger** i Kampagneovervågning for at få vist API-liste-id.</span><span class="sxs-lookup"><span data-stu-id="49523-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="49523-137">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="49523-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="49523-138">Det er obligatorisk at eksportere segmenter til Kampagneovervågning.</span><span class="sxs-lookup"><span data-stu-id="49523-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="49523-139">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="49523-139">Select **Save**.</span></span>

<span data-ttu-id="49523-140">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="49523-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="49523-141">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="49523-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="49523-142">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="49523-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="49523-143">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="49523-143">Data privacy and compliance</span></span>

<span data-ttu-id="49523-144">Når du gør det muligt for Dynamics 365 Customer Insights at overføre data til Kampagneovervågning, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder følsomme data som f.eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="49523-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="49523-145">Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at Kampagneovervågning overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have.</span><span class="sxs-lookup"><span data-stu-id="49523-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="49523-146">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="49523-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="49523-147">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="49523-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
