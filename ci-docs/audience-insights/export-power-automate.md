---
title: Power Automate-connector | Microsoft Docs
description: Oprette flows i Microsoft Power Automate fra Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405408"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="08610-103">Power Automate-connector (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="08610-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="08610-104">Udløs specifikke hændelser, der skal udføres automatisk, når dataene ændres, og administrer mere komplekse processer direkte i [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="08610-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="08610-105">Power Automate-udløsere</span><span class="sxs-lookup"><span data-stu-id="08610-105">Power Automate triggers</span></span>

<span data-ttu-id="08610-106">Du kan bruge forskellige udløsere, som giver dig mulighed for at oprette flow til at automatisere rutineopgaver, f.eks. meddelelser eller mere avancerede handlinger.</span><span class="sxs-lookup"><span data-stu-id="08610-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="08610-107">Udløses, når en opdatering af datakilde mislykkes.</span><span class="sxs-lookup"><span data-stu-id="08610-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="08610-108">Udløses, når en opdatering af datakilde lykkes.</span><span class="sxs-lookup"><span data-stu-id="08610-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="08610-109">Udløses, når en tærskel krydses i et segment.</span><span class="sxs-lookup"><span data-stu-id="08610-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="08610-110">Udløseren er begrænset til krydsning over grænsen.</span><span class="sxs-lookup"><span data-stu-id="08610-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="08610-111">Udløses, når en tærskel krydses i en forretningsmæssig måling.</span><span class="sxs-lookup"><span data-stu-id="08610-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="08610-112">Udløseren er begrænset til krydsning over grænsen.</span><span class="sxs-lookup"><span data-stu-id="08610-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="08610-113">Udløser, når en fuld opdatering af (datakilder, segmenter, målinger....) er fuldført.</span><span class="sxs-lookup"><span data-stu-id="08610-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="08610-114">Udløser, når en opdatering af samlingsprocessen (tilknytning, match, fletning) er fuldført.</span><span class="sxs-lookup"><span data-stu-id="08610-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="08610-115">[Konfigurere dine udløsere i Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="08610-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="08610-116">Power Automate-handlinger</span><span class="sxs-lookup"><span data-stu-id="08610-116">Power Automate actions</span></span>
<span data-ttu-id="08610-117">Power Automate-connectoren giver andre handlinger end de tilgængelige udløsere.</span><span class="sxs-lookup"><span data-stu-id="08610-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="08610-118">Se [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/), hvis du vil have flere oplysninger.</span><span class="sxs-lookup"><span data-stu-id="08610-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="08610-119">Opret et Power Automate-flow i målgruppen Insights</span><span class="sxs-lookup"><span data-stu-id="08610-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="08610-120">Gå til **Admin** > **System** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="08610-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="08610-121">Vælg fanen **Status** på siden **System**.</span><span class="sxs-lookup"><span data-stu-id="08610-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="08610-122">Vælg **Flow** i sektionen **Datakilder**, og vælg **Opret et flow** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="08610-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08610-123">![Power Automate-connector viser Opret et flow-handling](media/power-automate-connector-create-flow.png "Power Automate-connector viser Opret et flow-handling")</span><span class="sxs-lookup"><span data-stu-id="08610-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="08610-124">I Power Automate skal du vælge en af de tilgængelige udløsere for at oprette dit foretrukne flow.</span><span class="sxs-lookup"><span data-stu-id="08610-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="08610-125">Hvis du opretter dit første flow, skal du først godkendes af Power Automate-connectoren.</span><span class="sxs-lookup"><span data-stu-id="08610-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
