---
title: Brugerdefinerede maskinelle indlæringsmodeller | Microsoft Docs
description: Arbejde med brugerdefinerede modeller fra Azure Machine Learning i Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609737"
---
# <a name="custom-machine-learning-models"></a>Brugerdefinerede maskinelle indlæringsmodeller

> [!NOTE]
> Understøttelse af Machine Learning Studio (klassisk) slutter den 31. august 2024. Vi anbefaler, at du skifter til [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) fra denne dato.
>
> Fra og med 1. december 2021 kan du ikke oprette nye ressourcer i Machine Learning Studio (klassisk). Fra den 31. august 2024 kan du fortsætte med at bruge de eksisterende Machine Learning Studio (klassisk)-ressourcer. Du kan finde flere oplysninger i [Overføre til Azure Machine Learning](/azure/machine-learning/migrate-overview).

I brugerdefinerede modeller kan du administrere arbejdsprocesser baseret på Azure Machine Learning-modeller. Arbejdsprocesser hjælper dig med at vælge de data, du vil oprette indsigt fra, og knytte resultaterne til dine samlede kundedata. Du kan finde flere oplysninger om oprettelse af brugerdefinerede ML-modeller under [Brug af Azure Machine Learning-based models](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Forudsætninger

- Webtjenester, der er udgivet via [Azure Machine Learning-batchpipelines](/azure/machine-learning/concept-ml-pipelines).
- Pipeline skal udgives under et [pipeline-slutpunkt](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- En [Azure Data Lake Gen2-lagerkonto](/azure/storage/blobs/data-lake-storage-quickstart-create-account), der er knyttet til din Azure Studio-forekomst.
- I forbindelse med Azure Machine Learning-arbejdsområder med pipelines skal du have administratortilladelser med ejer- eller brugeradgang til arbejdsområdet Azure Machine Learning.

  > [!NOTE]
  > Data overføres mellem dine Customer Insights-forekomster og de valgte Azure-webtjenester eller pipelines i arbejdsprocessen. Når du overfører data til en Azure-service, skal du sikre, at servicen er konfigureret til at behandle data på den måde og placering, der er nødvendig for at overholde eventuelle juridiske eller administrative krav for disse data for din organisation.

## <a name="add-a-new-workflow"></a>Tilføje en ny arbejdsproces

1. Gå til **Intelligens** > **Brugerdefinerede modeller**, og vælg **Ny arbejdsproces**.

1. Angiv et genkendeligt **navn**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Skærmbillede af ruden Ny arbejdsproces.":::

1. Vælg den organisation, der indeholder webtjenesten, i **Lejer, som indeholder din webtjeneste**.

1. Hvis dit Azure Machine Learning-abonnement er i en anden lejer end Customer Insights, skal du vælge **Log på** med dine legitimationsoplysninger for den valgte organisation.

1. Vælg de **Arbejdsområder**, der er knyttet til din webtjeneste.

1. Vælg Azure Machine Learning-pipeline i rullelisten **webtjeneste, der indeholder din model**. Vælg derefter **Næste**.
   Få mere at vide om, hvordan du [udgiver en pipeline i Azure Machine Learning ved hjælp af designeren](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. For hvert **Webtjenesteinput** skal du vælge det tilsvarende **Objekt** fra Customer Insights. Vælg derefter **Næste**.
   > [!NOTE]
   > Den brugerdefinerede modelarbejdsproces anvender heuristik til at knytte inputfelterne i webtjenesten til objektattributterne baseret på feltets navn og datatype. Du får vist en fejlmeddelelse, hvis et webtjenestefelt ikke kan knyttes til et objekt.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Konfigurere en arbejdsproces.":::

1. Angiv følgende egenskaber for **Modeloutputparametre**:
   - **Objektnavn** for pipeline-outputresultater
   - **Navn på parameter for outputdatalager** for batchpipeline
   - **Navn på parameter for outputsti** for batchpipeline

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Modeloutputparameter-panel.":::

1. Vælg den tilsvarende attribut under **Kunde-id i resultater**, der identificerer kunderne, og vælg **Gem**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Relater resultater til Kundedata-panel.":::

   Skærmen **Arbejdsproces blev gemt** viser detaljer om arbejdsprocessen. Hvis du har konfigureret en arbejdsproces for en Azure Machine Learning-pipeline, knyttes Customer Insights til det arbejdsområde, der indeholder pipelinen. Customer Insights får en **bidragyder**-rolle i Azure-arbejdsområdet.

1. Vælg **Udført**. Siden **Brugerdefinerede modeller** vises.

1. Vælg den lodrette ellipse (&vellip;) for arbejdsprocessen, og vælg **Kør**. Arbejdsprocessen kører også automatisk sammen med alle [planlagte opdateringer](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Administrere en eksisterende arbejdsproces

Gå til **Intelligens** > **Brugerdefinerede modeller** for at få vist de arbejdsprocesser, du har oprettet.

Vælg en arbejdsproces for at få vist tilgængelige handlinger.

- **Redigere** en arbejdsproces
- **Køre** en arbejdsproces
- [**Slette**](#delete-a-workflow) en arbejdsproces

### <a name="edit-a-workflow"></a>Redigere en arbejdsproces

1. Gå til **Intelligens** > **Brugerdefinerede modeller**.

1. Ud for den arbejdsproces, du vil opdatere, skal du vælge den lodrette ellipse (&vellip;) og vælge **Rediger**.

1. Rediger **Vist navn** efter behov, og vælg **Næste**.

1. For hvert **Webtjenesteinput** kan du eventuelt opdatere det tilsvarende **Objekt** fra Customer Insights. Vælg derefter **Næste**.

1. Rediger en af følgende for **Modeloutputparametre**:
   - **Objektnavn** for pipeline-outputresultater
   - **Navn på parameter for outputdatalager** for batchpipeline
   - **Navn på parameter for outputsti** for batchpipeline

1. Rediger den tilsvarende attribut under **Kunde-id i resultater**, så den identificerer kunder. Vælg en attribut fra udledningsoutputtet med værdier, der svarer til kolonnen Kunde-id i kundeobjektet. Hvis der ikke findes en sådan kolonne i datasættet, skal du vælge en attribut, der entydigt identificerer rækken.

1. Vælg **Gem**

### <a name="delete-a-workflow"></a>Slette en arbejdsproces

1. Gå til **Intelligens** > **Brugerdefinerede modeller**.

1. Ud for den arbejdsproces, du vil slette, skal du vælge den lodrette ellipse (&vellip;) og vælge **Slet**.

1. Bekræft sletningen.

Din arbejdsproces bliver slettet. Det [objekt](entities.md), der blev oprettet, da du oprettede arbejdsprocessen, bevares, og du kan få det vist på siden **Data** > **Objekter**.

## <a name="view-the-results"></a>Se resultaterne

Resultater fra en arbejdsproces gemmes i det objektnavn, der er defineret for **Modeloutputparameter**. Du kan få adgang til disse data fra [siden **Data** > **Objekter**](entities.md) eller med [API-adgang](apis.md).

### <a name="api-access"></a>API-adgang

Hvis den specifikke OData-forespørgsel skal hente data fra et brugerdefineret modelobjekt, skal du bruge følgende format:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Erstat `<your instance id>` med id'et for dit Customer Insights-miljø, som vises på adresselinjen i din browser ved adgang til Customer Insights.

1. Erstat `<custom model output entity>` med det objektnavn, du har angivet for **Modeloutputparametre**.

1. Erstat `<guid value>` med kunde-id'et for den kunde, som du vil have adgang til. Dette id vises på [siden med kundeprofiler](customer-profiles.md) i feltet CustomerID.

## <a name="frequently-asked-questions"></a>Ofte stillede spørgsmål

- Hvorfor kan jeg ikke se min pipeline, når jeg konfigurerer en brugerdefineret modelarbejdsproces?
  Dette problem skyldes ofte et konfigurationsproblem i pipelinen. Sørg for, at [inputparameteren er konfigureret](azure-machine-learning-experiments.md#dataset-configuration), og at [outputdataene og stiparametrene](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) også er konfigureret.

- Hvad betyder fejlen "Intelligensarbejdsprocessen kunne ikke gemmes"? 
  Brugernefår som regel denne fejlmeddelelse, hvis de ikke har administratorrettigheder som Ejer eller Brugeradgang til arbejdsområdet. Brugeren skal have et højere tilladelsesniveau for at få Customer Insights til at behandle arbejdsprocessen som en tjeneste i stedet for brugerlegitimationsoplysningerne til efterfølgende kørsler af arbejdsprocessen.

- Understøttes et privat slutpunkt/privat link til arbejdsprocessen for min brugerdefinerede model?
  Customer Insights understøtter i øjeblikket ikke som standard private slutpunkter til brugerdefinerede modeller, men der findes en manuel løsning. Kontakt support for at få oplysninger.

## <a name="responsible-ai"></a>Ansvarlig AI

Forudsigelser indeholder funktioner til oprettelse af bedre kundeoplevelser, forbedring af virksomhedsfunktioner og omsætningsstrømme. Det anbefales på det kraftigste, at du balancerer værdien af forudsigelse i forhold til den effekt, den har, og vurderer, at det introduceres på en etisk måde. Få mere at vide om, hvordan Microsoft [adresserer ansvarlig AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Du kan også få mere at vide om [teknikker og processer til maskinel indlæring](/azure/machine-learning/concept-responsible-ml), der er specifikke for Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
