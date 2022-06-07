---
title: Arbejde med API'er
description: Brug af API'er og forstå begrænsningerne.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 9a04276f7326533cd389cba6554f468123463bac
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808499"
---
# <a name="work-with-customer-insights-apis"></a>Arbejd med Customer Insights API'er

Dynamics 365 Customer Insights leverer API'er til at opbygge dine egne applikationer baseret på dine data i Customer Insights.

> [!IMPORTANT]
> Oplysninger om disse API'er, der er angivet i [Customer Insights API'er](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). De indeholder yderligere oplysninger om operationer, parametre og svar.

I denne artikel beskrives, hvordan du kan få adgang til Customer Insights-API'er, oprette en Azure-appregistrering og komme i gang med klientbiblioteker.

## <a name="get-started-trying-the-customer-insights-apis"></a>Kom i gang med at prøve Customer Insights API'er

1. [Log på](https://home.ci.ai.dynamics.com) Customer Insights. Hvis du endnu ikke har et abonnement, kan du [tilmelde dig en prøveversion af Customer Insights](https://aka.ms/tryci).

1. Hvis du vil aktivere API'er i dit Customer Insights-miljø, skal du gå til **Administration** > **Sikkerhed**. Du skal have administratorrettigheder for at gøre det.

1. Gå til fanen **API'er**, og klik på knappen **Aktivér**.    
 
   Aktivering af API'er opretter en primær og sekundær abonnementsnøgle for den forekomst, der bruges i API-forespørgslerne. Du kan genoprette nøglerne ved at vælge **Genopret primær** eller **Genopret sekundær** på **Administration** > **Sikkerhed** > **API'er**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Vælg **Undersøg vores API'er** for at [afprøve API'er](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Vælg en API-handling, og vælg **Prøv den**.

1. Angiv værdien i rullemenuen **Autorisation** i sideruden til **implicit**. `Authorization`-overskriften tilføjes med ihændehavertoken. Din abonnementsnøgle udfyldes automatisk.
  
1. Du kan også tilføje alle nødvendige forespørgselsparametre.

1. Rul ned til bunden af sideruden, og vælg **Send**.

HTTP-svaret vil snart blive vist nedenfor.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Opret en ny app-registrering på Azure-portalen

Disse trin hjælper dig med at komme i gang med at bruge API'erne til Customer Insights i et Azure-program ved hjælp af delegerede tilladelser. Sørg for at fuldføre afsnittet [Introduktion](#get-started-trying-the-customer-insights-apis) først.

1. Log på [Azure-portalen](https://portal.azure.com) med den konto, der har adgang til Customer Insights-data.

1. Vælg **App-registreringer** i venstre side.

1. Vælg **Ny registrering**, angiv et programnavn og vælg kontotype.

   Tilføj evt. en URL-adresse til omdirigering. http://localhost er tilstrækkelig til at udvikle et program på den lokale computer.

1. Gå til **API-tilladelser** på den nye app-registrering.

1. Vælg **Tilføj en tilladelse**, og vælg **Dynamics 365 AI til Customer Insights** i sideruden.

1. Vælg **Delegerede tilladelser** under **Tilladelsestype**, og vælg derefter tilladelsen **user_impersonation**.

1. Vælg **Tilføj tilladelser**. Hvis du har brug for at få adgang til API'en uden en bruger, kan du gennemse afsnittet [Server til server-programtilladelser](#server-to-server-application-permissions).

1. Vælg **Tildel administratorsamtykke til...** for at fuldføre app-registreringen.

Du kan bruge program/klient-id'et til denne app-registrering sammen med Microsoft-godkendelsesbiblioteket (MSAL) til at hente ihændehavertoken, der skal sendes sammen med din anmodning til API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Du kan finde flere oplysninger om MSAL under [Oversigt over Microsoft-godkendelsesbibliotek (MSAL)](/azure/active-directory/develop/msal-overview).

Du kan finde flere oplysninger om app-registrering i Azure under [Registrere et program](/graph/auth-register-app-v2).

Du kan finde oplysninger om brug af API'er i vores klientbiblioteker under [Klientbiblioteker til Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Server til server-programtilladelser

[App-registreringsafsnittet](#create-a-new-app-registration-in-the-azure-portal) angiver, hvordan du kan registrere en app, der kræver, at brugeren logger på for at blive godkendt. Få mere at vide om, hvordan du opretter en app-tilmelding, der ikke kræver brugerkontakt og kan køres på en server.

1. Gå til **API-tilladelser** i din app-registrering i Azure-portalen.

1. Vælg **Tilføj en tilladelse**. 

1. Vælg fanen **API'er, min organisation bruger**, og vælg **Dynamics 365 AI for Customer Insights** på listen. 

1. Vælg **Applikationstilladelser** under **Tilladelsestype**, og vælg derefter tilladelsen **CustomerInsights.Api.All**.

1. Vælg **Tilføj tilladelser**.

1. Gå tilbage til **API-tilladelser** for din app-registrering.

1. Vælg **Tildel administratorsamtykke til...** for at fuldføre app-registreringen.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Hvis du vil afslutte, skal du tilføje navnet på app-registreringen som en bruger i Customer Insights.  
   
   Åbn Customer Insights, gå til **Administration** > **Sikkerhed**, og vælg **Tilføj bruger**.

1. Søg efter navnet på din app-registrering, vælg det i søgeresultaterne, og vælg **Gem**.

## <a name="sample-queries"></a>Eksempelforespørgsler

Vi har samlet en kort liste over OData-eksempelforespørgsler for at arbejde med API'er: [OData-forespørgselseksempler](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insights-klientbiblioteker

Dette afsnit hjælper dig med at komme i gang med at bruge de klientbiblioteker, der er tilgængelige for API'er til Customer Insights. Alle bibliotekskildekoder og eksempelprogrammer findes på [Customer Insights GitHub-siden](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Få mere at vide om, hvordan du kommer i gang med at bruge C#-klientbiblioteker fra NuGet.org. Du kan finde flere oplysninger om NuGet-pakken i [Microsoft. Dynamics. CustomerInsights. API](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Denne pakke er i øjeblikket rettet mod netstandard 2.0 og netcoreapp 2.0-strukturerne.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Tilføjelse af klientbiblioteket C# til et C#-projekt

1. I Visual Studio skal du åbne **NuGet-pakkestyring** til dit projekt.

1. Søg efter **Microsoft. Dynamics. CustomerInsights.Api**.

1. Vælg **Installér** for at tilføje pakken til projektet.
 
   Du kan også køre denne kommando i **NuGet-pakkestyringskonsollen**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Brug af klientbiblioteket C#

1. Brug [Microsoft-godkendelsesbiblioteket (MSAL)](/azure/active-directory/develop/msal-overview) til at hente en `AccessToken` ved hjælp af en eksisterende [Azure-app-registrering](#create-a-new-app-registration-in-the-azure-portal).

1. Når et token er godkendt og håndteret korrekt, skal du oprette et nyt token eller bruge en eksisterende `HttpClient`, hvor **DefaultRequestHeaders "Authorization"** er angivet til **Bearer "adgangstoken"** og **Ocp-Apim-Subscription-Key** angivet til [**abonnementsnøglen** fra Customer Insights-miljøet](#get-started-trying-the-customer-insights-apis).   
 
   Nulstil overskriften **Godkendelse**, hvis det er relevant. Når tokenet f. eks. er udløbet.

1. Det skal overføres `HttpClient` til konstruktion af `CustomerInsights`-klienten.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Foretag opkald med klienten i "udvidelsesmetoder" - f.eks. `GetAllInstancesAsync`. Hvis adgangen til den underliggende `Microsoft.Rest.HttpOperationResponse` er foretrukket, skal du bruge http-meddelelsesmetoder som f.eks. `GetAllInstancesWithHttpMessagesAsync`.

1. Svaret vil sandsynligvis være typen `object`, fordi metoden kan returnere flere typer (f. eks `IList<InstanceInfo>` og `ApiErrorResult`). Hvis du vil kontrollere returtypen, skal du bruge objekterne i de responstyper, der er angivet på [siden med API-detaljer](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for den pågældende handling.    
   
   Hvis der er behov for flere oplysninger om anmodningen, kan du bruge **http-meddelelsesmetoderne** til at få adgang til RAW-svarobjektet.

### <a name="nodejs-package"></a>NodeJS-pakke

Brug de NodeJS-klientbiblioteker, der er tilgængelige gennem NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Python-pakke

Brug de Python-klientbiblioteker, der er tilgængelige gennem PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
