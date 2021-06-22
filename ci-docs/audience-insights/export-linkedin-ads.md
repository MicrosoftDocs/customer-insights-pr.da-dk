---
title: Eksportere Customer Insights-data til LinkedIn Ads
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124473"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="ccc6c-103">Eksportere segmenter til LinkedIn Ads (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="ccc6c-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="ccc6c-104">Eksportere segmenter af samlede kundeprofiler til LinkedIn Ads for at oprette matchede målgrupper.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="ccc6c-105">Brug de matchede målgrupper til målretning af virksomheder og kontakter.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ccc6c-106">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="ccc6c-106">Prerequisites</span></span>

-   <span data-ttu-id="ccc6c-107">Du har en [LinkedIn Campaign Manager-konto](https://business.linkedin.com/marketing-solutions/ads) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ccc6c-108">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ccc6c-109">Debitorprofiler i de udlæste målgrupper indeholder et felt med en mailadresse.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ccc6c-110">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="ccc6c-110">Known limitations</span></span>

- <span data-ttu-id="ccc6c-111">Du kan eksportere op til 100K profiler pr. eksport til LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="ccc6c-112">Eksport til LinkedIn Ads er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="ccc6c-113">Det kan tage op til 10 minutter at eksportere op til 100K profiler til LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="ccc6c-114">Konfigurer forbindelsen til LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="ccc6c-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="ccc6c-115">I målgruppeindsigt skal du gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ccc6c-116">Vælg **Tilføj forbindelse**, og vælg **LinkedIn Ads** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="ccc6c-117">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ccc6c-118">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ccc6c-119">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ccc6c-120">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-120">Choose who can use this connection.</span></span> <span data-ttu-id="ccc6c-121">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="ccc6c-122">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ccc6c-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ccc6c-123">Angiv dit [LinkedIn Campaign Manager-konto-id](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="ccc6c-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="ccc6c-124">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ccc6c-125">Vælg **Opret** forbindelse for at initialisere forbindelsen til Kampagneovervågning.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="ccc6c-126">Vælg **Godkend med LinkedIn**, og angiv administratoroplysningerne for LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="ccc6c-127">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ccc6c-128">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ccc6c-129">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="ccc6c-129">Configure an export</span></span>

<span data-ttu-id="ccc6c-130">Du kan konfigurere en eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="ccc6c-131">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ccc6c-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ccc6c-132">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ccc6c-133">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ccc6c-134">Vælg en forbindelse i sektionen LinkedIn Ads i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="ccc6c-135">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ccc6c-136">Vælg, om du vil eksportere data for at udføre [målretning efter kontakt](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) eller [målretning efter virksomheder](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) på LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="ccc6c-137">Vælg det felt i din samlede kundeprofil, der repræsenterer en kundes mailadresse, i sektionen **Datamatching**.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ccc6c-138">Det er obligatorisk at eksportere segmenter til LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="ccc6c-139">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-139">Select the segments you want to export.</span></span> <span data-ttu-id="ccc6c-140">De matchede målgrupper i LinkedIn Campaign Manager oprettes automatisk med navnet på de segmenter, du har valgt at eksportere.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="ccc6c-141">Hvert segment resulterer i en separat afstemt målgruppe.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="ccc6c-142">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-142">Select **Save**.</span></span>

<span data-ttu-id="ccc6c-143">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ccc6c-144">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ccc6c-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ccc6c-145">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ccc6c-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ccc6c-146">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="ccc6c-146">Data privacy and compliance</span></span>

<span data-ttu-id="ccc6c-147">Når du aktiverer Dynamics 365 Customer Insights til at overføre data til LinkedIn Ads, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder følsomme data som f.eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ccc6c-148">Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at LinkedIn Ads overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ccc6c-149">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ccc6c-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ccc6c-150">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at stoppe brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="ccc6c-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
