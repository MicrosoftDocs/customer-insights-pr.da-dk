---
title: Eksport af Customer Insights-data til Snapchat
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760500"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="adf9c-103">Eksport af segmentlister til Snapchat (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="adf9c-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="adf9c-104">Eksportér segmenter med ensartede kundeprofiler til Snapchat, og brug dem til marketing.</span><span class="sxs-lookup"><span data-stu-id="adf9c-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="adf9c-105">Forudsætninger for en forbindelse</span><span class="sxs-lookup"><span data-stu-id="adf9c-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="adf9c-106">Du har en [Snapchat-forretningskonto](https://business.snapchat.com/), en [Snapchat Ads-konto](https://ads.snapchat.com/) og tilsvarende legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="adf9c-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="adf9c-107">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="adf9c-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="adf9c-108">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="adf9c-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="adf9c-109">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="adf9c-109">Known limitations</span></span>

- <span data-ttu-id="adf9c-110">Eksport til Snapchat er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="adf9c-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="adf9c-111">Det kan tage op til 15 minutter at eksportere op til 1 millioner profiler til Snapchat.</span><span class="sxs-lookup"><span data-stu-id="adf9c-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="adf9c-112">Konfigurer forbindelsen til Snapchat</span><span class="sxs-lookup"><span data-stu-id="adf9c-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="adf9c-113">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="adf9c-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="adf9c-114">Vælg **Tilføj forbindelse**, og vælg **Snapchat** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="adf9c-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="adf9c-115">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="adf9c-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="adf9c-116">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="adf9c-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="adf9c-117">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="adf9c-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="adf9c-118">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="adf9c-118">Choose who can use this connection.</span></span> <span data-ttu-id="adf9c-119">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="adf9c-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="adf9c-120">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="adf9c-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="adf9c-121">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="adf9c-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="adf9c-122">Vælg **Opret forbindelse** for at initialisere forbindelsen til Snapchat.</span><span class="sxs-lookup"><span data-stu-id="adf9c-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="adf9c-123">Vælg **Autentificer med Snapchat**, og angiv administratoroplysningerne for Snapchat.</span><span class="sxs-lookup"><span data-stu-id="adf9c-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="adf9c-124">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="adf9c-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="adf9c-125">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="adf9c-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="adf9c-126">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="adf9c-126">Configure an export</span></span>

<span data-ttu-id="adf9c-127">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="adf9c-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="adf9c-128">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="adf9c-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="adf9c-129">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="adf9c-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="adf9c-130">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="adf9c-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="adf9c-131">Vælg en forbindelse i sektionen Snapchat i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="adf9c-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="adf9c-132">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="adf9c-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="adf9c-133">Angiv [**Snapchat Audience-id**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="adf9c-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="adf9c-134">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="adf9c-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="adf9c-135">Det er obligatorisk at eksportere segmenter til Snapchat.</span><span class="sxs-lookup"><span data-stu-id="adf9c-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="adf9c-136">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="adf9c-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="adf9c-137">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="adf9c-137">Select **Save**.</span></span>

<span data-ttu-id="adf9c-138">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="adf9c-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="adf9c-139">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="adf9c-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="adf9c-140">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="adf9c-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="adf9c-141">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="adf9c-141">Data privacy and compliance</span></span>

<span data-ttu-id="adf9c-142">Når du gør det muligt for Dynamics 365 Customer Insights at overføre data til Snapchat, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder følsomme data som f.eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="adf9c-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="adf9c-143">Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at Snapchat overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have.</span><span class="sxs-lookup"><span data-stu-id="adf9c-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="adf9c-144">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="adf9c-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="adf9c-145">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="adf9c-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
