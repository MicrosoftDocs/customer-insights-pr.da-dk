---
title: Power Automate-connector | Microsoft Docs
description: Oprette flows i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976081"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="b94c1-103">Power Automate-connector (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="b94c1-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="b94c1-104">Udløs specifikke hændelser, der skal udføres automatisk, når dataene ændres, og administrer mere komplekse processer direkte i [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="b94c1-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="b94c1-105">Power Automate-udløsere</span><span class="sxs-lookup"><span data-stu-id="b94c1-105">Power Automate triggers</span></span>

<span data-ttu-id="b94c1-106">Brug udløsere til at oprette skystrømme og automatisere tilbagevendende opgaver, f.eks. meddelelser eller mere avancerede handlinger.</span><span class="sxs-lookup"><span data-stu-id="b94c1-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="b94c1-107">Udløses, når en opdatering af datakilde mislykkes.</span><span class="sxs-lookup"><span data-stu-id="b94c1-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="b94c1-108">Udløses, når en opdatering af datakilde lykkes.</span><span class="sxs-lookup"><span data-stu-id="b94c1-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="b94c1-109">Udløses, når en tærskel krydses i et segment.</span><span class="sxs-lookup"><span data-stu-id="b94c1-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="b94c1-110">Udløseren er begrænset til krydsning over grænsen.</span><span class="sxs-lookup"><span data-stu-id="b94c1-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="b94c1-111">Udløses, når en tærskel krydses i en forretningsmæssig måling.</span><span class="sxs-lookup"><span data-stu-id="b94c1-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="b94c1-112">Det er kun forretningsmålinger uden en dimension, der understøttes.</span><span class="sxs-lookup"><span data-stu-id="b94c1-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="b94c1-113">Udløseren er begrænset til krydsning over grænsen.</span><span class="sxs-lookup"><span data-stu-id="b94c1-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="b94c1-114">Udløser, når en fuld opdatering af (datakilder, segmenter, målinger....) er fuldført.</span><span class="sxs-lookup"><span data-stu-id="b94c1-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="b94c1-115">Udløser, når en opdatering af samlingsprocessen (tilknytning, match, fletning) er fuldført.</span><span class="sxs-lookup"><span data-stu-id="b94c1-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="b94c1-116">[Konfigurere dine udløsere i Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="b94c1-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="b94c1-117">Power Automate-handlinger</span><span class="sxs-lookup"><span data-stu-id="b94c1-117">Power Automate actions</span></span>
<span data-ttu-id="b94c1-118">Power Automate-connectoren giver andre handlinger end de tilgængelige udløsere.</span><span class="sxs-lookup"><span data-stu-id="b94c1-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="b94c1-119">Se [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/), hvis du vil have flere oplysninger.</span><span class="sxs-lookup"><span data-stu-id="b94c1-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="b94c1-120">Oprette et Power Automate-flow</span><span class="sxs-lookup"><span data-stu-id="b94c1-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="b94c1-121">Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="b94c1-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b94c1-122">På feltet **Power Automate** skal du vælge **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="b94c1-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="b94c1-123">Customer Insights-connector (prøveversion) i Power Automate åbnes.</span><span class="sxs-lookup"><span data-stu-id="b94c1-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="b94c1-124">**Log på** Power Automate.</span><span class="sxs-lookup"><span data-stu-id="b94c1-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="b94c1-125">Vælg en af de tilgængelige udløsere, og tilføj flere trin i det nye flow.</span><span class="sxs-lookup"><span data-stu-id="b94c1-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="b94c1-126">Du kan finde flere oplysninger under [Oprettelse af et skyflow i Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="b94c1-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="b94c1-127">Eksempler på, hvordan du bruger flow:</span><span class="sxs-lookup"><span data-stu-id="b94c1-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="b94c1-128">Sende en meddelelse til en Microsoft Teams-kanal, hvis en datakilde ikke kan opdateres.</span><span class="sxs-lookup"><span data-stu-id="b94c1-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="b94c1-129">Send en mail til dataejerne, når en grænseværdi for et segment overskrides.</span><span class="sxs-lookup"><span data-stu-id="b94c1-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
