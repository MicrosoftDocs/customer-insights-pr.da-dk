---
title: Forbedring ved hjælp af tredjepart Experian
description: Generelle oplysninger om Experian-tredjeparts forbedring.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309813"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="67bba-103">Forbedre kundeprofiler med demografi fra Experian (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="67bba-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="67bba-104">Experian er førende på globalt plan inden for rapportering om forbruger- og virksomhedskreditering og marketingtjenester.</span><span class="sxs-lookup"><span data-stu-id="67bba-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="67bba-105">Med Experian-tjeneste til indsamling af data kan du få en større forståelse af kunderne ved at forbedre dine kundeprofiler med demografiske data som størrelse, indkomst og meget mere.</span><span class="sxs-lookup"><span data-stu-id="67bba-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="67bba-106">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="67bba-106">Prerequisites</span></span>

<span data-ttu-id="67bba-107">Hvis du vil konfigurere Experian, skal følgende forudsætninger være opfyldt:</span><span class="sxs-lookup"><span data-stu-id="67bba-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="67bba-108">Du skal have et aktivt abonnement på Experian.</span><span class="sxs-lookup"><span data-stu-id="67bba-108">You have an active Experian subscription.</span></span> <span data-ttu-id="67bba-109">Hvis du vil have et abonnement, skal du [kontakte Experian](https://www.experian.com/marketing-services/contact) direkte.</span><span class="sxs-lookup"><span data-stu-id="67bba-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="67bba-110">[Få mere at vide om Experian-dataforbedring](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="67bba-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="67bba-111">En Experian-forbindelse er allerede konfigureret af en administrator *eller* du har [administratortilladelser](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="67bba-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="67bba-112">Du skal også bruge bruger-id, part-id og modelnummer for den SSH-aktiverede ST-konto (Secure Transport), som Experian har oprettet til dig.</span><span class="sxs-lookup"><span data-stu-id="67bba-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="67bba-113">Understøttede lande/områder</span><span class="sxs-lookup"><span data-stu-id="67bba-113">Supported countries/regions</span></span>

<span data-ttu-id="67bba-114">I øjeblikket understøtter vi kun forbedring af kundeprofiler i USA.</span><span class="sxs-lookup"><span data-stu-id="67bba-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="67bba-115">Konfiguration af forbedring</span><span class="sxs-lookup"><span data-stu-id="67bba-115">Configure the enrichment</span></span>

1. <span data-ttu-id="67bba-116">Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.</span><span class="sxs-lookup"><span data-stu-id="67bba-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="67bba-117">Vælg **Forbedr mine data** i feltet Experian.</span><span class="sxs-lookup"><span data-stu-id="67bba-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="67bba-118">![Experian felt](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="67bba-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="67bba-119">Vælg en [værdi](connections.md) på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="67bba-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="67bba-120">Kontakt en administrator, hvis der ikke er nogen forbindelse.</span><span class="sxs-lookup"><span data-stu-id="67bba-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="67bba-121">Hvis du er administrator, kan du oprette forbindelse ved at vælge **Tilføj forbindelse** og vælge på Experian på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="67bba-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="67bba-122">Vælg **Opret forbindelse Experian** for at bekræfte valget af forbindelse.</span><span class="sxs-lookup"><span data-stu-id="67bba-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="67bba-123">Vælg **Næste**, og vælg det **Kundedatasæt**, du vil forbedre med demografidata fra Experian.</span><span class="sxs-lookup"><span data-stu-id="67bba-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="67bba-124">Du kan vælge objektet **Kunde** for at forbedre alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre de kundeprofiler, der findes i dette segment.</span><span class="sxs-lookup"><span data-stu-id="67bba-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Skærmbillede, når du vælger kundedatasættet.":::

1. <span data-ttu-id="67bba-126">Vælg **Næste**, og definer, hvilken type felter fra dine ensartede profiler der skal bruges til at søge efter tilsvarende demografidata fra Experian.</span><span class="sxs-lookup"><span data-stu-id="67bba-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="67bba-127">Mindst ét af felterne **Navn og adresse**, **Telefon** eller **E-mail** er obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="67bba-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="67bba-128">Du kan opnå en mere nøjagtig overensstemmelse ved at tilføje op til to andre felter.</span><span class="sxs-lookup"><span data-stu-id="67bba-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="67bba-129">Denne indstilling påvirker de tilknytningsfelter, du har adgang til i næste trin.</span><span class="sxs-lookup"><span data-stu-id="67bba-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="67bba-130">Flere nøgle-id-attributter sendes til Experian for at give en højere overensstemmelseshastighed.</span><span class="sxs-lookup"><span data-stu-id="67bba-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="67bba-131">Start felttilknytningen ved at vælge **Næste**.</span><span class="sxs-lookup"><span data-stu-id="67bba-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="67bba-132">Definér, hvilke felter fra dine ensartede profiler der skal bruges til at søge efter tilsvarende demografidata fra Experian.</span><span class="sxs-lookup"><span data-stu-id="67bba-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="67bba-133">Obligatoriske felter er markeret.</span><span class="sxs-lookup"><span data-stu-id="67bba-133">Required fields are marked.</span></span>

1. <span data-ttu-id="67bba-134">Angiv et navn, der viser forbedringen og et navn på outputobjektet.</span><span class="sxs-lookup"><span data-stu-id="67bba-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="67bba-135">Vælg **Gem valgmuligheder**, når du har gennemset dine valg.</span><span class="sxs-lookup"><span data-stu-id="67bba-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="67bba-136">Konfiguration af forbindelse til Experian</span><span class="sxs-lookup"><span data-stu-id="67bba-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="67bba-137">Du skal være en administrator for at konfigurere forbindelser.</span><span class="sxs-lookup"><span data-stu-id="67bba-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="67bba-138">Vælg **Tilføj forbindelse**, når du konfigurerer en konfiguration, *eller* gå til **Administration** > **Forbindelser**, og vælg **Konfigurer** på Experian-feltet.</span><span class="sxs-lookup"><span data-stu-id="67bba-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="67bba-139">Vælg **Introduktion**.</span><span class="sxs-lookup"><span data-stu-id="67bba-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="67bba-140">Angiv et navn til forbindelsen i feltet **Vis navn**.</span><span class="sxs-lookup"><span data-stu-id="67bba-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="67bba-141">Angiv gyldigt bruger-id, part-id og modelnummer for din Experian Secure Transport-konto.</span><span class="sxs-lookup"><span data-stu-id="67bba-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="67bba-142">Gennemse og giv dit samtykke til **Beskyttelse af personlige oplysninger og overholdelse af data** ved at vælge **Jeg accepterer**.</span><span class="sxs-lookup"><span data-stu-id="67bba-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="67bba-143">Vælg **Kontroller** for at validere konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="67bba-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="67bba-144">Vælg **Gem**, når verifikationen er fuldført.</span><span class="sxs-lookup"><span data-stu-id="67bba-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian forbindelseskonfigurationsfelt.":::

## <a name="enrichment-results"></a><span data-ttu-id="67bba-146">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="67bba-146">Enrichment results</span></span>

<span data-ttu-id="67bba-147">Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="67bba-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="67bba-148">Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="67bba-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="67bba-149">Behandlingstiden afhænger af størrelsen på dine kundedata og de processer, der er oprettet for din konto af Experian.</span><span class="sxs-lookup"><span data-stu-id="67bba-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="67bba-150">Når forbedringsprocessen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**.</span><span class="sxs-lookup"><span data-stu-id="67bba-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="67bba-151">Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.</span><span class="sxs-lookup"><span data-stu-id="67bba-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="67bba-152">Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.</span><span class="sxs-lookup"><span data-stu-id="67bba-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="67bba-153">Næste trin</span><span class="sxs-lookup"><span data-stu-id="67bba-153">Next steps</span></span>

<span data-ttu-id="67bba-154">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="67bba-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="67bba-155">Opret [segmenter](segments.md) og [målpunkter](measures.md), og [eksporter endda dataene](export-destinations.md) for at levere personlige oplevelser til dine kunder.</span><span class="sxs-lookup"><span data-stu-id="67bba-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="67bba-156">Beskyttelse af personlige oplysninger og overholdelse af angivne standarder</span><span class="sxs-lookup"><span data-stu-id="67bba-156">Data privacy and compliance</span></span>

<span data-ttu-id="67bba-157">Når du gør det muligt at Dynamics 365 Customer Insights overfører data til Experian, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personlige data.</span><span class="sxs-lookup"><span data-stu-id="67bba-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="67bba-158">Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at Experian overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have.</span><span class="sxs-lookup"><span data-stu-id="67bba-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="67bba-159">Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="67bba-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="67bba-160">Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.</span><span class="sxs-lookup"><span data-stu-id="67bba-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
