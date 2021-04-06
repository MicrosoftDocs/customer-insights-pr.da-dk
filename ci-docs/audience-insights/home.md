---
title: Startsiden i målgruppen Insights
description: Begynd at udforske appen på startsiden.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597228"
---
# <a name="create-a-new-environment"></a><span data-ttu-id="36409-103">Opret et miljø</span><span class="sxs-lookup"><span data-stu-id="36409-103">Create a new environment</span></span>

## <a name="create-a-trial-environment"></a><span data-ttu-id="36409-104">Oprette et prøvemiljø</span><span class="sxs-lookup"><span data-stu-id="36409-104">Create a trial environment</span></span>

<span data-ttu-id="36409-105">Du kan tilmelde dig en prøveversion på [prøveabonnementssiden](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span><span class="sxs-lookup"><span data-stu-id="36409-105">You can sign up for a trial on the [trial sign up page](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span></span> 

> [!NOTE]
> <span data-ttu-id="36409-106">Prøver udløber efter 30 dage.</span><span class="sxs-lookup"><span data-stu-id="36409-106">Trials expire after 30 days.</span></span>

1. <span data-ttu-id="36409-107">Vælg indstillingen **Tilmeld dig en gratis prøveversion**, og vælg **Tilmeld nu**.</span><span class="sxs-lookup"><span data-stu-id="36409-107">Choose the **Sign up for a free trial** option and select **Sign up now**.</span></span>

1. <span data-ttu-id="36409-108">Angiv din arbejds- eller skolemailadresse, fortæl os mere om dig selv, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="36409-108">Provide your work or school email address, tell us a more about yourself and select **Next**.</span></span>

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialogboks, hvor du kan tilmelde dig for at få en gratis prøveversion":::

1. <span data-ttu-id="36409-110">Angiv et **Navn** til dit nye miljø.</span><span class="sxs-lookup"><span data-stu-id="36409-110">Provide a **Name** for your new environment.</span></span> 

1. <span data-ttu-id="36409-111">Vælg prøvetypen.</span><span class="sxs-lookup"><span data-stu-id="36409-111">Select the trial type.</span></span>

1. <span data-ttu-id="36409-112">Vælg et **Område** for dit miljø.</span><span class="sxs-lookup"><span data-stu-id="36409-112">Choose the **Region** for your environment.</span></span>

1. <span data-ttu-id="36409-113">Du kan også vælge til administratorer af en Dynamics 365-organisation: Vælg **Avancerede indstillinger**, og angiv URL-adressen til din organisation for at bruge forudsigelsesfunktioner som f.eks. kundeafgang.</span><span class="sxs-lookup"><span data-stu-id="36409-113">Optionally, for admins of a Dynamics 365 organization: Select **Advanced settings** and provide the URL of your organization to use prediction features like customer churn.</span></span>

1. <span data-ttu-id="36409-114">Vælg **Opret**.</span><span class="sxs-lookup"><span data-stu-id="36409-114">Select **Create**.</span></span> 

<span data-ttu-id="36409-115">Når miljøet er oprettet, kan du se **Demo**-miljøet, som giver dig mulighed for at udforske appen med fiktive data.</span><span class="sxs-lookup"><span data-stu-id="36409-115">After the environment was created, you'll see the **Demo** environment which lets you explore the app with fictitious data.</span></span> <span data-ttu-id="36409-116">Du kan ændre eksempeldataene, så de stemmer overens med din branche.</span><span class="sxs-lookup"><span data-stu-id="36409-116">You can change the sample data to match your industry.</span></span> <span data-ttu-id="36409-117">Vælg ikonet **Indstillinger** i sidehovedet, og vælg **Demoindstillinger**.</span><span class="sxs-lookup"><span data-stu-id="36409-117">Select the **Settings** icon in the header and select **Demo settings**.</span></span> <span data-ttu-id="36409-118">Derudover kan du ændre det visuelle tema.</span><span class="sxs-lookup"><span data-stu-id="36409-118">Additionally, you can change the visual theme.</span></span> 

<span data-ttu-id="36409-119">Du [skifter til det miljø](#switch-environments), du har oprettet under tilmeldingsprocessen, for at arbejde med dine egne data.</span><span class="sxs-lookup"><span data-stu-id="36409-119">You [switch to the environment](#switch-environments) you created during the sign-up process to work with your own data.</span></span>

## <a name="create-a-new-production-or-sandbox-environment"></a><span data-ttu-id="36409-120">Oprette et produktions- eller sandkassemiljø</span><span class="sxs-lookup"><span data-stu-id="36409-120">Create a new production or sandbox environment</span></span>

<span data-ttu-id="36409-121">Vælg **Miljøer** i appoverskriften, og vælg **Ny** i dit miljø.</span><span class="sxs-lookup"><span data-stu-id="36409-121">In your environment, select the **Environments** picker in the app header and select **New**.</span></span>

<span data-ttu-id="36409-122">Følg trinnene, som om du [opretter et prøvemiljø](#create-a-trial-environment).</span><span class="sxs-lookup"><span data-stu-id="36409-122">Follow the steps as if you [create a trial environment](#create-a-trial-environment).</span></span> <span data-ttu-id="36409-123">Som standard gemmes data i den Customer Insights-styrede datasø.</span><span class="sxs-lookup"><span data-stu-id="36409-123">By default, data is stored in the Customer Insights managed data lake.</span></span> <span data-ttu-id="36409-124">Du får en ekstra indstilling, når du vælger **Avancerede indstillinger**, for at gemme dine data i din egen Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="36409-124">You get an additional option when selecting **Advanced settings** to store your data in your own Azure Data Lake.</span></span> <span data-ttu-id="36409-125">Angiv dit kontonavn og din kontonøgle for at oprette forbindelse til din Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="36409-125">Provide your account name and account key to establish a connection to your Azure Data Lake.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="36409-126">Når du gemmer data i Azure Data Lake Storage, accepterer du, at data overføres til og gemmes på den relevante geografiske placering for den pågældende Azure-datalagerkonto, som kan være en anden placering end den, hvor data gemmes i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="36409-126">By saving data to your Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="36409-127">Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration.</span><span class="sxs-lookup"><span data-stu-id="36409-127">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a><span data-ttu-id="36409-128">Udforske startsiden</span><span class="sxs-lookup"><span data-stu-id="36409-128">Explore the home page</span></span>

<span data-ttu-id="36409-129">Du kan få [adgang til målgruppeindsigt fra Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) på følgende URL-adresse: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="36409-129">You can [access audience insights from Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) on the following URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span></span>
<span data-ttu-id="36409-130">På siden **Start** vises en oversigt over segmenter, mål og data til forbedring (hvis de er konfigureret) efter fuldførelse af [tilknyt](map-entities.md), [match](match-entities.md), og [flet](merge-entities.md)-faserne.</span><span class="sxs-lookup"><span data-stu-id="36409-130">The **Home** page shows an overview of segments, measures, and enrichment data (if configured)after completing the [map](map-entities.md), [match](match-entities.md), and [merge](merge-entities.md) phases.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="36409-131">![Indsigt på startside](media/home-page-insights.png "Indsigt på startside")</span><span class="sxs-lookup"><span data-stu-id="36409-131">![Insights on Home page](media/home-page-insights.png "Insights on Home page")</span></span>

<span data-ttu-id="36409-132">Under **Seneste segmenter** kan du se grupper af kunder baseret på de attributter for demografi, adfærd eller transaktioner, som du har defineret.</span><span class="sxs-lookup"><span data-stu-id="36409-132">Under **Recent segments**, you see groups of customers based on demographic, behavioral, or transactional attributes that you've defined.</span></span> <span data-ttu-id="36409-133">[Ved at oprette segmenter](segments.md) kan du gruppere kundebasen og målrette dine forretningsaktiviteter bedre.</span><span class="sxs-lookup"><span data-stu-id="36409-133">[Creating segments](segments.md) helps you to group your customer base and better target your business activities.</span></span>

<span data-ttu-id="36409-134">**Seneste målinger** viser de felter med [nøgletalsindikatorer (KPI'er)](measures.md), du har defineret.</span><span class="sxs-lookup"><span data-stu-id="36409-134">**Recent measures** show tiles with [key performance indicators (KPIs)](measures.md) that you've defined.</span></span> <span data-ttu-id="36409-135">Det kan f.eks. være den gennemsnitlige sandsynlighed for, at en kunde kommer i gang, eller det gennemsnitlige onlineforbrug pr. kunde.</span><span class="sxs-lookup"><span data-stu-id="36409-135">For example, average likelihood of a customer to churn or the average online spend per customer.</span></span>

<span data-ttu-id="36409-136">I sektionen **Seneste forbedringer** vises resultaterne af de forbedringer, der er blevet kørt og fuldført for nylig.</span><span class="sxs-lookup"><span data-stu-id="36409-136">The **Recent enrichments** section lists the results of the enrichment runs that completed recently.</span></span> <span data-ttu-id="36409-137">[Forbedringer](enrichment-hub.md) tilføjer oplysninger om kundebasen.</span><span class="sxs-lookup"><span data-stu-id="36409-137">[Enrichments](enrichment-hub.md) add information about your customer base.</span></span> <span data-ttu-id="36409-138">Det sker f.eks. ved at forstå, hvilke interesser og mærker de har et tilhørsforhold til.</span><span class="sxs-lookup"><span data-stu-id="36409-138">For example, by understanding the interests and brands that they have affinity for.</span></span>

## <a name="switch-environments"></a><span data-ttu-id="36409-139">Skift miljøer</span><span class="sxs-lookup"><span data-stu-id="36409-139">Switch environments</span></span>

<span data-ttu-id="36409-140">Vælg **Miljø**-kontrolelementet i øverste højre hjørne af siden for at skifte miljøer.</span><span class="sxs-lookup"><span data-stu-id="36409-140">Select the **Environment** control in the upper-right corner of the page to change environments.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="36409-141">![Skift miljø](media/home-page-environment-switcher.png "Skift miljø")</span><span class="sxs-lookup"><span data-stu-id="36409-141">![Switch environment](media/home-page-environment-switcher.png "Switch environment")</span></span>

<span data-ttu-id="36409-142">Administratorer kan oprette og administrere [flere miljøer](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="36409-142">Administrators can create and manage [multiple environments](manage-environments.md).</span></span> <span data-ttu-id="36409-143">Det kan være en god ide at vedligeholde mere end ét miljø, hvis organisationen f.eks. opererer i udlandet, og du har brug for at adskille data og indsigt på forskellige måder.</span><span class="sxs-lookup"><span data-stu-id="36409-143">Maintaining more than one environment may be useful if, for example, your organization operates internationally and you need to segregate data and insights in different ways.</span></span>

## <a name="next-step"></a><span data-ttu-id="36409-144">Næste trin</span><span class="sxs-lookup"><span data-stu-id="36409-144">Next step</span></span>

<span data-ttu-id="36409-145">Hvis du vil se dine egne indsigter på startsiden, skal du først [tilføje datakilder](data-sources.md) og [samle](data-unification.md) dataene for at oprette kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="36409-145">To see your own insights on the home page, you'll first need to [add data sources](data-sources.md) and [unify](data-unification.md) your data to build customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]