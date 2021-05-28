---
title: Eksportér Customer Insights-data til Facebook Ads Manager
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976035"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="37955-103">Eksport af segmentliste til Facebook Ads Manager (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="37955-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="37955-104">Eksportér segmenter af samlede kundeprofiler til Facebook Annonceadministrator for at oprette kampagner på Facebook og Instagram.</span><span class="sxs-lookup"><span data-stu-id="37955-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="37955-105">Forudsætninger for forbindelse</span><span class="sxs-lookup"><span data-stu-id="37955-105">Prerequisites for connection</span></span>

- <span data-ttu-id="37955-106">Du skal have en [**Facebook-reklamekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), der omfatter en [**Facebook-forretningskonto**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="37955-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="37955-107">Du skal være administrator for [**Facebook-reklamekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="37955-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="37955-108">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="37955-108">Known limitations</span></span>

- <span data-ttu-id="37955-109">Op til 10 millioner kundeprofiler pr. eksport til Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="37955-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="37955-110">Eksport til Facebook Ads Manager er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="37955-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="37955-111">Opret eller opdater kun brugerdefinerede målgrupper Facebook af typen *kundeliste*.</span><span class="sxs-lookup"><span data-stu-id="37955-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="37955-112">Eksport af segmenter med i alt 10 millioner profiler kan tage op til 90 minutter at fuldføre.</span><span class="sxs-lookup"><span data-stu-id="37955-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="37955-113">Konfigurer forbindelse til Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="37955-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="37955-114">Før brugere kan oprette en eksport, skal administrator konfigurere forbindelsen til tjenesten og tillade bidragydere at bruge forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="37955-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="37955-115">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="37955-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="37955-116">Vælg **Tilføj forbindelse**, og vælg **Facebook Ads Manager** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="37955-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="37955-117">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="37955-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="37955-118">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="37955-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="37955-119">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="37955-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="37955-120">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="37955-120">Choose who can use this connection.</span></span> <span data-ttu-id="37955-121">Hvis du ikke kan gøre noget, er standarden **Administratorer**.</span><span class="sxs-lookup"><span data-stu-id="37955-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="37955-122">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="37955-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="37955-123">Godkend med Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="37955-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="37955-124">Vælg **Fortsæt med Facebook** for at logge på din Facebook-annoncekonto.</span><span class="sxs-lookup"><span data-stu-id="37955-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="37955-125">Tillad **ads_management**-tilladelsen, efter at de er godkendt i Facebook.</span><span class="sxs-lookup"><span data-stu-id="37955-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="37955-126">Vælg den **Facebook-annoncekonto**, du vil arbejde med.</span><span class="sxs-lookup"><span data-stu-id="37955-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="37955-127">Vælg en **Eksisterende brugerdefineret målgruppe** på rullelisten, eller opret en **Ny brugerdefineret målgruppe**.</span><span class="sxs-lookup"><span data-stu-id="37955-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="37955-128">Du kan finde flere oplysninger under [**Målgrupper i Facebook Annonceadministrator**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="37955-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="37955-129">Du kan kun oprette eller opdatere brugerdefinerede målgrupper for Facebook med typen *kundeliste*, der har denne eksport.</span><span class="sxs-lookup"><span data-stu-id="37955-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="37955-130">I visse tilfælde kan du se brugerdefinerede målgrupper af forskellige typer på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="37955-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="37955-131">Hvis du vælger en anden type *kundeliste*, lykkes eksporten ikke.</span><span class="sxs-lookup"><span data-stu-id="37955-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="37955-132">Gennemse **Beskyttelse af personlige data og overholdelse af angivne standarder**, og vælg **Jeg accepterer**.</span><span class="sxs-lookup"><span data-stu-id="37955-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="37955-133">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="37955-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="37955-134">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="37955-134">Configure an export</span></span>

<span data-ttu-id="37955-135">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="37955-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="37955-136">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="37955-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="37955-137">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="37955-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="37955-138">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="37955-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="37955-139">Vælg i **Forbindelse til eksport** en forbindelse i sektionen **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="37955-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="37955-140">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="37955-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="37955-141">Brug feltet **Vælg din nøgleidentifikator** til at vælge **Mail**, **Navn og adresse** eller **Telefon**, du vil sende til Facebook Annonceadministrator.</span><span class="sxs-lookup"><span data-stu-id="37955-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="37955-142">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="37955-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="37955-143">Tilknyt de tilsvarende attributter fra det samlede kundeobjekt til den valgte nøgle-identifikator.</span><span class="sxs-lookup"><span data-stu-id="37955-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="37955-144">[TIP] De bedste chancer for et match sker, hvis du vælger **Mail** som nøgleidentifikator.</span><span class="sxs-lookup"><span data-stu-id="37955-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="37955-145">Tilføjelse af flere identifikatorer kan forbedre matchningen.</span><span class="sxs-lookup"><span data-stu-id="37955-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="37955-146">Vælg **Tilføj attribut** for at tilknytte flere attributter, der skal sendes til Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="37955-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="37955-147">Attributter fra Facebook Ads Manager tilknyttes følgende brugervenlige navne: **FN** = **Fornavn**, **LN** = **Efternavn**, **FI** = **Første initial**, **PHONE** = **Telefon**, **GEN** = **Køn**, **DOB** = **Fødselsdato**, **ST** = **Stat**, **CT** = **By**, **ZIP** = **Postnummer**, **COUNTRY** = **Land/område**</span><span class="sxs-lookup"><span data-stu-id="37955-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="37955-148">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="37955-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="37955-149">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="37955-149">Select **Save**.</span></span>

<span data-ttu-id="37955-150">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="37955-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="37955-151">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="37955-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="37955-152">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="37955-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="37955-153">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="37955-153">Data privacy and compliance</span></span>

<span data-ttu-id="37955-154">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Facebook Ads Manager, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="37955-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="37955-155">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Facebook-reklamer overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="37955-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="37955-156">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="37955-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="37955-157">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="37955-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
