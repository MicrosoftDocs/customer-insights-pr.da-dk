---
title: Eksporter Customer Insights-data til ActiveCampaign
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314596"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="8ff2d-103">Eksporter segmenter til ActiveCampaign (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="8ff2d-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="8ff2d-104">Eksporter segmenter af samlede kundeprofiler til ActiveCampaign, og brug dem til marketingaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8ff2d-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="8ff2d-105">Prerequisites</span></span>

-   <span data-ttu-id="8ff2d-106">Du har en [ActiveCampaign-konto](https://www.activecampaign.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8ff2d-107">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8ff2d-108">Samlede debitorprofiler i de eksporterede segmenter indeholder et felt med en mailadresse.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8ff2d-109">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="8ff2d-109">Known limitations</span></span>

- <span data-ttu-id="8ff2d-110">Du kan eksportere op til 1 million profiler pr. eksport til ActiveCampaign, og det kan tage op til 90 minutter at gennemføre.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="8ff2d-111">Eksport til ActiveCampaign er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="8ff2d-112">Antallet af profiler, du kan eksportere til ActiveCampaign, afhænger af kontrakten med ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="8ff2d-113">Konfigurer forbindelsen til ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="8ff2d-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="8ff2d-114">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8ff2d-115">Vælg **Tilføj forbindelse**, og vælg **ActiveCampaign** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="8ff2d-116">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8ff2d-117">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8ff2d-118">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8ff2d-119">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-119">Choose who can use this connection.</span></span> <span data-ttu-id="8ff2d-120">Som standard er det kun administratorer.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-120">By default, it's only administrators.</span></span> <span data-ttu-id="8ff2d-121">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8ff2d-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8ff2d-122">Angiv din [ActiveCampaign API-nøgle og REST slutpunkt Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="8ff2d-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="8ff2d-123">Værtsnavn for REST-slutpunkt er kun værtsnavnet uden https://.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="8ff2d-124">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8ff2d-125">Vælg **Opret forbindelse** for at initialisere forbindelsen til ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="8ff2d-126">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8ff2d-127">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8ff2d-128">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="8ff2d-128">Configure an export</span></span>

<span data-ttu-id="8ff2d-129">Du kan konfigurere en eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="8ff2d-130">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8ff2d-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8ff2d-131">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8ff2d-132">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8ff2d-133">Vælg en forbindelse i sektionen ActiveCampaign i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="8ff2d-134">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8ff2d-135">Angiv din [**Id for ActiveCampaign-liste**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="8ff2d-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="8ff2d-136">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8ff2d-137">Det kræves, at der eksporteres segmenter til ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="8ff2d-138">Du kan også eksportere Fornavn, Efternavn og Telefon for at oprette mere personlige e-mails.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="8ff2d-139">Vælg Tilføj attribut for at tilknytte disse felter.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="8ff2d-140">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-140">Select **Save**.</span></span>

<span data-ttu-id="8ff2d-141">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8ff2d-142">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8ff2d-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8ff2d-143">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8ff2d-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8ff2d-144">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="8ff2d-144">Data privacy and compliance</span></span>

<span data-ttu-id="8ff2d-145">Når du gør det muligt for Dynamics 365 Customer Insights at overfører data til ActiveCampaign, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8ff2d-146">Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at ActiveCampaign overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8ff2d-147">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8ff2d-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="8ff2d-148">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="8ff2d-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
