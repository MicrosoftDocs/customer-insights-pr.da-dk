---
title: Eksportere Customer Insights-data til Omnisend
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124472"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="81cb2-103">Eksportere segmenter til Omnisend (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="81cb2-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="81cb2-104">Eksportere segmenter med ensartede kundeprofiler til Omnisend, og brug dem til marketingaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="81cb2-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="81cb2-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="81cb2-105">Prerequisites</span></span>

-   <span data-ttu-id="81cb2-106">Du har en [Omnisend -konto](https://www.omnisend.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="81cb2-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="81cb2-107">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="81cb2-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="81cb2-108">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="81cb2-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="81cb2-109">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="81cb2-109">Known limitations</span></span>

- <span data-ttu-id="81cb2-110">Du kan eksportere op til 1 million profiler pr. eksport til Omnisend, og det kan tage op til 4 timer at gennemføre.</span><span class="sxs-lookup"><span data-stu-id="81cb2-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="81cb2-111">Eksport til Omnisend er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="81cb2-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="81cb2-112">Antallet af profiler, du kan eksportere til Omnisend, afhænger af din kontrakt med Omnisend.</span><span class="sxs-lookup"><span data-stu-id="81cb2-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="81cb2-113">Konfigurer forbindelsen til Omnisend</span><span class="sxs-lookup"><span data-stu-id="81cb2-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="81cb2-114">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="81cb2-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="81cb2-115">Vælg **Tilføj forbindelse**, og vælg **Omnisend** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="81cb2-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="81cb2-116">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="81cb2-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="81cb2-117">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="81cb2-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="81cb2-118">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="81cb2-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="81cb2-119">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="81cb2-119">Choose who can use this connection.</span></span> <span data-ttu-id="81cb2-120">Som standard er det kun administratorer.</span><span class="sxs-lookup"><span data-stu-id="81cb2-120">By default it's only administrators.</span></span> <span data-ttu-id="81cb2-121">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="81cb2-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="81cb2-122">Angiv [Omnisend-API-nøglen](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="81cb2-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="81cb2-123">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="81cb2-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="81cb2-124">Vælg **Opret forbindelse** for at initialisere forbindelsen til Omnisend.</span><span class="sxs-lookup"><span data-stu-id="81cb2-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="81cb2-125">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="81cb2-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="81cb2-126">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="81cb2-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="81cb2-127">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="81cb2-127">Configure an export</span></span>

<span data-ttu-id="81cb2-128">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="81cb2-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="81cb2-129">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="81cb2-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="81cb2-130">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="81cb2-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="81cb2-131">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="81cb2-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="81cb2-132">Vælg en forbindelse i sektionen Omnisend i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="81cb2-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="81cb2-133">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="81cb2-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="81cb2-134">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="81cb2-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="81cb2-135">Det er obligatorisk at eksportere segmenter til Omnisend.</span><span class="sxs-lookup"><span data-stu-id="81cb2-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="81cb2-136">Du kan også eksportere Fornavn, Efternavn, Adresse, Land/Område, Stat, By og Postnr. for at oprette mere personlige mails.</span><span class="sxs-lookup"><span data-stu-id="81cb2-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="81cb2-137">Vælg **Tilføj attribut** for at tilknytte disse felter.</span><span class="sxs-lookup"><span data-stu-id="81cb2-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="81cb2-138">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="81cb2-138">Select **Save**.</span></span>

<span data-ttu-id="81cb2-139">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="81cb2-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="81cb2-140">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="81cb2-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="81cb2-141">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="81cb2-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="81cb2-142">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="81cb2-142">Data privacy and compliance</span></span>

<span data-ttu-id="81cb2-143">Når du gør det muligt for Dynamics 365 Customer Insights at overføre data til Ommisend, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder følsomme data som f.eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="81cb2-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="81cb2-144">Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at Ommisend overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have.</span><span class="sxs-lookup"><span data-stu-id="81cb2-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="81cb2-145">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="81cb2-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="81cb2-146">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="81cb2-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
