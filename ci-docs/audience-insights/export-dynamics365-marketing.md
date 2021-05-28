---
title: Eksportér Customer Insights-data til Dynamics 365 Marketing
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976793"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="64489-103">Brug segmenter i Dynamics 365 Marketing (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="64489-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="64489-104">Brug [segmenter](segments.md) til at generere kampagner, og kontakt bestemte grupper af kunder sammen med Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="64489-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="64489-105">Du kan finde flere oplysninger under [Bruge segmenter fra Dynamics 365 Customer Insights sammen med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="64489-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="64489-106">Forudsætning for en forbindelse</span><span class="sxs-lookup"><span data-stu-id="64489-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="64489-107">Kontaktposter skal være til stede i Dynamics 365 Marketing, før du kan eksportere et segment fra Customer Insights til Marketing.</span><span class="sxs-lookup"><span data-stu-id="64489-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="64489-108">Læs mere om, hvordan du kontakter i [Dynamics 365 Marketing ved hjælp af Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="64489-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="64489-109">Hvis du eksporterer målgruppeindsigt til marketing, oprettes der ikke nye kontaktposter i marketingforekomsterne.</span><span class="sxs-lookup"><span data-stu-id="64489-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="64489-110">Kontaktpersonposterne fra Marketing skal være direkte målgruppeindsigt og bruges som en datakilde.</span><span class="sxs-lookup"><span data-stu-id="64489-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="64489-111">De skal også inkluderes i den samlede brugerdefinerede enhed for at knytte kunde-ID'er til kontakt-ID'er, før segmenter kan eksporteres.</span><span class="sxs-lookup"><span data-stu-id="64489-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="64489-112">Konfigurer forbindelsen til Marketing.</span><span class="sxs-lookup"><span data-stu-id="64489-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="64489-113">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="64489-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="64489-114">Vælg **Tilføj forbindelse**, og vælg **Dynamics 365 Marketing** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="64489-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="64489-115">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="64489-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="64489-116">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="64489-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="64489-117">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="64489-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="64489-118">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="64489-118">Choose who can use this connection.</span></span> <span data-ttu-id="64489-119">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="64489-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="64489-120">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="64489-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="64489-121">Angiv din organisationens URL-adresse for marketing i feltet **Serveradresse**.</span><span class="sxs-lookup"><span data-stu-id="64489-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="64489-122">I sektionen **Serveradministratorkonto** vælg **Log på** og vælg en Dynamics 365 Marketing-konto.</span><span class="sxs-lookup"><span data-stu-id="64489-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="64489-123">Knyt et kunde-ID-felt til Dynamics 365-kontakt-id.</span><span class="sxs-lookup"><span data-stu-id="64489-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="64489-124">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="64489-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="64489-125">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="64489-125">Configure an export</span></span>

<span data-ttu-id="64489-126">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="64489-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="64489-127">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="64489-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="64489-128">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="64489-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="64489-129">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="64489-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="64489-130">Vælg en forbindelse i sektionen Dynamics 365 Marketing i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="64489-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="64489-131">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="64489-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="64489-132">Vælg en eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="64489-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="64489-133">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="64489-133">Select **Save**.</span></span>

<span data-ttu-id="64489-134">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="64489-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="64489-135">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="64489-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="64489-136">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="64489-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
