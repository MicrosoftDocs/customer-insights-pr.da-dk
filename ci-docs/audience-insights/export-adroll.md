---
title: Eksportere Customer Insights-data til AdRoll
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895952"
---
# <a name="export-segment-lists-to-adroll-preview"></a><span data-ttu-id="aa32b-103">Eksport af segmentlister til AdRoll (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="aa32b-103">Export segment lists to AdRoll (preview)</span></span>

<span data-ttu-id="aa32b-104">Eksportér segmenter med ensartede kundeprofiler til AdRoll, og brug dem til reklamer.</span><span class="sxs-lookup"><span data-stu-id="aa32b-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="aa32b-105">Forudsætninger for en forbindelse</span><span class="sxs-lookup"><span data-stu-id="aa32b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="aa32b-106">Du har en [AdRoll-konto](https://www.adroll.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="aa32b-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="aa32b-107">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="aa32b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="aa32b-108">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="aa32b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="aa32b-109">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="aa32b-109">Known limitations</span></span>

- <span data-ttu-id="aa32b-110">Du kan eksportere op til 250.000 profiler pr. eksport til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="aa32b-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="aa32b-111">Du kan ikke eksportere segmenter med færre end 100 profiler til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="aa32b-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="aa32b-112">Eksport til AdRoll er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="aa32b-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="aa32b-113">Det kan tage op til 10 minutter at eksportere op til 250.000 profiler til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="aa32b-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="aa32b-114">Antallet af profiler, du kan eksportere til AdRoll, er afhængige og begrænsede i kontrakten med AdRoll.</span><span class="sxs-lookup"><span data-stu-id="aa32b-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="aa32b-115">Konfigurer forbindelsen til AdRoll</span><span class="sxs-lookup"><span data-stu-id="aa32b-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="aa32b-116">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="aa32b-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="aa32b-117">Vælg **Tilføj forbindelse**, og vælg **AdRoll** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="aa32b-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="aa32b-118">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="aa32b-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="aa32b-119">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="aa32b-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="aa32b-120">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="aa32b-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="aa32b-121">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="aa32b-121">Choose who can use this connection.</span></span> <span data-ttu-id="aa32b-122">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="aa32b-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="aa32b-123">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="aa32b-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="aa32b-124">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="aa32b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="aa32b-125">Vælg **Opret forbindelse** for at initialisere forbindelsen til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="aa32b-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="aa32b-126">Vælg **Godkendelse med AdRoll**, og angiv dine administratorlegitimationsoplysninger for AdRoll.</span><span class="sxs-lookup"><span data-stu-id="aa32b-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="aa32b-127">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="aa32b-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="aa32b-128">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="aa32b-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="aa32b-129">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="aa32b-129">Configure an export</span></span>

<span data-ttu-id="aa32b-130">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="aa32b-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="aa32b-131">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="aa32b-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="aa32b-132">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="aa32b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="aa32b-133">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="aa32b-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="aa32b-134">Vælg en forbindelse i sektionen AdRoll i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="aa32b-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="aa32b-135">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="aa32b-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="aa32b-136">Angiv dit **AdRoll Advertiser-id** for at få flere oplysninger under [AdRoll Adviser-profiler](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="aa32b-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="aa32b-137">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="aa32b-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="aa32b-138">Den kræves for at eksportere segmenter til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="aa32b-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="aa32b-139">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="aa32b-139">Select the segments you want to export.</span></span> <span data-ttu-id="aa32b-140">Vælg et segment med mindst 100 medlemmer.</span><span class="sxs-lookup"><span data-stu-id="aa32b-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="aa32b-141">Du kan ikke eksportere mindre segmenter.</span><span class="sxs-lookup"><span data-stu-id="aa32b-141">You can't export smaller segments.</span></span> <span data-ttu-id="aa32b-142">Derudover er maksimumstørrelsen på et segment, der skal eksporteres, 250.000 medlemmer pr. eksport.</span><span class="sxs-lookup"><span data-stu-id="aa32b-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="aa32b-143">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="aa32b-143">Select **Save**.</span></span>

<span data-ttu-id="aa32b-144">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="aa32b-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="aa32b-145">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="aa32b-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="aa32b-146">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="aa32b-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="aa32b-147">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="aa32b-147">Data privacy and compliance</span></span>

<span data-ttu-id="aa32b-148">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til AdRoll, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="aa32b-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="aa32b-149">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at AdRoll overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="aa32b-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="aa32b-150">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="aa32b-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="aa32b-151">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="aa32b-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
