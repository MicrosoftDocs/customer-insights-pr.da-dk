---
title: Eksportere Customer Insights-data til Autopilot
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269231"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="6c8ae-103">Connector til Autopilot (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="6c8ae-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="6c8ae-104">Eksportér segmenter med ensartede kundeprofiler til Autopilot, og brug dem til mailmarketing i Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6c8ae-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="6c8ae-105">Prerequisites</span></span>

-   <span data-ttu-id="6c8ae-106">Du har en [Autopilot-konto](https://www.autopilothq.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6c8ae-107">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6c8ae-108">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="6c8ae-109">Oprette forbindelse til Autopilot</span><span class="sxs-lookup"><span data-stu-id="6c8ae-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="6c8ae-110">Gå til **Adminstration** > **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6c8ae-111">Under **Autopilot** skal du vælge **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="6c8ae-112">Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Konfigurationsrude til Autopilot-forbindelse.":::

1. <span data-ttu-id="6c8ae-114">Angiv din **Autopilot API-nøgle** [Autopilot API-nøgle](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="6c8ae-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="6c8ae-115">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6c8ae-116">Vælg **Opret forbindelse** for at initialisere forbindelsen til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="6c8ae-117">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6c8ae-118">Vælg **Næste** for at konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="6c8ae-119">Konfigurer connectoren</span><span class="sxs-lookup"><span data-stu-id="6c8ae-119">Configure the connector</span></span>

1. <span data-ttu-id="6c8ae-120">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6c8ae-121">Gentag de samme trin for andre felter som **Fornavn**, **Efternavn**.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="6c8ae-122">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-122">Select the segments you want to export.</span></span> <span data-ttu-id="6c8ae-123">Det **anbefales ikke at eksportere mere end 100'000 kundeprofiler i alt** til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="6c8ae-124">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6c8ae-125">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="6c8ae-125">Export the data</span></span>

<span data-ttu-id="6c8ae-126">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6c8ae-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6c8ae-127">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6c8ae-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6c8ae-128">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="6c8ae-128">Known limitations</span></span>

- <span data-ttu-id="6c8ae-129">Du kan eksportere op til 100.000 kundeprofiler i alt til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="6c8ae-130">Eksport til Autopilot er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="6c8ae-131">Det kan tage op til et par timer at eksportere op til 100.000 profiler til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="6c8ae-132">Antallet af profiler, du kan eksportere til Autopilot, er afhængige og begrænsede i kontrakten med Autopilot.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6c8ae-133">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="6c8ae-133">Data privacy and compliance</span></span>

<span data-ttu-id="6c8ae-134">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Autopilot, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks.. personlige data.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6c8ae-135">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Autopilot overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="6c8ae-136">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6c8ae-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6c8ae-137">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="6c8ae-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]