---
title: Brugerdefinerede maskinelle indlæringsmodeller | Microsoft Docs
description: Arbejde med brugerdefinerede modeller fra Azure Machine Learning i Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668896"
---
# <a name="custom-machine-learning-models"></a>Brugerdefinerede maskinelle indlæringsmodeller

**Intelligens** > **Brugerdefinerede modeller** giver dig mulighed for at administrere arbejdsprocesser baseret på Azure Machine Learning-modeller. Arbejdsprocesser hjælper dig med at vælge de data, du vil oprette indsigt fra, og knytte resultaterne til dine samlede kundedata. Du kan finde flere oplysninger om oprettelse af brugerdefinerede ML-modeller under [Brug af Azure Machine Learning-based models](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Ansvarlig AI

Forudsigelser indeholder funktioner til oprettelse af bedre kundeoplevelser, forbedring af virksomhedsfunktioner og omsætningsstrømme. Det anbefales på det kraftigste, at du balancerer værdien af forudsigelse i forhold til den effekt, den har, og vurderer, at det introduceres på en etisk måde. Få mere at vide om, hvordan Microsoft [adresserer ansvarlig AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Du kan også få mere at vide om [teknikker og processer til maskinel indlæring](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml), der er specifikke for Azure Machine Learning.

## <a name="prerequisites"></a>Forudsætninger

- I øjeblikket understøtter denne funktion webtjenester, der publiceres via [Machine Learning Studio (klassisk)](https://studio.azureml.net) og [Azure Machine Learning-batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Du skal have en Azure Data Lake Gen2-lagerkonto, der er knyttet til din Azure Studio-forekomst, for at kunne bruge denne funktion. Du kan finde flere oplysninger under [Oprette en Azure Data Lake Storage Gen2-lagerkonto](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Tilføje en ny arbejdsproces

1. Gå til **Intelligens** > **Brugerdefinerede modeller**, og vælg **Ny arbejdsproces**.

1. Giv din brugerdefinerede model et genkendeligt navn i feltet **Navn**.

   > [!div class="mx-imgBorder"]
   > ![Skærmbillede af ruden Ny arbejdsproces](media/new-workflowv2.png "Skærmbillede af ruden Ny arbejdsproces")

1. Vælg den organisation, der indeholder webtjenesten, i **Lejer, som indeholder din webtjeneste**.

1. Hvis dit Azure Machine Learning-abonnement er i en anden lejer end Customer Insights, skal du vælge **Log på** med dine legitimationsoplysninger for den valgte organisation.

1. Vælg de **Arbejdsområder**, der er knyttet til din webtjeneste. Der er angivet to sektioner: En til Azure Machine Learning v1 (Machine Learning Studio (klassisk)) og Azure Machine Learning v2 (Azure Machine Learning ). Hvis du ikke er sikker på, hvilket arbejdsområde der er den rigtige til din Machine Learning Studio (klassisk)-webtjeneste, skal du vælge **Vilkårlig**.

1. Vælg Machine Learning Studio (klassisk)-webtjeneste eller Azure Machine Learning-pipeline i rullelisten **Webtjeneste, der indeholder din model**. Vælg derefter **Næste**.
   - Få mere at vide om at [udgive en webtjeneste i Machine Learning Studio (klassisk)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Få mere at vide om, hvordan du [udgiver en pipeline i Azure Machine Learning ved hjælp af designeren](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) eller [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). 
     > [!NOTE]
     > Din pipeline skal udgives under et [pipeline-slutpunkt](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. For hvert **Webtjenesteinput** skal du vælge det tilsvarende **Objekt** fra målgruppeindsigter og vælge **Næste**.

   > [!div class="mx-imgBorder"]
   > ![Konfigurere en arbejdsproces](media/intelligence-screen2-updated.png "Konfigurere en arbejdsproces")

1. Angiv følgende egenskaber i **Modeloutputparametre**-trinnet:
   - Machine Learning Studio (klassisk)
      1. Angiv det output **Objektnavn**, som flow for webtjenesteoutputresultater.
   - Azure Machine Learning
      1. Angiv det output **Objektnavn**, som flow for pipeline-outputresultater.
      1. Vælg **Navn på outputdatalagerparameter** i batch pipeline på rullelisten.
      1. Vælg **Navn på outputstiparameter** i batch pipeline på rullelisten.
      
      > [!div class="mx-imgBorder"]
      > ![Modeloutputparameter-panel](media/intelligence-screen3-outputparameters.png "Modeloutputparameter-panel")

1. Vælg den tilsvarende attribut på rullelisten **Kunde-id i resultater**, der identificerer kunder, og vælg **Gem**.
   
   > [!div class="mx-imgBorder"]
   > ![Relater resultater til Kundedata-panel](media/intelligence-screen4-relatetocustomer.png "Relater resultater til Kundedata-panel")

1. Du kan se skærmen **Arbejdsproces blev gemt** med detaljer om arbejdsprocessen.    
   Hvis du har konfigureret en arbejdsproces for en Azure Machine Learning pipeline, tilknyttes der målgruppeindsigt til det arbejdsområde, der indeholder pipelinen. Målgruppeindsigt får en **Bidragyder**-rolle i Azure-arbejdsområdet.

1. Vælg **Udført**.

1. Du kan nu køre arbejdsprocessen fra siden **Brugerdefinerede modeller**.

## <a name="edit-a-workflow"></a>Redigere en arbejdsproces

1. På siden **Brugerdefinerede modeller** vælg den lodrette ellipse i kolonnen **Handlinger** ud for en arbejdsproces, som du tidligere har oprettet, og vælg **Rediger**.

1. Du kan opdatere arbejdsprocessens genkendelige navn i feltet **Visningsnavn**, men du kan ikke ændre den konfigurerede webtjeneste eller pipeline. Vælg **Næste**.

1. For hvert **Webtjenesteinput** skal du vælge det tilsvarende **Objekt** fra målgruppeindsigter. Vælg derefter **Næste**.

1. Angiv følgende egenskaber i **Modeloutputparametre**-trinnet:
   - Machine Learning Studio (klassisk)
      1. Angiv det output **Objektnavn**, som flow for webtjenesteoutputresultater.
   - Azure Machine Learning
      1. Angiv det output **Objektnavn**, som flow for pipeline-outputresultater.
      1. Vælg **Navn på outputdatalager-parameter** for test-pipeline.
      1. Vælg **Navn på outputstiparameter** for test-pipeline.

1. Vælg den tilsvarende attribut på rullelisten **Kunde-id i resultater**, der identificerer kunder, og vælg **Gem**.
   Du skal vælge en attribut fra udledningsoutputtet med værdier, der svarer til kolonnen Kunde-ID i kundeobjektet. Hvis der ikke findes en sådan kolonne i datasættet, skal du vælge en attribut, der entydigt identificerer rækken.

## <a name="run-a-workflow"></a>Kørsel af en arbejdsproces

1. På siden **Brugerdefinerede modeller** vælg den lodrette ellipse i kolonnen **Handlinger** ud for en arbejdsproces, som du tidligere har oprettet.

1. Vælg **Kør**.

Arbejdsprocessen kører også automatisk sammen med alle planlagte opdateringer. Få mere at vide om [oprettelse af planlagte opdateringer](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Slette en arbejdsproces

1. På siden **Brugerdefinerede modeller** vælg den lodrette ellipse i kolonnen **Handlinger** ud for en arbejdsproces, som du tidligere har oprettet.

1. Vælg **Slet**, og bekræft sletningen.

Din arbejdsproces bliver slettet. Det [objekt](entities.md), der blev oprettet, da du oprettede arbejdsprocessen, bevares, og du kan få det vist på siden **Objekter**.
