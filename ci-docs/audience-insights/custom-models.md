---
title: Brugerdefinerede maskinelle indlæringsmodeller | Microsoft Docs
description: Arbejde med brugerdefinerede modeller fra Azure Machine Learning i Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267227"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="5570e-103">Brugerdefinerede maskinelle indlæringsmodeller</span><span class="sxs-lookup"><span data-stu-id="5570e-103">Custom machine learning models</span></span>

<span data-ttu-id="5570e-104">**Intelligens** > **Brugerdefinerede modeller** giver dig mulighed for at administrere arbejdsprocesser baseret på Azure Machine Learning-modeller.</span><span class="sxs-lookup"><span data-stu-id="5570e-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="5570e-105">Arbejdsprocesser hjælper dig med at vælge de data, du vil oprette indsigt fra, og knytte resultaterne til dine samlede kundedata.</span><span class="sxs-lookup"><span data-stu-id="5570e-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="5570e-106">Du kan finde flere oplysninger om oprettelse af brugerdefinerede ML-modeller under [Brug af Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="5570e-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="5570e-107">Ansvarlig AI</span><span class="sxs-lookup"><span data-stu-id="5570e-107">Responsible AI</span></span>

<span data-ttu-id="5570e-108">Forudsigelser indeholder funktioner til oprettelse af bedre kundeoplevelser, forbedring af virksomhedsfunktioner og omsætningsstrømme.</span><span class="sxs-lookup"><span data-stu-id="5570e-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="5570e-109">Det anbefales på det kraftigste, at du balancerer værdien af forudsigelse i forhold til den effekt, den har, og vurderer, at det introduceres på en etisk måde.</span><span class="sxs-lookup"><span data-stu-id="5570e-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="5570e-110">Få mere at vide om, hvordan Microsoft [adresserer ansvarlig AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="5570e-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="5570e-111">Du kan også få mere at vide om [teknikker og processer til maskinel indlæring](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml), der er specifikke for Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="5570e-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5570e-112">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="5570e-112">Prerequisites</span></span>

- <span data-ttu-id="5570e-113">I øjeblikket understøtter denne funktion webtjenester, der publiceres via [Machine Learning Studio (klassisk)](https://studio.azureml.net) og [Azure Machine Learning-batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="5570e-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="5570e-114">Du skal have en Azure Data Lake Gen2-lagerkonto, der er knyttet til din Azure Studio-forekomst, for at kunne bruge denne funktion.</span><span class="sxs-lookup"><span data-stu-id="5570e-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="5570e-115">Du kan finde flere oplysninger under [Oprette en Azure Data Lake Storage Gen2-lagerkonto](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="5570e-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="5570e-116">Tilføje en ny arbejdsproces</span><span class="sxs-lookup"><span data-stu-id="5570e-116">Add a new workflow</span></span>

1. <span data-ttu-id="5570e-117">Gå til **Intelligens** > **Brugerdefinerede modeller**, og vælg **Ny arbejdsproces**.</span><span class="sxs-lookup"><span data-stu-id="5570e-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="5570e-118">Giv din brugerdefinerede model et genkendeligt navn i feltet **Navn**.</span><span class="sxs-lookup"><span data-stu-id="5570e-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5570e-119">![Skærmbillede af ruden Ny arbejdsproces](media/new-workflowv2.png "Skærmbillede af ruden Ny arbejdsproces")</span><span class="sxs-lookup"><span data-stu-id="5570e-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="5570e-120">Vælg den organisation, der indeholder webtjenesten, i **Lejer, som indeholder din webtjeneste**.</span><span class="sxs-lookup"><span data-stu-id="5570e-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="5570e-121">Hvis dit Azure Machine Learning-abonnement er i en anden lejer end Customer Insights, skal du vælge **Log på** med dine legitimationsoplysninger for den valgte organisation.</span><span class="sxs-lookup"><span data-stu-id="5570e-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="5570e-122">Vælg de **Arbejdsområder**, der er knyttet til din webtjeneste.</span><span class="sxs-lookup"><span data-stu-id="5570e-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="5570e-123">Der er angivet to sektioner: En til Azure Machine Learning v1 (Machine Learning Studio (klassisk)) og Azure Machine Learning v2 (Azure Machine Learning ).</span><span class="sxs-lookup"><span data-stu-id="5570e-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="5570e-124">Hvis du ikke er sikker på, hvilket arbejdsområde der er den rigtige til din Machine Learning Studio (klassisk)-webtjeneste, skal du vælge **Vilkårlig**.</span><span class="sxs-lookup"><span data-stu-id="5570e-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="5570e-125">Vælg Machine Learning Studio (klassisk)-webtjeneste eller Azure Machine Learning-pipeline i rullelisten **Webtjeneste, der indeholder din model**.</span><span class="sxs-lookup"><span data-stu-id="5570e-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="5570e-126">Vælg derefter **Næste**.</span><span class="sxs-lookup"><span data-stu-id="5570e-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="5570e-127">Få mere at vide om at [udgive en webtjeneste i Machine Learning Studio (klassisk)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="5570e-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="5570e-128">Få mere at vide om, hvordan du [udgiver en pipeline i Azure Machine Learning ved hjælp af designeren](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="5570e-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="5570e-129">Din pipeline skal udgives under et [pipeline-slutpunkt](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="5570e-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="5570e-130">For hvert **Webtjenesteinput** skal du vælge det tilsvarende **Objekt** fra målgruppeindsigter og vælge **Næste**.</span><span class="sxs-lookup"><span data-stu-id="5570e-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="5570e-131">Den brugerdefinerede modelarbejdsproces anvender heuristik til at knytte inputfelterne i webtjenesten til objektattributterne baseret på feltets navn og datatype.</span><span class="sxs-lookup"><span data-stu-id="5570e-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="5570e-132">Du får vist en fejlmeddelelse, hvis et webtjenestefelt ikke kan knyttes til et objekt.</span><span class="sxs-lookup"><span data-stu-id="5570e-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5570e-133">![Konfigurere en arbejdsproces](media/intelligence-screen2-updated.png "Konfigurere en arbejdsproces")</span><span class="sxs-lookup"><span data-stu-id="5570e-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="5570e-134">Angiv følgende egenskaber i **Modeloutputparametre**-trinnet:</span><span class="sxs-lookup"><span data-stu-id="5570e-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="5570e-135">Machine Learning Studio (klassisk)</span><span class="sxs-lookup"><span data-stu-id="5570e-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="5570e-136">Angiv det output **Objektnavn**, som flow for webtjenesteoutputresultater.</span><span class="sxs-lookup"><span data-stu-id="5570e-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="5570e-137">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="5570e-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="5570e-138">Angiv det output **Objektnavn**, som flow for pipeline-outputresultater.</span><span class="sxs-lookup"><span data-stu-id="5570e-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="5570e-139">Vælg **Navn på outputdatalagerparameter** i batch pipeline på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="5570e-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="5570e-140">Vælg **Navn på outputstiparameter** i batch pipeline på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="5570e-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="5570e-141">![Modeloutputparameter-panel](media/intelligence-screen3-outputparameters.png "Modeloutputparameter-panel")</span><span class="sxs-lookup"><span data-stu-id="5570e-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="5570e-142">Vælg den tilsvarende attribut på rullelisten **Kunde-id i resultater**, der identificerer kunder, og vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="5570e-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5570e-143">![Relater resultater til Kundedata-panel](media/intelligence-screen4-relatetocustomer.png "Relater resultater til Kundedata-panel")</span><span class="sxs-lookup"><span data-stu-id="5570e-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="5570e-144">Du kan se skærmen **Arbejdsproces blev gemt** med detaljer om arbejdsprocessen.</span><span class="sxs-lookup"><span data-stu-id="5570e-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="5570e-145">Hvis du har konfigureret en arbejdsproces for en Azure Machine Learning pipeline, tilknyttes der målgruppeindsigt til det arbejdsområde, der indeholder pipelinen.</span><span class="sxs-lookup"><span data-stu-id="5570e-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="5570e-146">Målgruppeindsigt får en **Bidragyder**-rolle i Azure-arbejdsområdet.</span><span class="sxs-lookup"><span data-stu-id="5570e-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="5570e-147">Vælg **Udført**.</span><span class="sxs-lookup"><span data-stu-id="5570e-147">Select **Done**.</span></span>

1. <span data-ttu-id="5570e-148">Du kan nu køre arbejdsprocessen fra siden **Brugerdefinerede modeller**.</span><span class="sxs-lookup"><span data-stu-id="5570e-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="5570e-149">Redigere en arbejdsproces</span><span class="sxs-lookup"><span data-stu-id="5570e-149">Edit a workflow</span></span>

1. <span data-ttu-id="5570e-150">På siden **Brugerdefinerede modeller** vælg den lodrette ellipse i kolonnen **Handlinger** ud for en arbejdsproces, som du tidligere har oprettet, og vælg **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="5570e-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="5570e-151">Du kan opdatere arbejdsprocessens genkendelige navn i feltet **Visningsnavn**, men du kan ikke ændre den konfigurerede webtjeneste eller pipeline.</span><span class="sxs-lookup"><span data-stu-id="5570e-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="5570e-152">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="5570e-152">Select **Next**.</span></span>

1. <span data-ttu-id="5570e-153">For hvert **Webtjenesteinput** skal du vælge det tilsvarende **Objekt** fra målgruppeindsigter.</span><span class="sxs-lookup"><span data-stu-id="5570e-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="5570e-154">Vælg derefter **Næste**.</span><span class="sxs-lookup"><span data-stu-id="5570e-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="5570e-155">Angiv følgende egenskaber i **Modeloutputparametre**-trinnet:</span><span class="sxs-lookup"><span data-stu-id="5570e-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="5570e-156">Machine Learning Studio (klassisk)</span><span class="sxs-lookup"><span data-stu-id="5570e-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="5570e-157">Angiv det output **Objektnavn**, som flow for webtjenesteoutputresultater.</span><span class="sxs-lookup"><span data-stu-id="5570e-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="5570e-158">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="5570e-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="5570e-159">Angiv det output **Objektnavn**, som flow for pipeline-outputresultater.</span><span class="sxs-lookup"><span data-stu-id="5570e-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="5570e-160">Vælg **Navn på outputdatalager-parameter** for test-pipeline.</span><span class="sxs-lookup"><span data-stu-id="5570e-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="5570e-161">Vælg **Navn på outputstiparameter** for test-pipeline.</span><span class="sxs-lookup"><span data-stu-id="5570e-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="5570e-162">Vælg den tilsvarende attribut på rullelisten **Kunde-id i resultater**, der identificerer kunder, og vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="5570e-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="5570e-163">Du skal vælge en attribut fra udledningsoutputtet med værdier, der svarer til kolonnen Kunde-ID i kundeobjektet.</span><span class="sxs-lookup"><span data-stu-id="5570e-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="5570e-164">Hvis der ikke findes en sådan kolonne i datasættet, skal du vælge en attribut, der entydigt identificerer rækken.</span><span class="sxs-lookup"><span data-stu-id="5570e-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="5570e-165">Kørsel af en arbejdsproces</span><span class="sxs-lookup"><span data-stu-id="5570e-165">Run a workflow</span></span>

1. <span data-ttu-id="5570e-166">På siden **Brugerdefinerede modeller** vælg den lodrette ellipse i kolonnen **Handlinger** ud for en arbejdsproces, som du tidligere har oprettet.</span><span class="sxs-lookup"><span data-stu-id="5570e-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="5570e-167">Vælg **Kør**.</span><span class="sxs-lookup"><span data-stu-id="5570e-167">Select **Run**.</span></span>

<span data-ttu-id="5570e-168">Arbejdsprocessen kører også automatisk sammen med alle planlagte opdateringer.</span><span class="sxs-lookup"><span data-stu-id="5570e-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="5570e-169">Få mere at vide om [oprettelse af planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5570e-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="5570e-170">Slette en arbejdsproces</span><span class="sxs-lookup"><span data-stu-id="5570e-170">Delete a workflow</span></span>

1. <span data-ttu-id="5570e-171">På siden **Brugerdefinerede modeller** vælg den lodrette ellipse i kolonnen **Handlinger** ud for en arbejdsproces, som du tidligere har oprettet.</span><span class="sxs-lookup"><span data-stu-id="5570e-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="5570e-172">Vælg **Slet**, og bekræft sletningen.</span><span class="sxs-lookup"><span data-stu-id="5570e-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="5570e-173">Din arbejdsproces bliver slettet.</span><span class="sxs-lookup"><span data-stu-id="5570e-173">Your workflow will be deleted.</span></span> <span data-ttu-id="5570e-174">Det [objekt](entities.md), der blev oprettet, da du oprettede arbejdsprocessen, bevares, og du kan få det vist på siden **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="5570e-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]