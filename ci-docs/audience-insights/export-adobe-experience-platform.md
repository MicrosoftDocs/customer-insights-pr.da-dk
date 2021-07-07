---
title: Eksportere Customer Insights-data til Adobe Experience Platform
description: Få mere at vide om, hvordan publikum indsigtssegmenter i Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305517"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="1ad9a-103">Bruge Customer Insights-segmenter i Adobe Experience Platform (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="1ad9a-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="1ad9a-104">Som bruger af publikum indblik i Dynamics 365 Customer Insights har du muligvis oprettet segmenter for at gøre marketingkampagnerne mere effektive ved at målrette relevante målgrupper.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="1ad9a-105">Hvis du vil bruge et segment målgruppeindsigt i Adobe Experience Platform og programmer som Adobe Campaign Standard, skal du følge et par trin, der beskrives i denne artikel.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Procesdiagram over de trin, der beskrives i denne artikel.":::

## <a name="prerequisites"></a><span data-ttu-id="1ad9a-107">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="1ad9a-107">Prerequisites</span></span>

-   <span data-ttu-id="1ad9a-108">Dynamics 365 Customer Insights-licens</span><span class="sxs-lookup"><span data-stu-id="1ad9a-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="1ad9a-109">Adobe Experience Platform-licens</span><span class="sxs-lookup"><span data-stu-id="1ad9a-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="1ad9a-110">Adobe Campaign Standard-licens</span><span class="sxs-lookup"><span data-stu-id="1ad9a-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="1ad9a-111">Azure Blob Storage-konto</span><span class="sxs-lookup"><span data-stu-id="1ad9a-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="1ad9a-112">Kampagneoversigt</span><span class="sxs-lookup"><span data-stu-id="1ad9a-112">Campaign Overview</span></span>

<span data-ttu-id="1ad9a-113">For bedre at kunne forstå, hvordan du kan bruge segmenter målgruppeindsigt i Adobe Experience Platform, kan vi se på en fiktiv eksempelkampagne.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="1ad9a-114">Lad os antage, at din virksomhed tilbyder en månedlig, abonnementsbaseret service til kunderne i USA.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="1ad9a-115">Du vil identificere kunder, hvis abonnementer forfalder til fornyelse inden for de næste otte dage, men som endnu ikke har fornyet deres abonnement.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="1ad9a-116">Hvis du vil bevare disse kunder, skal du sende dem et kampagnetilbud via mail ved hjælp af Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="1ad9a-117">I dette eksempel vil vi køre kundemailkampagnen én gang.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="1ad9a-118">Denne artikel dækker ikke kørsel af kampagnen mere end én gang.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="1ad9a-119">Identificere din målgruppe</span><span class="sxs-lookup"><span data-stu-id="1ad9a-119">Identify your target audience</span></span>

<span data-ttu-id="1ad9a-120">I dette scenario antages det, at mailadresserne på kunderne er tilgængelige i målgruppeindsigt, og deres kampagnepræferencer er blevet analyseret for at identificere medlemmer af dette segment.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="1ad9a-121">Det [segment, du definerede i målgruppeindsigt](segments.md), kaldes **ChurnProneCustomers**, og du planlægger at sende disse kunder mailkampagnen.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skærmbillede af segmentsiden med segmentet ChurnProneCustomers oprettet.":::

<span data-ttu-id="1ad9a-123">Den mail med tilbud, du vil sende, indeholder kundens fornavn, efternavn og slutdatoen for abonnementet.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="1ad9a-124">Den giver kunderne den rabat, de får, hvis de fornyer deres abonnement, inden det udløber.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="1ad9a-125">Eksportere din målgruppe</span><span class="sxs-lookup"><span data-stu-id="1ad9a-125">Export your target audience</span></span>

<span data-ttu-id="1ad9a-126">Når målgruppen er identificeret, kan vi konfigurere eksporten fra målgruppeindsigt til en Azure Blob Storage-konto.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="1ad9a-127">Konfiguration af en forbindelse</span><span class="sxs-lookup"><span data-stu-id="1ad9a-127">Configure a connection</span></span>

1. <span data-ttu-id="1ad9a-128">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1ad9a-129">Vælg **Tilføj forbindelse**, og vælg **Azure Blob Storage**, eller vælg **Konfigurer** i feltet **Azure Blob Storage**.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurationsfelt til Azure Blob Storage."::: 

1. <span data-ttu-id="1ad9a-131">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1ad9a-132">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1ad9a-133">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1ad9a-134">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-134">Choose who can use this connection.</span></span> <span data-ttu-id="1ad9a-135">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1ad9a-136">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1ad9a-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1ad9a-137">Angiv **Firmanavn**, **Firmanøgle** og **Beholder** for den Blob Storage-konto, du vil eksportere segmentet til.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skærmbillede af lagerkontoens konfiguration. "::: 
   
    - <span data-ttu-id="1ad9a-139">Du kan få mere at vide om, hvordan du finder Blob Storage-kontonavnet og kontonøglen, under [Administration af indstillinger for lagerkonti i Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="1ad9a-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="1ad9a-140">Du kan få mere at vide om, hvordan du opretter en objektbeholder, i [Oprette en objektbeholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="1ad9a-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="1ad9a-141">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="1ad9a-142">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="1ad9a-142">Configure an export</span></span>

<span data-ttu-id="1ad9a-143">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1ad9a-144">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1ad9a-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1ad9a-145">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1ad9a-146">Hvis du vil oprette en ny eksport, skal du vælge **Tilføj eksport**.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="1ad9a-147">Vælg en forbindelse i sektionen Azure Blob Storage i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="1ad9a-148">Hvis du ikke kan se dette sektionsnavn, er der ingen tilgængelige forbindelser af denne type.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="1ad9a-149">Vælg det segment, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="1ad9a-150">I dette eksempel er det **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skærmbillede af brugergrænsefladen til valg af segment, hvor segmentet ChurnProneCustomers er valgt.":::

1. <span data-ttu-id="1ad9a-152">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-152">Select **Save**.</span></span>

<span data-ttu-id="1ad9a-153">Når du har gemt eksportdestinationen, finder du den under **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="1ad9a-154">Du kan nu [eksportere segmentet efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1ad9a-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="1ad9a-155">Eksporten vil også køre med alle [planlagte opdateringer](system.md).</span><span class="sxs-lookup"><span data-stu-id="1ad9a-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1ad9a-156">Sørg for, at antallet af poster i det eksporterede segment ligger inden for den tilladte grænse for din Adobe Campaign Standard-licens.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="1ad9a-157">Eksporterede data lagres i den Azure Blob Storage-objektbeholder, du har konfigureret ovenfor.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="1ad9a-158">Følgende mappesti oprettes automatisk i objektbeholderen:</span><span class="sxs-lookup"><span data-stu-id="1ad9a-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="1ad9a-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="1ad9a-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="1ad9a-160">Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="1ad9a-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="1ad9a-161">Filen *model.json* for de eksporterede objekter findes på *%ExportDestinationName%*-niveau.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="1ad9a-162">Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="1ad9a-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="1ad9a-163">Definere XDM (Experience Data Model) i Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="1ad9a-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="1ad9a-164">Før de eksporterede data fra målgruppeindsigt kan bruges i Adobe Experience Platform, skal vi definere Experience Data Model-skemaet og [konfigurere dataene til kundeprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="1ad9a-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="1ad9a-165">Få mere at vide om, hvad [XDM er](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html), og forstå det [grundlæggende i skemakompositionen](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="1ad9a-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="1ad9a-166">Importere data til Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="1ad9a-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="1ad9a-167">Nu, hvor alt er på plads, skal vi importere de forberedte målgruppedata fra målgruppeindsigt i Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="1ad9a-168">Du skal først [oprette en Azure Blob Storage-kildeforbindelse](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="1ad9a-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="1ad9a-169">Når du har defineret kildeforbindelsen, skal du [konfigurere et dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for en batchforbindelse til skylageret for at importere segmentoutputtet fra målgruppeindsigt i Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="1ad9a-170">Oprette en målgruppe i Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1ad9a-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="1ad9a-171">Hvis du vil sende e-mailen til denne kampagne, bruger vi Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="1ad9a-172">Når dataene er importeret til Adobe Experience Platform, skal vi [oprette en målgruppe](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) i Adobe Campaign Standard ved hjælp af dataene på Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="1ad9a-173">Lær at [bruge segmentgeneratoren](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) i Adobe Campaign Standard til at definere en målgruppe baseret på dataene i Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="1ad9a-174">Oprette og sende mailen ved hjælp af Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="1ad9a-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="1ad9a-175">Opret mailindholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) derefter mailen.</span><span class="sxs-lookup"><span data-stu-id="1ad9a-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på mail med tilbud om fornyelse fra Adobe Campaign Standard.":::
