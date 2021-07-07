---
title: Eksporter Customer Insights-data til Sendinblue
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314595"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="0fe81-103">Eksporter segmenter til Sendinblue (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="0fe81-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="0fe81-104">Eksportér segmenter ud fra samlede kundeprofiler til at generere kampagner, levere mailmarketing og bruge bestemte grupper af kunder med Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="0fe81-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0fe81-105">Forudsætninger for forbindelse</span><span class="sxs-lookup"><span data-stu-id="0fe81-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="0fe81-106">Du har en [Sendinblue-konto](https://www.sendinblue.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="0fe81-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0fe81-107">Der findes lister i Sendinblue og de tilsvarende id'er.</span><span class="sxs-lookup"><span data-stu-id="0fe81-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="0fe81-108">Du har [konfigureret segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0fe81-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="0fe81-109">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="0fe81-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0fe81-110">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="0fe81-110">Known limitations</span></span>

- <span data-ttu-id="0fe81-111">Op til 1 million profiler pr. eksport til Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="0fe81-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="0fe81-112">Eksport til Sendinblue er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="0fe81-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="0fe81-113">Eksport af segmenter med i alt 1 million profiler kan tage op til 90 minutter.</span><span class="sxs-lookup"><span data-stu-id="0fe81-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="0fe81-114">Antallet af profiler, du kan eksportere til Sendinblue, afhænger af og er begrænset af din kontrakt med Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="0fe81-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="0fe81-115">Konfigurer forbindelse til Sendinblue</span><span class="sxs-lookup"><span data-stu-id="0fe81-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="0fe81-116">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="0fe81-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0fe81-117">Vælg **Tilføj forbindelse**, og vælg **Sendinblue** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="0fe81-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="0fe81-118">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="0fe81-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0fe81-119">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="0fe81-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0fe81-120">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="0fe81-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0fe81-121">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="0fe81-121">Choose who can use this connection.</span></span> <span data-ttu-id="0fe81-122">Som standard er det kun administratorer.</span><span class="sxs-lookup"><span data-stu-id="0fe81-122">By default it's only administrators.</span></span> <span data-ttu-id="0fe81-123">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0fe81-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0fe81-124">Indtast din **[SendinBlue API-nøgle](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="0fe81-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="0fe81-125">Vælg **Jeg accepterer** for at bekræfte **Databeskyttelse af personlige oplysninger og overholdelse af standarder** og vælge **Opret forbindelse** for at initialisere forbindelsen til Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="0fe81-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="0fe81-126">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="0fe81-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0fe81-127">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="0fe81-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0fe81-128">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="0fe81-128">Configure an export</span></span>

<span data-ttu-id="0fe81-129">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="0fe81-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0fe81-130">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0fe81-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0fe81-131">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="0fe81-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0fe81-132">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="0fe81-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0fe81-133">Vælg en forbindelse i sektionen Sendinblue i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="0fe81-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="0fe81-134">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="0fe81-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0fe81-135">Angiv din Id for **Sendinblue-liste**.</span><span class="sxs-lookup"><span data-stu-id="0fe81-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="0fe81-136">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="0fe81-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0fe81-137">Du kan også eksportere **Fornavn**, **Efternavn** og **Telefon** for at oprette mere personlige e-mails.</span><span class="sxs-lookup"><span data-stu-id="0fe81-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="0fe81-138">Vælg **Tilføj attribut** for at tilknytte disse felter.</span><span class="sxs-lookup"><span data-stu-id="0fe81-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0fe81-139">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="0fe81-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="0fe81-140">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="0fe81-140">Select **Save**.</span></span>

<span data-ttu-id="0fe81-141">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="0fe81-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0fe81-142">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0fe81-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0fe81-143">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0fe81-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0fe81-144">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="0fe81-144">Data privacy and compliance</span></span>

<span data-ttu-id="0fe81-145">Når du gør det muligt for Dynamics 365 Customer Insights at overfører data til Sendinblue, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="0fe81-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0fe81-146">Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at Sendinblue overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have.</span><span class="sxs-lookup"><span data-stu-id="0fe81-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0fe81-147">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0fe81-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0fe81-148">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="0fe81-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
