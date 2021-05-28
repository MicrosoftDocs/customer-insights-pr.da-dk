---
title: Eksportér Customer Insights-data til Mailchimp
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976148"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="e375f-103">Eksport af segmentlister til Mailchimp (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="e375f-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="e375f-104">Eksportér segmenter af samlede kundeprofiler til MailChimp for at oprette nyhedsbreve og e-mailkampagner.</span><span class="sxs-lookup"><span data-stu-id="e375f-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e375f-105">Forudsætninger for forbindelse</span><span class="sxs-lookup"><span data-stu-id="e375f-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="e375f-106">Du har en [Mailchimp-konto](https://mailchimp.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="e375f-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e375f-107">Der findes eksisterende målgrupper i Mailchimp og de tilsvarende id'er.</span><span class="sxs-lookup"><span data-stu-id="e375f-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="e375f-108">Du kan finde flere oplysninger i [Mailchimp-målgrupper](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="e375f-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="e375f-109">Du har [konfigureret segmenter](segments.md)</span><span class="sxs-lookup"><span data-stu-id="e375f-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="e375f-110">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="e375f-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e375f-111">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="e375f-111">Known limitations</span></span>

- <span data-ttu-id="e375f-112">Op til 1000000 profiler pr. eksport til Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e375f-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="e375f-113">Eksport til Mailchimp er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="e375f-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="e375f-114">Eksport af segmenter med 1 millioner profiler kan tage op til tre timer.</span><span class="sxs-lookup"><span data-stu-id="e375f-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="e375f-115">Antallet af profiler, du kan eksportere til Mailchimp, er afhængige og begrænsede i kontrakten med Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e375f-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="e375f-116">Konfigurer forbindelsen til Mailchimp</span><span class="sxs-lookup"><span data-stu-id="e375f-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="e375f-117">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="e375f-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e375f-118">Vælg **Tilføj forbindelse**, og vælg **Autopilot** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="e375f-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="e375f-119">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="e375f-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e375f-120">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="e375f-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e375f-121">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="e375f-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e375f-122">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="e375f-122">Choose who can use this connection.</span></span> <span data-ttu-id="e375f-123">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="e375f-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e375f-124">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e375f-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e375f-125">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="e375f-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e375f-126">Vælg **Opret forbindelse** for at initialisere forbindelsen til Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e375f-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="e375f-127">Vælg **Godkendelse med Mailchimp**, og angiv dine Mailchimp-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="e375f-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="e375f-128">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="e375f-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e375f-129">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="e375f-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="e375f-130">Konfigurer connectoren</span><span class="sxs-lookup"><span data-stu-id="e375f-130">Configure the connector</span></span>

<span data-ttu-id="e375f-131">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="e375f-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e375f-132">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e375f-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e375f-133">Gå til **Data**> **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="e375f-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="e375f-134">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="e375f-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e375f-135">Vælg en forbindelse i sektionen Mailchimp i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="e375f-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="e375f-136">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="e375f-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e375f-137">Angiv din **[Mailchimp Målgruppe-id](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="e375f-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="e375f-138">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="e375f-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e375f-139">Du kan også eksportere **Fornavn** og **Efternavn** for at oprette mere personlige e-mails.</span><span class="sxs-lookup"><span data-stu-id="e375f-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="e375f-140">Vælg **Tilføj attribut** for at tilknytte disse felter.</span><span class="sxs-lookup"><span data-stu-id="e375f-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e375f-141">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="e375f-141">Select the segments you want to export.</span></span> <span data-ttu-id="e375f-142">Du kan eksportere op til 1000000 kundeprofiler i alt til Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e375f-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="e375f-143">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="e375f-143">Select **Save**.</span></span>

<span data-ttu-id="e375f-144">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="e375f-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e375f-145">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e375f-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e375f-146">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e375f-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e375f-147">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="e375f-147">Data privacy and compliance</span></span>

<span data-ttu-id="e375f-148">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Mailchimp, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="e375f-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e375f-149">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Mailchimp overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="e375f-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e375f-150">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e375f-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e375f-151">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="e375f-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
