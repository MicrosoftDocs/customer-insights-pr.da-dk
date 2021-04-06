---
title: Power Automate-connector | Microsoft Docs
description: Oprette flows i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597918"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="eed0f-103">Power Automate-connector (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="eed0f-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="eed0f-104">Udløs specifikke hændelser, der skal udføres automatisk, når dataene ændres, og administrer mere komplekse processer direkte i [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="eed0f-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="eed0f-105">Power Automate-udløsere</span><span class="sxs-lookup"><span data-stu-id="eed0f-105">Power Automate triggers</span></span>

<span data-ttu-id="eed0f-106">Brug udløsere til at oprette skystrømme og automatisere tilbagevendende opgaver, f.eks. meddelelser eller mere avancerede handlinger.</span><span class="sxs-lookup"><span data-stu-id="eed0f-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="eed0f-107">Udløses, når en opdatering af datakilde mislykkes.</span><span class="sxs-lookup"><span data-stu-id="eed0f-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="eed0f-108">Udløses, når en opdatering af datakilde lykkes.</span><span class="sxs-lookup"><span data-stu-id="eed0f-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="eed0f-109">Udløses, når en tærskel krydses i et segment.</span><span class="sxs-lookup"><span data-stu-id="eed0f-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="eed0f-110">Udløseren er begrænset til krydsning over grænsen.</span><span class="sxs-lookup"><span data-stu-id="eed0f-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="eed0f-111">Udløses, når en tærskel krydses i en forretningsmæssig måling.</span><span class="sxs-lookup"><span data-stu-id="eed0f-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="eed0f-112">Udløseren er begrænset til krydsning over grænsen.</span><span class="sxs-lookup"><span data-stu-id="eed0f-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="eed0f-113">Udløser, når en fuld opdatering af (datakilder, segmenter, målinger....) er fuldført.</span><span class="sxs-lookup"><span data-stu-id="eed0f-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="eed0f-114">Udløser, når en opdatering af samlingsprocessen (tilknytning, match, fletning) er fuldført.</span><span class="sxs-lookup"><span data-stu-id="eed0f-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="eed0f-115">[Konfigurere dine udløsere i Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="eed0f-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="eed0f-116">Power Automate-handlinger</span><span class="sxs-lookup"><span data-stu-id="eed0f-116">Power Automate actions</span></span>
<span data-ttu-id="eed0f-117">Power Automate-connectoren giver andre handlinger end de tilgængelige udløsere.</span><span class="sxs-lookup"><span data-stu-id="eed0f-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="eed0f-118">Se [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/), hvis du vil have flere oplysninger.</span><span class="sxs-lookup"><span data-stu-id="eed0f-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="eed0f-119">Oprette et Power Automate-flow</span><span class="sxs-lookup"><span data-stu-id="eed0f-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="eed0f-120">Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="eed0f-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="eed0f-121">På feltet **Power Automate** skal du vælge **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="eed0f-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="eed0f-122">Customer Insights-connector (prøveversion) i Power Automate åbnes.</span><span class="sxs-lookup"><span data-stu-id="eed0f-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="eed0f-123">**Log på** Power Automate.</span><span class="sxs-lookup"><span data-stu-id="eed0f-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="eed0f-124">Vælg en af de tilgængelige udløsere, og tilføj flere trin i det nye flow.</span><span class="sxs-lookup"><span data-stu-id="eed0f-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="eed0f-125">Du kan finde flere oplysninger under [Oprettelse af et skyflow i Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="eed0f-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="eed0f-126">Eksempler på, hvordan du bruger flow:</span><span class="sxs-lookup"><span data-stu-id="eed0f-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="eed0f-127">Sende en meddelelse til en Microsoft Teams-kanal, hvis en datakilde ikke kan opdateres.</span><span class="sxs-lookup"><span data-stu-id="eed0f-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="eed0f-128">Send en mail til dataejerne, når en grænseværdi for et segment overskrides.</span><span class="sxs-lookup"><span data-stu-id="eed0f-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]