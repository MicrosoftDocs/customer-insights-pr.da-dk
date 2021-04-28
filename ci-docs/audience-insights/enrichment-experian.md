---
title: Tilsætning af tredjeparts forbedringer fra Experian
description: Generelle oplysninger om Experian-forbedring fra tredjepart.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896366"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="10839-103">Forbedre kundeprofiler med demografi fra Experian (forbedre)</span><span class="sxs-lookup"><span data-stu-id="10839-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="10839-104">Experian er en global leder i forbruger- og virksomhedskreditrapportering og marketingservice.</span><span class="sxs-lookup"><span data-stu-id="10839-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="10839-105">Med Experians dataforbedringstjenester kan du få en dybere forståelse af dine kunder ved at udvide dine kundeprofiler med demografiske data, f.eks. husstandens størrelse og indkomst og meget mere.</span><span class="sxs-lookup"><span data-stu-id="10839-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="10839-106">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="10839-106">Prerequisites</span></span>

<span data-ttu-id="10839-107">Hvis du vil konfigurere Experian, skal følgende forudsætninger være opfyldt:</span><span class="sxs-lookup"><span data-stu-id="10839-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="10839-108">Du har et aktivt Experian-abonnement.</span><span class="sxs-lookup"><span data-stu-id="10839-108">You have an active Experian subscription.</span></span> <span data-ttu-id="10839-109">Hvis du vil have et abonnement, skal du [kontakte Experian](https://www.experian.com/marketing-services/contact) direkte.</span><span class="sxs-lookup"><span data-stu-id="10839-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="10839-110">[Få mere at vide om Experian-dataforbedring](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="10839-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="10839-111">En Experian-forbindelse er allerede konfigureret af en administrator *eller* du har [administratortilladelser](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="10839-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="10839-112">Du skal også bruge bruger-id, part-id og modelnummer for den SSH-aktiverede ST-konto (Secure Transport), som Experian har oprettet for dig.</span><span class="sxs-lookup"><span data-stu-id="10839-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="10839-113">Konfiguration af forbedring</span><span class="sxs-lookup"><span data-stu-id="10839-113">Configure the enrichment</span></span>

1. <span data-ttu-id="10839-114">Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.</span><span class="sxs-lookup"><span data-stu-id="10839-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="10839-115">Vælg **Forbedr mine data** på Experian-feltet.</span><span class="sxs-lookup"><span data-stu-id="10839-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10839-116">![Experian-felt](media/experian-tile.png "Experian-felt")</span><span class="sxs-lookup"><span data-stu-id="10839-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="10839-117">Vælg en [forbindelse](connections.md) på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="10839-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="10839-118">Kontakt en administrator, hvis der ikke er nogen forbindelse.</span><span class="sxs-lookup"><span data-stu-id="10839-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="10839-119">Hvis du er administrator, kan du oprette en forbindelse ved at vælge **Tilføj forbindelse** og vælge Experian på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="10839-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="10839-120">Vælg **Opret forbindelse til Experian** for at bekræfte den valgte forbindelse.</span><span class="sxs-lookup"><span data-stu-id="10839-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="10839-121">Vælg **Næste**, og angiv de **Kundedatasæt**, du vil forbedre med demografidata fra Experian.</span><span class="sxs-lookup"><span data-stu-id="10839-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="10839-122">Du kan vælge objektet **Kunde** for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.</span><span class="sxs-lookup"><span data-stu-id="10839-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Skærmbillede, når du vælger kundedatasættet.":::

1. <span data-ttu-id="10839-124">Vælg **Næste**, og definer, hvilke felter fra dine samlede profiler der bruges til at søge efter tilsvarende demografidata fra Experian.</span><span class="sxs-lookup"><span data-stu-id="10839-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="10839-125">Mindst ét af felterne **Navn og adresse**, **Telefon** eller **E-mail** er obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="10839-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="10839-126">Du kan opnå en mere nøjagtig overensstemmelse ved at tilføje op til to andre felter.</span><span class="sxs-lookup"><span data-stu-id="10839-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="10839-127">Denne indstilling påvirker de tilknytningsfelter, du har adgang til i næste trin.</span><span class="sxs-lookup"><span data-stu-id="10839-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="10839-128">Flere nøgle-id-attributter, der sendes til Experian, giver sandsynligvis større sammenfald.</span><span class="sxs-lookup"><span data-stu-id="10839-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="10839-129">Start felttilknytningen ved at vælge **Næste**.</span><span class="sxs-lookup"><span data-stu-id="10839-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="10839-130">Definer, hvilke felter fra dine samlede profiler der bruges til at søge efter tilsvarende demografidata fra Experian.</span><span class="sxs-lookup"><span data-stu-id="10839-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="10839-131">Obligatoriske felter er markeret.</span><span class="sxs-lookup"><span data-stu-id="10839-131">Required fields are marked.</span></span>

1. <span data-ttu-id="10839-132">Angiv et navn, der viser forbedringen og et navn på outputobjektet.</span><span class="sxs-lookup"><span data-stu-id="10839-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="10839-133">Vælg **Gem valgmuligheder**, når du har gennemset dine valg.</span><span class="sxs-lookup"><span data-stu-id="10839-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="10839-134">Konfiguration af forbindelsen til Experian</span><span class="sxs-lookup"><span data-stu-id="10839-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="10839-135">Du skal være en administrator for at konfigurere forbindelser.</span><span class="sxs-lookup"><span data-stu-id="10839-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="10839-136">Vælg **Tilføj forbindelse**, når du konfigurerer en konfiguration, *eller* gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i feltet Experian.</span><span class="sxs-lookup"><span data-stu-id="10839-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="10839-137">Vælg **Introduktion**.</span><span class="sxs-lookup"><span data-stu-id="10839-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="10839-138">Angiv et navn til forbindelsen i feltet **Vis navn**.</span><span class="sxs-lookup"><span data-stu-id="10839-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="10839-139">Angiv gyldigt bruger-id, part-id og modelnummer for din Experian Secure Transport-konto.</span><span class="sxs-lookup"><span data-stu-id="10839-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="10839-140">Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**</span><span class="sxs-lookup"><span data-stu-id="10839-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="10839-141">Vælg **Kontroller** for at validere konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="10839-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="10839-142">Vælg **Gem**, når verifikationen er fuldført.</span><span class="sxs-lookup"><span data-stu-id="10839-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Side til konfiguration af Experian-forbindelse.":::

## <a name="enrichment-results"></a><span data-ttu-id="10839-144">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="10839-144">Enrichment results</span></span>

<span data-ttu-id="10839-145">Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="10839-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="10839-146">Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="10839-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="10839-147">Behandlingstiden afhænger af størrelsen på dine kundedata og de forbedringer, der er konfigureret for din konto af Experian.</span><span class="sxs-lookup"><span data-stu-id="10839-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="10839-148">Når forbedringsprocessen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**.</span><span class="sxs-lookup"><span data-stu-id="10839-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="10839-149">Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.</span><span class="sxs-lookup"><span data-stu-id="10839-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="10839-150">Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.</span><span class="sxs-lookup"><span data-stu-id="10839-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="10839-151">Næste trin</span><span class="sxs-lookup"><span data-stu-id="10839-151">Next steps</span></span>

<span data-ttu-id="10839-152">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="10839-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="10839-153">Du kan oprette [segmenter](segments.md), [målepunkter](measures.md) og endda [eksportere dataene](export-destinations.md) for at give kunderne personlige oplevelser.</span><span class="sxs-lookup"><span data-stu-id="10839-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="10839-154">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="10839-154">Data privacy and compliance</span></span>

<span data-ttu-id="10839-155">Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Experian, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="10839-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="10839-156">Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Experian overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed.</span><span class="sxs-lookup"><span data-stu-id="10839-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="10839-157">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="10839-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="10839-158">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="10839-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
