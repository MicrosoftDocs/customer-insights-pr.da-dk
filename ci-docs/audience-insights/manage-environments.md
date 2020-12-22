---
title: Oprette og administrere miljøer
description: Få mere at vide om, hvordan du tilmelder dig tjenesten, og hvordan du administrerer miljøer.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644126"
---
# <a name="manage-environments"></a><span data-ttu-id="45e04-103">Administrere miljøer</span><span class="sxs-lookup"><span data-stu-id="45e04-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="45e04-104">I denne artikel forklares det, hvordan du kan oprette en ny organisation, og hvordan du kan klargøre et miljø.</span><span class="sxs-lookup"><span data-stu-id="45e04-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="45e04-105">Tilmelding og oprettelse af en organisation</span><span class="sxs-lookup"><span data-stu-id="45e04-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="45e04-106">Gå til [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/)-webstedet.</span><span class="sxs-lookup"><span data-stu-id="45e04-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="45e04-107">Vælg **Introduktion**.</span><span class="sxs-lookup"><span data-stu-id="45e04-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="45e04-108">Vælg dit foretrukne tilmeldingsscenario, og vælg det tilsvarende link.</span><span class="sxs-lookup"><span data-stu-id="45e04-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="45e04-109">Accepter vilkår og betingelser, og vælg **Fortsæt** for at begynde at oprette organisationen.</span><span class="sxs-lookup"><span data-stu-id="45e04-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="45e04-110">Når miljøet er oprettet, bliver du omdirigeret til [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="45e04-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="45e04-111">Brug demomiljøet til at udforske appen, eller opret et nyt miljø ved at udføre trinnene i næste afsnit.</span><span class="sxs-lookup"><span data-stu-id="45e04-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="45e04-112">Når du har angivet miljøindstillingerne, skal du vælge **Opret**.</span><span class="sxs-lookup"><span data-stu-id="45e04-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="45e04-113">Du bliver logget på, når du har oprettet miljøet.</span><span class="sxs-lookup"><span data-stu-id="45e04-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="45e04-114">Oprette et miljø i en eksisterende organisation</span><span class="sxs-lookup"><span data-stu-id="45e04-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="45e04-115">Du kan oprette et nyt miljø på to måder.</span><span class="sxs-lookup"><span data-stu-id="45e04-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="45e04-116">Du kan enten angive en helt ny konfiguration, eller du kan kopiere nogle konfigurationsindstillinger fra et eksisterende miljø.</span><span class="sxs-lookup"><span data-stu-id="45e04-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="45e04-117">Sådan opretter du et miljø:</span><span class="sxs-lookup"><span data-stu-id="45e04-117">To create an environment:</span></span>

1. <span data-ttu-id="45e04-118">Vælg **Indstillinger**-symbolet i overskriften i appen.</span><span class="sxs-lookup"><span data-stu-id="45e04-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="45e04-119">Vælg **Nyt miljø**.</span><span class="sxs-lookup"><span data-stu-id="45e04-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="45e04-120">![Miljøindstillinger](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="45e04-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="45e04-121">Vælg **Nyt miljø** i dialogboksen **Opret nyt miljø**.</span><span class="sxs-lookup"><span data-stu-id="45e04-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="45e04-122">Hvis du vil [kopiere data fra det aktuelle miljø](#additional-considerations-for-copy-configuration-preview), skal du vælge **Kopiér fra eksisterende miljø**.</span><span class="sxs-lookup"><span data-stu-id="45e04-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="45e04-123">Du får vist en liste over alle tilgængelige miljøer i din organisation, som du kan kopiere data fra.</span><span class="sxs-lookup"><span data-stu-id="45e04-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="45e04-124">Angiv følgende oplysninger:</span><span class="sxs-lookup"><span data-stu-id="45e04-124">Provide the following details:</span></span>
   - <span data-ttu-id="45e04-125">**Navn**: Navnet på dette miljø.</span><span class="sxs-lookup"><span data-stu-id="45e04-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="45e04-126">Dette felt er allerede udfyldt, hvis du har kopieret et eksisterende miljø, men du kan ændre det.</span><span class="sxs-lookup"><span data-stu-id="45e04-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="45e04-127">**Område**: Det område, hvor tjenesten er installeret og har sin vært.</span><span class="sxs-lookup"><span data-stu-id="45e04-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="45e04-128">**Type**: Vælg, om du vil oprette et produktions- eller sandkassemiljø.</span><span class="sxs-lookup"><span data-stu-id="45e04-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="45e04-129">Du kan også vælge **Avancerede indstillinger**:</span><span class="sxs-lookup"><span data-stu-id="45e04-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="45e04-130">**Gem alle data i**: Angiver, hvor du vil gemme de outputdata, der er genereret fra Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="45e04-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="45e04-131">Du har to muligheder: **Customer Insights-lager** (en Azure Data Lake, der administreres af Customer Insights-teamet) og **Azure Data Lake Storage Gen2** (dit eget Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="45e04-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="45e04-132">Som standard er indstillingen Customer Insights-lager valgt.</span><span class="sxs-lookup"><span data-stu-id="45e04-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="45e04-133">Når du gemmer data i Azure Data Lake Storage, accepterer du, at data overføres til og gemmes på den relevante geografiske placering for den pågældende Azure Storage-konto, som kan være forskellig fra den placering, hvor data gemmes i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="45e04-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="45e04-134">Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration.</span><span class="sxs-lookup"><span data-stu-id="45e04-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="45e04-135">I øjeblikket gemmes indtagede objekter altid i den styrede datasø i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="45e04-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="45e04-136">Vi understøtter kun Azure Data Lake Gen2 Storage-konti fra det samme Azure-område, som du valgte, da du oprettede miljøet.</span><span class="sxs-lookup"><span data-stu-id="45e04-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="45e04-137">Vi understøtter kun lagerkonti, der er aktiveret med Hierarkisk navneområde (HNS), i Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="45e04-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="45e04-138">For Azure Data Lake Storage Gen2 kan du vælge mellem at bruge en ressourcebaseret indstilling og en abonnementsbaseret indstilling til godkendelse.</span><span class="sxs-lookup"><span data-stu-id="45e04-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="45e04-139">Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="45e04-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="45e04-140">Navnet på **Beholder** kan ikke ændres og vil være "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="45e04-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="45e04-141">Hvis du vil bruge [forudsigelser](predictions.md), skal du angive Common Data Service-forekomst URL-adresse i feltet **Server-adresse** under **Brug af forudsigelser**.</span><span class="sxs-lookup"><span data-stu-id="45e04-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="45e04-142">Når du kører processer, f. eks. dataindsættelse eller segmentoprettelse, oprettes der tilsvarende mapper i den lagerkonto, du har angivet ovenfor.</span><span class="sxs-lookup"><span data-stu-id="45e04-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="45e04-143">Datafiler og model.json-filer oprettes og føjes til de respektive undermapper, afhængigt af den proces du kører.</span><span class="sxs-lookup"><span data-stu-id="45e04-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="45e04-144">Hvis du opretter flere miljøer med Customer Insights og vælger at gemme outputenhederne fra de pågældende miljøer i lagerkontoen, oprettes der separate mapper for hvert miljø med ci_<environmentid> i beholderen.</span><span class="sxs-lookup"><span data-stu-id="45e04-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="45e04-145">Flere overvejelser i forbindelse med kopieringskonfiguration (eksempel)</span><span class="sxs-lookup"><span data-stu-id="45e04-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="45e04-146">Følgende konfigurationsindstillinger er kopieret:</span><span class="sxs-lookup"><span data-stu-id="45e04-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="45e04-147">Funktionskonfigurationer</span><span class="sxs-lookup"><span data-stu-id="45e04-147">Feature configurations</span></span>
- <span data-ttu-id="45e04-148">Indtagne/importerede datakilder</span><span class="sxs-lookup"><span data-stu-id="45e04-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="45e04-149">Konfiguration af dataforening (tilknytte, matche, flette)</span><span class="sxs-lookup"><span data-stu-id="45e04-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="45e04-150">Segmenter</span><span class="sxs-lookup"><span data-stu-id="45e04-150">Segments</span></span>
- <span data-ttu-id="45e04-151">Målinger</span><span class="sxs-lookup"><span data-stu-id="45e04-151">Measures</span></span>
- <span data-ttu-id="45e04-152">Relationer</span><span class="sxs-lookup"><span data-stu-id="45e04-152">Relationships</span></span>
- <span data-ttu-id="45e04-153">Aktiviteter</span><span class="sxs-lookup"><span data-stu-id="45e04-153">Activities</span></span>
- <span data-ttu-id="45e04-154">Indeks for søgning og filtrering</span><span class="sxs-lookup"><span data-stu-id="45e04-154">Search & filter Index</span></span>
- <span data-ttu-id="45e04-155">Eksportdestinationer</span><span class="sxs-lookup"><span data-stu-id="45e04-155">Export destinations</span></span>
- <span data-ttu-id="45e04-156">Planlagt opdatering</span><span class="sxs-lookup"><span data-stu-id="45e04-156">Scheduled refresh</span></span>
- <span data-ttu-id="45e04-157">Forbedringer</span><span class="sxs-lookup"><span data-stu-id="45e04-157">Enrichments</span></span>
- <span data-ttu-id="45e04-158">Modeladministration</span><span class="sxs-lookup"><span data-stu-id="45e04-158">Model management</span></span>
- <span data-ttu-id="45e04-159">Rolletildelinger</span><span class="sxs-lookup"><span data-stu-id="45e04-159">Role assignments</span></span>

<span data-ttu-id="45e04-160">Følgende konfigurationsindstillinger er *ikke* kopieret:</span><span class="sxs-lookup"><span data-stu-id="45e04-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="45e04-161">Kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="45e04-161">Customer profiles.</span></span>
- <span data-ttu-id="45e04-162">Legitimationsoplysninger for datakilde.</span><span class="sxs-lookup"><span data-stu-id="45e04-162">Data source credentials.</span></span> <span data-ttu-id="45e04-163">Du skal angive legitimationsoplysningerne for hver datakilde og opdatere datakilderne manuelt.</span><span class="sxs-lookup"><span data-stu-id="45e04-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="45e04-164">Datakilder fra Common Data Model-mappen og Common Data Service-administreret sø.</span><span class="sxs-lookup"><span data-stu-id="45e04-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="45e04-165">Du skal oprette disse datakilder manuelt med det samme navn som i kildemiljøet.</span><span class="sxs-lookup"><span data-stu-id="45e04-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="45e04-166">Når du kopierer et miljø, får du vist en bekræftelsesmeddelelse om, at det nye miljø er blevet oprettet.</span><span class="sxs-lookup"><span data-stu-id="45e04-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="45e04-167">Vælg **gå til datakilder** for at få vist listen over datakilder.</span><span class="sxs-lookup"><span data-stu-id="45e04-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="45e04-168">Alle datakilderne viser en **Legitimationsoplysninger påkrævet** som status.</span><span class="sxs-lookup"><span data-stu-id="45e04-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="45e04-169">Rediger datakilderne, og angiv legitimationsoplysninger for at opdatere dem.</span><span class="sxs-lookup"><span data-stu-id="45e04-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="45e04-170">![Kopierede datakilder](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="45e04-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="45e04-171">Når du har opdateret datakilderne, skal du gå til **Data** > **Saml**.</span><span class="sxs-lookup"><span data-stu-id="45e04-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="45e04-172">Her kan du finde indstillinger fra kildemiljøet.</span><span class="sxs-lookup"><span data-stu-id="45e04-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="45e04-173">Rediger dem efter behov, eller vælg **Kør**, for at starte datasamlingsprocessen og det samlede kundeobjekt.</span><span class="sxs-lookup"><span data-stu-id="45e04-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="45e04-174">Når datasamlingen er fuldført, skal du gå til **Målinger** og **Segmenter** for at opdatere dem.</span><span class="sxs-lookup"><span data-stu-id="45e04-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="45e04-175">Redigere et eksisterende miljø</span><span class="sxs-lookup"><span data-stu-id="45e04-175">Edit an existing environment</span></span>

<span data-ttu-id="45e04-176">Du kan redigere nogle af oplysningerne i eksisterende miljøer.</span><span class="sxs-lookup"><span data-stu-id="45e04-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="45e04-177">Gå til **Administration** > **System** > **Om**.</span><span class="sxs-lookup"><span data-stu-id="45e04-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="45e04-178">Vælg **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="45e04-178">Select **Edit**.</span></span>

3. <span data-ttu-id="45e04-179">Du kan opdatere miljøets **Vist navn**, men du kan ikke ændre **Område** eller **Type**.</span><span class="sxs-lookup"><span data-stu-id="45e04-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="45e04-180">Hvis et miljø er konfigureret til at lagre data i Azure Data Lake Storage Gen2, kan du opdatere **Kontonøgle**.</span><span class="sxs-lookup"><span data-stu-id="45e04-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="45e04-181">Du kan dog ikke ændre **Kontonavn** eller navnet på **Objektbeholder**.</span><span class="sxs-lookup"><span data-stu-id="45e04-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="45e04-182">Du kan også vælge at opdatere fra en kontonøglebaseret forbindelse til en ressourcebaseret eller en abonnementsbaseret forbindelse.</span><span class="sxs-lookup"><span data-stu-id="45e04-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="45e04-183">Når det er opgraderet, kan du ikke vende tilbage til kontonøglen efter opdateringen.</span><span class="sxs-lookup"><span data-stu-id="45e04-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="45e04-184">Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="45e04-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="45e04-185">Du kan ikke ændre **objektbeholder**-oplysninger, når du opdaterer forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="45e04-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="45e04-186">Nulstil et eksisterende miljø</span><span class="sxs-lookup"><span data-stu-id="45e04-186">Reset an existing environment</span></span>

<span data-ttu-id="45e04-187">Du kan nulstille et miljø til en tom tilstand, hvis du vil slette alle konfigurationer og fjerne de påtagede data.</span><span class="sxs-lookup"><span data-stu-id="45e04-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="45e04-188">Gå til **Administration** > **System** > **Om**.</span><span class="sxs-lookup"><span data-stu-id="45e04-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="45e04-189">Vælg **Nulstil**.</span><span class="sxs-lookup"><span data-stu-id="45e04-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="45e04-190">Bekræft sletningen ved at skrive navnet på miljøet og vælge **Nulstil**.</span><span class="sxs-lookup"><span data-stu-id="45e04-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="45e04-191">Slet et eksisterende miljø</span><span class="sxs-lookup"><span data-stu-id="45e04-191">Delete an existing environment</span></span>

1. <span data-ttu-id="45e04-192">Gå til **Administration** > **System** > **Om**.</span><span class="sxs-lookup"><span data-stu-id="45e04-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="45e04-193">Vælg **Slet**.</span><span class="sxs-lookup"><span data-stu-id="45e04-193">Select **Delete**.</span></span>

1. <span data-ttu-id="45e04-194">Bekræft sletningen ved at skrive navnet på miljøet og vælge **Slet**.</span><span class="sxs-lookup"><span data-stu-id="45e04-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
