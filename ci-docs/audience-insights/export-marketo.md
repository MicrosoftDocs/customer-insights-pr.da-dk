---
title: Eksportér Customer Insights-data til Marketo
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267074"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="3b935-103">Connector til Marketo (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="3b935-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="3b935-104">Eksportér segmenter fra de samlede brugerprofiler til at generere kampagner, levere e-mailmarketing og bruge bestemte grupper af kunder med Marketo.</span><span class="sxs-lookup"><span data-stu-id="3b935-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3b935-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="3b935-105">Prerequisites</span></span>

-   <span data-ttu-id="3b935-106">Du har en [Marketo-konto](https://login.marketo.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="3b935-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3b935-107">Der findes eksisterende lister i Marketo og de tilsvarende id'er.</span><span class="sxs-lookup"><span data-stu-id="3b935-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="3b935-108">Du kan finde flere oplysninger i [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="3b935-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="3b935-109">Du har [konfigureret segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="3b935-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="3b935-110">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="3b935-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="3b935-111">Opret forbindelse til Marketo</span><span class="sxs-lookup"><span data-stu-id="3b935-111">Connect to Marketo</span></span>

1. <span data-ttu-id="3b935-112">Gå til **Adminstration** > **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="3b935-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3b935-113">Under **Marketo** skal du vælge **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="3b935-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="3b935-114">Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="3b935-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3b935-115">Angiv dit **[Marketo-klient-ID, klientens hemmelige og resterende værtsnavnsslutpunkt](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="3b935-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="3b935-116">Angiv dit **[Marketo-liste-id](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="3b935-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="3b935-117">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og kompatibilitet**, og vælg **Opret forbindelse** for at initialisere forbindelsen til Marketo.</span><span class="sxs-lookup"><span data-stu-id="3b935-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="3b935-118">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="3b935-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Eksportér skærmbilleder til Marketo-forbindelse":::

1. <span data-ttu-id="3b935-120">Vælg **Næste** for at konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="3b935-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="3b935-121">Konfigurer connectoren</span><span class="sxs-lookup"><span data-stu-id="3b935-121">Configure the connector</span></span>

1. <span data-ttu-id="3b935-122">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="3b935-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="3b935-123">Du kan også eksportere **Fornavn**, **Efternavn**, **By**, **Stat** og **Land/Region** som ekstra felter for at oprette mere personlige e-mails.</span><span class="sxs-lookup"><span data-stu-id="3b935-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="3b935-124">Vælg **Tilføj attribut** for at tilknytte disse felter.</span><span class="sxs-lookup"><span data-stu-id="3b935-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="3b935-125">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="3b935-125">Select the segments you want to export.</span></span> <span data-ttu-id="3b935-126">Du kan eksportere op til 1000000 kundeprofiler i alt til Marketo.</span><span class="sxs-lookup"><span data-stu-id="3b935-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Vælg felter og segmenter, der skal eksporteres til Marketo":::

1. <span data-ttu-id="3b935-128">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="3b935-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3b935-129">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="3b935-129">Export the data</span></span>

<span data-ttu-id="3b935-130">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3b935-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3b935-131">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3b935-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3b935-132">I Marketo kan du nu finde dine segmenter under [Marketo-lister](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="3b935-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3b935-133">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="3b935-133">Known limitations</span></span>

- <span data-ttu-id="3b935-134">Op til 1000000 profiler pr. eksport til Marketo.</span><span class="sxs-lookup"><span data-stu-id="3b935-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="3b935-135">Eksport til Marketo er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="3b935-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="3b935-136">Eksport af segmenter med i alt 1000000 profiler kan tage op til tre timer.</span><span class="sxs-lookup"><span data-stu-id="3b935-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="3b935-137">Antallet af profiler, du kan eksportere til Marketo, er afhængige og begrænsede i kontrakten med Marketo.</span><span class="sxs-lookup"><span data-stu-id="3b935-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3b935-138">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="3b935-138">Data privacy and compliance</span></span>

<span data-ttu-id="3b935-139">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Marketo, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="3b935-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3b935-140">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Marketo overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="3b935-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3b935-141">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3b935-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3b935-142">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="3b935-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]