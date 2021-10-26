---
title: Oprette miljøer i Customer Insights
description: Trin til oprettelse af miljøer med licensabonnement til Dynamics 365 Customer Insights.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 95afd1fedb98a451e4978ee66be2ea98ad7a4a76
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645676"
---
# <a name="create-an-environment-in-audience-insights"></a>Oprette et miljø i målgruppeindsigt

I denne artikel forklares, hvordan du opretter et nyt miljø, når organisationen har købt et Dynamics 365 Customer Insights-abonnement. 

Organisationer kan oprette *to* miljøer for alle Customer Insights-licenser. Hvis din organisation køber mere end én licens, skal du [kontakte vores supportteam](https://go.microsoft.com/fwlink/?linkid=2079641) for at få flere tilgængelige miljøer. Du kan finde flere oplysninger om kapacitet og tilføjelseskapacitet ved at hente [licensvejledningen til Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Hvis du vil prøve tjenesten, kan du gå til [Konfigurere et prøvemiljø](../trial-signup.md).

## <a name="create-a-new-environment"></a>Opret et nyt miljø

Når du har købt en abonnementslicens til Customer Insights, modtager den globale administrator af Microsoft 365-lejeren en mail, der inviterer dem til at oprette miljøet. Gå til [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) for at komme i gang. 

En styret oplevelse hjælper dig gennem trinnene til at indsamle alle nødvendige oplysninger til et nyt miljø. Du skal have [administratortilladelser](permissions.md) i målgruppeindsigt til at oprette eller administrere miljøer.

1. Åbn miljøvælgeren i målgruppeindsigt, og vælg **+ Ny**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Vælg miljøvælgeren.":::

1. Følg den styrede oplevelse, der er skitseret i følgende afsnit.

### <a name="step-1-provide-environment-information"></a>Trin 1: Angiv miljøoplysninger

I trinnet **Grundlæggende oplysninger** skal du vælge, om du vil oprette et miljø fra bunden eller [kopiere data fra et andet miljø](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog til oprettelse af en ny forbindelse til Customer Insights.":::

Angiv følgende oplysninger:
   - **Navn**: Navnet på dette miljø. Dette felt er allerede udfyldt, hvis du har kopieret et eksisterende miljø, men du kan ændre det.
   - **Vælg din forretning**: Vælg den primære målgruppe til det nye miljø. Du kan arbejde med individuelle kunder (B2C) eller [forretningskonti](work-with-business-accounts.md) (B2B).
   - **Type**: Vælg, om du vil oprette et produktions- eller sandkassemiljø. Sandkassemiljøer tillader ikke planlagt dataopdatering og er beregnet til forudimplementering og test. Sandkassemiljøer bruger samme primære målgruppe som det produktionsmiljø, der i øjeblikket er valgt.
   - **Område**: Det område, hvor tjenesten er installeret og har sin vært.

### <a name="step-2-configure-data-storage"></a>Trin 2: Konfigurer datalager

I trinnet **Datalager** skal du vælge, hvor dataene skal lagres fra målgruppeindsigt.

Du har to muligheder: **Customer Insights Storage** (et Azure Data Azure-område, der administreres af Customer Insights-teamet) og **Azure Data Lake Storage** (dit eget Azure Data Lake Storage). Som standard er indstillingen Customer Insights-lager valgt.

:::image type="content" source="media/data-storage-environment.png" alt-text="Vælg Azure Data Lake Storage, hvor du vil gemme målgruppeindsigtsdata.":::

Når du gemmer data i Azure Data Lake Storage, accepterer du, at data overføres til og gemmes på den relevante geografiske placering for den pågældende Azure-lagerkonto. Denne placering kan adskille sig fra, hvor data lagres i Dynamics 365 Customer Insights. Få mere at vide i [Microsofts center for sikkerhed og rettigheder](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights understøtter i øjeblikket følgende:
> - Objekter, der er indtaget fra Power BI-datastrømme, som er gemt i en Microsoft Dataverse-administreret Data Lake.  
> - Azure Data Lake Storage-konti fra det samme Azure-område, som du valgte under oprettelse af miljøet.
> - Azure Data Lake Storage-firmaer, hvor *hierarkisk navneområde* er aktiveret.

Du kan vælge mellem en ressourcebaseret indstilling og en abonnementsbaseret indstilling for godkendelse for Azure Data Lake Storage-indstillingen. Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md). Navnet **Beholder** er `customerinsights` og kan ikke ændres.

Når systemprocesser, f.eks. dataindtagelse, er fuldført, oprettes der tilsvarende mapper på den angivne lagerkonto. Datafiler og *model.json*-filer oprettes og føjes til mapper baseret på procesnavnet.

Hvis du opretter flere miljøer i Customer Insights og vælger at gemme outputobjekterne fra disse miljøer i lagerkontoen, opretter Customer Insights separate mapper for de enkelte miljøer med `ci_environmentID` i beholderen.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Trin 3: Opret forbindelse til Microsoft Dataverse
   
Med **Microsoft Dataverse**-trinnet kan du forbinde Customer Insights til dit Dataverse-miljø.

Hvis du vil bruge de [indbyggede forudsigelsesmodeller](predictions-overview.md#out-of-box-models), skal du konfigurere datadeling med Dataverse. Du kan også aktivere dataindtagelse fra datakilder i det lokale miljø, hvis du angiver den Microsoft Dataverse-URL-adresse til miljøet, som din organisation administrerer. Vælg **Aktivér datadeling** for at dele Customer Insights-outputdata med Dataverse-administreret Data Lake.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Konfigurationsindstillinger, der aktiverer datadeling med Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights understøtter ikke følgende scenarier til datadeling:
> - Hvis du gemmer alle data i dit eget Azure Data Lake Storage, kan du ikke aktivere datadeling med en Microsoft Dataverse-administreret Data Lake.
> - Hvis du aktiverer datadeling med en Microsoft Dataverse-administreret Data Lake, kan du ikke [oprette forudsagte eller manglende værdier i et objekt](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Trin 4: Fuldfør indstillingerne

Gennemgå alle de angivne indstillinger i trinnet **Gennemse**. Når alt ser ud, som det skal, skal du vælge **Opret** for at konfigurere miljøet. 

Du kan også ændre de fleste indstillinger senere. Du kan finde flere oplysninger under [Administrere miljøer](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbejde med dit nye miljø

Gennemgå følgende artikler for at hjælpe dig med at komme i gang med at konfigurere Customer Insights. 

- [Tilføj flere brugere, og tildel tilladelser](permissions.md).
- [Gennemgå datakilderne](data-sources.md) og kør dem gennem [processen til enhed af data](data-unification.md) for at få [ensartede kundeprofiler](customer-profiles.md).
- [Forbedr de ensartede kundeprofiler](enrichment-hub.md) eller [kør intelligente modeller](predictions-overview.md).
- [Opret segmenter](segments.md) for at gruppere kunder og [målingers](measures.md) gennemgangs-nøgletal.
- [Opret forbindelser](connections.md) og [eksporter](export-destinations.md) for at behandle undersæt af dataene i andre programmer.
