---
title: Eksportér Customer Insights-data til Facebook Ads Manager
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Facebook Annonceadministrator.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269967"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="944f4-103">Connector til Facebook Annonceadministrator (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="944f4-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="944f4-104">Eksportér segmenter af samlede kundeprofiler til Facebook Annonceadministrator for at oprette kampagner på Facebook og Instagram.</span><span class="sxs-lookup"><span data-stu-id="944f4-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="944f4-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="944f4-105">Prerequisites</span></span>

- <span data-ttu-id="944f4-106">Du skal have en [**Facebook-reklamekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), der indeholder en [**Facebook-forretningskonto**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="944f4-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="944f4-107">Du skal være administrator for [**Facebook-reklamekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="944f4-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="944f4-108">Opret forbindelse til Facebook Annonceadministrator</span><span class="sxs-lookup"><span data-stu-id="944f4-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="944f4-109">Gå til **Adminstration** > **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="944f4-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="944f4-110">Vælg **Konfigurer** under **Facebook Annonceadministrator**.</span><span class="sxs-lookup"><span data-stu-id="944f4-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="944f4-111">Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="944f4-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="944f4-112">Vælg **Fortsæt med Facebook** for at logge på din Facebook-annoncekonto.</span><span class="sxs-lookup"><span data-stu-id="944f4-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="944f4-113">Tillad **ads_management**-tilladelsen, efter at de er godkendt i Facebook.</span><span class="sxs-lookup"><span data-stu-id="944f4-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="944f4-114">Vælg den **Facebook-annoncekonto**, du vil arbejde med.</span><span class="sxs-lookup"><span data-stu-id="944f4-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="944f4-115">Vælg en **Eksisterende brugerdefineret målgruppe** på rullelisten, eller opret en **Ny brugerdefineret målgruppe**.</span><span class="sxs-lookup"><span data-stu-id="944f4-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="944f4-116">Du kan finde flere oplysninger under [**Målgrupper i Facebook Annonceadministrator**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="944f4-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="944f4-117">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="944f4-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="944f4-118">Vælg **Næste** for at konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="944f4-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="944f4-119">Konfigurer connectoren</span><span class="sxs-lookup"><span data-stu-id="944f4-119">Configure the connector</span></span>

1. <span data-ttu-id="944f4-120">Brug feltet **Vælg din nøgleidentifikator** til at vælge **Mail**, **Navn og adresse** eller **Telefon**, du vil sende til Facebook Annonceadministrator.</span><span class="sxs-lookup"><span data-stu-id="944f4-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="944f4-121">Tilknyt de tilsvarende attributter fra det samlede kundeobjekt til den valgte nøgle-identifikator.</span><span class="sxs-lookup"><span data-stu-id="944f4-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="944f4-122">[TIP] De bedste chancer for et match sker, hvis du vælger **Mail** som nøgleidentifikator.</span><span class="sxs-lookup"><span data-stu-id="944f4-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="944f4-123">Tilføjelse af flere identifikatorer kan forbedre matchningen.</span><span class="sxs-lookup"><span data-stu-id="944f4-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="944f4-124">Vælg **Tilføj attribut** for at tilknytte flere attributter, der skal sendes til Facebook Annonceadministrator.</span><span class="sxs-lookup"><span data-stu-id="944f4-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="944f4-125">Attributter fra Facebook Annonceadministrator tilknyttes følgende brugervenlige navne: **FN** = **Fornavn**, **LN** = **Efternavn**, **FI** = **Første initial**, **PHONE** = **Telefon**, **GEN** = **Køn**, **DOB** = **Fødselsdato**, **ST** = **Stat**, **CT** = **By**, **ZIP** = **Postnummer**, **COUNTRY** = **Land/område**</span><span class="sxs-lookup"><span data-stu-id="944f4-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="944f4-126">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="944f4-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="944f4-127">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="944f4-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="944f4-128">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="944f4-128">Export the data</span></span>

<span data-ttu-id="944f4-129">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="944f4-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="944f4-130">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="944f4-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="944f4-131">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="944f4-131">Known limitations</span></span>

- <span data-ttu-id="944f4-132">Op til 10 millioner kundeprofiler pr. eksport til Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="944f4-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="944f4-133">Eksport til Facebook Ads Manager er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="944f4-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="944f4-134">Eksport af segmenter med i alt 10 millioner profiler kan tage op til 90 minutter at fuldføre</span><span class="sxs-lookup"><span data-stu-id="944f4-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="944f4-135">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="944f4-135">Data privacy and compliance</span></span>

<span data-ttu-id="944f4-136">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Facebook Ads Manager, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="944f4-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="944f4-137">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Facebook-reklamer overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="944f4-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="944f4-138">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="944f4-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="944f4-139">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="944f4-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]