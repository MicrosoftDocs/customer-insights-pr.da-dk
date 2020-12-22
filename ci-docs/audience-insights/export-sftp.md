---
title: Eksportér Customer Insights-data til SFTP-værter
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til en SFTP-vært.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643496"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="8c511-103">Connector til SFTP (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="8c511-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="8c511-104">Brug dine kundedata i tredjepartsprogrammer ved at eksportere dem til en SFTP-vært.</span><span class="sxs-lookup"><span data-stu-id="8c511-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c511-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="8c511-105">Prerequisites</span></span>

- <span data-ttu-id="8c511-106">Tilgængelighed af en SFTP-vært og tilhørende legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="8c511-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="8c511-107">Forbindelse til SFTP</span><span class="sxs-lookup"><span data-stu-id="8c511-107">Connect to SFTP</span></span>

1. <span data-ttu-id="8c511-108">Gå til **Adminstration** > **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="8c511-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8c511-109">Vælg **Konfigurer** under **SFTP**.</span><span class="sxs-lookup"><span data-stu-id="8c511-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="8c511-110">Giv din destination et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="8c511-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8c511-111">Angiv et **Brugernavn**, en **adgangskode** og et **værtsnavn** til din SFTP-konto.</span><span class="sxs-lookup"><span data-stu-id="8c511-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="8c511-112">Eksempel: Hvis SFTP-serverens rodmappe er/root/mappe, og du vil have, at dataene skal eksporteres til/root/mappe/ci_export_destination_folder, skal værten være sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="8c511-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="8c511-113">Vælg **Bekræft** for at teste forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="8c511-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="8c511-114">Når bekræftelsen er fuldført, skal du vælge, om du vil eksportere dataene **Pakket** eller **Ikke-pakket** og vælge **feltseparator** for de eksporterede filer.</span><span class="sxs-lookup"><span data-stu-id="8c511-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="8c511-115">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="8c511-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8c511-116">Vælg **Næste** for at begynde at konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="8c511-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="8c511-117">Konfigurere forbindelsen</span><span class="sxs-lookup"><span data-stu-id="8c511-117">Configure the connection</span></span>

1. <span data-ttu-id="8c511-118">Vælg de **kundeattributter**, der skal eksporteres.</span><span class="sxs-lookup"><span data-stu-id="8c511-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="8c511-119">Du kan eksportere en eller flere attributter.</span><span class="sxs-lookup"><span data-stu-id="8c511-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="8c511-120">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="8c511-120">Select **Next**.</span></span>

1. <span data-ttu-id="8c511-121">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="8c511-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="8c511-122">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="8c511-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8c511-123">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="8c511-123">Export the data</span></span>

<span data-ttu-id="8c511-124">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8c511-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8c511-125">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8c511-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8c511-126">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="8c511-126">Data privacy and compliance</span></span>

<span data-ttu-id="8c511-127">Når du aktiverer Dynamics 365 Customer Insights for at overføre data via SFTP, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="8c511-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8c511-128">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at eksportdestinationen overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="8c511-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8c511-129">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8c511-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8c511-130">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="8c511-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
