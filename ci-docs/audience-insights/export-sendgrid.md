---
title: Eksportere Customer Insights-data til SendGrid
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759758"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="24174-103">Eksportér segmenter til SendGrid (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="24174-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="24174-104">Eksportér segmenter med ensartede kundeprofiler til SendGrid-kontaktlister, og brug dem til kampagner og mailmarketing i SendGrid.</span><span class="sxs-lookup"><span data-stu-id="24174-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="24174-105">Forudsætninger for en forbindelse</span><span class="sxs-lookup"><span data-stu-id="24174-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="24174-106">Du har en [SendGrid-konto](https://sendgrid.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="24174-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="24174-107">Der findes eksisterende kontaktlister i SendGrid og de tilsvarende id'er.</span><span class="sxs-lookup"><span data-stu-id="24174-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="24174-108">Du kan finde flere oplysninger [i SendGrid – Administrere kontakter](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="24174-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="24174-109">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="24174-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="24174-110">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="24174-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="24174-111">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="24174-111">Known limitations</span></span>

- <span data-ttu-id="24174-112">Op til 100.000 profiler i alt til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="24174-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="24174-113">Eksport til SendGrid er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="24174-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="24174-114">Det kan tage op til et par timer at eksportere op til 100.000 profiler til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="24174-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="24174-115">Antallet af profiler, du kan eksportere til SendGrid, er afhængige og begrænsede i kontrakten med SendGrid.</span><span class="sxs-lookup"><span data-stu-id="24174-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="24174-116">Konfigurer forbindelsen til SendGrid</span><span class="sxs-lookup"><span data-stu-id="24174-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="24174-117">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="24174-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="24174-118">Vælg **Tilføj forbindelse**, og vælg **SendGrid** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="24174-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="24174-119">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="24174-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="24174-120">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="24174-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="24174-121">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="24174-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="24174-122">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="24174-122">Choose who can use this connection.</span></span> <span data-ttu-id="24174-123">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="24174-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="24174-124">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="24174-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="24174-125">Angiv **SendGrid API-nøglen** [SendGrid API-nøgle](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="24174-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="24174-126">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="24174-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="24174-127">Vælg **Opret forbindelse** for at initialisere forbindelsen til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="24174-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="24174-128">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="24174-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="24174-129">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="24174-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="24174-130">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="24174-130">Configure an export</span></span>

<span data-ttu-id="24174-131">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="24174-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="24174-132">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="24174-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="24174-133">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="24174-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="24174-134">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="24174-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="24174-135">Vælg en forbindelse i sektionen SendGrid i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="24174-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="24174-136">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="24174-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="24174-137">Angiv dit **[SendGrid-liste-id](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**</span><span class="sxs-lookup"><span data-stu-id="24174-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="24174-138">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="24174-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="24174-139">Gentag de samme trin for andre valgfrie felter, f.eks.. **Fornavn**, **Efternavn**, **Land/Område**, **Stat**, **By** og **Postnummer**.</span><span class="sxs-lookup"><span data-stu-id="24174-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="24174-140">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="24174-140">Select the segments you want to export.</span></span> <span data-ttu-id="24174-141">Det **anbefales ikke at eksportere mere end 100.000 kundeprofiler i alt** til SendGrid.</span><span class="sxs-lookup"><span data-stu-id="24174-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="24174-142">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="24174-142">Select **Save**.</span></span>

<span data-ttu-id="24174-143">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="24174-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="24174-144">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="24174-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="24174-145">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="24174-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="24174-146">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="24174-146">Data privacy and compliance</span></span>

<span data-ttu-id="24174-147">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til SendGrid, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks.. personlige data.</span><span class="sxs-lookup"><span data-stu-id="24174-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="24174-148">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at SendGrid overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="24174-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="24174-149">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="24174-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="24174-150">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="24174-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]