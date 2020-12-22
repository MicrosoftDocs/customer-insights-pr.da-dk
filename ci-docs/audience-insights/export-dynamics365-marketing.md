---
title: Eksportér Customer Insights-data til Dynamics 365 Marketing
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643766"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="a3f25-103">Opret forbindelse til Dynamics 365 Marketing (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="a3f25-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a3f25-104">Brug [segmenter](segments.md) til at generere kampagner, og kontakt bestemte grupper af kunder sammen med Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a3f25-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="a3f25-105">Du kan finde flere oplysninger under [Bruge segmenter fra Dynamics 365 Customer Insights sammen med Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="a3f25-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a3f25-106">Forudsætning</span><span class="sxs-lookup"><span data-stu-id="a3f25-106">Prerequisite</span></span>

<span data-ttu-id="a3f25-107">Kontaktpersonposter [fra Dynamics 365 Marketing, der tilføres ved hjælp af Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a3f25-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="a3f25-108">Konfigurer forbindelsen til Marketing</span><span class="sxs-lookup"><span data-stu-id="a3f25-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="a3f25-109">Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="a3f25-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a3f25-110">Under **Dynamics 365 Marketing** vælg **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="a3f25-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="a3f25-111">Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="a3f25-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a3f25-112">Angiv din organisationens URL-adresse for marketing i feltet **Serveradresse**.</span><span class="sxs-lookup"><span data-stu-id="a3f25-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a3f25-113">I sektionen **Serveradministratorkonto** vælg **Log på** og vælg en Dynamics 365 Marketing-konto.</span><span class="sxs-lookup"><span data-stu-id="a3f25-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="a3f25-114">Knyt et kunde-ID-felt til Dynamics 365-kontakt-id.</span><span class="sxs-lookup"><span data-stu-id="a3f25-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a3f25-115">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="a3f25-115">Select **Next**.</span></span>

1. <span data-ttu-id="a3f25-116">Vælg en eller flere segmenter.</span><span class="sxs-lookup"><span data-stu-id="a3f25-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="a3f25-117">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="a3f25-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a3f25-118">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="a3f25-118">Export the data</span></span>

<span data-ttu-id="a3f25-119">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a3f25-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a3f25-120">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a3f25-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
