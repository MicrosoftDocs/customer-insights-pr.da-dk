---
title: Eksportér Customer Insights-data til Facebook Ads Manager
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Facebook Annonceadministrator.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643676"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="a1aab-103">Connector til Facebook Annonceadministrator (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="a1aab-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="a1aab-104">Eksportér segmenter af samlede kundeprofiler til Facebook Annonceadministrator for at oprette kampagner på Facebook og Instagram.</span><span class="sxs-lookup"><span data-stu-id="a1aab-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a1aab-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="a1aab-105">Prerequisites</span></span>

- <span data-ttu-id="a1aab-106">Du skal have en [**Facebook-reklamekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), der indeholder en [**Facebook-forretningskonto**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="a1aab-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="a1aab-107">Du skal være administrator for [**Facebook-reklamekonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="a1aab-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="a1aab-108">Opret forbindelse til Facebook Annonceadministrator</span><span class="sxs-lookup"><span data-stu-id="a1aab-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="a1aab-109">Gå til **Adminstration** > **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="a1aab-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a1aab-110">Vælg **Konfigurer** under **Facebook Annonceadministrator**.</span><span class="sxs-lookup"><span data-stu-id="a1aab-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="a1aab-111">Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="a1aab-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a1aab-112">Vælg **Fortsæt med Facebook** for at logge på din Facebook-annoncekonto.</span><span class="sxs-lookup"><span data-stu-id="a1aab-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="a1aab-113">Tillad **ads_management**-tilladelsen, efter at de er godkendt i Facebook.</span><span class="sxs-lookup"><span data-stu-id="a1aab-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="a1aab-114">Vælg den **Facebook-annoncekonto**, du vil arbejde med.</span><span class="sxs-lookup"><span data-stu-id="a1aab-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="a1aab-115">Vælg en **Eksisterende brugerdefineret målgruppe** på rullelisten, eller opret en **Ny brugerdefineret målgruppe**.</span><span class="sxs-lookup"><span data-stu-id="a1aab-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="a1aab-116">Du kan finde flere oplysninger under [**Målgrupper i Facebook Annonceadministrator**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="a1aab-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="a1aab-117">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="a1aab-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a1aab-118">Vælg **Næste** for at konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="a1aab-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a1aab-119">Konfigurer connectoren</span><span class="sxs-lookup"><span data-stu-id="a1aab-119">Configure the connector</span></span>

1. <span data-ttu-id="a1aab-120">Brug feltet **Vælg din nøgleidentifikator** til at vælge **Mail**, **Navn og adresse** eller **Telefon**, du vil sende til Facebook Annonceadministrator.</span><span class="sxs-lookup"><span data-stu-id="a1aab-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="a1aab-121">Tilknyt de tilsvarende attributter fra det samlede kundeobjekt til den valgte nøgle-identifikator.</span><span class="sxs-lookup"><span data-stu-id="a1aab-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="a1aab-122">[TIP] De bedste chancer for et match sker, hvis du vælger **Mail** som nøgleidentifikator.</span><span class="sxs-lookup"><span data-stu-id="a1aab-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="a1aab-123">Tilføjelse af flere identifikatorer kan forbedre matchningen.</span><span class="sxs-lookup"><span data-stu-id="a1aab-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="a1aab-124">Vælg **Tilføj attribut** for at tilknytte flere attributter, der skal sendes til Facebook Annonceadministrator.</span><span class="sxs-lookup"><span data-stu-id="a1aab-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="a1aab-125">Attributter fra Facebook Annonceadministrator tilknyttes følgende brugervenlige navne: **FN** = **Fornavn**, **LN** = **Efternavn**, **FI** = **Første initial**, **PHONE** = **Telefon**, **GEN** = **Køn**, **DOB** = **Fødselsdato**, **ST** = **Stat**, **CT** = **By**, **ZIP** = **Postnummer**, **COUNTRY** = **Land/område**</span><span class="sxs-lookup"><span data-stu-id="a1aab-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="a1aab-126">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="a1aab-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="a1aab-127">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="a1aab-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a1aab-128">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="a1aab-128">Export the data</span></span>

<span data-ttu-id="a1aab-129">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a1aab-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a1aab-130">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a1aab-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a1aab-131">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="a1aab-131">Data privacy and compliance</span></span>

<span data-ttu-id="a1aab-132">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Facebook Ads Manager, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="a1aab-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a1aab-133">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Facebook-reklamer overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="a1aab-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a1aab-134">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a1aab-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a1aab-135">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="a1aab-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
