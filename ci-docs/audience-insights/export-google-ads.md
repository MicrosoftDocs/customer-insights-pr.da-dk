---
title: Eksportér Customer Insights-data til Google Ads
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759686"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="f86f4-103">Eksport af segmenter til Google Ads (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="f86f4-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="f86f4-104">Eksportér segmenter af samlede kundeprofiler til Google Ads-målgruppelisten, og brug dem til at annoncere på Google Search, Gmail og YouTube og Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="f86f4-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="f86f4-105">Forudsætninger for forbindelse</span><span class="sxs-lookup"><span data-stu-id="f86f4-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="f86f4-106">Du har en [Google Ads-konto](https://ads.google.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="f86f4-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f86f4-107">Du har et [godkendt Google Ads-udviklertoken](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="f86f4-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="f86f4-108">Du opfylder kravene i [politikken for kundeoverensstemmelse](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="f86f4-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="f86f4-109">Du opfylder kravene til [listestørrelser for re-marketing](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="f86f4-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="f86f4-110">Der findes eksisterende målgrupper i Google Ads og de tilsvarende id'er.</span><span class="sxs-lookup"><span data-stu-id="f86f4-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="f86f4-111">Du kan finde flere oplysninger i [Google ads-målgrupper](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="f86f4-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="f86f4-112">Du har [konfigureret segmenter](segments.md)</span><span class="sxs-lookup"><span data-stu-id="f86f4-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="f86f4-113">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse, fornavn og efternavn</span><span class="sxs-lookup"><span data-stu-id="f86f4-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f86f4-114">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="f86f4-114">Known limitations</span></span>

- <span data-ttu-id="f86f4-115">Op til 1000000 profiler pr. eksport til Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f86f4-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="f86f4-116">Eksport til Google Ads er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="f86f4-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="f86f4-117">Eksport af segmenter med det samlede antal 1000000-profiler kan tage op til 5 minutter på grund af begrænsninger på udbydersiden.</span><span class="sxs-lookup"><span data-stu-id="f86f4-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="f86f4-118">Det kan tage op til 48 timer at foretage match ingen i Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f86f4-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="f86f4-119">Konfigurer forbindelse til Google Ads</span><span class="sxs-lookup"><span data-stu-id="f86f4-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="f86f4-120">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="f86f4-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f86f4-121">Vælg **Tilføj forbindelse**, og vælg **Google Ads** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="f86f4-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="f86f4-122">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="f86f4-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f86f4-123">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="f86f4-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f86f4-124">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="f86f4-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f86f4-125">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="f86f4-125">Choose who can use this connection.</span></span> <span data-ttu-id="f86f4-126">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="f86f4-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f86f4-127">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f86f4-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f86f4-128">Angiv din **[Google Ads-kunde-id](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="f86f4-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="f86f4-129">Angiv din **[Google Ads-godkendte udvikler-token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="f86f4-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="f86f4-130">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="f86f4-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f86f4-131">Vælg **Godkendelse med Google Ads**, og angiv dine Google Ads-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="f86f4-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="f86f4-132">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="f86f4-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f86f4-133">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="f86f4-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="f86f4-134">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="f86f4-134">Configure an export</span></span>

<span data-ttu-id="f86f4-135">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="f86f4-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f86f4-136">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f86f4-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f86f4-137">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="f86f4-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f86f4-138">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="f86f4-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f86f4-139">Vælg en forbindelse i sektionen Google Ads i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="f86f4-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="f86f4-140">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="f86f4-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f86f4-141">Angiv dit **[Google Ads-målgruppe-id](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**, og vælg **Opret forbindelse** for at initialisere forbindelsen til Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f86f4-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="f86f4-142">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="f86f4-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f86f4-143">Gentag de samme trin for felterne **Fornavn** og **Efternavn**.</span><span class="sxs-lookup"><span data-stu-id="f86f4-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="f86f4-144">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="f86f4-144">Select the segments you want to export.</span></span> <span data-ttu-id="f86f4-145">Du kan eksportere op til 1000000 kundeprofiler i alt til Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f86f4-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="f86f4-146">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="f86f4-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f86f4-147">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f86f4-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f86f4-148">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f86f4-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f86f4-149">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="f86f4-149">Data privacy and compliance</span></span>

<span data-ttu-id="f86f4-150">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Google Ads, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="f86f4-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f86f4-151">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Google Ads overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="f86f4-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f86f4-152">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f86f4-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f86f4-153">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="f86f4-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
