---
title: Indtag data via en Power Query-connector (indeholder video)
description: Connectorer til datakilder baseret på Power Query.
ms.date: 05/09/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: b99c3b446e580f455f9678d54d9db414aea9b331
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011650"
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

1. Vælg **Transformer data**. I dette trin skal du føje objekter til din datakilde. Objekter er datasæt. Hvis du har en database, der indeholder flere datasæt, er de enkelte datasæt sit eget objekt.

1. Dialogboksen **Power Query - Rediger forespørgsler** giver dig mulighed for at gennemse og finjustere dataene. De objekter, som systemerne har identificeret i den valgte datakilde, vises i venstre rude.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dialogboksen Rediger forespørgsler":::

1. Du kan også transformere dine data. Vælg et objekt, der skal redigeres eller transformeres. Brug indstillingerne i Power Query-vinduet til at anvende transformationer. De enkelte transformeringer er angivet under **Anvendte trin**. Power Query indeholder mange foruddefinerede transformationsindstillinger. Du kan finde flere oplysninger under [Power Query Transformationer](/power-query/power-query-what-is-power-query#transformations).

   Det anbefales, at du bruger følgende transformationer:

   - Hvis du indtager data fra en CSV-fil, indeholder den første række ofte overskrifter. Gå til **Transformér**, og vælg **Brug første række som overskrifter**.
   - Kontrollér, at datatypen er angivet korrekt. I forbindelse med datofelter kan du f.eks. vælge en datotype.

1. Hvis du vil føje flere objekter til datakilde i dialogboksen **Rediger forespørgsler**, skal du gå til **Startside** og vælge **Hent data**. Gentag trin 6-10, indtil du har tilføjet alle objekter for denne datakilde.

1. Vælg **Gem**. Siden **Datakilder** åbnes, der viser de nye datakilde status for **Opdatering**.

### <a name="available-power-query-data-sources"></a>Tilgængelige Power Query-datakilder

Se [Reference til Power Query-connector](/power-query/connectors/) for at finde en lister over de connectorer, du kan bruge til import af data til Customer Insights.

Connectorer med et afkrydsningsfelt i kolonnen **Customer Insights (Dataflows)** er tilgængelige til at oprette nye datakilder baseret på Power Query. Gennemse dokumentationen til en bestemt connector for at få mere at vide om dens forudsætninger, [forespørgselsbegrænsninger](/power-query/power-query-online-limits) og andre detaljer.

## <a name="add-data-from-on-premises-data-sources"></a>Tilføje data fra de lokale datakilder

Indtagelse af data fra det lokale miljø understøttes på baggrund af Microsoft Power Platform-dataflows (PPDFs). Du kan aktivere dataflows i Customer Insights ved at [angive URL Microsoft Dataverse-miljøet](create-environment.md), når du konfigurerer miljøet.

Datakilder, der er oprettet, når et Dataverse-miljø er blevet associeret med Customer Insights, bruger [Power Platform-dataflow](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) som standard. Dataflows understøtter forbindelser i det lokale miljø ved hjælp af datagateway. Du kan fjerne og genoprette datakilder, der fandtes, før et Dataverse-miljø blev tilknyttet, [ved hjælp af datagateways i det lokale miljø](/data-integration/gateway/service-gateway-app).

Datagateways fra et eksisterende Power BI- eller Power Apps-miljø er synlige, og du kan genbruge dem i Customer Insights. På siden med datakilder vises links til at gå til det Microsoft Power Platform-miljø, hvor du kan få vist og konfigurere det lokale miljøs datagateways.

> [!IMPORTANT]
> Kontrollér, at dine gateways er opdateret til den nyeste version. Du kan installere en opdatering og omkonfigurere en gateway fra en prompt, der vises direkte på gatewayskærmbilledet, eller [hente den nyeste version](https://powerapps.microsoft.com/downloads/). Hvis du ikke bruger den nyeste gatewayversion, lykkes opdateringen af dataflowet ikke, og fejlmeddelelser som **Nøgleordet understøttes ikke: konfigurationsegenskaber. Parameternavn: nøgleord**.

## <a name="edit-power-query-data-sources"></a>Rediger Power Query-datakilder

> [!NOTE]
> Det er måske ikke muligt at foretage ændringer af datakilder, der i øjeblikket bruges i en af appens processer (f.eks *segmentering*, *match* eller *fletning*).
>
> På siden **Indstillinger** kan du spore status for hver af de aktive processer. Når en proces er fuldført, kan du vende tilbage til siden **Datakilder** og foretage ændringerne.

1. Gå til **Data** > **Datakilder**.

1. Ud for den datakilde, du vil opdatere, og vælg **Rediger**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Anvend ændringer og transformationer i dialogboksen **Power Query – Rediger forespørgsler** som beskrevet i sektionen [Opret en ny datakilde](#create-a-new-data-source).

1. Vælg **Gem** i Power Query, når du har fuldført dine rettelser, for at gemme ændringerne.
