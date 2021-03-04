---
title: Eksportér Customer Insights-data til Google Ads
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268955"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="fa347-103">Connector til Google Ads (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="fa347-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="fa347-104">Eksportér segmenter af samlede kundeprofiler til Google Ads-målgruppelisten, og brug dem til at annoncere på Google Search, Gmail og YouTube og Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="fa347-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="fa347-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="fa347-105">Prerequisites</span></span>

-   <span data-ttu-id="fa347-106">Du har en [Google Ads-konto](https://ads.google.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="fa347-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fa347-107">Der findes eksisterende målgrupper i Google Ads og de tilsvarende id'er.</span><span class="sxs-lookup"><span data-stu-id="fa347-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="fa347-108">Du kan finde flere oplysninger i [Google ads-målgrupper](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="fa347-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="fa347-109">Du har [konfigureret segmenter](segments.md)</span><span class="sxs-lookup"><span data-stu-id="fa347-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="fa347-110">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse, fornavn og efternavn</span><span class="sxs-lookup"><span data-stu-id="fa347-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="fa347-111">Opret forbindelse til Google Ads</span><span class="sxs-lookup"><span data-stu-id="fa347-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="fa347-112">Gå til **Adminstration** > **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="fa347-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fa347-113">Under **Google Ads** skal du vælge **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="fa347-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="fa347-114">Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="fa347-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="fa347-115">Angiv din **[Google Ads-kunde-id](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="fa347-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="fa347-116">Angiv din **[Google Ads-godkendte udvikler-token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="fa347-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="fa347-117">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="fa347-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fa347-118">Angiv dit **[Google Ads-målgruppe-id](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**, og vælg **Opret forbindelse** for at initialisere forbindelsen til Google Ads.</span><span class="sxs-lookup"><span data-stu-id="fa347-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="fa347-119">Vælg **Godkendelse med Google Ads**, og angiv dine Google Ads-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="fa347-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="fa347-120">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="fa347-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Eksportér skærmbilleder til Google Ads-forbindelse":::

1. <span data-ttu-id="fa347-122">Vælg **Næste** for at konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="fa347-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="fa347-123">Konfigurer connectoren</span><span class="sxs-lookup"><span data-stu-id="fa347-123">Configure the connector</span></span>

1. <span data-ttu-id="fa347-124">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="fa347-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="fa347-125">Gentag de samme trin for felterne **Fornavn** og **Efternavn**.</span><span class="sxs-lookup"><span data-stu-id="fa347-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="fa347-126">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="fa347-126">Select the segments you want to export.</span></span> <span data-ttu-id="fa347-127">Du kan eksportere op til 1000000 kundeprofiler i alt til Google Ads.</span><span class="sxs-lookup"><span data-stu-id="fa347-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="fa347-128">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="fa347-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="fa347-129">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="fa347-129">Export the data</span></span>

<span data-ttu-id="fa347-130">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="fa347-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="fa347-131">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fa347-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fa347-132">I Google Ads kan du nu finde dine segmenter under [Google Ads-målgrupper](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="fa347-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fa347-133">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="fa347-133">Known limitations</span></span>

- <span data-ttu-id="fa347-134">Op til 1000000 profiler pr. eksport til Google Ads.</span><span class="sxs-lookup"><span data-stu-id="fa347-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="fa347-135">Eksport til Google Ads er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="fa347-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="fa347-136">Eksport af segmenter med det samlede antal 1000000-profiler kan tage op til 5 minutter på grund af begrænsninger på udbydersiden.</span><span class="sxs-lookup"><span data-stu-id="fa347-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="fa347-137">Det kan tage op til 48 timer at foretage match ingen i Google Ads.</span><span class="sxs-lookup"><span data-stu-id="fa347-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fa347-138">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="fa347-138">Data privacy and compliance</span></span>

<span data-ttu-id="fa347-139">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Google Ads, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="fa347-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fa347-140">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Google Ads overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="fa347-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="fa347-141">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fa347-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fa347-142">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="fa347-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]