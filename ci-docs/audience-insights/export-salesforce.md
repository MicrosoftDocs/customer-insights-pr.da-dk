---
title: Eksporter Customer Insights-data til Salesforce Marketing Cloud
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314594"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="e84c0-103">Eksporter segmenter og andre data til Salesforce Marketing Cloud (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="e84c0-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="e84c0-104">Brug dine kundedata i Salesforce Marketing Cloud ved at eksportere dem via en SFTP-lokation (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="e84c0-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e84c0-105">Forudsætninger for forbindelse</span><span class="sxs-lookup"><span data-stu-id="e84c0-105">Prerequisites for connection</span></span>

- <span data-ttu-id="e84c0-106">Tilgængeligheden af en SFTP-vært og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="e84c0-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="e84c0-107">Sådan konfigureres SFTP-lokationer til Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="e84c0-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="e84c0-108">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="e84c0-108">Known limitations</span></span>

- <span data-ttu-id="e84c0-109">Kørslen af en eksport afhænger af systemets ydeevne.</span><span class="sxs-lookup"><span data-stu-id="e84c0-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="e84c0-110">Vi anbefaler to CPU-kerner og 1 GB hukommelse som minimal konfiguration af serveren.</span><span class="sxs-lookup"><span data-stu-id="e84c0-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="e84c0-111">Det kan tage 90 minutter at eksportere enheder med op til 100 millioner kundeprofiler, når du bruger den anbefalede minimale konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e84c0-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="e84c0-112">Konfigurere forbindelsen til Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="e84c0-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="e84c0-113">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="e84c0-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e84c0-114">Vælg **Tilføj forbindelse**, og vælg **Salesforce Marketing Cloud** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="e84c0-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="e84c0-115">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="e84c0-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e84c0-116">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="e84c0-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e84c0-117">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="e84c0-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e84c0-118">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="e84c0-118">Choose who can use this connection.</span></span> <span data-ttu-id="e84c0-119">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="e84c0-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e84c0-120">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e84c0-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e84c0-121">Angiv et **Brugernavn**, **Adgangskode**, **Værtsnavn** og **Eksportmappe** til din SFTP-konto.</span><span class="sxs-lookup"><span data-stu-id="e84c0-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="e84c0-122">Vælg **Bekræft** for at teste forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="e84c0-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="e84c0-123">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="e84c0-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e84c0-124">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="e84c0-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e84c0-125">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="e84c0-125">Configure an export</span></span>

<span data-ttu-id="e84c0-126">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="e84c0-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e84c0-127">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e84c0-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e84c0-128">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="e84c0-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e84c0-129">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="e84c0-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e84c0-130">Vælg en forbindelse i sektionen SFTP i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="e84c0-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="e84c0-131">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="e84c0-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e84c0-132">Vælg, om du vil eksportere dataene **Gzippet** eller **Pakket ud** og **feltseparator** for de eksporterede filer.</span><span class="sxs-lookup"><span data-stu-id="e84c0-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="e84c0-133">Markér de objekter, f.eks. segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="e84c0-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e84c0-134">Hvert enkelt valgt objekt opdeles i op til fem outputfiler, når de eksporteres.</span><span class="sxs-lookup"><span data-stu-id="e84c0-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="e84c0-135">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="e84c0-135">Select **Save**.</span></span>

<span data-ttu-id="e84c0-136">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="e84c0-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e84c0-137">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e84c0-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e84c0-138">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e84c0-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="e84c0-139">Importér Customer Insights-data fra SFTP-lokation til Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="e84c0-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="e84c0-140">Opret [dataudvidelser i Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) for at importere datafilen Customer Insights fra SFTP-lokationen.</span><span class="sxs-lookup"><span data-stu-id="e84c0-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="e84c0-141">[Importér dataene fra SFTP-lokationen](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) til Salesforce Marketing Cloud-dataudvidelsen.</span><span class="sxs-lookup"><span data-stu-id="e84c0-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="e84c0-142">Konfigurer automatiseringen til at importere dataene til dataudvidelserne.</span><span class="sxs-lookup"><span data-stu-id="e84c0-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="e84c0-143">Få mere at vide om [automatiseringer af file drop og planlagte automatiseringer](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="e84c0-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="e84c0-144">Definer en [automatisering af file drop](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) eller en [planlagt automatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="e84c0-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="e84c0-145">Her er et eksempel på [en automatisering med SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="e84c0-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e84c0-146">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="e84c0-146">Data privacy and compliance</span></span>

<span data-ttu-id="e84c0-147">Når du aktiverer Dynamics 365 Customer Insights for at overføre data via SFTP, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="e84c0-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e84c0-148">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at eksportdestinationen overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="e84c0-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e84c0-149">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e84c0-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e84c0-150">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="e84c0-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
