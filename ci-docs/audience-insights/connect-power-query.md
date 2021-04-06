---
title: Indsættelse af data via en Power Query forbindelse
description: Connectorer til datakilder, der er baseret på Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b9a1b30e37c3792aa7bdfcfc177da9e8a32c324d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596906"
---
# <a name="connect-to-a-power-query-data-source"></a>Oprette forbindelse til en Power Query-datakilde

Power Query tilbyder en lang række connectorer til indtagelse af data. De fleste af disse connectorer understøttes af Dynamics 365 Customer Insights. Hvis du tilføjer datakilder, der er baseret på Power Query-connectorer, følger normalt de trin, der beskrives i næste afsnit. Men afhængigt af den connector, du bruger, er der brug for forskellige oplysninger. Du kan finde flere oplysninger i dokumentationen om de enkelte connectorer i [Power Query-connector-referencen](/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Oprette en ny datakilde

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

1. Vælg **Tilføj datakilde**.

1. Vælg metoden **Importér data**, og vælg **Næste**.

1. Angiv et **Navn** til datakilde, og vælg **Næste** for at oprette datakilden. Navneretningslinjer: 
   - Start med et bogstav.
   - Brug kun bogstaver og tal. Specialtegn og mellemrum er ikke tilladt.
   - Brug mellem 3 og 64 tegn.

1. Vælg en af de [tilgængelige connectorer](#available-power-query-data-sources). I dette eksempel skal du vælge **Text/CSV** som connector.

1. Angiv de nødvendige detaljer i **Forbindelsesindstillinger** for den valgte connector, og vælg **Næste** for at få vist en prøveversion af dataene.

1. Vælg **Transformer data**. I dette trin skal du føje objekter til din datakilde. Objekter er datasæt. Hvis du har en database, der indeholder flere datasæt, er de enkelte datasæt sit eget objekt.

1. Dialogboksen **Power Query - rediger forespørgsler** giver dig mulighed for at gennemse og finpudse dataene. De objekter, som systemerne har identificeret i den valgte datakilde, vises i venstre rude.

   > [!div class="mx-imgBorder"]
   > ![Dialogboksen Rediger forespørgsler](media/data-manager-configure-edit-queries.png "Dialogboksen Rediger forespørgsler")

1. Du kan også transformere dine data. Vælg et objekt, der skal redigeres eller transformeres. Brug indstillingerne i Power Query-vinduet til at anvende transformationer. Hver transformation er vist under **Anvendte trin**. Power Query indeholder mange standardindstillinger for transformation. Du kan finde flere oplysninger i [Power Query-transformationer](/power-query/power-query-what-is-power-query#transformations).

1. Du kan føje flere objekter til datakilden ved at vælge **Hent data** i dialogboksen **Rediger forespørgsler**.

   Disse transformeringer anbefales på det kraftigste:

   - Hvis du indtager data fra en CSV-fil, indeholder den første række ofte overskrifter. Gå til **Transformer tabel**, og vælg **Brug overskrifter som første række**.
   - Kontrollér, at datatypen er angivet korrekt.

1. Vælg **Gem** nederst i Power Query-vinduet for at gemme transformationerne. Når du har gemt, kan du finde din datakilde i **Data** > **Datakilder**.

1. På siden **Datakilder** skal du bemærke, at den nye datakilde har **Opdatering**-status.

## <a name="available-power-query-data-sources"></a>Tilgængelige Power Query-datakilder

Se [Power Query-connector-referencen](/power-query/connectors/) for at få en opdateret liste over connectorer, som du kan vælge for at importere data til Customer Insights. 

Connectorer med markering i kolonnen **Customer Insights (dataflows)** er tilgængelige for oprettelse af nye datakilder, der er baseret på Power Query. Gennemgå dokumentationen til en bestemt connector for at lære mere om dens forudsætninger, begrænsninger og andre detaljer.

## <a name="edit-power-query-data-sources"></a>Redigere Power Query-datakilder

> [!NOTE]
> Det er måske ikke muligt at foretage ændringer af datakilder, der i øjeblikket bruges i en af appens processer (f.eks *segmentering*, *match* eller *fletning*). 
>
> På siden **Indstillinger** kan du spore status for hver af de aktive processer. Når en proces er fuldført, kan du vende tilbage til siden **Datakilder** og foretage ændringerne.

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

2. Vælg den lodrette ellipse ud for den datakilde, du vil ændre, og vælg **Rediger** i rullemenuen.

   > [!div class="mx-imgBorder"]
   > ![Indstillingen Rediger](media/edit-option-data-sources.png "Indstillingen Rediger")

3. Anvend ændringerne og transformationerne i dialogboksen **Power Query – rediger forespørgsler** som beskrevet i afsnittet [Oprette en ny datakilde](#create-a-new-data-source).

4. Vælg **Gem** i Power Query, når du har fuldført redigeringen, for at gemme ændringerne.


[!INCLUDE[footer-include](../includes/footer-banner.md)]