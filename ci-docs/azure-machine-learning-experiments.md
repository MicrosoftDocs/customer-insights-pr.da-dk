---
title: Brug Azure Machine Learning-baserede modeller
description: Brug Azure Machine Learning-baserede modeller i Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a1efad2887a02a92ee2960b07b066edc331f3665
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081017"
---
# <a name="use-azure-machine-learning-based-models"></a>Brug Azure Machine Learning-baserede modeller

De samlede data i Dynamics 365 Customer Insights er en kilde til opbygning af maskinelle indlæringsmodeller, der kan generere yderligere forretningsindsigt. Customer Insights er integreret i Azure Machine Learning, så du kan bruge dine egne brugerdefinerede modeller.

## <a name="prerequisites"></a>Forudsætninger

- Adgang til Customer Insights
- Aktivt abonnement på Azure Enterprise
- [Samlede kundeprofiler](data-unification.md)
- [Objekteksport til Azure Blob-lager](export-azure-blob-storage.md) konfigureret

## <a name="set-up-azure-machine-learning-workspace"></a>Konfigurer Azure Machine Learning-arbejdsområde

1. Se [opret et arbejdsområde i Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) for at få vist forskellige indstillinger for oprettelse af arbejdsområdet. Du opnår den bedste ydeevne, hvis du opretter arbejdsområdet i et Azure-område, der er nærmest dit Customer Insights-miljø.

1. Få adgang til dit arbejdsområde via [Azure Machine Learning Studio](https://ml.azure.com/). Du kan kommunikere [interaktivt](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) med dit arbejdsområde på flere måder.

## <a name="work-with-azure-machine-learning-designer"></a>Arbejd med Azure Machine Learning-designer

Azure Machine Learning-designer viser et visuelt lærred, hvor du kan trække og slippe datasæt og moduler. En batch pipeline, der er oprettet i designeren, kan integreres i Customer Insights, hvis de er konfigureret tilsvarende. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Arbejd med Azure Machine Learning SDK

Datateknikere og AI-udviklere bruger [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) til at oprette maskinelle indlæringsprocesser. I øjeblikket kan modeller, der oplæres ved hjælp af SDK, ikke integreres direkte med Customer Insights. Der kræves en batch pipeline med udledning til den pågældende model for at kunne integrere med Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Krav til batch pipeline, der skal integreres med Customer Insights

### <a name="dataset-configuration"></a>Konfiguration af datasæt

Du skal oprette datasæt for at bruge objektdata fra Customer Insights i en batch pipeline med udledning. Disse datasæt skal registreres i arbejdsområdet. I øjeblikket understøtter vi kun [tabeldatasæt](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) i .csv-format. De datasæt, der er knyttet til objektdata, skal have parametre som en pipeline-parameter.
   
* Datasætparametre i Designer
   
     I designeren skal du åbne **Vælg kolonner i datasæt** og vælge **Indstil som pipeline-parameter**, hvor du angiver et navn til parameteren.

     > [!div class="mx-imgBorder"]
     > ![Datasætparametre i Designer.](media/intelligence-designer-dataset-parameters.png "Datasætparametre i Designer")
   
* Datasætparameter i SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Batch pipeline med udledning
  
* I designeren kan der bruges en trænings-pipeline til at oprette eller opdatere en pipeline med udledning. I øjeblikket understøttes kun batch pipelines med udledning.

* Ved hjælp af SDK kan du publicere en pipeline til et slutpunkt. I øjeblikket integreres Customer Insights med en standard-pipeline i en batch pipeline-slutpunkt i Machine Learning-arbejdsområdet.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Import af pipeline-data til Customer Insights

* Designeren indeholder [Eksportér Data-modulet](/azure/machine-learning/algorithm-module-reference/export-data), der gør det muligt at eksportere output fra en pipeline til Azure-lageret. I øjeblikket skal modulet bruge datalagertypen **Azure Blob Storage** og angive parametre for **Datalager** og eventuel **Sti**. Customer Insights tilsidesætter både disse parametre under kørsel af pipeline med et datalager og en sti, der er tilgængelig for produktet.
   > [!div class="mx-imgBorder"]
   > ![Eksport af Data Module Configuration.](media/intelligence-designer-importdata.png "Eksport af Data Module Configuration")
   
* Når du skriver udledningsresultatet ved hjælp af kode, kan du overføre outputtet til en sti i et *registreret datalager* i arbejdsområdet. Hvis der er angivet parametre for sti og datalager i pipeline, kan Customer Insights læse og importere udledningsoutput. I øjeblikket understøttes et enkelt-tabel output i CSV-format. Stien skal indeholde mappen og filnavnet.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]