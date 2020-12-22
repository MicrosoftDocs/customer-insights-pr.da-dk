---
title: Eksportér Customer Insights-data til Mailchimp
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405414"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="8b678-103">Connector til Mailchimp (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="8b678-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="8b678-104">Eksportér segmenter af samlede kundeprofiler til MailChimp for at oprette nyhedsbreve og e-mailkampagner.</span><span class="sxs-lookup"><span data-stu-id="8b678-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8b678-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="8b678-105">Prerequisites</span></span>

-   <span data-ttu-id="8b678-106">Du har en [Mailchimp-konto](https://mailchimp.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="8b678-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8b678-107">Der findes eksisterende målgrupper i Mailchimp og de tilsvarende id'er.</span><span class="sxs-lookup"><span data-stu-id="8b678-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="8b678-108">Du kan finde flere oplysninger i [Mailchimp-målgrupper](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="8b678-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="8b678-109">Du har [konfigureret segmenter](segments.md)</span><span class="sxs-lookup"><span data-stu-id="8b678-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="8b678-110">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="8b678-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="8b678-111">Opret forbindelse til Mailchimp</span><span class="sxs-lookup"><span data-stu-id="8b678-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="8b678-112">Gå til **Adminstration** > **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="8b678-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8b678-113">Under **Mailchimp** skal du vælge **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="8b678-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="8b678-114">Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="8b678-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8b678-115">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="8b678-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8b678-116">Angiv dit **[Mailchimp-målgruppe-id](https://mailchimp.com/help/find-audience-id/)**, og vælg **Opret forbindelse** for at initialisere forbindelsen til Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8b678-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="8b678-117">Vælg **Godkendelse med Mailchimp**, og angiv dine Mailchimp-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="8b678-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="8b678-118">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="8b678-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Eksportér skærmbilleder til Mailchimp-forbindelse":::

1. <span data-ttu-id="8b678-120">Vælg **Næste** for at konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="8b678-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="8b678-121">Konfigurer connectoren</span><span class="sxs-lookup"><span data-stu-id="8b678-121">Configure the connector</span></span>

1. <span data-ttu-id="8b678-122">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="8b678-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="8b678-123">Du kan også eksportere **Fornavn** og **Efternavn** som ekstra felter for at oprette mere personlige e-mails.</span><span class="sxs-lookup"><span data-stu-id="8b678-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="8b678-124">Vælg **Tilføj attribut** for at tilknytte disse felter.</span><span class="sxs-lookup"><span data-stu-id="8b678-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="8b678-125">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="8b678-125">Select the segments you want to export.</span></span> <span data-ttu-id="8b678-126">Du kan eksportere op til 1000000 kundeprofiler i alt til Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8b678-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Vælge felter og segmenter, der skal eksporteres til MailChimp":::

1. <span data-ttu-id="8b678-128">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="8b678-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8b678-129">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="8b678-129">Export the data</span></span>

<span data-ttu-id="8b678-130">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8b678-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8b678-131">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8b678-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8b678-132">I Mailchimp kan du nu finde dine segmenter under [Mailchimp-målgrupper](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="8b678-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8b678-133">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="8b678-133">Known limitations</span></span>

- <span data-ttu-id="8b678-134">Op til 1000000 profiler pr. eksport til Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8b678-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="8b678-135">Eksport til Mailchimp er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="8b678-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="8b678-136">Eksport af segmenter med det samlede antal 1000000-profiler kan tage op til tre timer på grund af begrænsninger på udbydersiden.</span><span class="sxs-lookup"><span data-stu-id="8b678-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="8b678-137">Antallet af profiler, du kan eksportere til Mailchimp, er afhængige og begrænsede i kontrakten med Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8b678-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8b678-138">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="8b678-138">Data privacy and compliance</span></span>

<span data-ttu-id="8b678-139">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Mailchimp, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="8b678-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8b678-140">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Mailchimp overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="8b678-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8b678-141">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8b678-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8b678-142">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="8b678-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
