---
title: Eksportér Customer Insights-data til Dynamics 365 Sales
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976219"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="34583-103">Brug segmenter i Dynamics 365 Sales (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="34583-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="34583-104">Brug dine kundedata til at oprette marketinglister, følge op på arbejdsprocesser og udsende kampagner med Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="34583-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="34583-105">Forudsætning for forbindelse</span><span class="sxs-lookup"><span data-stu-id="34583-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="34583-106">Kontaktposter skal være til stede i Dynamics 365 Sales, før du kan eksportere et segment fra Customer Insights til Sales.</span><span class="sxs-lookup"><span data-stu-id="34583-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="34583-107">Læs mere om, hvordan du kontakter i [Dynamics 365 Sales ved hjælp af Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="34583-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="34583-108">Hvis du eksporterer segmenter fra målgruppeindsigt til Sales, oprettes der ikke nye kontaktposter i Sales-forekomsterne.</span><span class="sxs-lookup"><span data-stu-id="34583-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="34583-109">Kontaktpersonposterne fra Sales skal være direkte målgruppeindsigt og bruges som en datakilde.</span><span class="sxs-lookup"><span data-stu-id="34583-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="34583-110">De skal også inkluderes i den samlede brugerdefinerede enhed for at knytte kunde-ID'er til kontakt-ID'er, før segmenter kan eksporteres.</span><span class="sxs-lookup"><span data-stu-id="34583-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="34583-111">Konfigurer forbindelsen til Sales</span><span class="sxs-lookup"><span data-stu-id="34583-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="34583-112">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="34583-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="34583-113">Vælg **Tilføj forbindelse**, og vælg **Dynamics 365 Sales** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="34583-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="34583-114">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="34583-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="34583-115">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="34583-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="34583-116">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="34583-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="34583-117">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="34583-117">Choose who can use this connection.</span></span> <span data-ttu-id="34583-118">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="34583-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="34583-119">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="34583-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="34583-120">Angiv din organisations URL-adresse for Sales i feltet **Serveradresse**.</span><span class="sxs-lookup"><span data-stu-id="34583-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="34583-121">I sektionen **Serveradministratorkonto** vælg **Log på** og vælg en Dynamics 365 Sales-konto.</span><span class="sxs-lookup"><span data-stu-id="34583-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="34583-122">Knyt et kunde-ID-felt til Dynamics 365-kontakt-id.</span><span class="sxs-lookup"><span data-stu-id="34583-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="34583-123">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="34583-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="34583-124">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="34583-124">Configure an export</span></span>

<span data-ttu-id="34583-125">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="34583-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="34583-126">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="34583-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="34583-127">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="34583-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="34583-128">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="34583-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="34583-129">Vælg en forbindelse i sektionen Dynamics 365 Sales i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="34583-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="34583-130">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="34583-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="34583-131">Vælg en eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="34583-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="34583-132">Vælg **Gem**</span><span class="sxs-lookup"><span data-stu-id="34583-132">Select **Save**</span></span>

<span data-ttu-id="34583-133">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="34583-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="34583-134">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="34583-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="34583-135">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="34583-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
