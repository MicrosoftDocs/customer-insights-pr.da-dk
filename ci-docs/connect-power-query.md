---
title: Oprette forbindelse til en Power Query-datakilde (indeholder video)
description: Indtag data via en Power Query-connector (indeholder video).
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609869"
---
# <a name="connect-to-a-power-query-data-source"></a>Oprette forbindelse til en Power Query-datakilde

Power Query indeholder et bredt sæt connectorer til indtagelse af data. De fleste af disse connectorer understøttes af Dynamics 365 Customer Insights.

Tilføjelse af datakilder baseret på Power Query-connectorer følger generelt de trin, der er angivet i denne sektion. Men afhængigt af den connector, du bruger, er der brug for forskellige oplysninger. Du kan få mere at vide i dokumentationen angående individuelle connectorer i [Reference til Power Query-connectorer](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Oprette en ny datakilde

1. Gå til **Data** > **Datakilder**.

1. Vælg **Tilføj datakilde**.

1. Vælg **Microsoft Power Query**.

1. Angiv et **navn** og en valgfri **beskrivelse** af datakilde, og vælg **Næste**.

1. Vælg en af de [tilgængelige connectorer](#available-power-query-data-sources). I dette eksempel vælger vi **Text/CSV**-connector.

1. Angiv de nødvendige detaljer i **Forbindelsesindstillinger** for den valgte connector, og vælg **Næste** for at få vist en prøveversion af dataene.

1. Vælg **Transformer data**.

1. Gennemse og finjuster dine data på siden **Power Query – Rediger forespørgsler**. De objekter, som systemerne har identificeret i den valgte datakilde, vises i venstre rude.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dialogboksen Rediger forespørgsler":::

1. Transformer dine data. Vælg et objekt, der skal redigeres eller transformeres. Brug indstillingerne i Power Query-vinduet til at anvende transformationer. De enkelte transformeringer er angivet under **Anvendte trin**. Power Query indeholder mange [foruddefinerede transformationsindstillinger](/power-query/power-query-what-is-power-query#transformations).

   > [!IMPORTANT]
   > Det anbefales, at du bruger følgende transformationer:
   >
   > - Hvis du indtager data fra en CSV-fil, indeholder den første række ofte overskrifter. Gå til **Transformér**, og vælg **Brug første række som overskrifter**.
   > - Kontrollér, at datatypen er angivet korrekt og stemmer overens med dataene. I forbindelse med datofelter kan du f.eks. vælge en datotype.

1. Hvis du vil føje flere objekter til datakilde i dialogboksen **Rediger forespørgsler**, skal du gå til **Startside** og vælge **Hent data**. Gentag trin 5-10, indtil du har tilføjet alle objekter for denne datakilde. Hvis du har en database, der indeholder flere datasæt, er de enkelte datasæt sit eget objekt.

1. Vælg **Gem**. Siden **Datakilder** åbnes, der viser de nye datakilde status for **Opdatering**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan tage tid at indlæse data. Når opdateringen er gennemført, kan de indtagne data gennemses fra siden [**Objekter**](entities.md).

> [!CAUTION]
>
> - En datakilde baseret på Power Query opretter et [dataflow i Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Du skal ikke ændre navnet på et dataflow i Power Platform administration, der bruges i Customer Insights. Når du omdøber et dataflow, opstår der problemer med referencerne mellem Customer Insights-datakilde og Dataverse-dataflowet.
> - Samtidige evalueringer af Power Query-datakilder i Customer Insights har de samme [opdateringsbegrænsninger som dataflow i PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Hvis en dataopdatering ikke lykkes, fordi den har nået evalueringsgrænsen, anbefales det, at du justerer opdateringsplanen for hvert dataflow for at sikre, at datakilderne ikke behandles på samme tid.

### <a name="available-power-query-data-sources"></a>Tilgængelige Power Query-datakilder

Se [Reference til Power Query-connector](/power-query/connectors/) for at finde en lister over de connectorer, du kan bruge til import af data til Customer Insights.

Connectorer med et afkrydsningsfelt i kolonnen **Customer Insights (Dataflows)** er tilgængelige til at oprette nye datakilder baseret på Power Query. Gennemse dokumentationen til en bestemt connector for at få mere at vide om dens forudsætninger, [forespørgselsbegrænsninger](/power-query/power-query-online-limits) og andre detaljer.

## <a name="add-data-from-on-premises-data-sources"></a>Tilføje data fra de lokale datakilder

Indtagelse af data fra det lokale miljø understøttes på baggrund af Microsoft Power Platform-dataflows (PPDFs). Du kan aktivere dataflows i Customer Insights ved at [angive URL Microsoft Dataverse-miljøet](create-environment.md), når du konfigurerer miljøet.

Datakilder, der er oprettet, når et Dataverse-miljø er blevet associeret med Customer Insights, bruger [Power Platform-dataflow](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) som standard. Dataflows understøtter forbindelser i det lokale miljø ved hjælp af datagateway. Du kan fjerne og genoprette datakilder, der fandtes, før et Dataverse-miljø blev tilknyttet, [ved hjælp af datagateways i det lokale miljø](/data-integration/gateway/service-gateway-app).

Datagateways fra et eksisterende Power BI-eller Power Apps-miljø vil være synlige, og du kan genbruge dem i Customer Insights, hvis datagatewayen og Customer Insights-miljøet er i samme Azure-område. På siden med datakilder vises links til at gå til det Microsoft Power Platform-miljø, hvor du kan få vist og konfigurere det lokale miljøs datagateways.

> [!IMPORTANT]
> Kontrollér, at dine gateways er opdateret til den nyeste version. Du kan installere en opdatering og omkonfigurere en gateway fra en prompt, der vises direkte på gatewayskærmbilledet, eller [hente den nyeste version](https://powerapps.microsoft.com/downloads/). Hvis du ikke bruger den nyeste gatewayversion, lykkes opdateringen af dataflowet ikke, og fejlmeddelelser som **Nøgleordet understøttes ikke: konfigurationsegenskaber. Parameternavn: nøgleord**.
>
> Fejl i det lokale miljø i Customer Insights skyldes ofte konfigurationsproblemer. Du kan finde flere oplysninger om, hvordan du foretager fejlfinding af problemer med datagateways, under [Foretage fejlfinding af datagatewayen i det lokale miljø](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Rediger Power Query-datakilder

> [!NOTE]
> Det er måske ikke muligt at foretage ændringer af datakilder, der i øjeblikket bruges i en af appens processer (f.eks. segmentering eller datasamling).
>
> På siden **Indstillinger** kan du spore status for hver af de aktive processer. Når en proces er fuldført, kan du vende tilbage til siden **Datakilder** og foretage ændringerne.

1. Gå til **Data** > **Datakilder**.

1. Ud for den datakilde, du vil opdatere, og vælg **Rediger**.

1. Anvend ændringer og transformationer i dialogboksen **Power Query – Rediger forespørgsler** som beskrevet i sektionen [Opret en ny datakilde](#create-a-new-data-source).

1. Vælg **Gem** for at anvende ændringerne og vende tilbage til siden **Datakilder**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Almindelige årsager til indtagelsesfejl eller beskadigede data

### <a name="data-type-does-not-match-data"></a>Datatypen stemmer ikke overens med data

Den mest almindelige uoverensstemmelse mellem datatyper opstår, når et datofelt ikke er angivet til det korrekte datoformat.

Dataene kan repareres ved kilden og indtages igen. Du kan også reparere transformeringen i Customer Insights. Sådan reparerer du transformeringen:

1. Gå til **Data** > **Datakilder**.

1. Ud for datakilden med de beskadigede data skal du vælge knappen **Rediger**.

1. Vælg **Næste**.

1. Vælg de enkelte forespørgsler, og søg efter transformeringer i "Anvendte trin", der er forkerte, eller datokolonner, der ikke er transformeret med et datoformat.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query – Redigering, der viser forkert datoformat":::

1. Rediger datatypen, så den stemmer overens med dataene.

1. Vælg **Gem**. Denne datakilde er opdateret.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>Fejlfinding af problemer med opdatering af PPDF Power Query-baserede datakilder

Hvis dataene er forældede, eller der vises fejlmeddelelser, efter at en datakilde er opdateret, skal du udføre følgende trin:

1. Naviger til [Power Platform](https://make.powerapps.com).

1. Vælg **Miljø** for din forekomst af Customer Insights.

1. Naviger til **Dataflow**.

1. I forbindelse med det dataflow, der svarer til datakilden i Customer Insights, skal du vælge den lodrette ellipse (&vellip;) og derefter vælge **Vis opdateringsoversigt**.

1. Hvis **Status** for dataflowet er **Vellykket**, er ejerskabet til den Power Query-baserede datakilde muligvis ændret:

   1. Gennemse opdateringsplanen fra opdateringsoversigten.
   1. Angiv den nye ejers tidsplan, og gem indstillingerne.

1. Hvis **Status** for dataflowet er **Mislykket**:

   1. Hent filen med opdateringsoversigten.
   1. Gennemse den hentede fil for at finde årsagen til fejlen.
   1. Hvis fejlen ikke kan løses, skal du vælge **?** for at åbne en supportanmodning. Inkluder den hentede fil med opdateringsoversigten.


[!INCLUDE [footer-include](includes/footer-banner.md)]
