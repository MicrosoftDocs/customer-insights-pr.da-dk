---
title: Eksportér Customer Insights-data til Dynamics 365 Sales
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643811"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="853df-103">Opret forbindelse til Dynamics 365 Sales (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="853df-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="853df-104">Brug dine kundedata til at oprette marketinglister, følge op på arbejdsprocesser og udsende kampagner med Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="853df-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="853df-105">Forudsætning</span><span class="sxs-lookup"><span data-stu-id="853df-105">Prerequisite</span></span>

<span data-ttu-id="853df-106">Kontaktpersonposter [fra Dynamics 365 Sales, der tilføres ved hjælp af Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="853df-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="853df-107">Konfigurer connectoren til Sales</span><span class="sxs-lookup"><span data-stu-id="853df-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="853df-108">Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="853df-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="853df-109">Under **Dynamics 365 Sales** vælg **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="853df-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="853df-110">Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="853df-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="853df-111">Angiv din organisations URL-adresse for Sales i feltet **Serveradresse**.</span><span class="sxs-lookup"><span data-stu-id="853df-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="853df-112">I sektionen **Serveradministratorkonto** vælg **Log på** og vælg en Dynamics 365 Sales-konto.</span><span class="sxs-lookup"><span data-stu-id="853df-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="853df-113">Knyt et kunde-ID-felt til Dynamics 365-kontakt-id.</span><span class="sxs-lookup"><span data-stu-id="853df-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="853df-114">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="853df-114">Select **Next**.</span></span>

1. <span data-ttu-id="853df-115">Vælg en eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="853df-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="853df-116">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="853df-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="853df-117">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="853df-117">Export the data</span></span>

<span data-ttu-id="853df-118">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="853df-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="853df-119">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="853df-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
