---
title: Dataindsættelse og begrænsninger i realtid
description: Generelle oplysninger om realtidsfunktioner i målgruppen Insights.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270273"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="235b4-103">Dataindtagelse i realtid (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="235b4-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="235b4-104">I næsten realtidsfunktionalitet kan du se i løbet af få sekunder de seneste interaktioner, som dine kunder har foretaget med dine produkter eller servicer.</span><span class="sxs-lookup"><span data-stu-id="235b4-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="235b4-105">[Planlagte opdateringer](system.md#schedule-tab) omfatter et stort antal poster og flere komplekse handlinger.</span><span class="sxs-lookup"><span data-stu-id="235b4-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="235b4-106">For det første hentes data fra datakilden.</span><span class="sxs-lookup"><span data-stu-id="235b4-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="235b4-107">Herefter bliver dataene samlet og derefter forbedret med yderligere oplysninger.</span><span class="sxs-lookup"><span data-stu-id="235b4-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="235b4-108">Enhver kørsel af denne proces kan tage fra få minutter til flere timer.</span><span class="sxs-lookup"><span data-stu-id="235b4-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="235b4-109">Realtidsfunktionen leverer data med det samme til forbrug, indtil den efterfølgende planlagte opdatering henter disse data fra datakilden.</span><span class="sxs-lookup"><span data-stu-id="235b4-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="235b4-110">Opdateringerne i realtid har en udløbsdato, hvorefter de ikke længere overskriver værdien fra datakilden:</span><span class="sxs-lookup"><span data-stu-id="235b4-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="235b4-111">Profilopdateringer gemmes i fire timer</span><span class="sxs-lookup"><span data-stu-id="235b4-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="235b4-112">Aktiviteter gemmes i 30 dage</span><span class="sxs-lookup"><span data-stu-id="235b4-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="235b4-113">Disse værdier er parametre for API-kald, som du kan ændre.</span><span class="sxs-lookup"><span data-stu-id="235b4-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="235b4-114">De skal sikre, at kildedataene forbliver din kilde til sandheden.</span><span class="sxs-lookup"><span data-stu-id="235b4-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="235b4-115">Hvis der skal inkluderes realtidsopdateringer i længere tid, skal du føje dem til en datakilde så de bliver udtrukket under den næste planlagte opdatering.</span><span class="sxs-lookup"><span data-stu-id="235b4-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="235b4-116">Realtidsopdatering af felter med samlet kundeprofil</span><span class="sxs-lookup"><span data-stu-id="235b4-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="235b4-117">Opdaterede profiler vises i visningen kundekort eller en anden visualisering i løbet af få sekunder.</span><span class="sxs-lookup"><span data-stu-id="235b4-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="235b4-118">Da realtidsoperationer finder sted, efter at datasamlingen er sket, gælder de kun for de samlede kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="235b4-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="235b4-119">Profilændringer i realtid vil derfor ikke opdatere målinger, segmentmedlemskab eller forbedringer.</span><span class="sxs-lookup"><span data-stu-id="235b4-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="235b4-120">Begrænsninger</span><span class="sxs-lookup"><span data-stu-id="235b4-120">Limitations</span></span>

- <span data-ttu-id="235b4-121">Kundeprofiler kan opdateres, men ikke oprettes eller slettes.</span><span class="sxs-lookup"><span data-stu-id="235b4-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="235b4-122">Det er ikke muligt at eksportere opdateringer i realtid til eksterne som Power BI i øjeblikket.</span><span class="sxs-lookup"><span data-stu-id="235b4-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="235b4-123">Realtidsoprettelse af aktiviteter</span><span class="sxs-lookup"><span data-stu-id="235b4-123">Real-time creation of activities</span></span>

<span data-ttu-id="235b4-124">I realtids-API kan du udgive en ny aktivitet fra kildesystemet (en enkelt kildepost) til en samlet kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="235b4-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="235b4-125">Den nye aktivitet bliver tilgængelig som en samlet aktivitet i den samlede kundeprofils tidslinje i løbet af få sekunder.</span><span class="sxs-lookup"><span data-stu-id="235b4-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="235b4-126">Du kan se tidslinjen i visningen kundekort eller en anden tidslinjeintegration, du har konfigureret.</span><span class="sxs-lookup"><span data-stu-id="235b4-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="235b4-127">Aktiviteter kan ikke ændres.</span><span class="sxs-lookup"><span data-stu-id="235b4-127">Activities are immutable.</span></span> <span data-ttu-id="235b4-128">De ændres ikke, når de er oprettet.</span><span class="sxs-lookup"><span data-stu-id="235b4-128">They don't change once created.</span></span>
> - <span data-ttu-id="235b4-129">I øjeblikket opdateres segmenter og målinger ikke, afhængigt af den nye aktivitet.</span><span class="sxs-lookup"><span data-stu-id="235b4-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="235b4-130">Aktiviteter, der kun er tilføjet via realtids-API, er ikke en del af eksporter, og de vises ikke i Power BI.</span><span class="sxs-lookup"><span data-stu-id="235b4-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="235b4-131">Der er to måder at oprette forbindelse til en realtids-API på:</span><span class="sxs-lookup"><span data-stu-id="235b4-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="235b4-132">[indirekte](#connect-via-the-dynamics-365-customer-insights-connector) ved hjælp af [Dynamics 365 Customer Insights-connectoren](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="235b4-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="235b4-133">[direkte](#connect-directly-to-the-real-time-api) med kode</span><span class="sxs-lookup"><span data-stu-id="235b4-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="235b4-134">Der gælder følgende forudsætninger for begge måder:</span><span class="sxs-lookup"><span data-stu-id="235b4-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="235b4-135">Et Customer Insights-miljø</span><span class="sxs-lookup"><span data-stu-id="235b4-135">A Customer Insights environment</span></span>
- <span data-ttu-id="235b4-136">Samlede kundeprofiler</span><span class="sxs-lookup"><span data-stu-id="235b4-136">Unified customer profiles</span></span>
- <span data-ttu-id="235b4-137">Aktiviteter er konfigureret og kører</span><span class="sxs-lookup"><span data-stu-id="235b4-137">Activities configured and run</span></span>
- <span data-ttu-id="235b4-138">Bidragyder- eller administratortilladelser til at godkende din konto</span><span class="sxs-lookup"><span data-stu-id="235b4-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="235b4-139">Forbindelse via Dynamics 365 Customer Insights-connectoren</span><span class="sxs-lookup"><span data-stu-id="235b4-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="235b4-140">I realtids-API kan du indtage data fra en dedikeret Power Platform-connector, [Dynamics 365 Customer Insights-connectoren](https://docs.microsoft.com/connectors/customerinsights/) uden at skulle skrive og installere nogen kode.</span><span class="sxs-lookup"><span data-stu-id="235b4-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="235b4-141">Connectoren kan udføre de samme realtidshandlinger som API'en.</span><span class="sxs-lookup"><span data-stu-id="235b4-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="235b4-142">Du skal have en gyldig licens til premium connectorer.</span><span class="sxs-lookup"><span data-stu-id="235b4-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="235b4-143">Du kan finde flere oplysninger under [Ofte stillede spørgsmål til Power Apps- og Power Automate-licenser](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="235b4-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="235b4-144">Power Platform [Power Apps og/eller Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="235b4-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="235b4-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="235b4-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="235b4-146">Du kan finde flere oplysninger om oprettelse af flow i [dokumentationen til Power Automate](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="235b4-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="235b4-147">Oprette direkte forbindelse til API i realtid</span><span class="sxs-lookup"><span data-stu-id="235b4-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="235b4-148">Du kan bruge realtids-funktionerne ved at oprette din egen pipeline og oprette forbindelse direkte til API i realtid.</span><span class="sxs-lookup"><span data-stu-id="235b4-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="235b4-149">Du kan bogføre en aktivitet i formatet af kildesystemet eller i UnifiedActivity-formatet.</span><span class="sxs-lookup"><span data-stu-id="235b4-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="235b4-150">Hent formatet ved at foretage et API-kald til /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="235b4-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="235b4-151">Du kan finde oplysninger om denne API, herunder parametre og svar, i afsnittet **EntityData** i [Customer Insights-API'er-reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="235b4-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="235b4-152">Du kan finde flere oplysninger i afsnittet [Arbejde med Customer Insights-API'er](apis.md).</span><span class="sxs-lookup"><span data-stu-id="235b4-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="235b4-153">Forstå dit realtidsforbrug med telemetri</span><span class="sxs-lookup"><span data-stu-id="235b4-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="235b4-154">Få et overblik over omfanget af anmodninger til API i realtid og oplysninger om de problemer, der kan opstå i systemet.</span><span class="sxs-lookup"><span data-stu-id="235b4-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="235b4-155">Du kan få [adgang til telemetri i realtid](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="235b4-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]