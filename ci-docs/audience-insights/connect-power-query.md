---
title: Indtag data via en Power Query-connector (video)
description: Connectorer til datakilder, der er baseret på Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 38c447d80a25feca087ca9f110278b8401423018
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903833"
---
# <a name="connect-to-a-power-query-data-source"></a>Oprette forbindelse til en Power Query-datakilde

Power Query tilbyder en lang række connectorer til indtagelse af data. De fleste af disse connectorer understøttes af Dynamics 365 Customer Insights. 

Hvis du tilføjer datakilder på Power Query-connectors, følger du som regel de trin, der er skitseret i dette afsnit. Men afhængigt af den connector, du bruger, er der brug for forskellige oplysninger. Du kan få mere at vide i dokumentationen om de enkelte tilslutninger i [referencen til Power Query-connector](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Oprette en ny datakilde

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

1. Vælg **Tilføj datakilde**.

1. Vælg **Microsoft Power Query**, og vælg derefter **Næste**.

1. Angiv et **Navn** til datakilde, og vælg **Næste** for at oprette datakilden.

1. Vælg en af de [tilgængelige connectorer](#available-power-query-data-sources). I dette eksempel vælger vi **Text/CSV**-connector.

1. Angiv de nødvendige detaljer i **Forbindelsesindstillinger** for den valgte connector, og vælg **Næste** for at få vist en prøveversion af dataene.

1. Vælg **Transformer data**. I dette trin skal du føje objekter til din datakilde. Objekter er datasæt. Hvis du har en database, der indeholder flere datasæt, er de enkelte datasæt sit eget objekt.

1. Dialogboksen **Power Query - rediger forespørgsler** giver dig mulighed for at gennemse og finpudse dataene. De objekter, som systemerne har identificeret i den valgte datakilde, vises i venstre rude.

   > [!div class="mx-imgBorder"]
   > ![Dialogboksen Rediger forespørgsler.](media/data-manager-configure-edit-queries.png "Dialogboksen Rediger forespørgsler")

1. Du kan også transformere dine data. Vælg et objekt, der skal redigeres eller transformeres. Brug indstillingerne i Power Query-vinduet til at anvende transformationer. Hver transformation er vist under **Anvendte trin**. Power Query indeholder mange standardindstillinger for transformation. Du kan finde flere oplysninger i [Power Query-transformationer](/power-query/power-query-what-is-power-query#transformations).

1. Du kan føje flere objekter til datakilden ved at vælge **Hent data** i dialogboksen **Rediger forespørgsler**.

   Det anbefales, at du bruger følgende transformationer:

   - Hvis du indtager data fra en CSV-fil, indeholder den første række ofte overskrifter. Gå til **Transformer tabel**, og vælg **Brug overskrifter som første række**.
   - Kontrollér, at datatypen er angivet korrekt.

1. Vælg **Gem** nederst i Power Query-vinduet for at gemme transformationerne. Når du har gemt, kan du finde din datakilde i **Data** > **Datakilder**.

1. På siden **Datakilder** skal du bemærke, at den nye datakilde har **Opdatering**-status.

## <a name="available-power-query-data-sources"></a>Tilgængelige Power Query-datakilder

Se [reference til Power Query-connector](/power-query/connectors/) for at få en liste over connectors, du kan bruge til at importere data til Customer Insights. 

Connectorer med markering i kolonnen **Customer Insights (dataflows)** er tilgængelige for oprettelse af nye datakilder, der er baseret på Power Query. Gennemgå dokumentationen til en bestemt connector for at lære mere om dens forudsætninger, begrænsninger og andre detaljer.

## <a name="edit-power-query-data-sources"></a>Redigere Power Query-datakilder

> [!NOTE]
> Det er måske ikke muligt at foretage ændringer af datakilder, der i øjeblikket bruges i en af appens processer (f.eks *segmentering*, *match* eller *fletning*). 
>
> På siden **Indstillinger** kan du spore status for hver af de aktive processer. Når en proces er fuldført, kan du vende tilbage til siden **Datakilder** og foretage ændringerne.

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

2. Vælg den lodrette ellipse ud for den datakilde, du vil ændre, og vælg **Rediger** i rullemenuen.

   > [!div class="mx-imgBorder"]
   > ![Indstillingen Rediger.](media/edit-option-data-sources.png "Indstillingen Rediger")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Anvend ændringerne og transformationerne i dialogboksen **Power Query – rediger forespørgsler** som beskrevet i afsnittet [Oprette en ny datakilde](#create-a-new-data-source).

4. Vælg **Gem** i Power Query, når du har fuldført redigeringen, for at gemme ændringerne.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
