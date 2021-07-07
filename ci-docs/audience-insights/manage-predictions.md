---
title: Delte opgaver til forudsigelsesscenarier
description: Få mere at vide om, hvordan du administrerer, foretager fejlfinding og finjusterer forudsigelser.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315871"
---
# <a name="manage-predictions"></a><span data-ttu-id="663b9-103">Administrere forudsigelser</span><span class="sxs-lookup"><span data-stu-id="663b9-103">Manage predictions</span></span>

<span data-ttu-id="663b9-104">I denne artikel beskrives nogle opgaver, som de fleste forudsigelsesscenarier deler.</span><span class="sxs-lookup"><span data-stu-id="663b9-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="663b9-105">Fejlfinding i forbindelse med mislykkede forudsigelse</span><span class="sxs-lookup"><span data-stu-id="663b9-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="663b9-106">Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**.</span><span class="sxs-lookup"><span data-stu-id="663b9-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="663b9-107">Vælg de lodrette ellipser ud for den forudsigelse, du vil have vist fejllogfiler for.</span><span class="sxs-lookup"><span data-stu-id="663b9-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="663b9-108">Vælg **logfiler**.</span><span class="sxs-lookup"><span data-stu-id="663b9-108">Select **Logs**.</span></span>

1. <span data-ttu-id="663b9-109">Gennemgå alle fejlene.</span><span class="sxs-lookup"><span data-stu-id="663b9-109">Review all the errors.</span></span> <span data-ttu-id="663b9-110">Der er flere typer fejl, der kan opstå, og som beskriver, hvilken betingelse der forårsagede fejlen.</span><span class="sxs-lookup"><span data-stu-id="663b9-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="663b9-111">En fejlmeddelelse om, at der ikke er nok data til præcist at forudsige noget, løses typisk ved at indlæse yderligere data i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="663b9-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="663b9-112">Rapport over inputdatas anvendelighed</span><span class="sxs-lookup"><span data-stu-id="663b9-112">Input data usability report</span></span>

<span data-ttu-id="663b9-113">Rapporten om brugbarhed af inputdata giver en konsolideret visning af de fejl og advarsler, som dine køreklare forudsigelser kan generere.</span><span class="sxs-lookup"><span data-stu-id="663b9-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="663b9-114">Den giver også anbefalinger til, hvordan man kan forbedre modellens ydeevne.</span><span class="sxs-lookup"><span data-stu-id="663b9-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="663b9-115">Rapporten er tilgængelig, når en model har fuldført sin træningsproces.</span><span class="sxs-lookup"><span data-stu-id="663b9-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="663b9-116">Den oprettes for hver model separat, uanset om det er fuldført.</span><span class="sxs-lookup"><span data-stu-id="663b9-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="663b9-117">Vis rapporten over inputdatas anvendelighed</span><span class="sxs-lookup"><span data-stu-id="663b9-117">View the input data usability report</span></span>

<span data-ttu-id="663b9-118">Når en køreklar model har fuldført sine træningstrin, skal du se rapporten:</span><span class="sxs-lookup"><span data-stu-id="663b9-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="663b9-119">Vælg ellipserne ud for modelnavnet, og vælg **Rapport over inputdatas anvendelighed**.</span><span class="sxs-lookup"><span data-stu-id="663b9-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="663b9-120">Vælg status for en model. Vælg **Se rapporten over brugbarhed af inputdata** i sideruden.</span><span class="sxs-lookup"><span data-stu-id="663b9-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="663b9-121">Vælg en af modellerne på listen, og vælg **Rapport over brugbarhed af inputdata** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="663b9-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="663b9-122">Åbn modellens resultatside, og vælg **Rapport over brugbarhed af inputdata** på kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="663b9-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="663b9-123">Oplysninger om rapporten over inputdatas anvendelighed</span><span class="sxs-lookup"><span data-stu-id="663b9-123">Information in the input data usability report</span></span>

<span data-ttu-id="663b9-124">Følgende kolonner i rapporten indeholder nyttige oplysninger til forbedring af dataene for modellen.</span><span class="sxs-lookup"><span data-stu-id="663b9-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Eksempel på en rapport om brugbarhed af inputdata, der viser en tabel med fejl, advarsler og anbefalinger.":::

- <span data-ttu-id="663b9-126">Navn: Beskrivende navn på fejlen, advarslen eller anbefalingen.</span><span class="sxs-lookup"><span data-stu-id="663b9-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="663b9-127">Trin: Modelfase, -træning eller -score, som oplysningerne refererer til.</span><span class="sxs-lookup"><span data-stu-id="663b9-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="663b9-128">Tilstand: Oplysningernes alvorlighed (fejl, advarsel, anbefaling).</span><span class="sxs-lookup"><span data-stu-id="663b9-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="663b9-129">Kolonnenavn: Kolonne i et objekt, der skal ændres for at forbedre modellens ydeevne.</span><span class="sxs-lookup"><span data-stu-id="663b9-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="663b9-130">Objektnavn: Navn på objektet, der skal ændres for at forbedre modellens ydeevne.</span><span class="sxs-lookup"><span data-stu-id="663b9-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="663b9-131">Detaljer: Oplysninger om fejlen, advarslen eller anbefalingen.</span><span class="sxs-lookup"><span data-stu-id="663b9-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="663b9-132">Opdatere en forudsigelse</span><span class="sxs-lookup"><span data-stu-id="663b9-132">Refresh a prediction</span></span>

<span data-ttu-id="663b9-133">Forudsigelser opdateres automatisk efter den samme [tidsplan, som dataene opdateres i](system.md#schedule-tab), som de er konfigureret i indstillinger.</span><span class="sxs-lookup"><span data-stu-id="663b9-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="663b9-134">Du kan også opdatere dem manuelt.</span><span class="sxs-lookup"><span data-stu-id="663b9-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="663b9-135">Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**.</span><span class="sxs-lookup"><span data-stu-id="663b9-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="663b9-136">Vælg de lodrette ellipser ud for den forudsigelse,, du vil opdatere.</span><span class="sxs-lookup"><span data-stu-id="663b9-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="663b9-137">Vælg **Opdater**.</span><span class="sxs-lookup"><span data-stu-id="663b9-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="663b9-138">Slette en forudsigelse</span><span class="sxs-lookup"><span data-stu-id="663b9-138">Delete a prediction</span></span>

<span data-ttu-id="663b9-139">Hvis du sletter en forudsigelse, fjernes outputenheden også.</span><span class="sxs-lookup"><span data-stu-id="663b9-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="663b9-140">Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**.</span><span class="sxs-lookup"><span data-stu-id="663b9-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="663b9-141">Vælg de lodrette ellipser ud for den forudsigelse, du vil slette.</span><span class="sxs-lookup"><span data-stu-id="663b9-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="663b9-142">Vælg **Slet**.</span><span class="sxs-lookup"><span data-stu-id="663b9-142">Select **Delete**.</span></span>
