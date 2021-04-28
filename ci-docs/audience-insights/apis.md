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
ms.openlocfilehash: 59161456914df84d7e72402ed1f5faf70a5119ba
ms.sourcegitcommit: a39e00a50ad3eda820fd756c5611081f0ca04662
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/09/2021
ms.locfileid: "5873655"
---
# <a name="work-with-customer-insights-apis"></a>Arbejd med Customer Insights API'er

Dynamics 365 Customer Insights leverer API'er til at opbygge dine egne programmer baseret på data i Customer Insights.

> [!IMPORTANT]
> Oplysninger om disse API'er, der er angivet i [Customer Insights API'er](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). De indeholder yderligere oplysninger om operationer, parametre og svar.

I denne artikel er der en vejledning i, hvordan du får adgang til Customer Insights API'er, opretter en registrering af Azure-app og hjælper dig med at komme i gang med de tilgængelige klientbiblioteker.

## <a name="get-started-trying-the-customer-insights-apis"></a>Kom i gang med at prøve Customer Insights API'er

1. [Log på](https://home.ci.ai.dynamics.com) Customer Insights. Hvis du endnu ikke har et abonnement, kan du [tilmelde dig en prøveversion af Customer Insights](https://aka.ms/tryci).

1. Hvis du vil aktivere API'er til Customer Insights-miljø, skal du gå til **Admin** > **Tilladelser**. Du skal have administratorrettigheder for at gøre det.

1. Gå til fanen **API'er**, og klik på knappen **Aktivér**.    
   Aktivering af API'er opretter en primær og sekundær abonnementsnøgle for den forekomst, der bruges i API-forespørgslerne. Du kan oprette nøglerne igen ved at vælge indstillingen **Genopret primær** eller **Genopret sekundær** i **Admin** > **Tilladelser** > **API'er**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Aktivér Customer Insights API'er":::

1. Vælg **Undersøg vores API'er** for at [afprøve API'er](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Vælg en API-handling, og vælg **Prøv den**.

1. I sideruden skal du angive værdien i rullemenuen **Autorisation** til **implicit**. Overskriften `Authorization` får tilføjet et ihændehavertoken. Din abonnementsnøgle udfyldes automatisk.
  
1. Du kan også tilføje alle nødvendige forespørgselsparametre.

1. Rul ned til bunden af sideruden, og vælg **Send**.

HTTP-svaret vil snart blive vist nedenfor.


   :::image type="content" source="media/try-apis.gif" alt-text="Animeret gif-fil, der viser, hvordan du vælger at teste API'er.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Opret en ny app-registrering på Azure-portalen

Denne fremgangsmåde hjælper dig med at komme i gang med at bruge API'er til Customer Insights i et Azure-program, der bruger uddelegerede tilladelser. Sørg for, at [Start her-afsnittet](#get-started-trying-the-customer-insights-apis) er afsluttet først.

1. Log på [Azure-portalen](https://portal.azure.com) med den konto, der har adgang til Customer Insights-data.

1. Vælg **App-registreringer** i venstre side.

1. Vælg **Ny registrering**, angiv et programnavn og vælge kontotype.
   Tilføj evt. en URL-adresse til omdirigering. http://localhost er tilstrækkelig til at udvikle et program på den lokale computer.

1. Gå til **API-tilladelser** på den nye app-registrering.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animeret gif-fil om at indstille API-tilladelse i appregistrering.":::

1. Vælg **Tilføj en tilladelse**, og vælg **Customer Insights** i sideruden.

1. Vælg **Tilladelsestype** for **Delegerende tilladelser**, og vælg tilladelse til **user_impersonation**.

1. Vælg **Tilføj tilladelser**. Hvis du har brug for at få adgang til API'en uden en bruger, kan du gennemse afsnittet [Server til server-programtilladelser](#server-to-server-application-permissions).

1. Vælg **Tildel administratorsamtykke til...** for at fuldføre app-registreringen.

Du kan bruge program/klient-id'et til denne app-registrering sammen med Microsoft-godkendelsesbiblioteket (MSAL) til at hente ihændehavertoken, der skal sendes sammen med din anmodning til API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animeret gif-fil om at give administratorsamtykke.":::

Du kan finde flere oplysninger om MSAL under [Oversigt over Microsoft-godkendelsesbibliotek (MSAL)](/azure/active-directory/develop/msal-overview).

Du kan finde flere oplysninger om app-registrering i Azure under [Den nye Azure Portal-appregistreringsoplevelse](/azure/active-directory/develop/app-registration-portal-training-guide).

Du kan finde oplysninger om, hvordan du bruger API'er til vores klientbiblioteker, under [Customer Insights i klientbiblioteker](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Server til server-programtilladelser

[App-registreringsafsnittet](#create-a-new-app-registration-in-the-azure-portal) angiver, hvordan du kan registrere en app, der kræver, at brugeren logger på for at blive godkendt. Få mere at vide om, hvordan du opretter en app-registrering, der ikke kræver brugerinteraktion og kan køres på en server.

1. Gå til **API-tilladelser** i din app-registrering i Azure-portalen.

1. Vælg **Tilføj en tilladelse**, og vælg **Customer Insights** i sideruden.

1. Vælg **Tilladelsestype** for **Programtilladelser**, og vælg tilladelse til **CustomerInsights.Api.All**.

1. Vælg **Tilføj tilladelser**.

1. Hvis du vil give administrator samtykke til denne programtilladelse, skal du tilføje en primær tjeneste.

   1. Installer Azure Active Directory (AD) PowerShell-modulet: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Opret forbindelse til din AD-konto: `Connect-AzureAD -TenantId <your tenant id>`. Du kan finde dit lejer-ID i **Oversigt** > **Azure Active Directory**.
   1. Kør følgende kommando for at tilføje en Azure AD-primær tjeneste: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Parameteren AppID gælder for det API-app til Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Primær tjeneste, eksempel":::

1. Gå tilbage til **API-tilladelser** for din app-registrering.

1. Vælg **Tildel administratorsamtykke til...** for at fuldføre app-registreringen.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animeret gif-fil om at give administratorsamtykke.":::

1. Hvis du vil afslutte, skal du tilføje navnet på app-registreringen som en bruger i Customer Insights.    
   Åbn Customer Insights, gå til **Admin** > **Tilladelser**, og vælg **Tilføj bruger**.

1. Søg efter navnet på din app-registrering, vælg det i søgeresultaterne, og vælg **Gem**.

## <a name="customer-insights-client-libraries"></a>Customer Insights-klientbiblioteker

Dette afsnit hjælper dig med at komme i gang med at bruge de klientbiblioteker, der er tilgængelige for API'er til Customer Insights. Alle bibliotekskildekoder og eksempelprogrammer findes på [Customer Insights GitHub-siden](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Få mere at vide om, hvordan du kommer i gang med at bruge C#-klientbiblioteker fra NuGet.org. Du kan finde flere oplysninger om NuGet-pakken i [Microsoft. Dynamics. CustomerInsights. API](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Denne pakke er i øjeblikket rettet mod netstandard 2.0 og netcoreapp 2.0-strukturerne.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Tilføjelse af klientbiblioteket C# til et C#-projekt

1. I Visual Studio skal du åbne **NuGet-pakkestyring** til dit projekt.

1. Søg efter **Microsoft. Dynamics. CustomerInsights.Api**.

1. Vælg **Installér** for at tilføje pakken til projektet.
   Du kan også køre denne kommando i **NuGet-pakkestyringskonsollen**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Tilføj NuGet-pakken til Visual Studio-projektet":::

#### <a name="use-the-c-client-library"></a>Brug af klientbiblioteket C#

1. Brug [Microsoft-godkendelsesbiblioteket (MSAL)](/azure/active-directory/develop/msal-overview) til at hente en `AccessToken` ved hjælp af en eksisterende [Azure-app-registrering](#create-a-new-app-registration-in-the-azure-portal).

1. Når du har fuldført godkendelse og hentning af et token, skal du oprette en ny eller bruge et eksisterende `HttpClient` med ekstra **DefaultRequestHeaders-"Authorization"**, der er angivet til **Ihændehaver <access token>** og **Ocp-Apim-Subscription-Key** er indstillet til [**abonnementsnøglen** fra Customer Insights-miljø](#get-started-trying-the-customer-insights-apis).    
   Nulstil overskriften **Godkendelse**, hvis det er relevant. Når tokenet f. eks. er udløbet.

1. Det skal overføres `HttpClient` til konstruktion af `CustomerInsights`-klienten.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Eksempel på httpclient":::

1. Foretag opkald med klienten i "udvidelsesmetoder" som f.eks. `GetAllInstancesAsync`. Hvis adgangen til den underliggende `Microsoft.Rest.HttpOperationResponse` er foretrukket, skal du bruge http-meddelelsesmetoder som f.eks. `GetAllInstancesWithHttpMessagesAsync`.

1. Svaret vil sandsynligvis være typen `object`, fordi metoden kan returnere flere typer (f. eks `IList<InstanceInfo>` og `ApiErrorResult`). Hvis du vil kontrollere returtypen, kan du sikkert konvertere objekterne til de responstyper, der er angivet på siden [API-detaljer](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for den pågældende handling.    
   Hvis der er behov for flere oplysninger om anmodningen, kan du bruge **http-meddelelsesmetoderne** til at få adgang til RAW-svarobjektet.

### <a name="nodejs-package"></a>NodeJS-pakke

Brug de NodeJS-klientbiblioteker, der er tilgængelige gennem NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python-pakke

Brug de Python-klientbiblioteker, der er tilgængelige gennem PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
