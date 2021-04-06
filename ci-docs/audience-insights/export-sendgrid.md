---
title: Eksportere Customer Insights-data til SendGrid
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597274"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="d9539-103">Connector til SendGrid (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="d9539-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="d9539-104">Eksportér segmenter med ensartede kundeprofiler til SendGrid-kontaktlister, og brug dem til kampagner og mailmarketing i SendGrid.</span><span class="sxs-lookup"><span data-stu-id="d9539-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d9539-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="d9539-105">Prerequisites</span></span>

-   <span data-ttu-id="d9539-106">Du har en [SendGrid-konto](https://sendgrid.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="d9539-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d9539-107">Der findes eksisterende kontaktlister i SendGrid og de tilsvarende id'er.</span><span class="sxs-lookup"><span data-stu-id="d9539-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="d9539-108">Du kan finde flere oplysninger [i SendGrid – Administrere kontakter](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="d9539-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="d9539-109">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="d9539-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d9539-110">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="d9539-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="d9539-111">Oprette forbindelse til SendGrid</span><span class="sxs-lookup"><span data-stu-id="d9539-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="d9539-112">Gå til **Adminstration** > **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="d9539-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d9539-113">Under **SendGrid** skal du vælge **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="d9539-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="d9539-114">Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="d9539-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Ruden SendGrid-eksportkonfiguration.":::

1. <span data-ttu-id="d9539-116">Angiv **SendGrid API-nøglen** [SendGrid API-nøgle](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="d9539-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="d9539-117">Angiv dit **[SendGrid-liste-id](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**</span><span class="sxs-lookup"><span data-stu-id="d9539-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="d9539-118">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="d9539-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d9539-119">Vælg **Opret forbindelse** for at initialisere forbindelsen til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="d9539-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="d9539-120">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="d9539-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d9539-121">Vælg **Næste** for at konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="d9539-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="d9539-122">Konfigurer connectoren</span><span class="sxs-lookup"><span data-stu-id="d9539-122">Configure the connector</span></span>

1. <span data-ttu-id="d9539-123">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="d9539-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d9539-124">Gentag de samme trin for andre valgfrie felter, f.eks.. **Fornavn**, **Efternavn**, **Land/Område**, **Stat**, **By** og **Postnummer**.</span><span class="sxs-lookup"><span data-stu-id="d9539-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="d9539-125">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="d9539-125">Select the segments you want to export.</span></span> <span data-ttu-id="d9539-126">Det **anbefales ikke at eksportere mere end 100.000 kundeprofiler i alt** til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="d9539-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="d9539-127">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="d9539-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d9539-128">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="d9539-128">Export the data</span></span>

<span data-ttu-id="d9539-129">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d9539-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d9539-130">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d9539-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d9539-131">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="d9539-131">Known limitations</span></span>

- <span data-ttu-id="d9539-132">Op til 100.000 profiler i alt til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="d9539-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="d9539-133">Eksport til SendGrid er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="d9539-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="d9539-134">Det kan tage op til et par timer at eksportere op til 100.000 profiler til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="d9539-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="d9539-135">Antallet af profiler, du kan eksportere til SendGrid, er afhængige og begrænsede i kontrakten med SendGrid.</span><span class="sxs-lookup"><span data-stu-id="d9539-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d9539-136">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="d9539-136">Data privacy and compliance</span></span>

<span data-ttu-id="d9539-137">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til SendGrid, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks.. personlige data.</span><span class="sxs-lookup"><span data-stu-id="d9539-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d9539-138">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at SendGrid overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="d9539-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d9539-139">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d9539-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d9539-140">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="d9539-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]