---
title: Eksportér Customer Insights-data til SFTP-værter
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til en SFTP-vært.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598378"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="d853a-103">Connector til SFTP (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="d853a-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="d853a-104">Brug dine kundedata i tredjepartsprogrammer ved at eksportere dem til en SFTP-vært.</span><span class="sxs-lookup"><span data-stu-id="d853a-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d853a-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="d853a-105">Prerequisites</span></span>

- <span data-ttu-id="d853a-106">Tilgængeligheden af en SFTP-vært og de tilhørende legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="d853a-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="d853a-107">Opret forbindelse til SFTP</span><span class="sxs-lookup"><span data-stu-id="d853a-107">Connect to SFTP</span></span>

1. <span data-ttu-id="d853a-108">Gå til **Adminstration** > **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="d853a-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d853a-109">Vælg **Konfigurer** under **SFTP**.</span><span class="sxs-lookup"><span data-stu-id="d853a-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="d853a-110">Giv din destination et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="d853a-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d853a-111">Angiv et **Brugernavn**, **Adgangskode**, **Værtsnavn** og **Eksportmappe** til din SFTP-konto.</span><span class="sxs-lookup"><span data-stu-id="d853a-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="d853a-112">Vælg **Bekræft** for at teste forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="d853a-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="d853a-113">Når verifikationen er fuldført, skal du vælge, om du vil eksportere dataene **Gzipped** eller **Udpakket** , og vælge **feltseparator** for de eksporterede filer.</span><span class="sxs-lookup"><span data-stu-id="d853a-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="d853a-114">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="d853a-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d853a-115">Vælg **Næste** for at begynde at konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="d853a-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="d853a-116">konfigurere eksporten</span><span class="sxs-lookup"><span data-stu-id="d853a-116">Configure the export</span></span>

1. <span data-ttu-id="d853a-117">Markér de objekter, f.eks. segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="d853a-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d853a-118">Hvert valgt objekt vil være på op til fem outputfiler, når de eksporteres.</span><span class="sxs-lookup"><span data-stu-id="d853a-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="d853a-119">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="d853a-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d853a-120">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="d853a-120">Export the data</span></span>

<span data-ttu-id="d853a-121">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d853a-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d853a-122">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d853a-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d853a-123">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="d853a-123">Known limitations</span></span>

- <span data-ttu-id="d853a-124">Kørslen af en eksport afhænger af systemets ydeevne.</span><span class="sxs-lookup"><span data-stu-id="d853a-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="d853a-125">Vi anbefaler to CPU-kerner og 1 GB hukommelse som minimal konfiguration af serveren.</span><span class="sxs-lookup"><span data-stu-id="d853a-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="d853a-126">Det kan tage 90 minutter at eksportere objekter med op til 100 millioner kundeprofiler, når du bruger den anbefalede minimale konfiguration af to CPU-kerner og 1 GB hukommelse.</span><span class="sxs-lookup"><span data-stu-id="d853a-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d853a-127">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="d853a-127">Data privacy and compliance</span></span>

<span data-ttu-id="d853a-128">Når du aktiverer Dynamics 365 Customer Insights for at overføre data via SFTP, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="d853a-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d853a-129">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at eksportdestinationen overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="d853a-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d853a-130">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d853a-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d853a-131">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="d853a-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]