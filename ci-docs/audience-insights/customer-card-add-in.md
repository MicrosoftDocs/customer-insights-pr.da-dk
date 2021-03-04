---
title: Installer og konfigurér tilføjelsesprogrammet Kundekort.
description: Installer og konfigurer tilføjelsesprogrammet Kundekort til Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268037"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="f4144-103">Tilføjelsesprogrammet Kundekort (eksempel)</span><span class="sxs-lookup"><span data-stu-id="f4144-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f4144-104">Få en 360-grads visning af dine kunder direkte i Dynamics 365-apps.</span><span class="sxs-lookup"><span data-stu-id="f4144-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="f4144-105">Få vist demografiske oplysninger, indsigt og aktivitetstidslinjer med tilføjelsesprogrammet Kundekort.</span><span class="sxs-lookup"><span data-stu-id="f4144-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f4144-106">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="f4144-106">Prerequisites</span></span>

- <span data-ttu-id="f4144-107">Dynamics 365-app (f.eks. Salgshub eller Kundeservicehub), version 9.0 og nyere med Unified Interface aktiveret.</span><span class="sxs-lookup"><span data-stu-id="f4144-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="f4144-108">Kundeprofiler, [der er overført fra Dynamics 365-appen ved hjælp af Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="f4144-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="f4144-109">Brugere af tilføjelsesprogrammet kundekort skal [tilføjes som brugere](permissions.md) i målgruppeindsigt.</span><span class="sxs-lookup"><span data-stu-id="f4144-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="f4144-110">[Konfigurerede søge- og filtreringsfunktioner](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="f4144-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="f4144-111">Demografisk kontrolelement: Demografiske felter (f.eks. alder eller køn) er tilgængelige i den samlede kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="f4144-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="f4144-112">Forbedringskontrol: Kræver aktive [forbedringer](enrichment-hub.md), der anvendes på kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="f4144-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="f4144-113">Intelligent kontrol: Kræver data, der er genereret ved hjælp af Azure Machine Learning ([Forudsigelser](predictions.md) eller [Brugerdefinerede modeller](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="f4144-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="f4144-114">Målingskontrol: Kræver [konfigurerede målinger](measures.md).</span><span class="sxs-lookup"><span data-stu-id="f4144-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="f4144-115">Tidslinjekontrol: Kræver [konfigurerede aktiviteter](activities.md).</span><span class="sxs-lookup"><span data-stu-id="f4144-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="f4144-116">Installere tilføjelsesprogrammet Kundekort</span><span class="sxs-lookup"><span data-stu-id="f4144-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="f4144-117">Tilføjelsesprogrammet Kundekort er en løsning til Customer Engagement-apps i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f4144-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="f4144-118">Hvis du vil installere løsningen, skal du gå til AppSource og søge efter **Dynamics-kundekort**.</span><span class="sxs-lookup"><span data-stu-id="f4144-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="f4144-119">Vælg [Tilføjelsesprogrammet Kundekort i AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview), og vælg **Hent det nu**.</span><span class="sxs-lookup"><span data-stu-id="f4144-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="f4144-120">Det kan være nødvendigt at logge på med dine administrator-legitimationsoplysninger, når Dynamics 365-appen skal installere løsningen.</span><span class="sxs-lookup"><span data-stu-id="f4144-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="f4144-121">Det kan tage et stykke tid, før løsningen er installeret i dit miljø.</span><span class="sxs-lookup"><span data-stu-id="f4144-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="f4144-122">Konfigurere tilføjelsesprogrammet Kundekort</span><span class="sxs-lookup"><span data-stu-id="f4144-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="f4144-123">Som administrator kan du gå til sektionen **Indstillinger** i Dynamics 365 og vælge **Løsninger**.</span><span class="sxs-lookup"><span data-stu-id="f4144-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="f4144-124">Vælg linket **Vist navn** til løsningen **tilføjelsesprogrammet Kundekort til Dynamics 365 Customer Insights (eksempel)**.</span><span class="sxs-lookup"><span data-stu-id="f4144-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4144-125">![Vælge vist navn](media/select-display-name.png "Vælge vist navn")</span><span class="sxs-lookup"><span data-stu-id="f4144-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="f4144-126">Vælg **Log på**, og angiv legitimationsoplysningerne for den administratorkonto, du bruger til at konfigurere Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f4144-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f4144-127">Kontrollér, at browserens blokering af pop op-vinduer ikke blokerer for godkendelsesvinduet, når du vælger knappen **Log på**.</span><span class="sxs-lookup"><span data-stu-id="f4144-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="f4144-128">Vælg det miljø, du vil hente data fra.</span><span class="sxs-lookup"><span data-stu-id="f4144-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="f4144-129">Definer, hvilket felt der skal knyttes til poster i appen Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f4144-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="f4144-130">Hvis du vil tilknytte en kontaktperson, skal du vælge det felt i kundeobjektet, der stemmer overens med id for dit kontaktpersonsobjekt.</span><span class="sxs-lookup"><span data-stu-id="f4144-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="f4144-131">Hvis du vil tilknytte en konto, skal du vælge det felt i kundeobjektet, der stemmer overens med id for dit kontoobjekt.</span><span class="sxs-lookup"><span data-stu-id="f4144-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4144-132">![Feltet Kontakt-id](media/contact-id-field.png "Feltet Kontakt-id")</span><span class="sxs-lookup"><span data-stu-id="f4144-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="f4144-133">Vælg **Gem konfiguration** for at gemme indstillingerne.</span><span class="sxs-lookup"><span data-stu-id="f4144-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="f4144-134">Derefter skal du tildele sikkerhedsroller i Dynamics 365, så brugerne kan tilpasse og få vist kundekortet.</span><span class="sxs-lookup"><span data-stu-id="f4144-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="f4144-135">I Dynamics 365 skal du gå til **Indstillinger** > **Sikkerhed** > **Brugere**.</span><span class="sxs-lookup"><span data-stu-id="f4144-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="f4144-136">Vælg de brugere, hvis brugerroller der skal redigeres, og vælg **Administrer roller**.</span><span class="sxs-lookup"><span data-stu-id="f4144-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="f4144-137">Tildel rollen **Customer Insights-korttilpasser** til brugere, der skal tilpasse det indhold, der vises på kortet, for hele organisationen.</span><span class="sxs-lookup"><span data-stu-id="f4144-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="f4144-138">Tilføj Kundekort-kontrolelementer til formularer</span><span class="sxs-lookup"><span data-stu-id="f4144-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="f4144-139">Hvis du vil føje Kundekort-kontrolelementer til formularen Kontakt, skal du gå til **Indstillinger** > **Tilpasninger** i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f4144-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="f4144-140">Vælg **Tilpas systemet**.</span><span class="sxs-lookup"><span data-stu-id="f4144-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="f4144-141">Gå til objektet **Kontakt**, udvid det, og vælg **Formularer**.</span><span class="sxs-lookup"><span data-stu-id="f4144-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="f4144-142">Vælg den kontaktformular, hvor du vil tilføje kontrolelementerne for kundekortet.</span><span class="sxs-lookup"><span data-stu-id="f4144-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4144-143">![Vælge formularen Kontakt](media/contact-active-forms.png "Vælge formularen Kontakt")</span><span class="sxs-lookup"><span data-stu-id="f4144-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="f4144-144">Hvis du vil tilføje et kontrolelement, skal du i formulareditoren trække et hvilket som helst felt fra **Feltoversigt** til det sted, hvor du vil placere kontrolelementet.</span><span class="sxs-lookup"><span data-stu-id="f4144-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="f4144-145">Vælg det felt i den formular, du lige har tilføjet, og vælg **Skift egenskaber**.</span><span class="sxs-lookup"><span data-stu-id="f4144-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="f4144-146">Gå til fanen **Kontrolelementer**, og vælg **Tilføj kontrolelement**.</span><span class="sxs-lookup"><span data-stu-id="f4144-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="f4144-147">Vælg et af de tilgængelige brugerdefinerede kontrolelementer, og vælg **Tilføj**.</span><span class="sxs-lookup"><span data-stu-id="f4144-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="f4144-148">Fjern markeringen i afkrydsningsfeltet **Vis etiket på formularen**, i dialogboksen **Feltegenskaber**.</span><span class="sxs-lookup"><span data-stu-id="f4144-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="f4144-149">Vælg indstillingen **Internet** for kontrolelementet.</span><span class="sxs-lookup"><span data-stu-id="f4144-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="f4144-150">Vælg den type forbedring, du vil have vist, ved at konfigurere feltet **Forbedring**.</span><span class="sxs-lookup"><span data-stu-id="f4144-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="f4144-151">Tilføj et særskilt forbedringskontrolelement for hver forbedringstype.</span><span class="sxs-lookup"><span data-stu-id="f4144-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="f4144-152">Vælg **Gem** og **Publicer** for at publicere den opdaterede kontaktpersonformular.</span><span class="sxs-lookup"><span data-stu-id="f4144-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="f4144-153">Gå til den publicerede kontaktformular.</span><span class="sxs-lookup"><span data-stu-id="f4144-153">Go to the published contact form.</span></span> <span data-ttu-id="f4144-154">Du kan se det netop tilføjede kontrolelement.</span><span class="sxs-lookup"><span data-stu-id="f4144-154">You'll see the newly added control.</span></span> <span data-ttu-id="f4144-155">Det kan være nødvendigt at logge på, første gang du bruger det.</span><span class="sxs-lookup"><span data-stu-id="f4144-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="f4144-156">Hvis du vil tilpasse det, du vil have vist på det brugerdefinerede kontrolelement, skal du vælge knappen Rediger i øverste højre hjørne.</span><span class="sxs-lookup"><span data-stu-id="f4144-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="f4144-157">Opgradere tilføjelsesprogrammet Kundekort</span><span class="sxs-lookup"><span data-stu-id="f4144-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="f4144-158">Tilføjelsesprogrammet Kundekort opgraderes ikke automatisk.</span><span class="sxs-lookup"><span data-stu-id="f4144-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="f4144-159">Hvis du vil opgradere til den nyeste version, skal du følge denne procedure i den Dynamics 365-app, hvor tilføjelsesprogrammet er installeret.</span><span class="sxs-lookup"><span data-stu-id="f4144-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="f4144-160">Gå til **Indstillinger** > **Tilpasning** og vælg **Løsninger** i Dynamics 365-appen.</span><span class="sxs-lookup"><span data-stu-id="f4144-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="f4144-161">I tabellen over tilføjelsesprogrammer skal du kigge efter **CustomerInsightsCustomerCard** og markere rækken.</span><span class="sxs-lookup"><span data-stu-id="f4144-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="f4144-162">Vælg **Anvend løsningsopgradering** på handlingslinjen.</span><span class="sxs-lookup"><span data-stu-id="f4144-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Opgradere løsningen i området Tilpasning i Dynamics 365-apps":::

1. <span data-ttu-id="f4144-164">Når du har startet opgraderingsprocessen, kan du se en indlæsningsindikator, indtil opgraderingen er fuldført.</span><span class="sxs-lookup"><span data-stu-id="f4144-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="f4144-165">Hvis der ikke findes en nyere version, vises der en fejlmeddelelse i opgraderingen.</span><span class="sxs-lookup"><span data-stu-id="f4144-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]