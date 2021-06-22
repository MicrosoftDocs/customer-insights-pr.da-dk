---
title: Eksportér Customer Insights-data til DotDigital
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124404"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="93199-103">Eksporter segmenter til DotDigital (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="93199-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="93199-104">Eksportér segmenter af Unified-kundeprofiler til DotDigital-adressekartotekerne, og brug dem til kampagner, e-mailmarketing og til at oprette kundesegmenter med DotDigital.</span><span class="sxs-lookup"><span data-stu-id="93199-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="93199-105">Forudsætninger for en forbindelse</span><span class="sxs-lookup"><span data-stu-id="93199-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="93199-106">Du har en [DotDigital-konto](https://dotdigital.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="93199-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="93199-107">Der findes eksisterende adressekartoteker i DotDigital og de tilsvarende id'er.</span><span class="sxs-lookup"><span data-stu-id="93199-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="93199-108">Id kan findes i URL-adressen, når du vælger og åbner et adressekartotek.</span><span class="sxs-lookup"><span data-stu-id="93199-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="93199-109">Du kan finde flere oplysninger i [DotDigital-adressekartoteker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="93199-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="93199-110">Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="93199-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="93199-111">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="93199-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="93199-112">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="93199-112">Known limitations</span></span>

- <span data-ttu-id="93199-113">Op til 1 million profiler pr. eksport til DotDigital.</span><span class="sxs-lookup"><span data-stu-id="93199-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="93199-114">Eksport til DotDigital er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="93199-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="93199-115">Eksport af segmenter med det samlede antal 1 million profiler kan tage op til tre timer på grund af begrænsninger på udbydersiden.</span><span class="sxs-lookup"><span data-stu-id="93199-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="93199-116">Antallet af profiler, du kan eksportere til DotDigital, er afhængige og begrænsede i kontrakten med DotDigital.</span><span class="sxs-lookup"><span data-stu-id="93199-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="93199-117">Konfigurer forbindelsen til DotDigital</span><span class="sxs-lookup"><span data-stu-id="93199-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="93199-118">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="93199-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="93199-119">Vælg **Tilføj forbindelse**, og vælg **DotDigital** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="93199-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="93199-120">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="93199-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="93199-121">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="93199-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="93199-122">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="93199-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="93199-123">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="93199-123">Choose who can use this connection.</span></span> <span data-ttu-id="93199-124">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="93199-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="93199-125">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="93199-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="93199-126">Angiv **DotDigital-brugernavn og adgangskode**.</span><span class="sxs-lookup"><span data-stu-id="93199-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="93199-127">Angiv dit **[DotDigital-adressekartoteks-id](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="93199-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="93199-128">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.</span><span class="sxs-lookup"><span data-stu-id="93199-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="93199-129">Vælg **Opret forbindelse** for at initialisere forbindelsen til DotDigital.</span><span class="sxs-lookup"><span data-stu-id="93199-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="93199-130">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="93199-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="93199-131">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="93199-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="93199-132">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="93199-132">Configure an export</span></span>

<span data-ttu-id="93199-133">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="93199-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="93199-134">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="93199-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="93199-135">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="93199-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="93199-136">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="93199-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="93199-137">Vælg en forbindelse i sektionen DotDigital i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="93199-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="93199-138">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="93199-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="93199-139">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="93199-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="93199-140">Gentag de samme trin for andre valgfrie felter, f. eks. **fornavn**, **Efternavn**, **Fulde navn**, **Køn** og **Postnummer**.</span><span class="sxs-lookup"><span data-stu-id="93199-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="93199-141">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="93199-141">Select the segments you want to export.</span></span> <span data-ttu-id="93199-142">Du kan eksportere op til 1 million kundeprofiler i alt til DotDigital.</span><span class="sxs-lookup"><span data-stu-id="93199-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="93199-143">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="93199-143">Select **Save**.</span></span>

<span data-ttu-id="93199-144">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="93199-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="93199-145">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="93199-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="93199-146">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="93199-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="93199-147">I DotDigital kan du nu finde dine segmenter i [DotDigital-adressekartoteker](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="93199-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="93199-148">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="93199-148">Data privacy and compliance</span></span>

<span data-ttu-id="93199-149">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til DotDigital, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="93199-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="93199-150">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at DotDigital overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="93199-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="93199-151">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="93199-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="93199-152">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="93199-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
