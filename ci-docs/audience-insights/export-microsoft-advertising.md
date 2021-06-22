---
title: Eksportere Customer Insights-data til Microsoft Advertising
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124471"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="296f9-103">Eksportere segmenter til Microsoft Advertising (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="296f9-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="296f9-104">Eksporter Customer Insights-segmenter til Microsoft Advertising for at oprette målgrupper for kundematch.</span><span class="sxs-lookup"><span data-stu-id="296f9-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="296f9-105">Brug disse målgrupper til dine annoncekampagner.</span><span class="sxs-lookup"><span data-stu-id="296f9-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="296f9-106">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="296f9-106">Prerequisites</span></span>

-   <span data-ttu-id="296f9-107">En [Microsoft Advertising-konto](https://ads.microsoft.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="296f9-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="296f9-108">Du har accepteret vilkårene for kundematch.</span><span class="sxs-lookup"><span data-stu-id="296f9-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="296f9-109">[Konfigurerede segmenter](segments.md) i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="296f9-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="296f9-110">Samlede debitorprofiler i de eksporterede segmenter indeholder et felt med en mailadresse.</span><span class="sxs-lookup"><span data-stu-id="296f9-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="296f9-111">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="296f9-111">Known limitations</span></span>

- <span data-ttu-id="296f9-112">Du kan eksportere op til 500K profiler pr. eksport til Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="296f9-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="296f9-113">Eksport til Microsoft Advertising er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="296f9-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="296f9-114">Det kan tage op til 10 minutter at eksportere op til 500K profiler til Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="296f9-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="296f9-115">Konfigurer forbindelsen til Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="296f9-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="296f9-116">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="296f9-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="296f9-117">Vælg **Tilføj forbindelse**, og vælg **Microsoft Advertising** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="296f9-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="296f9-118">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="296f9-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="296f9-119">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="296f9-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="296f9-120">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="296f9-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="296f9-121">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="296f9-121">Choose who can use this connection.</span></span> <span data-ttu-id="296f9-122">Standarden er administratorer.</span><span class="sxs-lookup"><span data-stu-id="296f9-122">The default is administrators.</span></span> <span data-ttu-id="296f9-123">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="296f9-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="296f9-124">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="296f9-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="296f9-125">Vælg **Opret forbindelse** for at initialisere forbindelsen til Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="296f9-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="296f9-126">Vælg **Godkend med Microsoft Advertising**, og angiv administratoroplysningerne for Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="296f9-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="296f9-127">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="296f9-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="296f9-128">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="296f9-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="296f9-129">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="296f9-129">Configure an export</span></span>

<span data-ttu-id="296f9-130">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="296f9-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="296f9-131">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="296f9-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="296f9-132">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="296f9-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="296f9-133">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="296f9-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="296f9-134">Vælg en forbindelse i sektionen Microsoft Advertising i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="296f9-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="296f9-135">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="296f9-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="296f9-136">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="296f9-136">Select the segments to export.</span></span> <span data-ttu-id="296f9-137">Målgrupperne Kundematch i Microsoft Advertising oprettes automatisk med navnet på de segmenter, der er valgt til eksport.</span><span class="sxs-lookup"><span data-stu-id="296f9-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="296f9-138">Hvert segment resulterer i en separat kundematchmålgruppe.</span><span class="sxs-lookup"><span data-stu-id="296f9-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="296f9-139">Angiv dit **Microsoft Advertising-kunde-id og -konto-id**.</span><span class="sxs-lookup"><span data-stu-id="296f9-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="296f9-140">Du kan finde kunde-id' et (`cid`) og konto-id'et (`aid`) i parametrene for URL-adressen, når du er logget på Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="296f9-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="296f9-141">Vælg det felt i din samlede kundeprofil med en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**.</span><span class="sxs-lookup"><span data-stu-id="296f9-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="296f9-142">Det er obligatorisk at eksportere segmenter til Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="296f9-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="296f9-143">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="296f9-143">Select **Save**.</span></span>

<span data-ttu-id="296f9-144">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="296f9-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="296f9-145">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="296f9-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="296f9-146">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="296f9-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="296f9-147">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="296f9-147">Data privacy and compliance</span></span>

<span data-ttu-id="296f9-148">Når du gør det muligt for Dynamics 365 Customer Insights at overføre data til Microsoft Advertising, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder følsomme data som f.eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="296f9-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="296f9-149">Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at Microsoft Advertising overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have.</span><span class="sxs-lookup"><span data-stu-id="296f9-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="296f9-150">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="296f9-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="296f9-151">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at stoppe brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="296f9-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
