---
title: Eksperimenter til Azure Machine Learning
description: Brug Azure Machine Learning-baserede modeller i Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668761"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="01c21-103">Brug Azure Machine Learning-baserede modeller</span><span class="sxs-lookup"><span data-stu-id="01c21-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="01c21-104">De samlede data i Dynamics 365 Customer Insights er en kilde til opbygning af maskinelle indlæringsmodeller, der kan generere yderligere forretningsindsigt.</span><span class="sxs-lookup"><span data-stu-id="01c21-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="01c21-105">Customer Insights er integreret med Machine Learning Studio (classic) og Azure Machine Learning til brug af dine egne brugerdefinerede modeller.</span><span class="sxs-lookup"><span data-stu-id="01c21-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="01c21-106">Se [Machine Learning Studio (klassisk)-eksperimenter](machine-learning-studio-experiments.md), hvor der er eksempler på de eksperimenter, der er baseret på Machine Learning Studio (klassisk).</span><span class="sxs-lookup"><span data-stu-id="01c21-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="01c21-107">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="01c21-107">Prerequisites</span></span>

- <span data-ttu-id="01c21-108">Adgang til Customer Insights</span><span class="sxs-lookup"><span data-stu-id="01c21-108">Access to Customer Insights</span></span>
- <span data-ttu-id="01c21-109">Aktivt abonnement på Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="01c21-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="01c21-110">Samlede kundeprofiler</span><span class="sxs-lookup"><span data-stu-id="01c21-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="01c21-111">[Objekteksport til Azure Blob-lager](export-azure-blob-storage.md) konfigureret</span><span class="sxs-lookup"><span data-stu-id="01c21-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="01c21-112">Konfigurer Azure Machine Learning-arbejdsområde</span><span class="sxs-lookup"><span data-stu-id="01c21-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="01c21-113">Se [opret et arbejdsområde i Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for at få vist forskellige indstillinger for oprettelse af arbejdsområdet.</span><span class="sxs-lookup"><span data-stu-id="01c21-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="01c21-114">Du opnår den bedste ydeevne, hvis du opretter arbejdsområdet i et Azure-område, der er nærmest dit Customer Insights-miljø.</span><span class="sxs-lookup"><span data-stu-id="01c21-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="01c21-115">Få adgang til dit arbejdsområde via [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="01c21-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="01c21-116">Du kan kommunikere [interaktivt](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) med dit arbejdsområde på flere måder.</span><span class="sxs-lookup"><span data-stu-id="01c21-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="01c21-117">Arbejd med Azure Machine Learning-designer</span><span class="sxs-lookup"><span data-stu-id="01c21-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="01c21-118">Azure Machine Learning-designer indeholder et visuelt lærred, hvor du kan trække og slippe datasæt og moduler, der ligner Machine Learning Studio (klassisk).</span><span class="sxs-lookup"><span data-stu-id="01c21-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="01c21-119">En batch pipeline, der er oprettet i designeren, kan integreres i Customer Insights, hvis de er konfigureret tilsvarende.</span><span class="sxs-lookup"><span data-stu-id="01c21-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="01c21-120">Arbejd med Azure Machine Learning SDK</span><span class="sxs-lookup"><span data-stu-id="01c21-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="01c21-121">Datateknikere og AI-udviklere bruger [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) til at oprette maskinelle indlæringsprocesser.</span><span class="sxs-lookup"><span data-stu-id="01c21-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="01c21-122">I øjeblikket kan modeller, der oplæres ved hjælp af SDK, ikke integreres direkte med Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="01c21-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="01c21-123">Der kræves en batch pipeline med udledning til den pågældende model for at kunne integrere med Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="01c21-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="01c21-124">Krav til batch pipeline, der skal integreres med Customer Insights</span><span class="sxs-lookup"><span data-stu-id="01c21-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="01c21-125">Konfiguration af datasæt</span><span class="sxs-lookup"><span data-stu-id="01c21-125">Dataset Configuration</span></span>

<span data-ttu-id="01c21-126">Du skal oprette datasæt for at bruge objektdata fra Customer Insights i en batch pipeline med udledning.</span><span class="sxs-lookup"><span data-stu-id="01c21-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="01c21-127">Disse datasæt skal registreres i arbejdsområdet.</span><span class="sxs-lookup"><span data-stu-id="01c21-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="01c21-128">I øjeblikket understøtter vi kun [tabeldatasæt](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) i .csv-format.</span><span class="sxs-lookup"><span data-stu-id="01c21-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="01c21-129">De datasæt, der er knyttet til objektdata, skal have parametre som en pipeline-parameter.</span><span class="sxs-lookup"><span data-stu-id="01c21-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="01c21-130">Datasætparametre i Designer</span><span class="sxs-lookup"><span data-stu-id="01c21-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="01c21-131">I designeren skal du åbne **Vælg kolonner i datasæt** og vælge **Indstil som pipeline-parameter**, hvor du angiver et navn til parameteren.</span><span class="sxs-lookup"><span data-stu-id="01c21-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="01c21-132">![Datasætparametre i Designer](media/intelligence-designer-dataset-parameters.png "Datasætparametre i Designer")</span><span class="sxs-lookup"><span data-stu-id="01c21-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="01c21-133">Datasætparameter i SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="01c21-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="01c21-134">Batch pipeline med udledning</span><span class="sxs-lookup"><span data-stu-id="01c21-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="01c21-135">I designeren kan der bruges en trænings-pipeline til at oprette eller opdatere en pipeline med udledning.</span><span class="sxs-lookup"><span data-stu-id="01c21-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="01c21-136">I øjeblikket understøttes kun batch pipelines med udledning.</span><span class="sxs-lookup"><span data-stu-id="01c21-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="01c21-137">Ved hjælp af SDK kan du publicere en pipeline til et slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="01c21-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="01c21-138">I øjeblikket integreres Customer Insights med en standard-pipeline i en batch pipeline-slutpunkt i Machine Learning-arbejdsområdet.</span><span class="sxs-lookup"><span data-stu-id="01c21-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="01c21-139">Import af pipeline-data til Customer Insights</span><span class="sxs-lookup"><span data-stu-id="01c21-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="01c21-140">Designeren indeholder [Eksportér Data-modulet](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data), der gør det muligt at eksportere output fra en pipeline til Azure-lageret.</span><span class="sxs-lookup"><span data-stu-id="01c21-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="01c21-141">I øjeblikket skal modulet bruge datalagertypen **Azure Blob Storage** og angive parametre for **Datalager** og eventuel **Sti**.</span><span class="sxs-lookup"><span data-stu-id="01c21-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="01c21-142">Customer Insights tilsidesætter både disse parametre under kørsel af pipeline med et datalager og en sti, der er tilgængelig for produktet.</span><span class="sxs-lookup"><span data-stu-id="01c21-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01c21-143">![Eksport af Data Module Configuration](media/intelligence-designer-importdata.png "Eksport af Data Module Configuration")</span><span class="sxs-lookup"><span data-stu-id="01c21-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="01c21-144">Når du skriver udledningsresultatet ved hjælp af kode, kan du overføre outputtet til en sti i et *registreret datalager* i arbejdsområdet.</span><span class="sxs-lookup"><span data-stu-id="01c21-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="01c21-145">Hvis der er angivet parametre for sti og datalager i pipeline, kan Customer Insights læse og importere udledningsoutput.</span><span class="sxs-lookup"><span data-stu-id="01c21-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="01c21-146">I øjeblikket understøttes et enkelt-tabel output i CSV-format.</span><span class="sxs-lookup"><span data-stu-id="01c21-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="01c21-147">Stien skal indeholde mappen og filnavnet.</span><span class="sxs-lookup"><span data-stu-id="01c21-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```
