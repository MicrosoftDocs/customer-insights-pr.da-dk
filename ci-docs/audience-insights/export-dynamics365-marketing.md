---
title: Eksportér Customer Insights-data til Dynamics 365 Marketing
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269047"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="00160-103">Opret forbindelse til Dynamics 365 Marketing (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="00160-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="00160-104">Brug [segmenter](segments.md) til at generere kampagner, og kontakt bestemte grupper af kunder sammen med Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="00160-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="00160-105">Du kan finde flere oplysninger under [Bruge segmenter fra Dynamics 365 Customer Insights sammen med Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="00160-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="00160-106">Forudsætning</span><span class="sxs-lookup"><span data-stu-id="00160-106">Prerequisite</span></span>

- <span data-ttu-id="00160-107">Kontaktposter skal være til stede i Dynamics 365 Marketing, før du kan eksportere et segment fra Customer Insights til Marketing.</span><span class="sxs-lookup"><span data-stu-id="00160-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="00160-108">Læs mere om, hvordan du kontakter i [Dynamics 365 Marketing ved hjælp af Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="00160-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="00160-109">Hvis du eksporterer målgruppeindsigt til marketing, oprettes der ikke nye kontaktposter i marketingforekomsterne.</span><span class="sxs-lookup"><span data-stu-id="00160-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="00160-110">Kontaktpersonposterne fra Marketing skal være direkte målgruppeindsigt og bruges som en datakilde.</span><span class="sxs-lookup"><span data-stu-id="00160-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="00160-111">De skal også inkluderes i den samlede brugerdefinerede enhed for at knytte kunde-ID'er til kontakt-ID'er, før segmenter kan eksporteres.</span><span class="sxs-lookup"><span data-stu-id="00160-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="00160-112">Konfigurer forbindelsen til Marketing</span><span class="sxs-lookup"><span data-stu-id="00160-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="00160-113">Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="00160-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="00160-114">Under **Dynamics 365 Marketing** vælg **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="00160-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="00160-115">Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="00160-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="00160-116">Angiv din organisationens URL-adresse for marketing i feltet **Serveradresse**.</span><span class="sxs-lookup"><span data-stu-id="00160-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="00160-117">I sektionen **Serveradministratorkonto** vælg **Log på** og vælg en Dynamics 365 Marketing-konto.</span><span class="sxs-lookup"><span data-stu-id="00160-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="00160-118">Knyt et kunde-ID-felt til Dynamics 365-kontakt-id.</span><span class="sxs-lookup"><span data-stu-id="00160-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="00160-119">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="00160-119">Select **Next**.</span></span>

1. <span data-ttu-id="00160-120">Vælg en eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="00160-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="00160-121">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="00160-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="00160-122">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="00160-122">Export the data</span></span>

<span data-ttu-id="00160-123">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="00160-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="00160-124">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="00160-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]