---
title: Indtag data via en Power Query-connector (indeholder video)
description: Connectorer til datakilder baseret på Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 727cb9a4d754b6dbd74d6ecab1b183d41f713d8f
ms.sourcegitcommit: aadee829eff111c95eb30c0a97a68dcc87994acf
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092065"
---
# <a name="connect-to-a-power-query-data-source"></a>Oprette forbindelse til en Power Query-datakilde

Power Query indeholder et bredt sæt connectorer til indtagelse af data. De fleste af disse connectorer understøttes af Dynamics 365 Customer Insights. 

Tilføjelse af datakilder baseret på Power Query-connectorer følger generelt de trin, der er angivet i denne sektion. Men afhængigt af den connector, du bruger, er der brug for forskellige oplysninger. Du kan få mere at vide i dokumentationen angående individuelle connectorer i [Reference til Power Query-connectorer](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Oprette en ny datakilde

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

1. Vælg **Tilføj datakilde**.

1. Vælg **Microsoft Power Query**.

1. Angiv et **Navn** til datakilde, og vælg **Næste** for at oprette datakilden.

1. Vælg en af de [tilgængelige connectorer](#available-power-query-data-sources). I dette eksempel vælger vi **Text/CSV**-connector.

1. Angiv de nødvendige detaljer i **Forbindelsesindstillinger** for den valgte connector, og vælg **Næste** for at få vist en prøveversion af dataene.

1. Vælg **Transformer data**. I dette trin skal du føje objekter til din datakilde. Objekter er datasæt. Hvis du har en database, der indeholder flere datasæt, er de enkelte datasæt sit eget objekt.

1. Dialogboksen **Power Query - Rediger forespørgsler** giver dig mulighed for at gennemse og finjustere dataene. De objekter, som systemerne har identificeret i den valgte datakilde, vises i venstre rude.

   > [!div class="mx-imgBorder"]
   > ![Dialogboksen Rediger forespørgsler.](media/data-manager-configure-edit-queries.png "Dialogboksen Rediger forespørgsler")

1. Du kan også transformere dine data. Vælg et objekt, der skal redigeres eller transformeres. Brug indstillingerne i Power Query-vinduet til at anvende transformationer. Hver transformation er vist under **Anvendte trin**. Power Query indeholder mange foruddefinerede transformationsindstillinger. Du kan finde flere oplysninger under [Power Query Transformationer](/power-query/power-query-what-is-power-query#transformations).

   Det anbefales, at du bruger følgende transformationer:

   - Hvis du indtager data fra en CSV-fil, indeholder den første række ofte overskrifter. Gå til **Transformér**, og vælg **Brug første række som overskrifter**.
   - Kontrollér, at datatypen er angivet korrekt. I forbindelse med datofelter kan du f.eks. vælge en datotype.

1. Hvis du vil føje flere objekter til datakilde i dialogboksen **Rediger forespørgsler**, skal du gå til **Startside** og vælge **Hent data**.

1. Vælg **Gem** i nederste hjørne af Power Query-vinduet for at gemme transformationerne. Når du har gemt, kan du finde din datakilde i **Data** > **Datakilder**.

1. På siden **Datakilder** skal du bemærke, at den nye datakilde har **Opdatering**-status.

## <a name="available-power-query-data-sources"></a>Tilgængelige Power Query-datakilder

Se [Reference til Power Query-connector](/power-query/connectors/) for at finde en lister over de connectorer, du kan bruge til import af data til Customer Insights. 

Connectorer med et afkrydsningsfelt i kolonnen **Customer Insights (Dataflows)** er tilgængelige til at oprette nye datakilder baseret på Power Query. Gennemgå dokumentationen til en bestemt connector for at lære mere om dens forudsætninger, begrænsninger og andre detaljer.

## <a name="edit-power-query-data-sources"></a>Rediger Power Query-datakilder

> [!NOTE]
> Det er måske ikke muligt at foretage ændringer af datakilder, der i øjeblikket bruges i en af appens processer (f.eks *segmentering*, *match* eller *fletning*). 
>
> På siden **Indstillinger** kan du spore status for hver af de aktive processer. Når en proces er fuldført, kan du vende tilbage til siden **Datakilder** og foretage ændringerne.

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

2. Vælg den lodrette ellipse ud for den datakilde, du vil ændre, og vælg **Rediger** i rullemenuen.

   > [!div class="mx-imgBorder"]
   > ![Indstillingen Rediger.](media/edit-option-data-sources.png "Indstillingen Rediger")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Anvend ændringer og transformationer i dialogboksen **Power Query – Rediger forespørgsler** som beskrevet i sektionen [Opret en ny datakilde](#create-a-new-data-source).

4. Vælg **Gem** i Power Query, når du har fuldført dine rettelser, for at gemme ændringerne.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
