---
title: Opret forbindelse til objekter i den Common Data Service administrerede Data Lake
description: Importere data fra en Common Data Service-administreret datasø.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643391"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="b03d1-103">Oprette forbindelse til data i en Common Data Service-administreret datasø</span><span class="sxs-lookup"><span data-stu-id="b03d1-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b03d1-104">Denne artikel indeholder oplysninger om, hvordan eksisterende Dynamics 365-kunder hurtigt kan oprette forbindelse til deres analyseenheder i den Common Data Service-administrerede sø.</span><span class="sxs-lookup"><span data-stu-id="b03d1-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="b03d1-105">Du skal være administrator på Common Data Service-organisationen for at fortsætte og se listen over de objekter, der er tilgængelige i den administrerede sø.</span><span class="sxs-lookup"><span data-stu-id="b03d1-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="b03d1-106">Vigtige overvejelser</span><span class="sxs-lookup"><span data-stu-id="b03d1-106">Important considerations</span></span>

<span data-ttu-id="b03d1-107">Data, der gemmes i onlinetjenester, f.eks. Azure Data Lake Storage, gemmes på en anden placering end der, hvor dataene behandles eller gemmes i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b03d1-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="b03d1-108">Ved at importere eller oprette forbindelse til data, der er gemt i onlinetjenester, accepterer du, at data kan overføres til og gemmes sammen med Dynamics 365 Customer Insights.  [Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="b03d1-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="b03d1-109">Opret forbindelse til Common Data Service-administreret sø</span><span class="sxs-lookup"><span data-stu-id="b03d1-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="b03d1-110">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="b03d1-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b03d1-111">Vælg **Tilføj datakilde**.</span><span class="sxs-lookup"><span data-stu-id="b03d1-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="b03d1-112">Vælg **Opret forbindelse til Common Data Service**, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="b03d1-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="b03d1-113">Angiv et **Navn** til datakilden, og vælg derefter **Næste**.</span><span class="sxs-lookup"><span data-stu-id="b03d1-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="b03d1-114">Angiv **Serveradressen** for din Common Data Service-organisation, og vælg **Log på**.</span><span class="sxs-lookup"><span data-stu-id="b03d1-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b03d1-115">![Dialogboksen til angivelse af Common Data Service-serveradresse](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="b03d1-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="b03d1-116">Vælg det sæt objekter, som du vil indsætte fra listen med tilgængelige.</span><span class="sxs-lookup"><span data-stu-id="b03d1-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="b03d1-117">Hvis nogle objekter allerede er valgt, vil de muligvis blive brugt af andre Dynamics 365-programmer (fx Dynamics 365 Sales Insights eller Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="b03d1-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="b03d1-118">Du kan ikke ændre markeringen.</span><span class="sxs-lookup"><span data-stu-id="b03d1-118">You can't change the selection.</span></span> <span data-ttu-id="b03d1-119">Disse objekter er tilgængelige, når datakilden er oprettet.</span><span class="sxs-lookup"><span data-stu-id="b03d1-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b03d1-120">![Dialogboks, der viser en liste over objekter i Common Data Service-organisationen](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="b03d1-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="b03d1-121">Gem din markering for at begynde at synkronisere de valgte objekter til den Common Data Service-administrerede sø.</span><span class="sxs-lookup"><span data-stu-id="b03d1-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="b03d1-122">Du kan finde den netop tilføjede forbindelse på siden **-datakilder**.</span><span class="sxs-lookup"><span data-stu-id="b03d1-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="b03d1-123">Det vil blive sat i kø til opdatering og vise antallet af objekter som 0, indtil alle objekterne er synkroniseret.</span><span class="sxs-lookup"><span data-stu-id="b03d1-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="b03d1-124">Kun én datakilde af et miljø kan bruge samme Common Data Service administrerede Data Lake samtidig.</span><span class="sxs-lookup"><span data-stu-id="b03d1-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="b03d1-125">Redigere en Common Data Service-administreret sø-datakilde</span><span class="sxs-lookup"><span data-stu-id="b03d1-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="b03d1-126">Du kan kun redigere objekt-valget, efter du har oprettet datakilden.</span><span class="sxs-lookup"><span data-stu-id="b03d1-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="b03d1-127">Hvis du f.eks. har tilføjet yderligere objekter i Common Data Service, og du også vil importere dem.</span><span class="sxs-lookup"><span data-stu-id="b03d1-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="b03d1-128">Hvis du vil oprette forbindelse til en anden Common Data Service, [skal du oprette en ny datakilde](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="b03d1-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="b03d1-129">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="b03d1-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b03d1-130">Vælg ellipsen ud for den datakilde, du vil opdatere.</span><span class="sxs-lookup"><span data-stu-id="b03d1-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="b03d1-131">Vælg indstillingen **Rediger** på listen.</span><span class="sxs-lookup"><span data-stu-id="b03d1-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="b03d1-132">Vælg yderligere objekter på listen med tilgængelige objekter, og vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="b03d1-132">Select additional entities from the available list of entities and select **Save**.</span></span>
