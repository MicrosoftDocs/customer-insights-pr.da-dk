---
title: Eksportér Customer Insights-data til Marketo
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759814"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="ea025-103">Eksportér segmenter til Marketo (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="ea025-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="ea025-104">Eksportér segmenter fra de samlede brugerprofiler til at generere kampagner, levere e-mailmarketing og bruge bestemte grupper af kunder med Marketo.</span><span class="sxs-lookup"><span data-stu-id="ea025-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ea025-105">Forudsætninger for forbindelse</span><span class="sxs-lookup"><span data-stu-id="ea025-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="ea025-106">Du har en [Marketo-konto](https://login.marketo.com/) og tilsvarende administratorlegitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="ea025-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ea025-107">Der findes eksisterende lister i Marketo og de tilsvarende id'er.</span><span class="sxs-lookup"><span data-stu-id="ea025-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="ea025-108">Du kan finde flere oplysninger i [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="ea025-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="ea025-109">Du har [konfigureret segmenter](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ea025-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="ea025-110">Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="ea025-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ea025-111">Kendte begrænsninger</span><span class="sxs-lookup"><span data-stu-id="ea025-111">Known limitations</span></span>

- <span data-ttu-id="ea025-112">Op til 1000000 profiler pr. eksport til Marketo.</span><span class="sxs-lookup"><span data-stu-id="ea025-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="ea025-113">Eksport til Marketo er begrænset til segmenter.</span><span class="sxs-lookup"><span data-stu-id="ea025-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="ea025-114">Eksport af segmenter med i alt 1000000 profiler kan tage op til tre timer.</span><span class="sxs-lookup"><span data-stu-id="ea025-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="ea025-115">Antallet af profiler, du kan eksportere til Marketo, er afhængige og begrænsede i kontrakten med Marketo.</span><span class="sxs-lookup"><span data-stu-id="ea025-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="ea025-116">Konfigurer forbindelsen til Marketo.</span><span class="sxs-lookup"><span data-stu-id="ea025-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="ea025-117">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="ea025-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ea025-118">Vælg **Tilføj forbindelse**, og vælg **Marketo** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="ea025-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="ea025-119">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="ea025-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ea025-120">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="ea025-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ea025-121">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="ea025-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ea025-122">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="ea025-122">Choose who can use this connection.</span></span> <span data-ttu-id="ea025-123">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="ea025-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ea025-124">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ea025-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ea025-125">Angiv dit **[Marketo-klient-ID, klientens hemmelige og resterende værtsnavnsslutpunkt](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="ea025-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="ea025-126">Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og kompatibilitet**, og vælg **Opret forbindelse** for at initialisere forbindelsen til Marketo.</span><span class="sxs-lookup"><span data-stu-id="ea025-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="ea025-127">Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.</span><span class="sxs-lookup"><span data-stu-id="ea025-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ea025-128">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="ea025-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ea025-129">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="ea025-129">Configure an export</span></span>

<span data-ttu-id="ea025-130">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="ea025-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ea025-131">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ea025-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ea025-132">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="ea025-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ea025-133">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="ea025-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ea025-134">Vælg en forbindelse i sektionen Marketo i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="ea025-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="ea025-135">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="ea025-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ea025-136">Angiv dit **[Marketo-liste-id](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="ea025-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="ea025-137">I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse.</span><span class="sxs-lookup"><span data-stu-id="ea025-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="ea025-138">Du kan også eksportere **Fornavn**, **Efternavn**, **By**, **Land** og **Land/Område** for at oprette mere personlige mails.</span><span class="sxs-lookup"><span data-stu-id="ea025-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="ea025-139">Vælg **Tilføj attribut** for at tilknytte disse felter.</span><span class="sxs-lookup"><span data-stu-id="ea025-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="ea025-140">Vælg de segmenter, du vil eksportere.</span><span class="sxs-lookup"><span data-stu-id="ea025-140">Select the segments you want to export.</span></span> <span data-ttu-id="ea025-141">Du kan eksportere op til 1000000 kundeprofiler i alt til Marketo.</span><span class="sxs-lookup"><span data-stu-id="ea025-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="ea025-142">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="ea025-142">Select **Save**.</span></span>

<span data-ttu-id="ea025-143">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="ea025-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ea025-144">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ea025-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ea025-145">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ea025-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="ea025-146">I Marketo kan du nu finde dine segmenter under [Marketo-lister](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="ea025-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ea025-147">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="ea025-147">Data privacy and compliance</span></span>

<span data-ttu-id="ea025-148">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Marketo, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="ea025-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ea025-149">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Marketo overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="ea025-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ea025-150">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ea025-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ea025-151">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="ea025-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]