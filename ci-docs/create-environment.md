---
title: Oprette miljøer i Customer Insights
description: Trin til oprettelse af miljøer med licensabonnement til Dynamics 365 Customer Insights.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0efda9d2997bcfd069b6d2445b69d159d7d3e59b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646036"
---
# <a name="create-an-environment-in-customer-insights"></a>Oprette et miljø i Customer Insights

I denne artikel forklares, hvordan du opretter et nyt miljø, når organisationen har købt et Dynamics 365 Customer Insights-abonnement. 

Organisationer kan oprette flere miljøer for hver Customer Insights-licens. Hvis din organisation køber mere end én licens, skal du [kontakte vores supportteam](https://go.microsoft.com/fwlink/?linkid=2079641) for at få flere tilgængelige miljøer. Du kan finde flere oplysninger om kapacitet og kapacitet til tilføjelser i [Dynamics 365-licensvejledningen](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Hvis du vil prøve tjenesten, kan du gå til [Konfigurere et prøvemiljø](trial-signup.md).

## <a name="create-a-new-environment"></a>Opret et nyt miljø

Efter køb af en abonnementslicens til Customer Insights, modtager Microsoft 365-lejerens globale administrator en mail, hvor de opfordres til at oprette miljøet. Gå til [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) for at komme i gang. 

En styret oplevelse hjælper dig gennem trinnene til at indsamle alle nødvendige oplysninger til et nyt miljø. Du skal have [administratortilladelser](permissions.md) i Customer Insights til at oprette eller administrere miljøer.

1. Åbn miljøvælgeren, og vælg **+ Ny**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Vælg miljøvælgeren.":::

1. Følg den styrede oplevelse, der er skitseret i følgende afsnit.

### <a name="step-1-provide-environment-information"></a>Trin 1: Angiv miljøoplysninger

I trinnet **Grundlæggende oplysninger** skal du vælge, om du vil oprette et miljø fra bunden eller [kopiere data fra et andet miljø](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog til oprettelse af en ny forbindelse til Customer Insights.":::

Angiv følgende oplysninger:
   - **Navn**: Navnet på dette miljø. Dette felt er allerede udfyldt, hvis du har kopieret et eksisterende miljø, men du kan ændre det.
   - **Vælg din forretning**: Vælg den primære målgruppe til det nye miljø. Du kan arbejde med individuelle firmaer (B-til-C) eller [forretningskonti](work-with-business-accounts.md) (B-til-B).
   - **Type**: Vælg, om du vil oprette et produktions- eller sandkassemiljø. Sandkassemiljøer tillader ikke planlagt dataopdatering og er beregnet til forudimplementering og test. Sandkassemiljøer bruger samme primære målgruppe som det produktionsmiljø, der i øjeblikket er valgt.
   - **Område**: Det område, hvor tjenesten er installeret og har sin vært.

### <a name="step-2-configure-data-storage"></a>Trin 2: Konfigurer datalager

I trinnet **Datalager** skal du vælge, hvor dataene fra Customer Insights skal lagres.

Du har to muligheder: **Customer Insights Storage** (Azure-datasø, der administreres af Customer Insights-teamet) og **Azure Data Lake Storage** (dit eget Azure Data Lake Storage). Som standard er indstillingen Customer Insights-lager valgt.

:::image type="content" source="media/data-storage-environment.png" alt-text="Vælg Azure Data Lake Storage for at lagre dine data.":::

Når du gemmer data i Azure Data Lake Storage, accepterer du, at data overføres til og gemmes på den relevante geografiske placering for den pågældende Azure-lagerkonto. Denne placering kan adskille sig fra, hvor data lagres i Dynamics 365 Customer Insights. Få mere at vide i [Microsofts center for sikkerhed og rettigheder](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights understøtter i øjeblikket følgende:
> - Objekter, der er indtaget fra Power BI-datastrømme, som er gemt i en Microsoft Dataverse-administreret Data Lake.  
> - Azure Data Lake Storage-konti fra det samme Azure-område, som du valgte under oprettelse af miljøet.
> - Azure Data Lake Storage-konti der er Gen2, og som har aktiveret *Hierarkisk navneområde*. Azure Data Lake Gen1-lagerkonti understøttes ikke.

Du kan vælge mellem en ressourcebaseret indstilling og en abonnementsbaseret indstilling for godkendelse for Azure Data Lake Storage-indstillingen. Du kan finde flere oplysninger i [Oprette forbindelse til en Azure Data Lake Storage-konto ved hjælp af en Azure-tjenestekonto](connect-service-principal.md). Der skal findes en beholder med navnet `customerinsights` på lagerkontoen.

Når systemprocesser, f.eks. dataindtagelse, er fuldført, oprettes der tilsvarende mapper på den angivne lagerkonto. Datafiler og *model.json*-filer oprettes og føjes til mapper baseret på procesnavnet.

Hvis du opretter flere miljøer i Customer Insights og vælger at gemme outputobjekterne fra disse miljøer i lagerkontoen, opretter Customer Insights separate mapper for de enkelte miljøer med `ci_environmentID` i beholderen.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Trin 3: Opret forbindelse til Microsoft Dataverse
   
Med **Microsoft Dataverse**-trinnet kan du forbinde Customer Insights til dit Dataverse-miljø.

Tildel dit eget Microsoft Dataverse-miljø mulighed for at dele data (profiler og indsigt) med virksomhedsprogrammer, der er baseret på Dataverse, f.eks. Dynamics 365 Marketing eller modelbaserede programmer i Power Apps. Lad dette felt være tomt, hvis du ikke har dit eget Dataverse-miljø. Vi klargør et til dig.

Hvis du opretter forbindelse til Dataverse-miljøet, kan du også [indtage data fra det lokale miljø datakilder ved hjælp af Power Platform-dataflow og gateways](data-sources.md#add-data-from-on-premises-data-sources). Du kan også bruge [stanard-forudsigelsesmodeller](predictions-overview.md?tabs=b2c#out-of-box-models) ved at oprette forbindelse til et Dataverse-miljø.

> [!IMPORTANT]
> 1. Customer Insights og Dataverse skal være i samme område for at kunne dele data.
> 1. Du skal have en global administratorrolle i Dataverse-miljøet. Kontrollér, om dette [Dataverse-miljø er knyttet](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) til visse sikkerhedsgrupper, og kontrollér, at du er føjet til de pågældende sikkerhedsgrupper.
> 1. Der er ikke allerede knyttet et eksisterende Customer Insights-miljø til det pågældende Dataverse-miljø. Få mere at vide om , hvordan du [fjerner en eksisterende forbindelse til et Dataverse-miljø](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="datadeling med Microsoft Dataverse er automatisk aktiveret for nye forekomster.":::

Du kan finde flere oplysninger om, hvordan du aktiverer datadeling med Microsoft Dataverse fra dit eget Azure Data Lake Storage, under [Oprette forbindelse til Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights understøtter ikke følgende scenarier til datadeling:
- Hvis du aktiverer datadeling med en Dataverse, kan du ikke [oprette forudsagte eller manglende værdier i et objekt](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Trin 4: Fuldfør indstillingerne

Gennemgå alle de angivne indstillinger i trinnet **Gennemse**. Når alt ser ud, som det skal, skal du vælge **Opret** for at konfigurere miljøet. 

Du kan også ændre de fleste indstillinger senere. Du kan finde flere oplysninger under [Administrere miljøer](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbejde med dit nye miljø

Gennemgå følgende artikler for at hjælpe dig med at komme i gang med at konfigurere Customer Insights: 

- [Tilføj flere brugere, og tildel tilladelser](permissions.md).
- [Gennemgå datakilderne](data-sources.md) og kør dem gennem [processen til enhed af data](data-unification.md) for at få [ensartede kundeprofiler](customer-profiles.md).
- [Forbedr de ensartede kundeprofiler](enrichment-hub.md) eller [kør intelligente modeller](predictions-overview.md).
- [Opret segmenter](segments.md) for at gruppere kunder og [målingers](measures.md) til gennemgangs-nøgletal.
- [Opret forbindelser](connections.md) og [eksporter](export-destinations.md) for at behandle undersæt af dataene i andre programmer.
