---
title: Power BI-connector
description: Få at vide, hvordan du kan bruge Dynamics 365 Customer Insights-connectoren i Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405413"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="ddb7a-103">Connector til Power BI (prøve)</span><span class="sxs-lookup"><span data-stu-id="ddb7a-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="ddb7a-104">Opret visualiseringer for dataene ved hjælp af Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="ddb7a-105">Generer yderligere indsigt, og opret rapporter med dine samlede kundedata.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ddb7a-106">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="ddb7a-106">Prerequisites</span></span>

- <span data-ttu-id="ddb7a-107">Du har samlet kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="ddb7a-108">Den nyeste version af [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) er installeret på computeren.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="ddb7a-109">[Få mere at vide om Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="ddb7a-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="ddb7a-110">Konfigurer connectoren til Power BI</span><span class="sxs-lookup"><span data-stu-id="ddb7a-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="ddb7a-111">Vælg **Fil** > **Hent data** i Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="ddb7a-112">Vælg **Se mere**, og søg efter **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="ddb7a-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="ddb7a-113">Vælg resultatet, og vælg **Opret forbindelse**.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="ddb7a-114">**Log på** med den samme organisationskonto, som du bruger til Customer Insights, og vælg **Opret forbindelse**.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="ddb7a-115">Den konto, du angiver i dette trin, bruges til at hente data fra Customer Insights og behøver ikke at være den samme som den, du er logget på i Power BI.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="ddb7a-116">Hvis du vil nulstille den konto, der bruges til hentning af data, skal du åbne Power BI og gå til **Fil** > **Muligheder** > **Indstillinger** > **Datakildeindstillinger**.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="ddb7a-117">Vælg **Dynamics 365 Customer Insights-logon** på listen over datakilder, og vælg **Ryd tilladelser**.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="ddb7a-118">I dialogboksen **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="ddb7a-119">der vises en liste om alle de miljøer, du har adgang til.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="ddb7a-120">Udvid et miljø, og åbn en af mapperne (objekter, målpunkter, segmenter, forbedringer).</span><span class="sxs-lookup"><span data-stu-id="ddb7a-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="ddb7a-121">Du kan f.eks. åbne mappen **Objekter** for at få vist alle de objekter, du kan importere.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="ddb7a-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span><span class="sxs-lookup"><span data-stu-id="ddb7a-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="ddb7a-123">Markér afkrydsningsfelterne ud for de objekter, der skal inkluderes, og vælg **Indlæs**.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="ddb7a-124">Du kan vælge flere objekter fra flere miljøer.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="ddb7a-125">Der vises en dialogboks for indlæsning, mens objekterne indlæses.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="ddb7a-126">Når alle de valgte objekter er indlæst, kan du bruge funktionerne i Power BI til at visualisere dataene.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="ddb7a-127">Store datasæt</span><span class="sxs-lookup"><span data-stu-id="ddb7a-127">Large data sets</span></span>

<span data-ttu-id="ddb7a-128">Customer Insights-connectoren for Power BI er udviklet til at fungere for datasæt, der indeholder op til 1 million kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="ddb7a-129">Import af større datasæt fungerer muligvis, men tager længere tid.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="ddb7a-130">Processen kan derudover køres med en timeout på grund af Power BI-begrænsninger.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="ddb7a-131">Du kan finde flere oplysninger i [Power BI: Anbefalinger til store datasæt](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="ddb7a-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="ddb7a-132">Arbejde med et delsæt af data</span><span class="sxs-lookup"><span data-stu-id="ddb7a-132">Work with a subset of data</span></span>

<span data-ttu-id="ddb7a-133">Overvej at arbejde med et delsæt af dine data.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="ddb7a-134">Du kan f. eks. oprette [segmenter](segments.md) i stedet for at eksportere alle kundeposter til Power BI.</span><span class="sxs-lookup"><span data-stu-id="ddb7a-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
