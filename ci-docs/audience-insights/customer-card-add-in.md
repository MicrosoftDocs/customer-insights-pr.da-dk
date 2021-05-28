---
title: Tilføjelsesprogrammet Kundekort til Dynamics 365-apps
description: Vis data fra målgruppeindsigt i Dynamics 365-apps med dette tilføjelsesprogram.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059581"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="e5d1e-103">Tilføjelsesprogrammet Kundekort (eksempel)</span><span class="sxs-lookup"><span data-stu-id="e5d1e-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e5d1e-104">Få en 360-grads visning af dine kunder direkte i Dynamics 365-apps.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="e5d1e-105">Når tilføjelsesprogrammet Kundekort er installeret i en understøttet Dynamics 365-app, kan du vælge at få vist demografi, indsigt og aktivitetstidslinjer.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="e5d1e-106">Tilføjelsesprogrammet henter data fra Customer Insights, uden at det påvirker dataene i den tilknyttede Dynamics 365-app.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e5d1e-107">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="e5d1e-107">Prerequisites</span></span>

- <span data-ttu-id="e5d1e-108">Tilføjelsesprogrammet fungerer kun med Dynamics 365-modelbaserede apps, f.eks. Sales eller Customer Service, version 9.0 og nyere.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="e5d1e-109">Hvis dine Dynamics 365-data skal knyttes til kundeprofilers målgruppeindsigt, skal de [indtages fra Dynamics 365-appen ved hjælp af Common Data Service connectoren](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e5d1e-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="e5d1e-110">Alle Dynamics 365-brugere af Kundekort-tilføjelsesprogrammet skal [tilføjes som brugere](permissions.md) i målgruppeindsigt for at kunne se dataene.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="e5d1e-111">[Konfigurerede søge- og filterfunktioner](search-filter-index.md) i målgruppeindsigt kræves for at få opslag af data til at fungere.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="e5d1e-112">Hvert tilføjelsesprograms kontrolelement afhænger af specifikke data i målgruppeindsigt:</span><span class="sxs-lookup"><span data-stu-id="e5d1e-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="e5d1e-113">Målingskontrol: Kræver [konfigurerede målinger](measures.md).</span><span class="sxs-lookup"><span data-stu-id="e5d1e-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="e5d1e-114">Intelligenskontrol: Kræver data genereret ved hjælp af [forudsigelser](predictions.md) eller [brugerdefinerede modeller](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="e5d1e-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="e5d1e-115">Demografisk kontrolelement: Demografiske felter (f.eks. alder eller køn) er tilgængelige i den samlede kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="e5d1e-116">Forbedringskontrol: Kræver aktive [forbedringer](enrichment-hub.md), der anvendes på kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="e5d1e-117">Tidslinjekontrol: Kræver [konfigurerede aktiviteter](activities.md).</span><span class="sxs-lookup"><span data-stu-id="e5d1e-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="e5d1e-118">Installere tilføjelsesprogrammet Kundekort</span><span class="sxs-lookup"><span data-stu-id="e5d1e-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="e5d1e-119">Tilføjelsesprogrammet Kundekort er en løsning til Customer Engagement-apps i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="e5d1e-120">Hvis du vil installere løsningen, skal du gå til AppSource og søge efter **Dynamics-kundekort**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="e5d1e-121">Vælg [Tilføjelsesprogrammet Kundekort i AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview), og vælg **Hent det nu**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="e5d1e-122">Det kan være nødvendigt at logge på med dine administrator-legitimationsoplysninger, når Dynamics 365-appen skal installere løsningen.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="e5d1e-123">Det kan tage et stykke tid, før løsningen er installeret i dit miljø.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="e5d1e-124">Konfigurere tilføjelsesprogrammet Kundekort</span><span class="sxs-lookup"><span data-stu-id="e5d1e-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="e5d1e-125">Som administrator kan du gå til sektionen **Indstillinger** i Dynamics 365 og vælge **Løsninger**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="e5d1e-126">Vælg linket **Vist navn** til løsningen **tilføjelsesprogrammet Kundekort til Dynamics 365 Customer Insights (eksempel)**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e5d1e-127">![Vælge vist navn](media/select-display-name.png "Vælge vist navn")</span><span class="sxs-lookup"><span data-stu-id="e5d1e-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="e5d1e-128">Vælg **Log på**, og angiv legitimationsoplysningerne for den administratorkonto, du bruger til at konfigurere Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e5d1e-129">Kontrollér, at browserens blokering af pop op-vinduer ikke blokerer for godkendelsesvinduet, når du vælger knappen **Log på**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="e5d1e-130">Vælg det Customer Insights-miljø, du vil hente data fra.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="e5d1e-131">Definer felttilknytningen til poster i Dynamics 365-appen.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="e5d1e-132">Afhængigt af dine data i Customer Insights kan du vælge at tilknytte følgende muligheder:</span><span class="sxs-lookup"><span data-stu-id="e5d1e-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="e5d1e-133">Hvis du vil tilknytte en kontaktperson, skal du vælge det felt i kundeobjektet, der stemmer overens med id for dit kontaktpersonsobjekt.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="e5d1e-134">Hvis du vil tilknytte en konto, skal du vælge det felt i kundeobjektet, der stemmer overens med id for dit kontoobjekt.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e5d1e-135">![Feltet Kontakt-id](media/contact-id-field.png "Feltet Kontakt-id")</span><span class="sxs-lookup"><span data-stu-id="e5d1e-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="e5d1e-136">Vælg **Gem konfiguration** for at gemme indstillingerne.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="e5d1e-137">Derefter skal du tildele sikkerhedsroller i Dynamics 365, så brugerne kan tilpasse og få vist kundekortet.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="e5d1e-138">I Dynamics 365 skal du gå til **Indstillinger** > **Sikkerhed** > **Brugere**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="e5d1e-139">Vælg de brugere, hvis brugerroller der skal redigeres, og vælg **Administrer roller**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="e5d1e-140">Tildel rollen **Customer Insights-korttilpasser** til brugere, der skal tilpasse det indhold, der vises på kortet, for hele organisationen.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="e5d1e-141">Tilføj Kundekort-kontrolelementer til formularer</span><span class="sxs-lookup"><span data-stu-id="e5d1e-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="e5d1e-142">Hvis du vil føje Kundekort-kontrolelementer til formularen Kontakt, skal du gå til **Indstillinger** > **Tilpasninger** i Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="e5d1e-143">Vælg **Tilpas systemet**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="e5d1e-144">Gå til objektet **Kontakt**, udvid det, og vælg **Formularer**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="e5d1e-145">Vælg den kontaktformular, hvor du vil tilføje kontrolelementerne for kundekortet.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e5d1e-146">![Vælge formularen Kontakt](media/contact-active-forms.png "Vælge formularen Kontakt")</span><span class="sxs-lookup"><span data-stu-id="e5d1e-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="e5d1e-147">Hvis du vil tilføje et kontrolelement, skal du i formulareditoren trække et hvilket som helst felt fra **Feltoversigt** til det sted, hvor du vil placere kontrolelementet.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="e5d1e-148">Vælg det felt i den formular, du lige har tilføjet, og vælg **Skift egenskaber**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="e5d1e-149">Gå til fanen **Kontrolelementer**, og vælg **Tilføj kontrolelement**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="e5d1e-150">Vælg et af de tilgængelige brugerdefinerede kontrolelementer, og vælg **Tilføj**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="e5d1e-151">Fjern markeringen i afkrydsningsfeltet **Vis etiket på formularen**, i dialogboksen **Feltegenskaber**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="e5d1e-152">Vælg indstillingen **Internet** for kontrolelementet.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="e5d1e-153">Vælg den type forbedring, du vil have vist, ved at konfigurere feltet **Forbedring**.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="e5d1e-154">Tilføj et særskilt forbedringskontrolelement for hver forbedringstype.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="e5d1e-155">Vælg **Gem** og **Publicer** for at publicere den opdaterede kontaktpersonformular.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="e5d1e-156">Gå til den publicerede kontaktformular.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-156">Go to the published contact form.</span></span> <span data-ttu-id="e5d1e-157">Du kan se det netop tilføjede kontrolelement.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-157">You'll see the newly added control.</span></span> <span data-ttu-id="e5d1e-158">Det kan være nødvendigt at logge på, første gang du bruger det.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="e5d1e-159">Hvis du vil tilpasse det, du vil have vist på det brugerdefinerede kontrolelement, skal du vælge knappen Rediger i øverste højre hjørne.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="e5d1e-160">Opgradere tilføjelsesprogrammet Kundekort</span><span class="sxs-lookup"><span data-stu-id="e5d1e-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="e5d1e-161">Tilføjelsesprogrammet Kundekort opgraderes ikke automatisk.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="e5d1e-162">Hvis du vil opgradere til den nyeste version, skal du følge denne procedure i den Dynamics 365-app, hvor tilføjelsesprogrammet er installeret.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="e5d1e-163">Gå til **Indstillinger** > **Tilpasning** og vælg **Løsninger** i Dynamics 365-appen.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="e5d1e-164">I tabellen over tilføjelsesprogrammer skal du kigge efter **CustomerInsightsCustomerCard** og markere rækken.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="e5d1e-165">Vælg **Anvend løsningsopgradering** på handlingslinjen.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Opgradere løsningen i området Tilpasning i Dynamics 365-apps":::

1. <span data-ttu-id="e5d1e-167">Når du har startet opgraderingsprocessen, kan du se en indlæsningsindikator, indtil opgraderingen er fuldført.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="e5d1e-168">Hvis der ikke findes en nyere version, vises der en fejlmeddelelse i opgraderingen.</span><span class="sxs-lookup"><span data-stu-id="e5d1e-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
