---
title: Eksportere Customer Insights-data til Autopilot
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760136"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="cbf83-103">Eksportér segmenter til Autopilot (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="cbf83-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="cbf83-104">Eksportér segmenter med ensartede kundeprofiler til Autopilot, og brug dem til mailmarketing i Autopilot.</span><span class="sxs-lookup"><span data-stu-id="cbf83-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="cbf83-105">Forudsætninger for en forbindelse</span><span class="sxs-lookup"><span data-stu-id="cbf83-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="cbf83-106">Du har en [Autopilot-konto](https://www.autopilothq.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="cbf83-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="cbf83-107">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="cbf83-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="cbf83-108">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="cbf83-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cbf83-109">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="cbf83-109">Known limitations</span></span>

- <span data-ttu-id="cbf83-110">Du kan eksportere op til 100.000 kundeprofiler i alt til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="cbf83-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="cbf83-111">Eksport til Autopilot er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="cbf83-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="cbf83-112">Det kan tage op til et par timer at eksportere op til 100.000 profiler til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="cbf83-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="cbf83-113">Antallet af profiler, du kan eksportere til Autopilot, er afhængige og begrænsede i kontrakten med Autopilot.</span><span class="sxs-lookup"><span data-stu-id="cbf83-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="cbf83-114">Konfigurer forbindelsen til Autopilot</span><span class="sxs-lookup"><span data-stu-id="cbf83-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="cbf83-115">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="cbf83-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="cbf83-116">Vælg **Tilføj forbindelse**, og vælg **Autopilot** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="cbf83-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="cbf83-117">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="cbf83-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="cbf83-118">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="cbf83-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="cbf83-119">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="cbf83-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="cbf83-120">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="cbf83-120">Choose who can use this connection.</span></span> <span data-ttu-id="cbf83-121">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="cbf83-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="cbf83-122">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="cbf83-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="cbf83-123">Angiv [Autopilot-API-nøglen](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="cbf83-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="cbf83-124">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="cbf83-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cbf83-125">Vælg **Opret forbindelse** for at initialisere forbindelsen til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="cbf83-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="cbf83-126">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="cbf83-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="cbf83-127">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="cbf83-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="cbf83-128">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="cbf83-128">Configure an export</span></span>

<span data-ttu-id="cbf83-129">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="cbf83-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="cbf83-130">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="cbf83-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="cbf83-131">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="cbf83-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cbf83-132">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="cbf83-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="cbf83-133">Vælg en forbindelse i sektionen Autopilot i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="cbf83-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="cbf83-134">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="cbf83-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="cbf83-135">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="cbf83-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="cbf83-136">Gentag de samme trin for andre felter som **Fornavn**, **Efternavn**.</span><span class="sxs-lookup"><span data-stu-id="cbf83-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="cbf83-137">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="cbf83-137">Select the segments you want to export.</span></span> <span data-ttu-id="cbf83-138">Det **anbefales ikke at eksportere mere end 100'000 kundeprofiler i alt** til Autopilot.</span><span class="sxs-lookup"><span data-stu-id="cbf83-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="cbf83-139">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="cbf83-139">Select **Save**.</span></span>

<span data-ttu-id="cbf83-140">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="cbf83-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="cbf83-141">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cbf83-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="cbf83-142">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="cbf83-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cbf83-143">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="cbf83-143">Data privacy and compliance</span></span>

<span data-ttu-id="cbf83-144">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Autopilot, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks.. personlige data.</span><span class="sxs-lookup"><span data-stu-id="cbf83-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cbf83-145">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Autopilot overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="cbf83-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="cbf83-146">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cbf83-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="cbf83-147">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="cbf83-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
