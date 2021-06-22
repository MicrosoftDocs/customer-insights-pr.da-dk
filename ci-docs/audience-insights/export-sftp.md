---
title: Eksportér Customer Insights-data til SFTP-værter
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til en SFTP-lokation.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124312"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a><span data-ttu-id="b7a38-103">Eksportere segmenter og andre data til SFTP (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="b7a38-103">Export segments and other data to SFTP (preview)</span></span>

<span data-ttu-id="b7a38-104">Brug dine kundedata i tredjepartsprogrammer ved at eksportere dem til en SFTP (Secure File Transfer Protocol)-lokation.</span><span class="sxs-lookup"><span data-stu-id="b7a38-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="b7a38-105">Forudsætninger for forbindelse</span><span class="sxs-lookup"><span data-stu-id="b7a38-105">Prerequisites for connection</span></span>

- <span data-ttu-id="b7a38-106">Tilgængeligheden af en SFTP-vært og de tilhørende legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="b7a38-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b7a38-107">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="b7a38-107">Known limitations</span></span>

- <span data-ttu-id="b7a38-108">Kørslen af en eksport afhænger af systemets ydeevne.</span><span class="sxs-lookup"><span data-stu-id="b7a38-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="b7a38-109">Vi anbefaler to CPU-kerner og 1 GB hukommelse som minimal konfiguration af serveren.</span><span class="sxs-lookup"><span data-stu-id="b7a38-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="b7a38-110">Det kan tage 90 minutter at eksportere objekter med op til 100 millioner kundeprofiler, når du bruger den anbefalede minimale konfiguration af to CPU-kerner og 1 GB hukommelse.</span><span class="sxs-lookup"><span data-stu-id="b7a38-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="b7a38-111">Konfigurer forbindelse til SFTP</span><span class="sxs-lookup"><span data-stu-id="b7a38-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="b7a38-112">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="b7a38-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b7a38-113">Vælg **Tilføj forbindelse**, og vælg **SFTP** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="b7a38-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="b7a38-114">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="b7a38-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b7a38-115">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="b7a38-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b7a38-116">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="b7a38-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b7a38-117">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="b7a38-117">Choose who can use this connection.</span></span> <span data-ttu-id="b7a38-118">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="b7a38-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b7a38-119">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b7a38-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b7a38-120">Angiv et **Brugernavn**, **Adgangskode**, **Værtsnavn** og **Eksportmappe** til din SFTP-konto.</span><span class="sxs-lookup"><span data-stu-id="b7a38-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="b7a38-121">Vælg **Bekræft** for at teste forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="b7a38-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="b7a38-122">Vælg, om du vil eksportere dataene **Gzippet** eller **Pakket ud** og **feltseparator** for de eksporterede filer.</span><span class="sxs-lookup"><span data-stu-id="b7a38-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="b7a38-123">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="b7a38-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b7a38-124">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="b7a38-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b7a38-125">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="b7a38-125">Configure an export</span></span>

<span data-ttu-id="b7a38-126">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="b7a38-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b7a38-127">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b7a38-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b7a38-128">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="b7a38-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b7a38-129">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="b7a38-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b7a38-130">Vælg en forbindelse i sektionen SFTP i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="b7a38-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="b7a38-131">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="b7a38-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b7a38-132">Markér de objekter, f.eks. segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="b7a38-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b7a38-133">Hvert enkelt valgt objekt opdeles i op til fem outputfiler, når de eksporteres.</span><span class="sxs-lookup"><span data-stu-id="b7a38-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="b7a38-134">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="b7a38-134">Select **Save**.</span></span>

<span data-ttu-id="b7a38-135">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="b7a38-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b7a38-136">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b7a38-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b7a38-137">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b7a38-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b7a38-138">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="b7a38-138">Data privacy and compliance</span></span>

<span data-ttu-id="b7a38-139">Når du aktiverer Dynamics 365 Customer Insights for at overføre data via SFTP, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="b7a38-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b7a38-140">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at eksportdestinationen overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="b7a38-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b7a38-141">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b7a38-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b7a38-142">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="b7a38-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
