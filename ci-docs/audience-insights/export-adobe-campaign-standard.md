---
title: Eksportere Customer Insights-data til Adobe Campaign Standard
description: Få at vide, hvordan du kan bruge målgruppeindsigtssegmenter i Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305379"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="5013c-103">Bruge Customer Insights-segmenter i Adobe Campaign Standard (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="5013c-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="5013c-104">Som bruger af publikum indblik i Dynamics 365 Customer Insights har du muligvis oprettet segmenter for at gøre marketingkampagnerne mere effektive ved at målrette relevante målgrupper.</span><span class="sxs-lookup"><span data-stu-id="5013c-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="5013c-105">Hvis du vil bruge et segment målgruppeindsigt i Adobe Experience Platform og programmer som Adobe Campaign Standard, skal du følge et par trin, der beskrives i denne artikel.</span><span class="sxs-lookup"><span data-stu-id="5013c-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Procesdiagram over de trin, der beskrives i denne artikel.":::

## <a name="prerequisites"></a><span data-ttu-id="5013c-107">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="5013c-107">Prerequisites</span></span>

-   <span data-ttu-id="5013c-108">Dynamics 365 Customer Insights-licens</span><span class="sxs-lookup"><span data-stu-id="5013c-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="5013c-109">Adobe Campaign Standard-licens</span><span class="sxs-lookup"><span data-stu-id="5013c-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="5013c-110">Azure Blob Storage-konto</span><span class="sxs-lookup"><span data-stu-id="5013c-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="5013c-111">Kampagneoversigt</span><span class="sxs-lookup"><span data-stu-id="5013c-111">Campaign overview</span></span>

<span data-ttu-id="5013c-112">For bedre at kunne forstå, hvordan du kan bruge segmenter målgruppeindsigt i Adobe Experience Platform, kan vi se på en fiktiv eksempelkampagne.</span><span class="sxs-lookup"><span data-stu-id="5013c-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="5013c-113">Lad os antage, at din virksomhed tilbyder en månedlig, abonnementsbaseret service til kunderne i USA.</span><span class="sxs-lookup"><span data-stu-id="5013c-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="5013c-114">Du vil identificere kunder, hvis abonnementer forfalder til fornyelse inden for de næste otte dage, men som endnu ikke har fornyet deres abonnement.</span><span class="sxs-lookup"><span data-stu-id="5013c-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="5013c-115">Hvis du vil bevare disse kunder, skal du sende dem et kampagnetilbud via mail ved hjælp af Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="5013c-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="5013c-116">I dette eksempel vil vi køre kundemailkampagnen én gang.</span><span class="sxs-lookup"><span data-stu-id="5013c-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="5013c-117">Denne artikel dækker ikke kørsel af kampagnen mere end én gang.</span><span class="sxs-lookup"><span data-stu-id="5013c-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="5013c-118">Men målgruppeindsigt og Adobe Campaign Standard kan dog konfigureres til at fungere i et tilbagevendende kampagnescenarie.</span><span class="sxs-lookup"><span data-stu-id="5013c-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="5013c-119">Identificere din målgruppe</span><span class="sxs-lookup"><span data-stu-id="5013c-119">Identify your target audience</span></span>

<span data-ttu-id="5013c-120">I dette scenario antages det, at mailadresserne på kunderne er tilgængelige i målgruppeindsigt, og deres kampagnepræferencer er blevet analyseret for at identificere medlemmer af dette segment.</span><span class="sxs-lookup"><span data-stu-id="5013c-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="5013c-121">Det [segment, du definerede i målgruppeindsigt](segments.md), kaldes **ChurnProneCustomers**, og du planlægger at sende disse kunder mailkampagnen.</span><span class="sxs-lookup"><span data-stu-id="5013c-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skærmbillede af segmentsiden med segmentet ChurnProneCustomers oprettet.":::

<span data-ttu-id="5013c-123">Den mail med tilbud, du vil sende, indeholder kundens fornavn, efternavn og slutdatoen for abonnementet.</span><span class="sxs-lookup"><span data-stu-id="5013c-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="5013c-124">Den giver kunderne den rabat, de får, hvis de fornyer deres abonnement, inden det udløber.</span><span class="sxs-lookup"><span data-stu-id="5013c-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="5013c-125">Eksportere din målgruppe</span><span class="sxs-lookup"><span data-stu-id="5013c-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="5013c-126">Konfiguration af en forbindelse</span><span class="sxs-lookup"><span data-stu-id="5013c-126">Configure a connection</span></span>

<span data-ttu-id="5013c-127">Når målgruppen er identificeret, kan vi konfigurere eksporten fra målgruppeindsigt til en Azure Blob Storage-konto.</span><span class="sxs-lookup"><span data-stu-id="5013c-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="5013c-128">I målgruppeindsigt skal du gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="5013c-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5013c-129">Vælg **Tilføj forbindelse**, og vælg **Adobe-kampagne** for at konfigurere forbindelsen, eller vælg **Konfigurer** i feltet **Adobe-kampagne**.</span><span class="sxs-lookup"><span data-stu-id="5013c-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurationsfelt til Adobe Campaign Standard.":::

1. <span data-ttu-id="5013c-131">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="5013c-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5013c-132">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="5013c-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5013c-133">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="5013c-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5013c-134">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="5013c-134">Choose who can use this connection.</span></span> <span data-ttu-id="5013c-135">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="5013c-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5013c-136">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5013c-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5013c-137">Angiv **Firmanavn**, **Firmanøgle** og **Beholder** for den Azure Blob-lagerkonto, du vil eksportere segmentet til.</span><span class="sxs-lookup"><span data-stu-id="5013c-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skærmbillede af lagerkontoens konfiguration. "::: 

   - <span data-ttu-id="5013c-139">Du kan få mere at vide om, hvordan du finder navnet på og kontonøglen til Azure Blob Storage-kontoen, under [Administrere indstillinger for lagerkonto i Azure-portalen](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="5013c-139">To learn more about how to find the Azure Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="5013c-140">Du kan få mere at vide om, hvordan du opretter en objektbeholder, i [Oprette en objektbeholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="5013c-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="5013c-141">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="5013c-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="5013c-142">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="5013c-142">Configure an export</span></span>

<span data-ttu-id="5013c-143">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="5013c-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5013c-144">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5013c-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5013c-145">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="5013c-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5013c-146">Hvis du vil oprette en ny eksport, skal du vælge **Tilføj eksport**.</span><span class="sxs-lookup"><span data-stu-id="5013c-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="5013c-147">Vælg en forbindelse i sektionen Adobe Campaign i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="5013c-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="5013c-148">Hvis du ikke kan se dette sektionsnavn, er der ingen tilgængelige forbindelser af denne type.</span><span class="sxs-lookup"><span data-stu-id="5013c-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="5013c-149">Vælg det segment, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="5013c-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="5013c-150">I dette eksempel er det **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="5013c-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skærmbillede af brugergrænsefladen til valg af segment, hvor segmentet ChurnProneCustomers er valgt.":::

1. <span data-ttu-id="5013c-152">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="5013c-152">Select **Next**.</span></span>

1. <span data-ttu-id="5013c-153">Nu skal du knytte **Kilde**-felterne fra kildekampagneindsigtssegmentet til **Mål**-feltnavnene i Adobe Campaign Standard-profilskemaet.</span><span class="sxs-lookup"><span data-stu-id="5013c-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Felttilknytning for Adobe Campaign Standard-connector.":::

   <span data-ttu-id="5013c-155">Vælg **Tilføj attribut**, hvis du vil tilføje flere attributter.</span><span class="sxs-lookup"><span data-stu-id="5013c-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="5013c-156">Målnavnet kan være et andet end kildefeltnavnet, så du stadig kan knytte segmentoutput fra målgruppeindsigt til Adobe Campaign Standard, hvis felterne ikke har det samme navn i de to systemer.</span><span class="sxs-lookup"><span data-stu-id="5013c-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5013c-157">Mailadressen bruges som identitetsfelt, men du kan bruge et hvilket som helst andet id fra din målgruppeindsigts kundeprofil til at knytte data til Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="5013c-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="5013c-158">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="5013c-158">Select **Save**.</span></span>

<span data-ttu-id="5013c-159">Når du har gemt eksportdestinationen, finder du den under **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="5013c-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="5013c-160">Du kan nu [eksportere segmentet efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5013c-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="5013c-161">Eksporten vil også køre med alle [planlagte opdateringer](system.md).</span><span class="sxs-lookup"><span data-stu-id="5013c-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5013c-162">Sørg for, at antallet af poster i det eksporterede segment ligger inden for den tilladte grænse for din Adobe Campaign Standard-licens.</span><span class="sxs-lookup"><span data-stu-id="5013c-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="5013c-163">Eksporterede data lagres i den Azure Blob Storage-objektbeholder, du har konfigureret ovenfor.</span><span class="sxs-lookup"><span data-stu-id="5013c-163">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="5013c-164">Følgende mappesti oprettes automatisk i objektbeholderen:</span><span class="sxs-lookup"><span data-stu-id="5013c-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="5013c-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="5013c-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="5013c-166">Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="5013c-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="5013c-167">Konfigurere Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5013c-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="5013c-168">Når et segment fra målgruppeindsigt eksporteres, indeholder det de kolonner, du har valgt, mens du definerer eksportdestinationen i forrige trin.</span><span class="sxs-lookup"><span data-stu-id="5013c-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="5013c-169">Disse data kan bruges til at [oprette profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="5013c-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="5013c-170">Hvis du vil bruge segmentet i Adobe Campaign Standard, skal du udvide profilskemaet i Adobe Campaign Standard, så det inkluderer yderligere to felter.</span><span class="sxs-lookup"><span data-stu-id="5013c-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="5013c-171">Lær at [udvide profilressourcen](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) med nye felter i Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="5013c-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="5013c-172">I eksemplet er disse felter *Segmentnavn og segmentdato (valgfrit)*.</span><span class="sxs-lookup"><span data-stu-id="5013c-172">In our example, these fields are *Segment Name and Segment Date (optional)*.</span></span>

<span data-ttu-id="5013c-173">Vi bruger disse felter til at identificere profilerne i Adobe Campaign Standard, som vi vil målrette mod denne kampagne.</span><span class="sxs-lookup"><span data-stu-id="5013c-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="5013c-174">Hvis der ikke er andre poster i Adobe Campaign Standard, ud over det, du vil importere, kan du springe dette trin over.</span><span class="sxs-lookup"><span data-stu-id="5013c-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="5013c-175">Importere data til Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5013c-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="5013c-176">Nu, hvor alt er på plads, skal vi importere de forberedte målgruppedata fra målgruppeindsigt i Adobe Campaign Standard for at oprette profiler.</span><span class="sxs-lookup"><span data-stu-id="5013c-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="5013c-177">Lær at [importere profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) ved hjælp af en arbejdsproces.</span><span class="sxs-lookup"><span data-stu-id="5013c-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="5013c-178">Importarbejdsprocessen i billedet nedenfor er konfigureret til at køre hver ottende time og søge efter eksporterede publikum insights-segmenter (.csv-fil i Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="5013c-178">The import workflow in the image below has been configured to run every eight hours and look for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="5013c-179">I arbejdsprocessen udtrækkes indholdet af .csv-filen i en angivet kolonnerækkefølge.</span><span class="sxs-lookup"><span data-stu-id="5013c-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="5013c-180">Arbejdsprocessen er opbygget til at udføre grundlæggende fejlbehandling og sikre, at hver post har en mailadresse, inden dataene i Adobe Campaign Standard anvendes.</span><span class="sxs-lookup"><span data-stu-id="5013c-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="5013c-181">I arbejdsprocessen udtrækkes også segmentnavnet fra filnavnet, inden det overgives til Adobe Campaign Standard-profildata.</span><span class="sxs-lookup"><span data-stu-id="5013c-181">The workflow also extracts the segment name from the filename before upserting into Adobe Campaign Standard profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Skærmbillede af en importarbejdsproces i brugergrænsefladen i Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="5013c-183">Hente målgruppe i Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5013c-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="5013c-184">Når dataene er importeret til Adobe Campaign Standard, kan du [oprette en arbejdsproces](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) og [forespørge](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) på kunderne baseret på *Segmentnavn* og *Segmentdato* for at vælge de profiler, der blev identificeret for eksempelkampagnen.</span><span class="sxs-lookup"><span data-stu-id="5013c-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="5013c-185">Oprette og sende mailen ved hjælp af Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="5013c-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="5013c-186">Opret mailindholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) derefter mailen.</span><span class="sxs-lookup"><span data-stu-id="5013c-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på mail med tilbud om fornyelse fra Adobe Campaign Standard.":::
