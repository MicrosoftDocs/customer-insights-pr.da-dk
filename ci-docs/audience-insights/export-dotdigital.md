---
title: Eksportér Customer Insights-data til DotDigital
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598010"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="2e082-103">Connector til DotDigital (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="2e082-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="2e082-104">Eksportér segmenter af Unified-kundeprofiler til DotDigital-adressekartotekerne, og brug dem til kampagner, e-mailmarketing og til at oprette kundesegmenter med DotDigital.</span><span class="sxs-lookup"><span data-stu-id="2e082-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="2e082-105">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="2e082-105">Prerequisites</span></span>

-   <span data-ttu-id="2e082-106">Du har en [DotDigital-konto](https://dotdigital.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="2e082-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2e082-107">Der findes eksisterende adressekartoteker i DotDigital og de tilsvarende id'er.</span><span class="sxs-lookup"><span data-stu-id="2e082-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="2e082-108">Id kan findes i URL-adressen, når du vælger og åbner et adressekartotek.</span><span class="sxs-lookup"><span data-stu-id="2e082-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="2e082-109">Du kan finde flere oplysninger i [DotDigital-adressekartoteker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="2e082-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="2e082-110">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="2e082-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2e082-111">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="2e082-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="2e082-112">Opret forbindelse til DotDigital</span><span class="sxs-lookup"><span data-stu-id="2e082-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="2e082-113">Gå til **Adminstration** > **Eksportdestinationer**.</span><span class="sxs-lookup"><span data-stu-id="2e082-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2e082-114">Under **DotDigital** skal du vælge **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="2e082-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="2e082-115">Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="2e082-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfigurationsrude til DotDigital-eksport.":::

1. <span data-ttu-id="2e082-117">Angiv **DotDigital-brugernavn og adgangskode**.</span><span class="sxs-lookup"><span data-stu-id="2e082-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="2e082-118">Angiv dit **[DotDigital-adressekartoteks-id](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="2e082-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="2e082-119">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="2e082-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2e082-120">Vælg **Opret forbindelse** for at initialisere forbindelsen til DotDigital.</span><span class="sxs-lookup"><span data-stu-id="2e082-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="2e082-121">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="2e082-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2e082-122">Vælg **Næste** for at konfigurere eksporten.</span><span class="sxs-lookup"><span data-stu-id="2e082-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="2e082-123">Konfigurer connectoren</span><span class="sxs-lookup"><span data-stu-id="2e082-123">Configure the connector</span></span>

1. <span data-ttu-id="2e082-124">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="2e082-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2e082-125">Gentag de samme trin for andre valgfrie felter, f. eks. **fornavn**, **Efternavn**, **Fulde navn**, **Køn** og **Postnummer**.</span><span class="sxs-lookup"><span data-stu-id="2e082-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="2e082-126">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="2e082-126">Select the segments you want to export.</span></span> <span data-ttu-id="2e082-127">Du kan eksportere op til 1 million kundeprofiler i alt til DotDigital.</span><span class="sxs-lookup"><span data-stu-id="2e082-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="2e082-128">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="2e082-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2e082-129">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="2e082-129">Export the data</span></span>

<span data-ttu-id="2e082-130">Du kan [eksportere data efter behov](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2e082-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2e082-131">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2e082-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2e082-132">I DotDigital kan du nu finde dine segmenter i [DotDigital-adressekartoteker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="2e082-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2e082-133">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="2e082-133">Known limitations</span></span>

- <span data-ttu-id="2e082-134">Op til 1 million profiler pr. eksport til DotDigital.</span><span class="sxs-lookup"><span data-stu-id="2e082-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="2e082-135">Eksport til DotDigital er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="2e082-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="2e082-136">Eksport af segmenter med det samlede antal 1 million profiler kan tage op til tre timer på grund af begrænsninger på udbydersiden.</span><span class="sxs-lookup"><span data-stu-id="2e082-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="2e082-137">Antallet af profiler, du kan eksportere til DotDigital, er afhængige og begrænsede i kontrakten med DotDigital.</span><span class="sxs-lookup"><span data-stu-id="2e082-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2e082-138">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="2e082-138">Data privacy and compliance</span></span>

<span data-ttu-id="2e082-139">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til DotDigital, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="2e082-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2e082-140">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at DotDigital overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="2e082-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="2e082-141">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2e082-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2e082-142">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="2e082-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]