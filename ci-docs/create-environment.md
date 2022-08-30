---
title: Opret et nyt miljø
description: Trin for at oprette miljøer i Dynamics 365 Customer Insights.
ms.date: 08/15/2022
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
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304236"
---
# <a name="create-a-new-environment"></a>Opret et nyt miljø

Efter [køb af en abonnementslicens til Dynamics 365 Customer Insights](paid-license.md), modtager Microsoft 365-lejerens globale administrator en mail, hvor de inviteres til at oprette miljøet. Gå til [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) for at komme i gang. I dette scenarie skal du starte med [Trin 1: Angiv grundlæggende oplysninger](#step-1-provide-basic-information).

Når det første miljø er oprettet, kan Microsoft 365-lejerens globale administrator [tilføje brugere fra sin organisation som administratorer](permissions.md). Derefter kan disse administratorer administrere brugere og miljøer. Hvis din organisation køber mere end én licens til Customer Insights, skal du [kontakte vores supportteam](https://go.microsoft.com/fwlink/?linkid=2079641) for at få flere tilgængelige miljøer. Du kan finde flere oplysninger om kapacitet og kapacitet til tilføjelser i [Dynamics 365-licensvejledningen](https://go.microsoft.com/fwlink/?LinkId=866544). Når du har mulighed for at oprette flere miljøer, skal du gå til [Start processen til oprettelse af miljø](#start-the-environment-creation-process).

> [!TIP]
> Hvis du vil prøve tjenesten, kan du gå til [Konfigurere et prøvemiljø](trial-signup.md).

## <a name="prerequisites"></a>Forudsætninger

[Administratortilladelser](permissions.md) i Customer Insights

## <a name="start-the-environment-creation-process"></a>Start processen til oprettelse af miljø

1. Åbn miljøvælgeren, og vælg **+ Ny**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Vælg miljøvælgeren.":::

1. Følg den guidede oplevelse, der er skitseret i følgende afsnit, for at give alle nødvendige oplysninger til et nyt miljø.

## <a name="step-1-provide-basic-information"></a>Trin 1: Angiv grundlæggende oplysninger

1. Vælg, om du vil oprette et miljø fra bunden eller kopiere data fra et andet miljø. [Kopiering af data fra et andet miljø](#copy-the-environment-configuration) kræver flere trin.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog til oprettelse af en ny forbindelse til Customer Insights.":::

1. Angiv følgende oplysninger:

   - **Navn**: Navnet på dette miljø. Dette felt er allerede udfyldt, hvis du har kopieret et eksisterende miljø, men du kan ændre det.
   - **Vælg din virksomhed**: Primær målgruppe for det nye miljø: individuelle forbrugere (B-til-C) eller [forretningskonti](work-with-business-accounts.md) (B-til-B). Hvis din organisation primært gør forretninger med enkeltpersoner, for eksempel en forhandler eller en cafe, skal du vælge individuelle forbrugere. Hvis din primære målgruppe er andre virksomheder, for eksempel en bilproducent eller papirhandel, skal du vælge virksomhedskonti.
   - **Type**: Type af miljø: produktions- eller sandkassemiljø. Sandkassemiljøer tillader ikke planlagt dataopdatering og er beregnet til forudimplementering og test. Sandkassemiljøer bruger samme primære målgruppe som det produktionsmiljø, der i øjeblikket er valgt.
   - **Område**: Det område, hvor tjenesten er udrullet og har sin vært. Hvis du vil [bruge din egen Azure Data Lake Storage-konto](own-data-lake-storage.md) eller [oprette forbindelse til en eksisterende Microsoft Dataverse-organisation](customer-insights-dataverse.md), skal Customer Insights-miljøet være i samme område.

1. Vælg **Næste**.

## <a name="step-2-configure-data-storage"></a>Trin 2: Konfigurer datalager

1. Vælg , hvor du vil gemme Customer Insights-data:

   - **Customer Insights-lager**: Datalager administreres automatisk. Det er standardindstillingen, og medmindre der er specifikke krav om at gemme data på din egen lagerkonto, anbefales det, at du bruger denne indstilling.
   - **Azure Data Lake Storage**: Din egen Azure Data Lake Storage-konto for at gemme dataene, så du har fuld kontrol over, hvor dataene gemmes. Følg trinnene under [Brug din egen Azure Data Lake Storage-konto](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Vælg den foretrukne mulighed for at lagre dine data.":::

1. Vælg **Næste**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Trin 3: Opret forbindelse til Microsoft Dataverse

Hvis du har et Dataverse-miljø, skal du tilslutte Customer Insights. Del data med Dataverse for at bruge dem med virksomhedsprogrammer, der er baseret på Dataverse, for eksempel Dynamics 365 Marketing eller modelbaserede programmer i Power Apps.

1. Følg trinnene i [Arbejde med Customer Insights-data i Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="datadeling med Microsoft Dataverse er automatisk aktiveret for nye miljøer.":::

1. Vælg **Næste**.

## <a name="step-4-finalize-the-settings"></a>Trin 4: Fuldfør indstillingerne

Gennemgå de angivne indstillinger. Når alt ser ud, som det skal, skal du vælge **Opret** for at konfigurere miljøet.

Hvis du vil ændre nogle af indstillingerne senere, skal du se [Administrere miljøer](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Arbejde med dit nye miljø

Gennemgå følgende artikler for at hjælpe dig med at komme i gang med at konfigurere Customer Insights:

- [Tilføj flere brugere, og tildel tilladelser](permissions.md).
- [Gennemgå datakilderne](data-sources.md) og kør dem gennem [processen til enhed af data](data-unification.md) for at få [unified customer profiles](customer-profiles.md).
- [Forbedr unified customer profiles](enrichment-hub.md) eller [kør intelligente modeller](predictions-overview.md).
- [Opret segmenter](segments.md) for at gruppere kunder og [målingers](measures.md) til gennemgangs-nøgletal.
- [Opret forbindelser](connections.md) og [eksporter](export-destinations.md) for at behandle undersæt af dataene i andre programmer.

## <a name="copy-the-environment-configuration"></a>Kopier miljøkonfiguration

Hvis du som administrator vælger at kopiere konfigurationen fra et eksisterende miljø, skal du vælge på listen over alle tilgængelige miljøer i din organisation.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Skærmbillede af indstillingerne i miljøindstillingerne.":::

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

### <a name="set-up-a-copied-environment"></a>Konfigurere et kopieret miljø

Når du kopierer miljøkonfigurationen, får du en bekræftelsesmeddelelse, når det kopierede miljø er blevet oprettet. Du skal udføre følgende trin for at bekræfte legitimationsoplysninger.

1. Vælg **gå til datakilder** for at få vist listen over datakilder. Alle datakilderne viser **Legitimationsoplysninger påkrævet** som status.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Liste over datakilder, der er kopieret og skal godkendes.":::

1. Rediger datakilderne, og angiv legitimationsoplysninger for at opdatere dem. Datakilder fra mappen Common Data Model og Dataverse skal oprettes manuelt med det samme navn som i kildemiljøet.

1. Når du har opdateret datakilderne, skal du gå til **Data** > **Saml**. Her kan du finde indstillinger fra kildemiljøet. Rediger dem efter behov, eller vælg **Foren** > **Foren kundeprofiler og afhængigheder** for at starte datasamlingsprocessen og oprette det forenede kundeobjekt.

   > [!TIP]
   > For firmaer og kontakter skal du vælge **Foren firmaer** > **Foren profiler og afhængigheder**.

1. Når datasamlingen er fuldført, skal du gå til **Målinger** og **Segmenter** for at opdatere dem.

1. Gå til **Administration** > **Forbindelser** for at genaktivere forbindelserne i det nye miljø.

1. Gå til **Data** > **Forbedring** og **Data** > **Eksporter** for at genaktivere dem.

[!INCLUDE [footer-include](includes/footer-banner.md)]
