---
title: Forbind almindelig datamodeldata til en Azure Data Lake-konto
description: Arbejd med Common Data Model-data ved hjælp af Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267853"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="31e22-103">Tilknyt en Common Data Model med en Azure Data Lake-konto</span><span class="sxs-lookup"><span data-stu-id="31e22-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="31e22-104">Denne artikel indeholder oplysninger om, hvordan du kan indsætte data fra en Common Data Model-mappe ved hjælp af din Azure Data Lake Storage Gen2-konto.</span><span class="sxs-lookup"><span data-stu-id="31e22-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="31e22-105">Vigtige overvejelser</span><span class="sxs-lookup"><span data-stu-id="31e22-105">Important considerations</span></span>

- <span data-ttu-id="31e22-106">Data i Azure Data Lake skal følge Common Data Model-standarden.</span><span class="sxs-lookup"><span data-stu-id="31e22-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="31e22-107">Andre formater understøttes ikke i øjeblikket.</span><span class="sxs-lookup"><span data-stu-id="31e22-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="31e22-108">Dataindsættelse understøtter udelukkende Azure Data Lake *Gen2*-lagerkonti.</span><span class="sxs-lookup"><span data-stu-id="31e22-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="31e22-109">Du kan ikke bruge Azure Data Lake Gen1-lagerkonti til indsættelse af data.</span><span class="sxs-lookup"><span data-stu-id="31e22-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="31e22-110">Hvis du vil godkende med en Azure-tjenestekonto, skal du sørge for, at den er konfigureret i din lejer.</span><span class="sxs-lookup"><span data-stu-id="31e22-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="31e22-111">Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="31e22-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="31e22-112">Den Azure Data Lake, som du vil oprette forbindelse til og hente data fra, skal være i samme Azure-område som Dynamics 365 Customer Insights-miljøet.</span><span class="sxs-lookup"><span data-stu-id="31e22-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="31e22-113">Forbindelser til en Common Data Model-mappe fra en Data Lake i et andet Azure-område understøttes ikke.</span><span class="sxs-lookup"><span data-stu-id="31e22-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="31e22-114">Du kan se Azure-området for miljøet ved at gå til **Admin** > **System** > **Om** i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="31e22-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="31e22-115">Data, der lagres i onlinetjenester, kan gemmes på en anden placering end det sted, hvor dataene behandles eller lagres i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="31e22-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="31e22-116">Ved at importere eller oprette forbindelse til data, der er gemt i onlinetjenester, accepterer du, at data kan overføres til og gemmes sammen med Dynamics 365 Customer Insights.  [Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="31e22-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="31e22-117">Opret forbindelse til en Common Data Model-mappe</span><span class="sxs-lookup"><span data-stu-id="31e22-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="31e22-118">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="31e22-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="31e22-119">Vælg **Tilføj datakilde**.</span><span class="sxs-lookup"><span data-stu-id="31e22-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="31e22-120">Vælg **Opret forbindelse til Common Data model-mappe**, angiv et **Navn** for datakilde, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="31e22-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="31e22-121">Navneretningslinjer:</span><span class="sxs-lookup"><span data-stu-id="31e22-121">Name guidelines:</span></span> 
   - <span data-ttu-id="31e22-122">Start med et bogstav.</span><span class="sxs-lookup"><span data-stu-id="31e22-122">Start with a letter.</span></span>
   - <span data-ttu-id="31e22-123">Brug kun bogstaver og tal.</span><span class="sxs-lookup"><span data-stu-id="31e22-123">Use letters and numbers only.</span></span> <span data-ttu-id="31e22-124">Specialtegn og mellemrum er ikke tilladt.</span><span class="sxs-lookup"><span data-stu-id="31e22-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="31e22-125">Brug mellem 3 og 64 tegn.</span><span class="sxs-lookup"><span data-stu-id="31e22-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="31e22-126">Du kan vælge mellem at bruge en ressourcebaseret indstilling og en abonnementsbaseret indstilling til godkendelse.</span><span class="sxs-lookup"><span data-stu-id="31e22-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="31e22-127">Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="31e22-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="31e22-128">Angiv oplysninger om **Objektbeholder**, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="31e22-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="31e22-129">![Dialogboks, hvor du kan angive nye forbindelsesdetaljer for Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="31e22-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="31e22-130">Du skal bruge en af følgende roller i enten beholderen eller lagerkontoen, der er nævnt ovenfor, for at du kan oprette forbindelse til og oprette en datakilde:</span><span class="sxs-lookup"><span data-stu-id="31e22-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="31e22-131">Lager for Blob-datalæser</span><span class="sxs-lookup"><span data-stu-id="31e22-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="31e22-132">Lager for Blob-dataejer</span><span class="sxs-lookup"><span data-stu-id="31e22-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="31e22-133">Lager for Blob Data-bidragyder</span><span class="sxs-lookup"><span data-stu-id="31e22-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="31e22-134">I dialogboksen **Vælg en Common Data Model-mappe** skal du vælge den model.json- eller manifest.json-fil, du vil importere data fra, og vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="31e22-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="31e22-135">Alle model.json- eller manifest.json-filer, der er knyttet til andre datakilder i miljøet, vises ikke på listen.</span><span class="sxs-lookup"><span data-stu-id="31e22-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="31e22-136">Du får vist en liste over tilgængelige objekter i den valgte model.json- eller manifest.json-fil.</span><span class="sxs-lookup"><span data-stu-id="31e22-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="31e22-137">Du kan se og foretage valg på listen med tilgængelige objekter og vælge **Gem**.</span><span class="sxs-lookup"><span data-stu-id="31e22-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="31e22-138">Alle de valgte objekter hentes fra den nye datakilde.</span><span class="sxs-lookup"><span data-stu-id="31e22-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="31e22-139">![Dialogboks, der viser en liste over objekter fra en model.json-fil](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="31e22-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="31e22-140">Angiv, hvilke dataobjekter du vil aktivere dataprofilering for, og vælge **Gem**.</span><span class="sxs-lookup"><span data-stu-id="31e22-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="31e22-141">Dataprofilering muliggør analyser og andre funktioner.</span><span class="sxs-lookup"><span data-stu-id="31e22-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="31e22-142">Du kan vælge hele objektet, som vælger alle attributter fra objektet, eller selv vælge bestemte attributter.</span><span class="sxs-lookup"><span data-stu-id="31e22-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="31e22-143">Som standard er intet objekt aktiveret for dataprofilering.</span><span class="sxs-lookup"><span data-stu-id="31e22-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="31e22-144">![Dialogboks, der viser en dataprofil](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="31e22-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="31e22-145">Når du har gemt dine valg, åbnes siden **Datakilder**.</span><span class="sxs-lookup"><span data-stu-id="31e22-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="31e22-146">Du bør nu kunne se Common Data Model-mappeforbindelsen som en datakilde.</span><span class="sxs-lookup"><span data-stu-id="31e22-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="31e22-147">En model.json- eller manifest.json-fil kan kun knyttes til én datakilde i det samme miljø.</span><span class="sxs-lookup"><span data-stu-id="31e22-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="31e22-148">Men den samme model.json- eller manifest.json-fil kan bruges til datakilder i flere miljøer.</span><span class="sxs-lookup"><span data-stu-id="31e22-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="31e22-149">Redigere en datakilde til en Common Data Model-mappe</span><span class="sxs-lookup"><span data-stu-id="31e22-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="31e22-150">Du kan opdatere adgangsnøglen til den lagerkonto, der indeholder Common Data Model-mappen.</span><span class="sxs-lookup"><span data-stu-id="31e22-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="31e22-151">Du kan også ændre model.json- eller manifest.json-filen.</span><span class="sxs-lookup"><span data-stu-id="31e22-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="31e22-152">Hvis du vil oprette forbindelse til en anden objektbeholder fra lagerkontoen eller ændre kontonavnet, skal du [oprette en ny datakildeforbindelse](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="31e22-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="31e22-153">Gå til **Data** > **Datakilder** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="31e22-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="31e22-154">Vælg ellipsen ud for den datakilde, du vil opdatere.</span><span class="sxs-lookup"><span data-stu-id="31e22-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="31e22-155">Vælg indstillingen **Rediger** på listen.</span><span class="sxs-lookup"><span data-stu-id="31e22-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="31e22-156">Du kan også vælge at opdatere **Adgangsnøgle** og vælge **Næste**.</span><span class="sxs-lookup"><span data-stu-id="31e22-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialogboks til redigering og opdatering af en adgangsnøgle til en eksisterende datakilde](media/edit-access-key.png)

5. <span data-ttu-id="31e22-158">Du kan også vælge at opdatere fra en kontonøgleforbindelse til en ressourcebaseret eller en abonnementsbaseret forbindelse.</span><span class="sxs-lookup"><span data-stu-id="31e22-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="31e22-159">Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="31e22-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="31e22-160">Du kan ikke ændre **objektbeholder**-oplysninger, når du opdaterer forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="31e22-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Dialogboks, hvor du kan angive forbindelsesdetaljer for Azure Data Lake til en eksisterende lagerkonto](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="31e22-162">Du skal bruge en af følgende roller i enten beholderen eller lagerkontoen, der er nævnt ovenfor, for at du kan oprette forbindelse til og oprette en datakilde:</span><span class="sxs-lookup"><span data-stu-id="31e22-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="31e22-163">Lager for Blob-datalæser</span><span class="sxs-lookup"><span data-stu-id="31e22-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="31e22-164">Lager for Blob-dataejer</span><span class="sxs-lookup"><span data-stu-id="31e22-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="31e22-165">Lager for Blob Data-bidragyder</span><span class="sxs-lookup"><span data-stu-id="31e22-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="31e22-166">Du kan også vælge en anden model.json- eller manifest.json-fil med et andet sæt objekter fra beholderen.</span><span class="sxs-lookup"><span data-stu-id="31e22-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="31e22-167">Du kan også vælge yderligere objekter, der skal indsættes.</span><span class="sxs-lookup"><span data-stu-id="31e22-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="31e22-168">Du kan også fjerne eventuelle objekter, der allerede er valgt, hvis der ikke er afhængigheder.</span><span class="sxs-lookup"><span data-stu-id="31e22-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="31e22-169">Hvis der er afhængigheder i den eksisterende model.json- eller manifest.json-fil og i sættet af objekter, vises der en fejlmeddelelse, og du kan ikke vælge en anden model.json- eller manifest.json-fil.</span><span class="sxs-lookup"><span data-stu-id="31e22-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="31e22-170">Fjern disse afhængigheder, før du ændrer filen model.json eller manifest.json eller opretter en ny datakilde med den model.json- eller manifest.json-fil, du vil bruge for at undgå at fjerne afhængighederne.</span><span class="sxs-lookup"><span data-stu-id="31e22-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="31e22-171">Alternativt kan du vælge yderligere attributter eller objekter for at aktivere dataprofilering eller deaktivere allerede markerede.</span><span class="sxs-lookup"><span data-stu-id="31e22-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]