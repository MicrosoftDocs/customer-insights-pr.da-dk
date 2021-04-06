---
title: Eksportere Customer Insights-data til Adobe Campaign Standard
description: Få at vide, hvordan du kan bruge målgruppeindsigtssegmenter i Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596308"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="f8cd6-103">Bruge Customer Insights-segmenter i Adobe Campaign Standard (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="f8cd6-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="f8cd6-104">Som bruger af målgruppeindsigt for Dynamics 365 Customer Insights har du muligvis oprettet segmenter for at gøre marketingkampagnerne mere effektive ved at målrette relevante målgrupper.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="f8cd6-105">Hvis du vil bruge et segment målgruppeindsigt i Adobe Experience Platform og programmer som Adobe Campaign Standard, skal du følge et par trin, der beskrives i denne artikel.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Procesdiagram over de trin, der beskrives i denne artikel.":::

## <a name="prerequisites"></a><span data-ttu-id="f8cd6-107">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="f8cd6-107">Prerequisites</span></span>

-   <span data-ttu-id="f8cd6-108">Dynamics 365 Customer Insights-licens</span><span class="sxs-lookup"><span data-stu-id="f8cd6-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="f8cd6-109">Adobe Campaign Standard-licens</span><span class="sxs-lookup"><span data-stu-id="f8cd6-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="f8cd6-110">Azure Blob Storage-konto</span><span class="sxs-lookup"><span data-stu-id="f8cd6-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="f8cd6-111">Kampagneoversigt</span><span class="sxs-lookup"><span data-stu-id="f8cd6-111">Campaign Overview</span></span>

<span data-ttu-id="f8cd6-112">For bedre at kunne forstå, hvordan du kan bruge segmenter målgruppeindsigt i Adobe Experience Platform, kan vi se på en fiktiv eksempelkampagne.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="f8cd6-113">Lad os antage, at din virksomhed tilbyder en månedlig, abonnementsbaseret service til kunderne i USA.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="f8cd6-114">Du vil identificere kunder, hvis abonnementer forfalder til fornyelse inden for de næste otte dage, men som endnu ikke har fornyet deres abonnement.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="f8cd6-115">Hvis du vil bevare disse kunder, skal du sende dem et kampagnetilbud via mail ved hjælp af Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="f8cd6-116">I dette eksempel vil vi køre kundemailkampagnen én gang.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="f8cd6-117">Denne artikel dækker ikke kørsel af kampagnen mere end én gang.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="f8cd6-118">Men målgruppeindsigt og Adobe Campaign Standard kan dog konfigureres til at fungere i et tilbagevendende kampagnescenarie.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="f8cd6-119">Identificere din målgruppe</span><span class="sxs-lookup"><span data-stu-id="f8cd6-119">Identify your target audience</span></span>

<span data-ttu-id="f8cd6-120">I dette scenario antages det, at mailadresserne på kunderne er tilgængelige i målgruppeindsigt, og deres kampagnepræferencer er blevet analyseret for at identificere medlemmer af dette segment.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="f8cd6-121">Det [segment, du definerede i målgruppeindsigt](segments.md), kaldes **ChurnProneCustomers**, og du planlægger at sende disse kunder mailkampagnen.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skærmbillede af segmentsiden med segmentet ChurnProneCustomers oprettet.":::

<span data-ttu-id="f8cd6-123">Den mail med tilbud, du vil sende, indeholder kundens fornavn, efternavn og slutdatoen for abonnementet.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="f8cd6-124">Den giver kunderne den rabat, de får, hvis de fornyer deres abonnement, inden det udløber.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="f8cd6-125">Eksportere din målgruppe</span><span class="sxs-lookup"><span data-stu-id="f8cd6-125">Export your target audience</span></span>

<span data-ttu-id="f8cd6-126">Når målgruppen er identificeret, kan vi konfigurere eksporten fra målgruppeindsigt til en Azure Blob Storage-konto.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="f8cd6-127">Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f8cd6-128">Vælg **Konfigurer** i feltet **Adobe Campaign**.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurationsfelt til Adobe Campaign Standard.":::

1. <span data-ttu-id="f8cd6-130">Angiv et **vist navn** til denne nye eksportdestination, og angiv derefter **Firmanavn**, **Kontonøgle** og **Objektbeholder** for den Azure Blob Storage-konto, du vil eksportere segmentet til.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skærmbillede af lagerkontoens konfiguration. "::: 

   - <span data-ttu-id="f8cd6-132">Du kan få mere at vide om, hvordan du finder navnet på og kontonøglen til Azure Blob Storage-kontoen, under [Administrere indstillinger for lagerkonto i Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="f8cd6-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="f8cd6-133">Du kan få mere at vide om, hvordan du opretter en objektbeholder, i [Oprette en objektbeholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="f8cd6-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="f8cd6-134">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-134">Select **Next**.</span></span>

1. <span data-ttu-id="f8cd6-135">Vælg det segment, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="f8cd6-136">I dette eksempel er det **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skærmbillede af brugergrænsefladen til valg af segment, hvor segmentet ChurnProneCustomers er valgt.":::

1. <span data-ttu-id="f8cd6-138">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-138">Select **Next**.</span></span>

1. <span data-ttu-id="f8cd6-139">Nu skal du knytte **Kilde**-felterne fra kildekampagneindsigtssegmentet til **Mål**-feltnavnene i Adobe Campaign Standard-profilskemaet.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Felttilknytning for Adobe Campaign Standard-connector.":::

   <span data-ttu-id="f8cd6-141">Vælg **Tilføj attribut**, hvis du vil tilføje flere attributter.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="f8cd6-142">Målnavnet kan være et andet end kildefeltnavnet, så du stadig kan knytte segmentoutput fra målgruppeindsigt til Adobe Campaign Standard, hvis felterne ikke har det samme navn i de to systemer.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f8cd6-143">Mailadressen bruges som identitetsfelt, men du kan bruge et hvilket som helst andet id fra din målgruppeindsigts kundeprofil til at knytte data til Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="f8cd6-144">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-144">Select **Save**.</span></span>

<span data-ttu-id="f8cd6-145">Når du har gemt eksportdestinationen, finder du den under **Administrator** > **Eksporter** > **Mine eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Skærmbillede med en liste over eksporter og eksempelsegment fremhævet.":::

<span data-ttu-id="f8cd6-147">Du kan nu [eksportere segmentet efter behov](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f8cd6-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="f8cd6-148">Eksporten vil også køre med alle [planlagte opdateringer](system.md).</span><span class="sxs-lookup"><span data-stu-id="f8cd6-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f8cd6-149">Sørg for, at antallet af poster i det eksporterede segment ligger inden for den tilladte grænse for din Adobe Campaign Standard-licens.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="f8cd6-150">Eksporterede data lagres i den Azure Blob Storage-objektbeholder, du har konfigureret ovenfor.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="f8cd6-151">Følgende mappesti oprettes automatisk i objektbeholderen:</span><span class="sxs-lookup"><span data-stu-id="f8cd6-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="f8cd6-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="f8cd6-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="f8cd6-153">Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="f8cd6-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="f8cd6-154">Konfigurere Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="f8cd6-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="f8cd6-155">Når et segment fra målgruppeindsigt eksporteres, indeholder det de kolonner, du har valgt, mens du definerer eksportdestinationen i forrige trin.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="f8cd6-156">Disse data kan bruges til at [oprette profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="f8cd6-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="f8cd6-157">Hvis du vil bruge segmentet i Adobe Campaign Standard, skal du udvide profilskemaet i Adobe Campaign Standard, så det inkluderer yderligere to felter.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="f8cd6-158">Lær at [udvide profilressourcen](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) med nye felter i Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="f8cd6-159">I eksemplet er disse felter *Segmentnavn og segmentdato (valgfrit).*</span><span class="sxs-lookup"><span data-stu-id="f8cd6-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="f8cd6-160">Vi bruger disse felter til at identificere profilerne i Adobe Campaign Standard, som vi vil målrette mod denne kampagne.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="f8cd6-161">Hvis der ikke er andre poster i Adobe Campaign Standard, ud over det, du vil importere, kan du springe dette trin over.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="f8cd6-162">Importere data til Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="f8cd6-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="f8cd6-163">Nu, hvor alt er på plads, skal vi importere de forberedte målgruppedata fra målgruppeindsigt i Adobe Campaign Standard for at oprette profiler.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="f8cd6-164">Lær at [importere profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) ved hjælp af en arbejdsproces.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="f8cd6-165">Importarbejdsprocessen i billedet nedenfor er konfigureret til at køre hver 8. time og søger efter eksporterede segmenter til målgruppeindsigt (.csv-fil i Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="f8cd6-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="f8cd6-166">I arbejdsprocessen udtrækkes indholdet af .csv-filen i en angivet kolonnerækkefølge.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="f8cd6-167">Arbejdsprocessen er opbygget til at udføre grundlæggende fejlbehandling og sikre, at hver post har en mailadresse, inden dataene i Adobe Campaign Standard anvendes.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="f8cd6-168">I arbejdsprocessen udtrækkes også segmentnavnet fra filnavnet, inden det overgives til ACS-profildata.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Skærmbillede af en importarbejdsproces i brugergrænsefladen i Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="f8cd6-170">Hente målgruppe i Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="f8cd6-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="f8cd6-171">Når dataene er importeret til Adobe Campaign Standard, kan du [oprette en arbejdsproces](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) og [forespørge](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) på kunderne baseret på *Segmentnavn* og *Segmentdato* for at vælge de profiler, der blev identificeret for eksempelkampagnen.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="f8cd6-172">Oprette og sende mailen ved hjælp af Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="f8cd6-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="f8cd6-173">Opret mailindholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) derefter mailen.</span><span class="sxs-lookup"><span data-stu-id="f8cd6-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på mail med tilbud om fornyelse fra Adobe Campaign Standard.":::