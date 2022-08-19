---
title: Sådan opretter du et nyt miljø
description: Trin for at oprette miljøer i Dynamics 365 Customer Insights.
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 875cbbd095dfd239ab83c1c80db28ea7c0a04ed0
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245550"
---
# <a name="how-to-create-a-new-environment"></a>Sådan opretter du et nyt miljø

Efter [køb af en abonnementslicens til Dynamics 365 Customer Insights](paid-license.md), modtager Microsoft 365-lejerens globale administrator en mail, hvor de inviteres til at oprette miljøet. Gå til [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) for at komme i gang. I dette scenarie kan du gå direkte til [Trin 1: Angiv grundlæggende oplysninger](#step-1-provide-basic-information).

Når det første miljø er oprettet, kan Microsoft 365-lejerens globale administrator [tilføje brugere fra organisationen som administratorer](permissions.md). Fremover kan disse administratorer administrere brugere og miljøer. Hvis din organisation køber mere end én licens til Customer Insights, skal du [kontakte vores supportteam](https://go.microsoft.com/fwlink/?linkid=2079641) for at få flere tilgængelige miljøer. Du kan finde flere oplysninger om kapacitet og kapacitet til tilføjelser i [Dynamics 365-licensvejledningen](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Hvis du vil prøve tjenesten, kan du gå til [Konfigurere et prøvemiljø](trial-signup.md).

## <a name="prerequisites"></a>Forudsætninger

Du skal have [administratortilladelser](permissions.md) i Customer Insights til at oprette eller administrere miljøer.

## <a name="start-the-environment-creation-process"></a>Start processen til oprettelse af miljø

1. Åbn miljøvælgeren, og vælg **+ Ny**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Vælg miljøvælgeren.":::

1. Følg den guidede oplevelse, der er skitseret i følgende afsnit, for at give alle nødvendige oplysninger til et nyt miljø. Hvis du har konfigureret et miljø tidligere, kan du også [kopiere konfigurationen](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Trin 1: Angiv grundlæggende oplysninger

I trinnet **Grundlæggende oplysninger** skal du vælge, om du vil oprette et miljø fra bunden eller [kopiere data fra et andet miljø](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog til oprettelse af en ny forbindelse til Customer Insights.":::

Angiv følgende oplysninger:

- **Navn**: Navnet på dette miljø. Dette felt er allerede udfyldt, hvis du har kopieret et eksisterende miljø, men du kan ændre det. Hvis du har mere end ét arbejdsmiljø, skal du give hver en let identificerbar visningsnavn.
- **Vælg din forretning**: Vælg den primære målgruppe til det nye miljø. Du kan arbejde med individuelle firmaer (B-til-C) eller [forretningskonti](work-with-business-accounts.md) (B-til-B). Hvis din organisation primært gør forretninger med enkeltpersoner, for eksempel en forhandler eller en cafe, skal du vælge individuelle forbrugere. Hvis din primære målgruppe er andre virksomheder, for eksempel en bilproducent eller en papirvirksomhed, skal du vælge virksomhedskonti.
- **Type**: Vælg, om du vil oprette et produktions- eller sandkassemiljø. Sandkassemiljøer tillader ikke planlagt dataopdatering og er beregnet til forudimplementering og test. Sandkassemiljøer bruger samme primære målgruppe som det produktionsmiljø, der i øjeblikket er valgt.
- **Område**: Det område, hvor tjenesten er installeret og har sin vært. Hvis du vil [bruge din egen Azure Data Lake Storage-konto](own-data-lake-storage.md) eller [oprette forbindelse til en eksisterende Microsoft Dataverse-organisation](customer-insights-dataverse.md), skal Customer Insights-miljøet være i samme område.

## <a name="step-2-configure-data-storage"></a>Trin 2: Konfigurer datalager

I trinnet **Datalager** skal du vælge, hvor dataene fra Customer Insights skal lagres.

Du kan vælge mellem to muligheder:

- **Customer Insights-lager**: Datalager administreres af Customer Insights-teamet. Det er standardindstillingen, og medmindre der er specifikke krav om at gemme data på din egen lagerkonto, anbefales det, at du bruger denne indstilling.
- **Azure Data Lake Storage**: Angiv din egen Azure Data Lake Storage-konto for at gemme dataene, så du har fuld kontrol over, hvor dataene gemmes. Du kan finde flere oplysninger under [Bruge din egen Azure Data Lake Storage-konto](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Vælg den foretrukne mulighed for at lagre dine data.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Trin 3: Opret forbindelse til Microsoft Dataverse

Med **Microsoft Dataverse**-trinnet kan du forbinde Customer Insights til dit Dataverse-miljø. Del data med Dataverse for at bruge dem med virksomhedsprogrammer, der er baseret på Dataverse, for eksempel Dynamics 365 Marketing eller modelbaserede programmer i Power Apps.

Lad dette felt være tomt, hvis du ikke har dit eget Dataverse-miljø. Vi opretter et til dig.

Du kan finde flere oplysninger under [Arbejde med Customer Insights-data i Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="datadeling med Microsoft Dataverse er automatisk aktiveret for nye miljøer.":::

### <a name="step-4-finalize-the-settings"></a>Trin 4: Fuldfør indstillingerne

Gennemgå alle de angivne indstillinger i trinnet **Gennemse**. Når alt ser ud, som det skal, skal du vælge **Opret** for at konfigurere miljøet.

Du kan ændre nogle af indstillingerne senere. Du kan finde flere oplysninger under [Administrere miljøer](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbejde med dit nye miljø

Gennemgå følgende artikler for at hjælpe dig med at komme i gang med at konfigurere Customer Insights:

- [Tilføj flere brugere, og tildel tilladelser](permissions.md).
- [Gennemgå datakilderne](data-sources.md) og kør dem gennem [processen til enhed af data](data-unification.md) for at få [unified customer profiles](customer-profiles.md).
- [Forbedr unified customer profiles](enrichment-hub.md) eller [kør intelligente modeller](predictions-overview.md).
- [Opret segmenter](segments.md) for at gruppere kunder og [målingers](measures.md) til gennemgangs-nøgletal.
- [Opret forbindelser](connections.md) og [eksporter](export-destinations.md) for at behandle undersæt af dataene i andre programmer.

## <a name="copy-the-environment-configuration"></a>Kopier miljøkonfiguration

Som administrator kan du vælge at kopiere konfigurationen fra et eksisterende miljø, når du opretter et nyt.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Skærmbillede af indstillingerne i miljøindstillingerne.":::

Du får vist en liste over alle tilgængelige miljøer i din organisation, som du kan kopiere data fra.

Følgende konfigurationsindstillinger er kopieret:

- Datakilder importeres via Power Query
- Datasamlingskonfiguration
- Segmenter
- Målinger
- Relationer
- Aktiviteter
- Indeks for søgning og filtrering
- Eksport
- Opdater tidsplan
- Forbedringer
- Forudsigelsesmodeller
- Rolletildelinger

## <a name="set-up-a-copied-environment"></a>Konfigurere et kopieret miljø

Når du kopierer miljøkonfigurationen, skal du gennemgå nogle ekstra trin for at bekræfte legitimationsoplysningerne:

- Kundeprofiler. Først skal du godkende og indtage datakilderne og køre processen til samling af data for at genoprette kundeprofilerne.
- Legitimationsoplysninger for datakilde. Du skal angive legitimationsoplysningerne for alle datakilder for at godkende og opdatere datakilderne manuelt.
- Datakilder fra mappen Common Data Model og Dataverse. Du skal oprette disse datakilder manuelt med det samme navn som i kildemiljøet.
- Forbindelseshemmeligheder, der bruges til eksport og forbedringer. Du skal godkende forbindelserne igen og derefter genaktivere forbedringerne og eksporter.

Der vises en bekræftelsesmeddelelse, når det kopierede miljø er blevet oprettet. Vælg **gå til datakilder** for at få vist listen over datakilder.

Alle datakilderne viser en **Legitimationsoplysninger påkrævet** som status. Rediger datakilderne, og angiv legitimationsoplysninger for at opdatere dem.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste over datakilder, der er kopieret og skal godkendes.":::

Når du har opdateret datakilderne, skal du gå til **Data** > **Saml**. Her kan du finde indstillinger fra kildemiljøet. Rediger dem efter behov, eller vælg **Kør**, for at starte datasamlingsprocessen og det samlede kundeobjekt.

Når datasamlingen er fuldført, skal du gå til **Målinger** og **Segmenter** for at opdatere dem.

Før du genaktiverer eksport og forbedringer, skal du gå **til Admin** > **Forbindelser** for at genaktivere forbindelserne i det nye miljø.

[!INCLUDE [footer-include](includes/footer-banner.md)]
