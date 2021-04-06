---
title: Arbejde med API'er
description: Brug af API'er og forstå begrænsningerne.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710453"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="0dc46-103">Arbejd med Customer Insights API'er</span><span class="sxs-lookup"><span data-stu-id="0dc46-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="0dc46-104">Dynamics 365 Customer Insights leverer API'er til at opbygge dine egne programmer baseret på data i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0dc46-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0dc46-105">Oplysninger om disse API'er, der er angivet i [Customer Insights API'er](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="0dc46-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="0dc46-106">De indeholder yderligere oplysninger om operationer, parametre og svar.</span><span class="sxs-lookup"><span data-stu-id="0dc46-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="0dc46-107">I denne artikel er der en vejledning i, hvordan du får adgang til Customer Insights API'er, opretter en registrering af Azure-app og hjælper dig med at komme i gang med de tilgængelige klientbiblioteker.</span><span class="sxs-lookup"><span data-stu-id="0dc46-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="0dc46-108">Kom i gang med at prøve Customer Insights API'er</span><span class="sxs-lookup"><span data-stu-id="0dc46-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="0dc46-109">[Log på](https://home.ci.ai.dynamics.com) Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0dc46-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="0dc46-110">Hvis du endnu ikke har et abonnement, kan du [tilmelde dig en prøveversion af Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="0dc46-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="0dc46-111">Hvis du vil aktivere API'er til Customer Insights-miljø, skal du gå til **Admin** > **Tilladelser**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="0dc46-112">Du skal have administratorrettigheder for at gøre det.</span><span class="sxs-lookup"><span data-stu-id="0dc46-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="0dc46-113">Gå til fanen **API'er**, og klik på knappen **Aktivér**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="0dc46-114">Aktivering af API'er opretter en primær og sekundær abonnementsnøgle for den forekomst, der bruges i API-forespørgslerne.</span><span class="sxs-lookup"><span data-stu-id="0dc46-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="0dc46-115">Du kan oprette nøglerne igen ved at vælge indstillingen **Genopret primær** eller **Genopret sekundær** i **Admin** > **Tilladelser** > **API'er**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Aktivér Customer Insights API'er":::

1. <span data-ttu-id="0dc46-117">Vælg **Undersøg vores API'er** for at [afprøve API'er](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="0dc46-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="0dc46-118">Vælg en API-handling, og vælg **Prøv den**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="0dc46-119">I sideruden skal du angive værdien i rullemenuen **Autorisation** til **implicit**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="0dc46-120">Overskriften `Authorization` får tilføjet et ihændehavertoken.</span><span class="sxs-lookup"><span data-stu-id="0dc46-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="0dc46-121">Din abonnementsnøgle udfyldes automatisk.</span><span class="sxs-lookup"><span data-stu-id="0dc46-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="0dc46-122">Du kan også tilføje alle nødvendige forespørgselsparametre.</span><span class="sxs-lookup"><span data-stu-id="0dc46-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="0dc46-123">Rul ned til bunden af sideruden, og vælg **Send**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="0dc46-124">HTTP-svaret vil snart blive vist nedenfor.</span><span class="sxs-lookup"><span data-stu-id="0dc46-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="Animeret gif-fil, der viser, hvordan du vælger at teste API'er.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="0dc46-126">Opret en ny app-registrering på Azure-portalen</span><span class="sxs-lookup"><span data-stu-id="0dc46-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="0dc46-127">Denne fremgangsmåde hjælper dig med at komme i gang med at bruge API'er til Customer Insights i et Azure-program, der bruger uddelegerede tilladelser.</span><span class="sxs-lookup"><span data-stu-id="0dc46-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="0dc46-128">Sørg for, at [Start her-afsnittet](#get-started-trying-the-customer-insights-apis) er afsluttet først.</span><span class="sxs-lookup"><span data-stu-id="0dc46-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="0dc46-129">Log på [Azure-portalen](https://portal.azure.com) med den konto, der har adgang til Customer Insights-data.</span><span class="sxs-lookup"><span data-stu-id="0dc46-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="0dc46-130">Vælg **App-registreringer** i venstre side.</span><span class="sxs-lookup"><span data-stu-id="0dc46-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="0dc46-131">Vælg **Ny registrering**, angiv et programnavn og vælge kontotype.</span><span class="sxs-lookup"><span data-stu-id="0dc46-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="0dc46-132">Tilføj evt. en URL-adresse til omdirigering.</span><span class="sxs-lookup"><span data-stu-id="0dc46-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="0dc46-133">http://localhost er tilstrækkelig til at udvikle et program på den lokale computer.</span><span class="sxs-lookup"><span data-stu-id="0dc46-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="0dc46-134">Gå til **API-tilladelser** på den nye app-registrering.</span><span class="sxs-lookup"><span data-stu-id="0dc46-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animeret gif-fil om at indstille API-tilladelse i appregistrering.":::

1. <span data-ttu-id="0dc46-136">Vælg **Tilføj en tilladelse**, og vælg **Customer Insights** i sideruden.</span><span class="sxs-lookup"><span data-stu-id="0dc46-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="0dc46-137">Vælg **Tilladelsestype** for **Delegerende tilladelser**, og vælg tilladelse til **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="0dc46-138">Vælg **Tilføj tilladelser**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-138">Select **Add permissions**.</span></span> <span data-ttu-id="0dc46-139">Hvis du har brug for at få adgang til API'en uden en bruger, kan du gennemse afsnittet [Server til server-programtilladelser](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="0dc46-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="0dc46-140">Vælg **Tildel administratorsamtykke til...** for at fuldføre app-registreringen.</span><span class="sxs-lookup"><span data-stu-id="0dc46-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="0dc46-141">Du kan bruge program/klient-id'et til denne app-registrering sammen med Microsoft-godkendelsesbiblioteket (MSAL) til at hente ihændehavertoken, der skal sendes sammen med din anmodning til API.</span><span class="sxs-lookup"><span data-stu-id="0dc46-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animeret gif-fil om at give administratorsamtykke.":::

<span data-ttu-id="0dc46-143">Du kan finde flere oplysninger om MSAL under [Oversigt over Microsoft-godkendelsesbibliotek (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="0dc46-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="0dc46-144">Du kan finde flere oplysninger om app-registrering i Azure under [Den nye Azure Portal-appregistreringsoplevelse](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="0dc46-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="0dc46-145">Du kan finde oplysninger om, hvordan du bruger API'er til vores klientbiblioteker, under [Customer Insights i klientbiblioteker](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="0dc46-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="0dc46-146">Server til server-programtilladelser</span><span class="sxs-lookup"><span data-stu-id="0dc46-146">Server-to-server application permissions</span></span>

<span data-ttu-id="0dc46-147">[App-registreringsafsnittet](#create-a-new-app-registration-in-the-azure-portal) angiver, hvordan du kan registrere en app, der kræver, at brugeren logger på for at blive godkendt.</span><span class="sxs-lookup"><span data-stu-id="0dc46-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="0dc46-148">Få mere at vide om, hvordan du opretter en app-registrering, der ikke kræver brugerinteraktion og kan køres på en server.</span><span class="sxs-lookup"><span data-stu-id="0dc46-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="0dc46-149">Gå til **API-tilladelser** i din app-registrering i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="0dc46-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="0dc46-150">Vælg **Tilføj en tilladelse**, og vælg **Customer Insights** i sideruden.</span><span class="sxs-lookup"><span data-stu-id="0dc46-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="0dc46-151">Vælg **Tilladelsestype** for **Programtilladelser**, og vælg tilladelse til **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="0dc46-152">Vælg **Tilføj tilladelser**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="0dc46-153">Hvis du vil give administrator samtykke til denne programtilladelse, skal du tilføje en primær tjeneste.</span><span class="sxs-lookup"><span data-stu-id="0dc46-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="0dc46-154">Installer Azure Active Directory (AD) PowerShell-modulet: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="0dc46-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="0dc46-155">Opret forbindelse til din AD-konto: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="0dc46-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="0dc46-156">Du kan finde dit lejer-ID i **Oversigt** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="0dc46-157">Kør følgende kommando for at tilføje en Azure AD-primær tjeneste: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Parameteren AppID gælder for det API-app til Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0dc46-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Primær tjeneste, eksempel":::

1. <span data-ttu-id="0dc46-159">Gå tilbage til **API-tilladelser** for din app-registrering.</span><span class="sxs-lookup"><span data-stu-id="0dc46-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="0dc46-160">Vælg **Tildel administratorsamtykke til...** for at fuldføre app-registreringen.</span><span class="sxs-lookup"><span data-stu-id="0dc46-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animeret gif-fil om at give administratorsamtykke.":::

1. <span data-ttu-id="0dc46-162">Hvis du vil afslutte, skal du tilføje navnet på app-registreringen som en bruger i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0dc46-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="0dc46-163">Åbn Customer Insights, gå til **Admin** > **Tilladelser**, og vælg **Tilføj bruger**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="0dc46-164">Søg efter navnet på din app-registrering, vælg det i søgeresultaterne, og vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="0dc46-165">Customer Insights-klientbiblioteker</span><span class="sxs-lookup"><span data-stu-id="0dc46-165">Customer Insights client libraries</span></span>

<span data-ttu-id="0dc46-166">Dette afsnit hjælper dig med at komme i gang med at bruge de klientbiblioteker, der er tilgængelige for API'er til Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0dc46-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="0dc46-167">Alle bibliotekskildekoder og eksempelprogrammer findes på [Customer Insights GitHub-siden](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="0dc46-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="0dc46-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="0dc46-168">C# NuGet</span></span>

<span data-ttu-id="0dc46-169">Få mere at vide om, hvordan du kommer i gang med at bruge C#-klientbiblioteker fra NuGet.org. Du kan finde flere oplysninger om NuGet-pakken i [Microsoft. Dynamics. CustomerInsights. API](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="0dc46-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="0dc46-170">Denne pakke er i øjeblikket rettet mod netstandard 2.0 og netcoreapp 2.0-strukturerne.</span><span class="sxs-lookup"><span data-stu-id="0dc46-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="0dc46-171">Tilføjelse af klientbiblioteket C# til et C#-projekt</span><span class="sxs-lookup"><span data-stu-id="0dc46-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="0dc46-172">I Visual Studio skal du åbne **NuGet-pakkestyring** til dit projekt.</span><span class="sxs-lookup"><span data-stu-id="0dc46-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="0dc46-173">Søg efter **Microsoft. Dynamics. CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="0dc46-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="0dc46-174">Vælg **Installér** for at tilføje pakken til projektet.</span><span class="sxs-lookup"><span data-stu-id="0dc46-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="0dc46-175">Du kan også køre denne kommando i **NuGet-pakkestyringskonsollen**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="0dc46-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Tilføj NuGet-pakken til Visual Studio-projektet":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="0dc46-177">Brug af klientbiblioteket C#</span><span class="sxs-lookup"><span data-stu-id="0dc46-177">Use the C# client library</span></span>

1. <span data-ttu-id="0dc46-178">Brug [Microsoft-godkendelsesbiblioteket (MSAL)](/azure/active-directory/develop/msal-overview) til at hente en `AccessToken` ved hjælp af en eksisterende [Azure-app-registrering](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="0dc46-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="0dc46-179">Når du har fuldført godkendelse og hentning af et token, skal du oprette en ny eller bruge et eksisterende `HttpClient` med ekstra **DefaultRequestHeaders-"Authorization"**, der er angivet til **Ihændehaver <access token>** og **Ocp-Apim-Subscription-Key** er indstillet til [**abonnementsnøglen** fra Customer Insights-miljø](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="0dc46-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="0dc46-180">Nulstil overskriften **Godkendelse**, hvis det er relevant.</span><span class="sxs-lookup"><span data-stu-id="0dc46-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="0dc46-181">Når tokenet f. eks. er udløbet.</span><span class="sxs-lookup"><span data-stu-id="0dc46-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="0dc46-182">Det skal overføres `HttpClient` til konstruktion af `CustomerInsights`-klienten.</span><span class="sxs-lookup"><span data-stu-id="0dc46-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Eksempel på httpclient":::

1. <span data-ttu-id="0dc46-184">Foretag opkald med klienten i "udvidelsesmetoder" som f.eks. `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="0dc46-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="0dc46-185">Hvis adgangen til den underliggende `Microsoft.Rest.HttpOperationResponse` er foretrukket, skal du bruge http-meddelelsesmetoder som f.eks. `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="0dc46-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="0dc46-186">Svaret vil sandsynligvis være typen `object`, fordi metoden kan returnere flere typer (f. eks `IList<InstanceInfo>` og `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="0dc46-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="0dc46-187">Hvis du vil kontrollere returtypen, kan du sikkert konvertere objekterne til de responstyper, der er angivet på siden [API-detaljer](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for den pågældende handling.</span><span class="sxs-lookup"><span data-stu-id="0dc46-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="0dc46-188">Hvis der er behov for flere oplysninger om anmodningen, kan du bruge **http-meddelelsesmetoderne** til at få adgang til RAW-svarobjektet.</span><span class="sxs-lookup"><span data-stu-id="0dc46-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="0dc46-189">NodeJS-pakke</span><span class="sxs-lookup"><span data-stu-id="0dc46-189">NodeJS package</span></span>

<span data-ttu-id="0dc46-190">Brug de NodeJS-klientbiblioteker, der er tilgængelige gennem NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="0dc46-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="0dc46-191">Python-pakke</span><span class="sxs-lookup"><span data-stu-id="0dc46-191">Python package</span></span>

<span data-ttu-id="0dc46-192">Brug de Python-klientbiblioteker, der er tilgængelige gennem PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="0dc46-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
