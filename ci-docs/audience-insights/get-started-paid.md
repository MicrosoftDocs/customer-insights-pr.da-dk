---
title: Oprette og konfigurere en betalt licens til Customer Insights
description: Trin til at få et licenseret abonnement på Dynamics 365 Customer Insights og konfigurere det.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034445"
---
# <a name="get-started-with-a-paid-subscription"></a>Introduktion til betalt abonnement

I denne artikel forklares, hvordan du opretter et nyt miljø, når organisationen har købt et Dynamics 365 Customer Insights-abonnement. Hvis du gerne vil købe Customer Insights, vises vores kontaktmuligheder på [Dynamics 365 Customer Insights-hjemmesiden](https://dynamics.microsoft.com/ai/customer-insights/). 

Hvis du vil prøve tjenesten og funktionerne, skal du se [Konfigurere et prøvemiljø](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Oprette et miljø i en eksisterende organisation

Når du har købt en abonnementslicens til Customer Insights, modtager den globale administrator af Microsoft 365-lejeren en mail, der inviterer dem til at oprette miljøet. Gå til [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) for at komme i gang. 

Customer Insights er ikke licenseret pr. bruger, så det vises ikke i området Licenser. Hvis du leder efter licensen i Microsoft 365 Administration, skal du gå til **Dine produkter**. 

> [!NOTE]
> Organisationer kan oprette *to* miljøer for alle Customer Insights-licenser. Hvis din organisation køber licenser mere end én gang, skal du [kontakte vores supporttteam](https://go.microsoft.com/fwlink/?linkid=2079641) for at få flere tilgængelige miljøer. Du kan finde flere oplysninger om kapacitet og tilføjelseskapacitet ved at hente [licensvejledningen til Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Sådan opretter du et miljø:

1. Vælg **Nyt miljø** i dialogboksen **Opret et miljø**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog til oprettelse af en ny forbindelse til Customer Insights.":::

   Vi anbefaler, at du starter med at konfigurere et miljø fra bunden. Men hvis du er administrator eller medlem af et prøvemiljø, kan du [kopiere data fra et andet miljø](manage-environments.md#copy-the-environment-configuration) ved at vælge **Kopier fra eksisterende miljø**. Du får vist en liste over alle tilgængelige miljøer i din organisation, som du kan kopiere data fra.

1. Angiv følgende oplysninger:
   - **Navn**: Navnet på dette miljø. Dette felt er allerede udfyldt, hvis du har kopieret et eksisterende miljø, men du kan ændre det.
   - **Område**: Det område, hvor tjenesten er installeret og har sin vært.
   - **Type**: Vælg, om du vil oprette et produktions- eller sandkassemiljø. Sandkassemiljøer tillader ikke planlagt dataopdatering og er beregnet til forudimplementering og test.
   
1. Du kan også vælge **Avancerede indstillinger**:

   - **Gem alle data i**: Angiver, hvor du vil gemme de outputdata, der er genereret fra Customer Insights. Du har to muligheder: **Customer Insights Storage** (et Azure Data Azure-område, der administreres af Customer Insights-teamet) og **Azure Data Lake Storage** (dit eget Azure Data Lake Storage). Som standard er indstillingen Customer Insights-lager valgt.

     > [!NOTE]
     > Når du gemmer data i Azure Data Lake Storage, accepterer du, at data overføres til og gemmes på den relevante geografiske placering for den pågældende Azure Storage-konto, som kan være forskellig fra den placering, hvor data gemmes i Dynamics 365 Customer Insights. [Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration.](https://www.microsoft.com/trust-center)
     >
     > I øjeblikket gemmes indtagne objekter fra Power BI-dataflows i den Microsoft Dataverse-styrede Data Lake. 
     > 
     > Vi understøtter kun Azure Data Lake Storage-firmaer fra det samme Azure-område, som du valgte under oprettelsen af miljøet. 
     > 
     > Vi understøtter kun Azure Data Lake Storage-firmaer, hvor hierarkisk navneområde er aktiveret.


   - Du kan vælge mellem en ressourcebaseret indstilling og en abonnementsbaseret indstilling for godkendelse for Azure Data Lake Storage-indstillingen. Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md). Navnet **Beholder** kan ikke ændres og vil blive `customerinsights`.
   
   - Hvis du vil bruge [standardmodeller](predictions-overview.md#out-of-box-models), konfigurere datadeling med Microsoft Dataverse eller aktivere dataindtagelse fra det lokale miljø datakilder, skal du angive Microsoft Dataverse-miljøets URL-adresse under **Konfigurer datadeling med Microsoft Dataverse og aktivere yderligere funktioner**. Vælg **Aktivér datadeling** for at dele Customer Insights-outputdata med Microsoft Dataverse-administreret Data Lake.

     > [!NOTE]
     > - Datadeling med Microsoft Dataverse Administreret Data Lake understøttes ikke i øjeblikket, når du gemmer alle data i din egen Azure Data Lake Storage.
     > - [Forudsigelse manglende værdier i et objekt](predictions.md) understøttes i øjeblikket ikke, når du aktiverer datadeling med Microsoft Dataverse Administreret Data Lake.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Konfigurationsindstillinger, der aktiverer datadeling med Microsoft Dataverse.":::

   Når systemprocesser som datalagring er fuldført, oprettes der tilsvarende mapper på den angivne lagerkonto. Datafiler og model.json-filer oprettes og føjes til mapper baseret på procesnavnet.

   Hvis du opretter flere miljøer med Customer Insights og vælger at gemme outputenhederne fra de pågældende miljøer i lagerkontoen, oprettes der separate mapper for hvert miljø med ci_<environmentid> i beholderen.

1. Vælg **Opret** for at konfigurere et miljø. 

## <a name="configure-an-environment"></a>Konfigurere et miljø

Gennemgå følgende artikler for at hjælpe dig med at komme i gang med at konfigurere Customer Insights. 

- [Tilføj flere brugere, og tildel tilladelser](permissions.md).
- [Gennemgå datakilderne](data-sources.md) og kør dem gennem [processen til enhed af data](data-unification.md) for at få [ensartede kundeprofiler](customer-profiles.md).
- [Forbedr de ensartede kundeprofiler](enrichment-hub.md) eller [kør intelligente modeller](predictions-overview.md).
- Opret [segmenter](segments.md) for at gruppere kunder og [målgennemgang](measures.md) af nøgletal.
- Opret [forbindelser](connections.md) og [eksporter](export-destinations.md) for at behandle undersæt af dataene i andre programmer.
