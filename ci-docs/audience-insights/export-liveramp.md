---
title: LiveRamp-connector
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporten til LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760320"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="e942f-103">Eksportér segmenter til LiveRamp&reg; (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="e942f-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="e942f-104">Aktivér dine data i LiveRamp for at oprette forbindelse til over 500 platforme på tværs af digitale, sociale og tv-medier.</span><span class="sxs-lookup"><span data-stu-id="e942f-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="e942f-105">Arbejd med dine data i LiveRamp for at målrette, undertrykke og tilpasse reklamekampagner.</span><span class="sxs-lookup"><span data-stu-id="e942f-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e942f-106">Forudsætninger for en forbindelse</span><span class="sxs-lookup"><span data-stu-id="e942f-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="e942f-107">Du skal have et LiveRamp-abonnement for at kunne bruge denne connector.</span><span class="sxs-lookup"><span data-stu-id="e942f-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="e942f-108">Hvis du vil have et abonnement, skal du [kontakte LiveRamp](https://liveramp.com/contact/) direkte.</span><span class="sxs-lookup"><span data-stu-id="e942f-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="e942f-109">[Få mere at vide om LiveRamp-onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="e942f-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="e942f-110">Konfigurer forbindelsen til LiveRamp</span><span class="sxs-lookup"><span data-stu-id="e942f-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="e942f-111">Gå til **Administrator** > **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="e942f-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e942f-112">Vælg **Tilføj forbindelse**, og vælg **LiveRamp** for at konfigurere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="e942f-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="e942f-113">Giv din forbindelse et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="e942f-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e942f-114">Visningsnavn og forbindelsestype beskriver denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="e942f-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e942f-115">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="e942f-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e942f-116">Vælg, hvem der kan bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="e942f-116">Choose who can use this connection.</span></span> <span data-ttu-id="e942f-117">Hvis du ikke kan gøre noget, er standarden Administratorer.</span><span class="sxs-lookup"><span data-stu-id="e942f-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e942f-118">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e942f-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e942f-119">Angiv et **Brugernavn** og en **Adgangskode** til din LiveRamp Secure FTP (SFTP)-konto.</span><span class="sxs-lookup"><span data-stu-id="e942f-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="e942f-120">Disse legitimationsoplysninger kan være forskellige fra dine legitimationsoplysninger for LiveRamp-onboarding.</span><span class="sxs-lookup"><span data-stu-id="e942f-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="e942f-121">Vælg **Bekræft** for at teste forbindelsen til LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="e942f-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="e942f-122">Når bekræftelsen er fuldført, skal du give dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**.</span><span class="sxs-lookup"><span data-stu-id="e942f-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="e942f-123">Vælg **Gem** for at fuldføre forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="e942f-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e942f-124">Konfigurere en eksport</span><span class="sxs-lookup"><span data-stu-id="e942f-124">Configure an export</span></span>

<span data-ttu-id="e942f-125">Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type.</span><span class="sxs-lookup"><span data-stu-id="e942f-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e942f-126">Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e942f-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e942f-127">Gå til **Data** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="e942f-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e942f-128">Vælg **Tilføj destination** for at oprette en ny eksport.</span><span class="sxs-lookup"><span data-stu-id="e942f-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e942f-129">Vælg en forbindelse i sektionen LiveRamp i feltet **Forbindelse til eksport**.</span><span class="sxs-lookup"><span data-stu-id="e942f-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="e942f-130">Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.</span><span class="sxs-lookup"><span data-stu-id="e942f-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e942f-131">I feltet **Vælg din nøgle-identifikator** vælg **Email**, **Navn og adresse** eller **Telefon** som du vil sende til LiveRamp i forbindelse med identifikation.</span><span class="sxs-lookup"><span data-stu-id="e942f-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e942f-132">![LiveRamp connector med attributtilknytning](media/export-liveramp-segments.png "LiveRamp connector med attributtilknytning")</span><span class="sxs-lookup"><span data-stu-id="e942f-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="e942f-133">Tilknyt de tilsvarende attributter fra det samlede kundeobjekt til den valgte nøgle-identifikator.</span><span class="sxs-lookup"><span data-stu-id="e942f-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="e942f-134">Vælg **Tilføj attribut** for at tilknytte flere attributter, der skal sendes til LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="e942f-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="e942f-135">Hvis du sender flere nøgle-identifikatorattributter til LiveRamp, får du sandsynligvis en højere match-rate.</span><span class="sxs-lookup"><span data-stu-id="e942f-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="e942f-136">Vælg de segmenter, du vil eksportere til LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="e942f-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="e942f-137">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="e942f-137">Select **Save**.</span></span>

<span data-ttu-id="e942f-138">Når du gemmer en eksport, køres eksporten ikke med det samme.</span><span class="sxs-lookup"><span data-stu-id="e942f-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e942f-139">Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e942f-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e942f-140">Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e942f-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e942f-141">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="e942f-141">Data privacy and compliance</span></span>

<span data-ttu-id="e942f-142">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Liveramp, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="e942f-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e942f-143">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Liveramp overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="e942f-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e942f-144">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e942f-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e942f-145">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="e942f-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
