---
title: Eksport af Customer Insights-data til Constant Contact-kontaktperson
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760501"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="4abbd-103">Eksport af segmentlister til Constant Contact (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="4abbd-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="4abbd-104">Eksportér segmenter med ensartede kundeprofiler til Constant Contact, og brug dem til marketingaktiviteter.</span><span class="sxs-lookup"><span data-stu-id="4abbd-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="4abbd-105">Forudsætninger for en forbindelse</span><span class="sxs-lookup"><span data-stu-id="4abbd-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="4abbd-106">Du har en [Constant Contact-konto](https://www.constantcontact.com/account-home) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="4abbd-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4abbd-107">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="4abbd-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="4abbd-108">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="4abbd-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4abbd-109">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="4abbd-109">Known limitations</span></span>

- <span data-ttu-id="4abbd-110">Du kan eksportere op til 1 millioner profiler pr. eksport til Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="4abbd-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="4abbd-111">Eksport til Constant Contact er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="4abbd-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="4abbd-112">Det kan tage op til 1 time at eksportere op til 1 millioner profiler til Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="4abbd-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="4abbd-113">Det antal profiler, du kan eksportere til Constant Contact, er afhængigt af og begrænset af kontrakten med Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="4abbd-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="4abbd-114">Konfigurere til Constant Contact</span><span class="sxs-lookup"><span data-stu-id="4abbd-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="4abbd-115">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="4abbd-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4abbd-116">Vælg **Tilføj forbindelse**, og vælg **Constant Contact** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="4abbd-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="4abbd-117">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="4abbd-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4abbd-118">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="4abbd-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4abbd-119">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="4abbd-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4abbd-120">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="4abbd-120">Choose who can use this connection.</span></span> <span data-ttu-id="4abbd-121">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="4abbd-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4abbd-122">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4abbd-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4abbd-123">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="4abbd-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4abbd-124">Vælg **Opret forbindelse** for at initialisere forbindelsen til Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="4abbd-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="4abbd-125">Vælg **Autentificer med AdRoll**, og angiv administratoroplysningerne for Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="4abbd-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="4abbd-126">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="4abbd-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4abbd-127">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="4abbd-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4abbd-128">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="4abbd-128">Configure an export</span></span>

<span data-ttu-id="4abbd-129">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="4abbd-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4abbd-130">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4abbd-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4abbd-131">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="4abbd-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4abbd-132">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="4abbd-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4abbd-133">Vælg en forbindelse i sektionen Constant Contact i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="4abbd-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="4abbd-134">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="4abbd-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4abbd-135">Angiv din [**Constant Contact-liste-id**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="4abbd-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="4abbd-136">Åbn en liste i Constant Contact for at finde liste-id'et i URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="4abbd-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="4abbd-137">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="4abbd-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="4abbd-138">Det er obligatorisk at eksportere segmenter til Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="4abbd-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="4abbd-139">Du kan også eksportere Fornavn og Efternavn som ekstra felter for at oprette mere personlige e-mails.</span><span class="sxs-lookup"><span data-stu-id="4abbd-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="4abbd-140">Vælg **Tilføj attribut** for at tilknytte disse felter.</span><span class="sxs-lookup"><span data-stu-id="4abbd-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="4abbd-141">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="4abbd-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="4abbd-142">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="4abbd-142">Select **Save**.</span></span>

<span data-ttu-id="4abbd-143">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="4abbd-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4abbd-144">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4abbd-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4abbd-145">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4abbd-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4abbd-146">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="4abbd-146">Data privacy and compliance</span></span>

<span data-ttu-id="4abbd-147">Når du gør det muligt for Dynamics 365 Customer Insights at overføre data til Constant Contact, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder følsomme data som f.eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="4abbd-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4abbd-148">Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at Constant Contact overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have.</span><span class="sxs-lookup"><span data-stu-id="4abbd-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4abbd-149">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4abbd-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="4abbd-150">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="4abbd-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
