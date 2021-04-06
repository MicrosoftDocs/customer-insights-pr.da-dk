---
title: Eksportere Customer Insights-data til AdRoll
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697067"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="425e5-103">Connector til AdRoll (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="425e5-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="425e5-104">Eksportér segmenter med ensartede kundeprofiler til AdRoll, og brug dem til reklamer.</span><span class="sxs-lookup"><span data-stu-id="425e5-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="425e5-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="425e5-105">Prerequisites</span></span>

-   <span data-ttu-id="425e5-106">Du har en [AdRoll-konto](https://www.adroll.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="425e5-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="425e5-107">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="425e5-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="425e5-108">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="425e5-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="425e5-109">Opret forbindelse til AdRoll</span><span class="sxs-lookup"><span data-stu-id="425e5-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="425e5-110">Gå til **Adminstration** > **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="425e5-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="425e5-111">Under **AdRoll** skal du vælge **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="425e5-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="425e5-112">Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="425e5-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Konfigurationsrude til AdRoll-forbindelse.":::

1. <span data-ttu-id="425e5-114">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="425e5-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="425e5-115">Vælg **Opret forbindelse** for at initialisere forbindelsen til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="425e5-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="425e5-116">Vælg **Godkendelse med AdRoll**, og angiv dine administratorlegitimationsoplysninger for AdRoll.</span><span class="sxs-lookup"><span data-stu-id="425e5-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="425e5-117">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="425e5-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="425e5-118">Angiv dit **AdRoll-annoncør-id** [AdRoll-annoncering](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="425e5-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="425e5-119">Vælg **Næste** for at konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="425e5-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="425e5-120">Konfigurer connectoren</span><span class="sxs-lookup"><span data-stu-id="425e5-120">Configure the connector</span></span>

1. <span data-ttu-id="425e5-121">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="425e5-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="425e5-122">Den kræves for at eksportere segmenter til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="425e5-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="425e5-123">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="425e5-123">Select the segments you want to export.</span></span> <span data-ttu-id="425e5-124">Vælg et segment med mindst 100 medlemmer.</span><span class="sxs-lookup"><span data-stu-id="425e5-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="425e5-125">Du kan ikke eksportere mindre segmenter.</span><span class="sxs-lookup"><span data-stu-id="425e5-125">You can't export smaller segments.</span></span> <span data-ttu-id="425e5-126">Derudover er maksimumstørrelsen på et segment, der skal eksporteres, 250.000 medlemmer pr. eksport.</span><span class="sxs-lookup"><span data-stu-id="425e5-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="425e5-127">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="425e5-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="425e5-128">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="425e5-128">Export the data</span></span>

<span data-ttu-id="425e5-129">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="425e5-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="425e5-130">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="425e5-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="425e5-131">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="425e5-131">Known limitations</span></span>

- <span data-ttu-id="425e5-132">Du kan eksportere op til 250.000 profiler pr. eksport til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="425e5-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="425e5-133">Du kan ikke eksportere segmenter med færre end 100 profiler til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="425e5-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="425e5-134">Eksport til AdRoll er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="425e5-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="425e5-135">Det kan tage op til 10 minutter at eksportere op til 250.000 profiler til AdRoll.</span><span class="sxs-lookup"><span data-stu-id="425e5-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="425e5-136">Antallet af profiler, du kan eksportere til AdRoll, er afhængige og begrænsede i kontrakten med AdRoll.</span><span class="sxs-lookup"><span data-stu-id="425e5-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="425e5-137">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="425e5-137">Data privacy and compliance</span></span>

<span data-ttu-id="425e5-138">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til AdRoll, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="425e5-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="425e5-139">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at AdRoll overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="425e5-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="425e5-140">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="425e5-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="425e5-141">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="425e5-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
