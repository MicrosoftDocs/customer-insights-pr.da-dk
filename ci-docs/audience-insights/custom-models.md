---
title: Brugerdefinerede maskinelle indlæringsmodeller | Microsoft Docs
description: Arbejde med brugerdefinerede modeller fra Azure Machine Learning i Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 87fb517e9f0b380f9721f77470dceb3bcb7e5616
ms.sourcegitcommit: 55c00ea61c78db7b3b54894c01afb3246dff31c8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/22/2021
ms.locfileid: "5700661"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="bd921-103">Brugerdefinerede maskinelle indlæringsmodeller</span><span class="sxs-lookup"><span data-stu-id="bd921-103">Custom machine learning models</span></span>

<span data-ttu-id="bd921-104">**Intelligens** > **Brugerdefinerede modeller** giver dig mulighed for at administrere arbejdsprocesser baseret på Azure Machine Learning-modeller.</span><span class="sxs-lookup"><span data-stu-id="bd921-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="bd921-105">Arbejdsprocesser hjælper dig med at vælge de data, du vil oprette indsigt fra, og knytte resultaterne til dine samlede kundedata.</span><span class="sxs-lookup"><span data-stu-id="bd921-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="bd921-106">Du kan finde flere oplysninger om oprettelse af brugerdefinerede ML-modeller under [Brug af Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="bd921-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="bd921-107">Ansvarlig AI</span><span class="sxs-lookup"><span data-stu-id="bd921-107">Responsible AI</span></span>

<span data-ttu-id="bd921-108">Forudsigelser indeholder funktioner til oprettelse af bedre kundeoplevelser, forbedring af virksomhedsfunktioner og omsætningsstrømme.</span><span class="sxs-lookup"><span data-stu-id="bd921-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="bd921-109">Det anbefales på det kraftigste, at du balancerer værdien af forudsigelse i forhold til den effekt, den har, og vurderer, at det introduceres på en etisk måde.</span><span class="sxs-lookup"><span data-stu-id="bd921-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="bd921-110">Få mere at vide om, hvordan Microsoft [adresserer ansvarlig AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="bd921-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="bd921-111">Du kan også få mere at vide om [teknikker og processer til maskinel indlæring](/azure/machine-learning/concept-responsible-ml), der er specifikke for Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="bd921-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bd921-112">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="bd921-112">Prerequisites</span></span>

- <span data-ttu-id="bd921-113">I øjeblikket understøtter denne funktion webtjenester, der publiceres via [Machine Learning Studio (klassisk)](https://studio.azureml.net) og [Azure Machine Learning-batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="bd921-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="bd921-114">Du skal have en Azure Data Lake Gen2-lagerkonto, der er knyttet til din Azure Studio-forekomst, for at kunne bruge denne funktion.</span><span class="sxs-lookup"><span data-stu-id="bd921-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="bd921-115">Du kan finde flere oplysninger under [Oprette en Azure Data Lake Storage Gen2-lagerkonto](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="bd921-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="bd921-116">I forbindelse med Azure Machine Learning-arbejdsområder med pipelines skal du have administratortilladelser med ejer- eller brugeradgang til arbejdsområdet Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="bd921-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bd921-117">Data overføres mellem dine Customer Insights-forekomster og de valgte Azure-webtjenester eller pipelines i arbejdsprocessen.</span><span class="sxs-lookup"><span data-stu-id="bd921-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="bd921-118">Når du overfører data til en Azure-service, skal du sikre, at servicen er konfigureret til at behandle data på den måde og placering, der er nødvendig for at overholde eventuelle juridiske eller administrative krav for disse data for din organisation.</span><span class="sxs-lookup"><span data-stu-id="bd921-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="bd921-119">Tilføje en ny arbejdsproces</span><span class="sxs-lookup"><span data-stu-id="bd921-119">Add a new workflow</span></span>

1. <span data-ttu-id="bd921-120">Gå til **Intelligens** > **Brugerdefinerede modeller**, og vælg **Ny arbejdsproces**.</span><span class="sxs-lookup"><span data-stu-id="bd921-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="bd921-121">Giv din brugerdefinerede model et genkendeligt navn i feltet **Navn**.</span><span class="sxs-lookup"><span data-stu-id="bd921-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bd921-122">![Skærmbillede af ruden Ny arbejdsproces](media/new-workflowv2.png "Skærmbillede af ruden Ny arbejdsproces")</span><span class="sxs-lookup"><span data-stu-id="bd921-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="bd921-123">Vælg den organisation, der indeholder webtjenesten, i **Lejer, som indeholder din webtjeneste**.</span><span class="sxs-lookup"><span data-stu-id="bd921-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="bd921-124">Hvis dit Azure Machine Learning-abonnement er i en anden lejer end Customer Insights, skal du vælge **Log på** med dine legitimationsoplysninger for den valgte organisation.</span><span class="sxs-lookup"><span data-stu-id="bd921-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="bd921-125">Vælg de **Arbejdsområder**, der er knyttet til din webtjeneste.</span><span class="sxs-lookup"><span data-stu-id="bd921-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="bd921-126">Der er angivet to sektioner: En til Azure Machine Learning v1 (Machine Learning Studio (klassisk)) og Azure Machine Learning v2 (Azure Machine Learning ).</span><span class="sxs-lookup"><span data-stu-id="bd921-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="bd921-127">Hvis du ikke er sikker på, hvilket arbejdsområde der er den rigtige til din Machine Learning Studio (klassisk)-webtjeneste, skal du vælge **Vilkårlig**.</span><span class="sxs-lookup"><span data-stu-id="bd921-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="bd921-128">Vælg Machine Learning Studio (klassisk)-webtjeneste eller Azure Machine Learning-pipeline i rullelisten **Webtjeneste, der indeholder din model**.</span><span class="sxs-lookup"><span data-stu-id="bd921-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="bd921-129">Vælg derefter **Næste**.</span><span class="sxs-lookup"><span data-stu-id="bd921-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="bd921-130">Få mere at vide om at [udgive en webtjeneste i Machine Learning Studio (klassisk)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="bd921-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="bd921-131">Få mere at vide om, hvordan du [udgiver en pipeline i Azure Machine Learning ved hjælp af designeren](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="bd921-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="bd921-132">Din pipeline skal udgives under et [pipeline-slutpunkt](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="bd921-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="bd921-133">For hvert **Webtjenesteinput** skal du vælge det tilsvarende **Objekt** fra målgruppeindsigter og vælge **Næste**.</span><span class="sxs-lookup"><span data-stu-id="bd921-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="bd921-134">Den brugerdefinerede modelarbejdsproces anvender heuristik til at knytte inputfelterne i webtjenesten til objektattributterne baseret på feltets navn og datatype.</span><span class="sxs-lookup"><span data-stu-id="bd921-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="bd921-135">Du får vist en fejlmeddelelse, hvis et webtjenestefelt ikke kan knyttes til et objekt.</span><span class="sxs-lookup"><span data-stu-id="bd921-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bd921-136">![Konfigurere en arbejdsproces](media/intelligence-screen2-updated.png "Konfigurere en arbejdsproces")</span><span class="sxs-lookup"><span data-stu-id="bd921-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="bd921-137">Angiv følgende egenskaber i **Modeloutputparametre**-trinnet:</span><span class="sxs-lookup"><span data-stu-id="bd921-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="bd921-138">Machine Learning Studio (klassisk)</span><span class="sxs-lookup"><span data-stu-id="bd921-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="bd921-139">Angiv det output **Objektnavn**, som flow for webtjenesteoutputresultater.</span><span class="sxs-lookup"><span data-stu-id="bd921-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="bd921-140">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="bd921-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="bd921-141">Angiv det output **Objektnavn**, som flow for pipeline-outputresultater.</span><span class="sxs-lookup"><span data-stu-id="bd921-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="bd921-142">Vælg **Navn på outputdatalagerparameter** i batch pipeline på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="bd921-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="bd921-143">Vælg **Navn på outputstiparameter** i batch pipeline på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="bd921-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="bd921-144">![Modeloutputparameter-panel](media/intelligence-screen3-outputparameters.png "Modeloutputparameter-panel")</span><span class="sxs-lookup"><span data-stu-id="bd921-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="bd921-145">Vælg den tilsvarende attribut på rullelisten **Kunde-id i resultater**, der identificerer kunder, og vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="bd921-145">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bd921-146">![Relater resultater til Kundedata-panel](media/intelligence-screen4-relatetocustomer.png "Relater resultater til Kundedata-panel")</span><span class="sxs-lookup"><span data-stu-id="bd921-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="bd921-147">Du kan se skærmen **Arbejdsproces blev gemt** med detaljer om arbejdsprocessen.</span><span class="sxs-lookup"><span data-stu-id="bd921-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="bd921-148">Hvis du har konfigureret en arbejdsproces for en Azure Machine Learning pipeline, tilknyttes der målgruppeindsigt til det arbejdsområde, der indeholder pipelinen.</span><span class="sxs-lookup"><span data-stu-id="bd921-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="bd921-149">Målgruppeindsigt får en **Bidragyder**-rolle i Azure-arbejdsområdet.</span><span class="sxs-lookup"><span data-stu-id="bd921-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="bd921-150">Vælg **Udført**.</span><span class="sxs-lookup"><span data-stu-id="bd921-150">Select **Done**.</span></span>

1. <span data-ttu-id="bd921-151">Du kan nu køre arbejdsprocessen fra siden **Brugerdefinerede modeller**.</span><span class="sxs-lookup"><span data-stu-id="bd921-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="bd921-152">Redigere en arbejdsproces</span><span class="sxs-lookup"><span data-stu-id="bd921-152">Edit a workflow</span></span>

1. <span data-ttu-id="bd921-153">På siden **Brugerdefinerede modeller** vælg den lodrette ellipse i kolonnen **Handlinger** ud for en arbejdsproces, som du tidligere har oprettet, og vælg **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="bd921-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="bd921-154">Du kan opdatere arbejdsprocessens genkendelige navn i feltet **Visningsnavn**, men du kan ikke ændre den konfigurerede webtjeneste eller pipeline.</span><span class="sxs-lookup"><span data-stu-id="bd921-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="bd921-155">Vælg **Næste**.</span><span class="sxs-lookup"><span data-stu-id="bd921-155">Select **Next**.</span></span>

1. <span data-ttu-id="bd921-156">For hvert **Webtjenesteinput** skal du vælge det tilsvarende **Objekt** fra målgruppeindsigter.</span><span class="sxs-lookup"><span data-stu-id="bd921-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="bd921-157">Vælg derefter **Næste**.</span><span class="sxs-lookup"><span data-stu-id="bd921-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="bd921-158">Angiv følgende egenskaber i **Modeloutputparametre**-trinnet:</span><span class="sxs-lookup"><span data-stu-id="bd921-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="bd921-159">Machine Learning Studio (klassisk)</span><span class="sxs-lookup"><span data-stu-id="bd921-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="bd921-160">Angiv det output **Objektnavn**, som flow for webtjenesteoutputresultater.</span><span class="sxs-lookup"><span data-stu-id="bd921-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="bd921-161">Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="bd921-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="bd921-162">Angiv det output **Objektnavn**, som flow for pipeline-outputresultater.</span><span class="sxs-lookup"><span data-stu-id="bd921-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="bd921-163">Vælg **Navn på outputdatalager-parameter** for test-pipeline.</span><span class="sxs-lookup"><span data-stu-id="bd921-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="bd921-164">Vælg **Navn på outputstiparameter** for test-pipeline.</span><span class="sxs-lookup"><span data-stu-id="bd921-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="bd921-165">Vælg den tilsvarende attribut på rullelisten **Kunde-id i resultater**, der identificerer kunder, og vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="bd921-165">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="bd921-166">Vælg en attribut fra udledningsoutputtet med værdier, der svarer til kolonnen Kunde-id i kundeobjektet.</span><span class="sxs-lookup"><span data-stu-id="bd921-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="bd921-167">Hvis der ikke findes en sådan kolonne i datasættet, skal du vælge en attribut, der entydigt identificerer rækken.</span><span class="sxs-lookup"><span data-stu-id="bd921-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="bd921-168">Kørsel af en arbejdsproces</span><span class="sxs-lookup"><span data-stu-id="bd921-168">Run a workflow</span></span>

1. <span data-ttu-id="bd921-169">På siden **Brugerdefinerede modeller** vælg den lodrette ellipse i kolonnen **Handlinger** ud for en arbejdsproces, som du tidligere har oprettet.</span><span class="sxs-lookup"><span data-stu-id="bd921-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="bd921-170">Vælg **Kør**.</span><span class="sxs-lookup"><span data-stu-id="bd921-170">Select **Run**.</span></span>

<span data-ttu-id="bd921-171">Arbejdsprocessen kører også automatisk sammen med alle planlagte opdateringer.</span><span class="sxs-lookup"><span data-stu-id="bd921-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="bd921-172">Få mere at vide om [oprettelse af planlagte opdateringer](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bd921-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="bd921-173">Slette en arbejdsproces</span><span class="sxs-lookup"><span data-stu-id="bd921-173">Delete a workflow</span></span>

1. <span data-ttu-id="bd921-174">På siden **Brugerdefinerede modeller** vælg den lodrette ellipse i kolonnen **Handlinger** ud for en arbejdsproces, som du tidligere har oprettet.</span><span class="sxs-lookup"><span data-stu-id="bd921-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="bd921-175">Vælg **Slet**, og bekræft sletningen.</span><span class="sxs-lookup"><span data-stu-id="bd921-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="bd921-176">Din arbejdsproces bliver slettet.</span><span class="sxs-lookup"><span data-stu-id="bd921-176">Your workflow will be deleted.</span></span> <span data-ttu-id="bd921-177">Det [objekt](entities.md), der blev oprettet, da du oprettede arbejdsprocessen, bevares, og du kan få det vist på siden **Objekter**.</span><span class="sxs-lookup"><span data-stu-id="bd921-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="bd921-178">Resultater</span><span class="sxs-lookup"><span data-stu-id="bd921-178">Results</span></span>

<span data-ttu-id="bd921-179">Resultater fra en arbejdsproces gemmes i det objekt, der er konfigureret i fasen Modeloutputparameter.</span><span class="sxs-lookup"><span data-stu-id="bd921-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="bd921-180">Du kan få adgang til disse data fra [objektsiden](entities.md) eller med [API-adgang](apis.md).</span><span class="sxs-lookup"><span data-stu-id="bd921-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="bd921-181">API-adgang</span><span class="sxs-lookup"><span data-stu-id="bd921-181">API Access</span></span>

<span data-ttu-id="bd921-182">Hvis den specifikke OData-forespørgsel skal hente data fra et brugerdefineret modelobjekt, skal du bruge følgende format:</span><span class="sxs-lookup"><span data-stu-id="bd921-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="bd921-183">Erstat `<your instance id>` med id'et for dit Customer Insights-miljø, som du finder på adresselinjen i din browser ved adgang til Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bd921-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="bd921-184">Erstat `<custom model output entity>` med det objektnavn, du har angivet i trinnet Modeloutputparametre i konfigurationen af den brugerdefinerede model.</span><span class="sxs-lookup"><span data-stu-id="bd921-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="bd921-185">Erstat `<guid value>` med kunde-id'et for den kunde, som du vil have adgang til posten for.</span><span class="sxs-lookup"><span data-stu-id="bd921-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="bd921-186">Du kan som regel finde dette id på [siden kundeprofiler](customer-profiles.md) i feltet CustomerID.</span><span class="sxs-lookup"><span data-stu-id="bd921-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="bd921-187">Ofte stillede spørgsmål</span><span class="sxs-lookup"><span data-stu-id="bd921-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="bd921-188">Hvorfor kan jeg ikke se min pipeline, når jeg konfigurerer en brugerdefineret modelarbejdsproces?</span><span class="sxs-lookup"><span data-stu-id="bd921-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="bd921-189">Dette problem skyldes ofte et konfigurationsproblem i pipelinen.</span><span class="sxs-lookup"><span data-stu-id="bd921-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="bd921-190">Sørg for, at [inputparameteren er konfigureret](azure-machine-learning-experiments.md#dataset-configuration), og at [outputdataene og stiparametrene](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) også er konfigureret.</span><span class="sxs-lookup"><span data-stu-id="bd921-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="bd921-191">Hvad betyder fejlen "Intelligensarbejdsprocessen kunne ikke gemmes"?</span><span class="sxs-lookup"><span data-stu-id="bd921-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="bd921-192">Brugernefår som regel denne fejlmeddelelse, hvis de ikke har administratorrettigheder som Ejer eller Brugeradgang til arbejdsområdet.</span><span class="sxs-lookup"><span data-stu-id="bd921-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="bd921-193">Brugeren skal have et højere tilladelsesniveau for at få Customer Insights til at behandle arbejdsprocessen som en tjeneste i stedet for brugerlegitimationsoplysningerne til efterfølgende kørsler af arbejdsprocessen.</span><span class="sxs-lookup"><span data-stu-id="bd921-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
