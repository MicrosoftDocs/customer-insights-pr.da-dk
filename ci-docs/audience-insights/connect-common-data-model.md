---
title: Forbind almindelig datamodeldata til en Azure Data Lake-konto
description: Arbejd med Common Data Model-data ved hjælp af Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643451"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="ba999-103">Tilknyt en Common Data Model med en Azure Data Lake-konto</span><span class="sxs-lookup"><span data-stu-id="ba999-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="ba999-104">Denne artikel indeholder oplysninger om, hvordan du kan indsætte data fra en Common Data Model-mappe ved hjælp af din Azure Data Lake Storage Gen2-konto.</span><span class="sxs-lookup"><span data-stu-id="ba999-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="ba999-105">Vigtige overvejelser</span><span class="sxs-lookup"><span data-stu-id="ba999-105">Important considerations</span></span>

- <span data-ttu-id="ba999-106">Data i Azure Data Lake skal følge Common Data Model-standarden.</span><span class="sxs-lookup"><span data-stu-id="ba999-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="ba999-107">Andre formater understøttes ikke i øjeblikket.</span><span class="sxs-lookup"><span data-stu-id="ba999-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="ba999-108">Dataindsættelse understøtter udelukkende Azure Data Lake *Gen2*-lagerkonti.</span><span class="sxs-lookup"><span data-stu-id="ba999-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="ba999-109">Du kan ikke bruge Azure Data Lake Gen1-lagerkonti til indsættelse af data.</span><span class="sxs-lookup"><span data-stu-id="ba999-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="ba999-110">Hvis du vil godkende med en Azure-tjenestekonto, skal du sørge for, at den er konfigureret i din lejer.</span><span class="sxs-lookup"><span data-stu-id="ba999-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="ba999-111">Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="ba999-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="ba999-112">Den Azure Data Lake, som du vil oprette forbindelse til og hente data fra, skal være i samme Azure-område som Dynamics 365 Customer Insights-miljøet.</span><span class="sxs-lookup"><span data-stu-id="ba999-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="ba999-113">Forbindelser til en Common Data Model-mappe fra en Data Lake i et andet Azure-område understøttes ikke.</span><span class="sxs-lookup"><span data-stu-id="ba999-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="ba999-114">Du kan se Azure-området for miljøet ved at gå til **Admin** > **System** > **Om** i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="ba999-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="ba999-115">Data, der lagres i onlinetjenester, kan gemmes på en anden placering end det sted, hvor dataene behandles eller lagres i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ba999-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="ba999-116">Ved at importere eller oprette forbindelse til data, der er gemt i onlinetjenester, accepterer du, at data kan overføres til og gemmes sammen med Dynamics 365 Customer Insights.  [Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="ba999-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="ba999-117">Opret forbindelse til en Common Data Model-mappe</span><span class="sxs-lookup"><span data-stu-id="ba999-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="ba999-118">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="ba999-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="ba999-119">Vælg **Tilføj datakilde**.</span><span class="sxs-lookup"><span data-stu-id="ba999-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="ba999-120">Vælg **Opret forbindelse til Common Data model-mappe**, angiv et **Navn** for datakilde, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="ba999-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="ba999-121">Du kan vælge mellem at bruge en ressourcebaseret indstilling og en abonnementsbaseret indstilling til godkendelse.</span><span class="sxs-lookup"><span data-stu-id="ba999-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="ba999-122">Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="ba999-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="ba999-123">Angiv oplysninger om **Objektbeholder**, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="ba999-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba999-124">![Dialogboksen til angivelse af forbindelsesoplysninger for Azure Data Lake](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="ba999-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="ba999-125">I dialogboksen **Vælg en Common Data Model-mappe** skal du vælge den model.json-fil, du vil importere data fra, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="ba999-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="ba999-126">Alle model.json-filer, der er knyttet til andre datakilder i miljøet, vises ikke på listen.</span><span class="sxs-lookup"><span data-stu-id="ba999-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="ba999-127">Du får vist en liste over tilgængelige objekter i den valgte model.json-fil.</span><span class="sxs-lookup"><span data-stu-id="ba999-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="ba999-128">Du kan se og foretage valg på listen med tilgængelige objekter og vælge **Gem**.</span><span class="sxs-lookup"><span data-stu-id="ba999-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="ba999-129">Alle de valgte objekter hentes fra den nye datakilde.</span><span class="sxs-lookup"><span data-stu-id="ba999-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba999-130">![Dialogboks, der viser en liste over objekter fra en model.json-fil](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="ba999-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="ba999-131">Angiv, hvilke dataobjekter du vil aktivere dataprofilering for, og vælge **Gem**.</span><span class="sxs-lookup"><span data-stu-id="ba999-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="ba999-132">Dataprofilering muliggør analyser og andre funktioner.</span><span class="sxs-lookup"><span data-stu-id="ba999-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="ba999-133">Du kan vælge hele objektet, som vælger alle attributter fra objektet, eller selv vælge bestemte attributter.</span><span class="sxs-lookup"><span data-stu-id="ba999-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="ba999-134">Som standard er intet objekt aktiveret for dataprofilering.</span><span class="sxs-lookup"><span data-stu-id="ba999-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba999-135">![Dialogboks, der viser en dataprofil](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="ba999-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="ba999-136">Når du har gemt dine valg, åbnes siden **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="ba999-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="ba999-137">Du bør nu kunne se Common Data Model-mappeforbindelsen som en datakilde.</span><span class="sxs-lookup"><span data-stu-id="ba999-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="ba999-138">En model.json-fil kan kun knyttes til én datakilde i det samme miljø.</span><span class="sxs-lookup"><span data-stu-id="ba999-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="ba999-139">Men den samme model.json-fil kan bruges til datakilder i flere miljøer.</span><span class="sxs-lookup"><span data-stu-id="ba999-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="ba999-140">Redigere en datakilde til en Common Data Model-mappe</span><span class="sxs-lookup"><span data-stu-id="ba999-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="ba999-141">Du kan opdatere adgangsnøglen til den lagerkonto, der indeholder Common Data Model-mappen.</span><span class="sxs-lookup"><span data-stu-id="ba999-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="ba999-142">Du kan også ændre model.json-filen.</span><span class="sxs-lookup"><span data-stu-id="ba999-142">You may also change the model.json file.</span></span> <span data-ttu-id="ba999-143">Hvis du vil oprette forbindelse til en anden objektbeholder fra lagerkontoen eller ændre kontonavnet, skal du [oprette en ny datakildeforbindelse](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="ba999-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="ba999-144">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="ba999-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="ba999-145">Vælg ellipsen ud for den datakilde, du vil opdatere.</span><span class="sxs-lookup"><span data-stu-id="ba999-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="ba999-146">Vælg indstillingen **Rediger** på listen.</span><span class="sxs-lookup"><span data-stu-id="ba999-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="ba999-147">Du kan også vælge at opdatere **Adgangsnøgle** og vælge **Næste**.</span><span class="sxs-lookup"><span data-stu-id="ba999-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialogboks til redigering og opdatering af en adgangsnøgle til en eksisterende datakilde](media/edit-access-key.png)

5. <span data-ttu-id="ba999-149">Du kan også vælge at opdatere fra en kontonøgleforbindelse til en ressourcebaseret eller en abonnementsbaseret forbindelse.</span><span class="sxs-lookup"><span data-stu-id="ba999-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="ba999-150">Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="ba999-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="ba999-151">Du kan ikke ændre **objektbeholder**-oplysninger, når du opdaterer forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="ba999-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba999-152">![Dialogboksen til angivelse af forbindelsesoplysninger for Azure Data Lake](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="ba999-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="ba999-153">Du kan også vælge en anden model.json-fil med et andet sæt objekter fra beholderen.</span><span class="sxs-lookup"><span data-stu-id="ba999-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="ba999-154">Du kan også vælge yderligere objekter, der skal indsættes.</span><span class="sxs-lookup"><span data-stu-id="ba999-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="ba999-155">Du kan også fjerne eventuelle objekter, der allerede er valgt, hvis der ikke er afhængigheder.</span><span class="sxs-lookup"><span data-stu-id="ba999-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ba999-156">Hvis der er afhængigheder i den eksisterende model.json-fil og i sættet af objekter, får du vist en fejlmeddelelse, og du kan ikke vælge en anden model.json-fil.</span><span class="sxs-lookup"><span data-stu-id="ba999-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="ba999-157">Fjern disse afhængigheder, før du ændrer model.json-filen, eller opret en ny datakilde med den model.json-fil, du vil bruge, for at undgå at fjerne afhængighederne.</span><span class="sxs-lookup"><span data-stu-id="ba999-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="ba999-158">Alternativt kan du vælge yderligere attributter eller objekter for at aktivere dataprofilering eller deaktivere allerede markerede.</span><span class="sxs-lookup"><span data-stu-id="ba999-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
