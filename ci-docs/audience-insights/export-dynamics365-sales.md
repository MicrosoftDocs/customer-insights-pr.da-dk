---
title: Eksportér Customer Insights-data til Dynamics 365 Sales
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598102"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="07271-103">Opret forbindelse til Dynamics 365 Sales (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="07271-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="07271-104">Brug dine kundedata til at oprette marketinglister, følge op på arbejdsprocesser og udsende kampagner med Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="07271-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="07271-105">Forudsætning</span><span class="sxs-lookup"><span data-stu-id="07271-105">Prerequisite</span></span>

1. <span data-ttu-id="07271-106">Kontaktposter skal være til stede i Dynamics 365 Sales, før du kan eksportere et segment fra Customer Insights til Sales.</span><span class="sxs-lookup"><span data-stu-id="07271-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="07271-107">Læs mere om, hvordan du kontakter i [Dynamics 365 Sales ved hjælp af Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="07271-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="07271-108">Hvis du eksporterer segmenter fra målgruppeindsigt til Sales, oprettes der ikke nye kontaktposter i Sales-forekomsterne.</span><span class="sxs-lookup"><span data-stu-id="07271-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="07271-109">Kontaktpersonposterne fra Sales skal være direkte målgruppeindsigt og bruges som en datakilde.</span><span class="sxs-lookup"><span data-stu-id="07271-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="07271-110">De skal også inkluderes i den samlede brugerdefinerede enhed for at knytte kunde-ID'er til kontakt-ID'er, før segmenter kan eksporteres.</span><span class="sxs-lookup"><span data-stu-id="07271-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="07271-111">Konfigurer connectoren til Sales</span><span class="sxs-lookup"><span data-stu-id="07271-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="07271-112">Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="07271-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="07271-113">Under **Dynamics 365 Sales** vælg **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="07271-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="07271-114">Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="07271-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="07271-115">Angiv din organisations URL-adresse for Sales i feltet **Serveradresse**.</span><span class="sxs-lookup"><span data-stu-id="07271-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="07271-116">I sektionen **Serveradministratorkonto** vælg **Log på** og vælg en Dynamics 365 Sales-konto.</span><span class="sxs-lookup"><span data-stu-id="07271-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="07271-117">Knyt et kunde-ID-felt til Dynamics 365-kontakt-id.</span><span class="sxs-lookup"><span data-stu-id="07271-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="07271-118">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="07271-118">Select **Next**.</span></span>

1. <span data-ttu-id="07271-119">Vælg en eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="07271-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="07271-120">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="07271-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="07271-121">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="07271-121">Export the data</span></span>

<span data-ttu-id="07271-122">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="07271-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="07271-123">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="07271-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]