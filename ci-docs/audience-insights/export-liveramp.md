---
title: LiveRamp-connector
description: Få mere at vide om, hvordan du eksporterer data til LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597550"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="56c6e-103">LiveRamp&reg;-forbindelse (forhåndsvisning)</span><span class="sxs-lookup"><span data-stu-id="56c6e-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="56c6e-104">Aktivér dine data i LiveRamp for at oprette forbindelse til mere end 500 platforme på tværs af digitale, sociale og TV-økosystemer.</span><span class="sxs-lookup"><span data-stu-id="56c6e-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="56c6e-105">Arbejd med dine data i LiveRamp for at målrette, undertrykke og tilpasse reklamekampagner.</span><span class="sxs-lookup"><span data-stu-id="56c6e-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="56c6e-106">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="56c6e-106">Prerequisites</span></span>

- <span data-ttu-id="56c6e-107">Du skal have et LiveRamp-abonnement for at kunne bruge denne connector.</span><span class="sxs-lookup"><span data-stu-id="56c6e-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="56c6e-108">Hvis du vil have et abonnement, skal du [kontakte LiveRamp](https://liveramp.com/contact/) direkte.</span><span class="sxs-lookup"><span data-stu-id="56c6e-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="56c6e-109">[Få mere at vide om LiveRamp-onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="56c6e-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="56c6e-110">Oprette forbindelse til LiveRamp</span><span class="sxs-lookup"><span data-stu-id="56c6e-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="56c6e-111">Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="56c6e-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="56c6e-112">Vælg **Konfigurer** i feltet **LiveRamp**.</span><span class="sxs-lookup"><span data-stu-id="56c6e-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="56c6e-113">Giv din destination et genkendeligt navn i feltet **Vist navn**.</span><span class="sxs-lookup"><span data-stu-id="56c6e-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="56c6e-114">Angiv et **Brugernavn** og en **Adgangskode** til din LiveRamp Secure FTP (SFTP)-konto.</span><span class="sxs-lookup"><span data-stu-id="56c6e-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="56c6e-115">Disse legitimationsoplysninger kan være forskellige fra dine legitimationsoplysninger for LiveRamp-onboarding.</span><span class="sxs-lookup"><span data-stu-id="56c6e-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="56c6e-116">Vælg **Bekræft** for at teste forbindelsen til LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="56c6e-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="56c6e-117">Når bekræftelsen er fuldført, skal du give dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**.</span><span class="sxs-lookup"><span data-stu-id="56c6e-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="56c6e-118">Vælg **Næste** for at konfigurere LiveRamp Connector.</span><span class="sxs-lookup"><span data-stu-id="56c6e-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="56c6e-119">Konfigurer connectoren</span><span class="sxs-lookup"><span data-stu-id="56c6e-119">Configure the connector</span></span>

1. <span data-ttu-id="56c6e-120">I feltet **Vælg din nøgle-identifikator** vælg **Email**, **Navn og adresse** eller **Telefon** som du vil sende til LiveRamp i forbindelse med identifikation.</span><span class="sxs-lookup"><span data-stu-id="56c6e-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="56c6e-121">Tilknyt de tilsvarende attributter fra det samlede kundeobjekt til den valgte nøgle-identifikator.</span><span class="sxs-lookup"><span data-stu-id="56c6e-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="56c6e-122">Vælg **Tilføj attribut** for at tilknytte yderligere attributter, der skal sendes til LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="56c6e-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="56c6e-123">Hvis du sender flere nøgle-identifikatorattributter til LiveRamp, får du sandsynligvis en højere match-rate.</span><span class="sxs-lookup"><span data-stu-id="56c6e-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="56c6e-124">Vælg de segmenter, du vil eksportere til LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="56c6e-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="56c6e-125">Vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="56c6e-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="56c6e-126">![LiveRamp connector med attributtilknytning](media/export-liveramp-segments.png "LiveRamp connector med attributtilknytning")</span><span class="sxs-lookup"><span data-stu-id="56c6e-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="56c6e-127">Eksportér dataene</span><span class="sxs-lookup"><span data-stu-id="56c6e-127">Export the data</span></span>

<span data-ttu-id="56c6e-128">Eksporten starter kort tid efter, hvis alle forudsætninger for eksport er opfyldt.</span><span class="sxs-lookup"><span data-stu-id="56c6e-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="56c6e-129">Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="56c6e-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="56c6e-130">Når eksporten er fuldført, kan du logge på LiveRamp-onboarding for at aktivere og distribuere dine data.</span><span class="sxs-lookup"><span data-stu-id="56c6e-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="56c6e-131">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="56c6e-131">Data privacy and compliance</span></span>

<span data-ttu-id="56c6e-132">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Liveramp, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="56c6e-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="56c6e-133">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Liveramp overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="56c6e-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="56c6e-134">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="56c6e-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="56c6e-135">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="56c6e-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]