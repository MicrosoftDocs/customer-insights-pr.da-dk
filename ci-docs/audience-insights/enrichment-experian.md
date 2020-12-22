---
title: Tilsætning af tredjeparts forbedringer fra Experian
description: Generelle oplysninger om Experian-forbedring fra tredjepart.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668800"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="c123e-103">Forbedre kundeprofiler med demografi fra Experian (forbedre)</span><span class="sxs-lookup"><span data-stu-id="c123e-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="c123e-104">Experian er en global leder i forbruger- og virksomhedskreditrapportering og marketingservice.</span><span class="sxs-lookup"><span data-stu-id="c123e-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="c123e-105">Med Experians dataforbedringstjenester kan du få en dybere forståelse af dine kunder ved at udvide dine kundeprofiler med demografiske data, f.eks. husstandens størrelse og indkomst og meget mere.</span><span class="sxs-lookup"><span data-stu-id="c123e-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c123e-106">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="c123e-106">Prerequisites</span></span>

<span data-ttu-id="c123e-107">Hvis du vil konfigurere Experian, skal følgende forudsætninger være opfyldt:</span><span class="sxs-lookup"><span data-stu-id="c123e-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c123e-108">Du har et aktivt Experian-abonnement.</span><span class="sxs-lookup"><span data-stu-id="c123e-108">You have an active Experian subscription.</span></span> <span data-ttu-id="c123e-109">Hvis du vil have et abonnement, skal du [kontakte Experian](https://www.experian.com/marketing-services/contact) direkte.</span><span class="sxs-lookup"><span data-stu-id="c123e-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="c123e-110">[Få mere at vide om Experian-dataforbedring](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="c123e-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="c123e-111">Du har et bruger-id, part-id og modelnummer til din SSH-konto (Secure Transport), som Experian har oprettet for dig.</span><span class="sxs-lookup"><span data-stu-id="c123e-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="c123e-112">Du har [Administrator](permissions.md#administrator)-tilladelser i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="c123e-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="c123e-113">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c123e-113">Configuration</span></span>

1. <span data-ttu-id="c123e-114">Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.</span><span class="sxs-lookup"><span data-stu-id="c123e-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="c123e-115">Vælg **Forbedr mine data** på Experian-feltet.</span><span class="sxs-lookup"><span data-stu-id="c123e-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c123e-116">![Experian-felt](media/experian-tile.png "Experian-felt")</span><span class="sxs-lookup"><span data-stu-id="c123e-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="c123e-117">Vælg **Start her**, og angiv bruger-id, part-id og modelnummer for din Experian-konto til Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="c123e-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="c123e-118">Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**.</span><span class="sxs-lookup"><span data-stu-id="c123e-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="c123e-119">Bekræft alle input ved at vælge **Anvend**.</span><span class="sxs-lookup"><span data-stu-id="c123e-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="c123e-120">Tilknyt dine felter</span><span class="sxs-lookup"><span data-stu-id="c123e-120">Map your fields</span></span>

1. <span data-ttu-id="c123e-121">Vælg **Tilføj data**, og vælg dine nøgle-id'er fra **Navn og adresse**, **Mail** eller **Telefon**, der skal sendes til Experian for identitetsfortolkning.</span><span class="sxs-lookup"><span data-stu-id="c123e-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="c123e-122">Flere nøgle-id-attributter, der sendes til Experian, giver sandsynligvis større sammenfald.</span><span class="sxs-lookup"><span data-stu-id="c123e-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="c123e-123">Vælg **Næste**, og knyt de tilsvarende attributter fra det samlede kundeobjekt for de valgte nøgle-id-felter.</span><span class="sxs-lookup"><span data-stu-id="c123e-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="c123e-124">Vælg **Tilføj attribut** for at tilknytte eventuelle yderligere attributter, du vil sende til Experian.</span><span class="sxs-lookup"><span data-stu-id="c123e-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="c123e-125">Vælg **Gem** for at fuldføre felttilknytningen.</span><span class="sxs-lookup"><span data-stu-id="c123e-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c123e-126">![Experian-felttilknytning](media/experian-field-mapping.png "Experian-felttilknytning")</span><span class="sxs-lookup"><span data-stu-id="c123e-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="c123e-127">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="c123e-127">Enrichment results</span></span>

<span data-ttu-id="c123e-128">Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="c123e-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="c123e-129">Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c123e-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c123e-130">Behandlingstiden afhænger af størrelsen på dine kundedata og de forbedringer, der er konfigureret for din konto af Experian.</span><span class="sxs-lookup"><span data-stu-id="c123e-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="c123e-131">Når forbedringsprocessen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**.</span><span class="sxs-lookup"><span data-stu-id="c123e-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="c123e-132">Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.</span><span class="sxs-lookup"><span data-stu-id="c123e-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c123e-133">Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.</span><span class="sxs-lookup"><span data-stu-id="c123e-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c123e-134">Næste trin</span><span class="sxs-lookup"><span data-stu-id="c123e-134">Next steps</span></span>

<span data-ttu-id="c123e-135">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="c123e-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c123e-136">Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.</span><span class="sxs-lookup"><span data-stu-id="c123e-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c123e-137">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="c123e-137">Data privacy and compliance</span></span>

<span data-ttu-id="c123e-138">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Experian, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="c123e-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c123e-139">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Experian overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="c123e-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c123e-140">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c123e-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c123e-141">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="c123e-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
