---
title: Vis kundeprofiler
description: Få en kombineret visning af dine samlede kundedata.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596860"
---
# <a name="customer-profiles"></a>Kundeprofiler

På siden **Kunder** vises en kombineret visning af dine kunder baseret på de profildata, der er indsamlet fra [alle datakilder](data-sources.md). Kundeprofiler er tilgængelige, når du [opretter det samlede kundeobjekt](data-unification.md). Sørg for at fuldføre dataforeningsprocessen for at få mere detaljerede visninger af dine kunder. På siden kan du også søge efter kunder.

Kunder kan være enkeltpersoner eller organisationer (prøveversion). Hver enkelt kunde- eller organisationsprofil repræsenteres af et felt. Vælg et felt for at få vist flere oplysninger om den pågældende kunde eller organisation. Brug sideinddelingskontrolelementerne nederst på siden for at få vist flere poster.

> [!div class="mx-imgBorder"] 
> ![B2C-kundeprofiler](media/profiles-customers.png "B2C-kundeprofiler")

Organisationer (prøveversion)
> [!div class="mx-imgBorder"] 
> ![B2B-kundeprofiler](media/profile-customers-b2b.png "B2B-kundeprofiler")

> [!NOTE]
> Hvis du ikke kan se felterne, når du vælger **Kunder** i navigationen, skal din administrator [definere mindst én søgbar attribut](search-filter-index.md) i **Indeks for søgning og filtrering**.

## <a name="search-for-customers"></a>Søge efter kunder

Søg efter kunder ved at angive et navn eller en anden attribut i søgefeltet. Søgningen virker kun i det kundeprofilobjekt, der oprettes under dataforeningsprocessen.

Som administrator kan du konfigurere søgbare attributter på siden **Indeks for søgning og filtrering**. Du kan finde flere oplysninger under [Administrere indeks for søgning og filtrering](search-filter-index.md).

## <a name="filter-customers"></a>Filtrere kunder

Du kan filtrere kunder efter objektfelterne for kundeprofil. På samme måde som for søgning skal administratoren først definere felterne som filtrerbare på siden **Indeks for søgning og filtrering**.

1. Vælg **Filter** på siden **Kunder**.

2. Markér afkrydsningsfelterne ud for de attributter, som du vil filtrere kunder efter.

   > [!div class="mx-imgBorder"] 
   > ![Kundeprofiler](media/profiles-customers3.png "Kundeprofiler")

3. Fjern dine filtre ved at vælge **Ryd filtre** på siden **Kunder**.

##  <a name="customer-details-page"></a>Siden Kundeoplysninger

Vælg et af kundefelterne for at åbne siden **Kundeoplysninger**. Denne visning indeholder en samlet oplysning for den valgte kunde.

Kundeoplysninger indeholder:

-   **Felt til kundeprofil:** Dette felt vises de forskellige værdier fra objektet Kundeprofil. Disse oplysninger kan være e-mailadresse, navn, by osv. 

-   **Potentielle interesser, potentielle mærker:** Viser, om du har konfigureret en opgørelse fra en oprindeligt leverandør. Den repræsenterer potentielle interesser og tilhørsforhold for mærker, som en kunde med en profil, der ligner denne kunde, kan have. Du kan finde flere oplysninger i [Forbedre kundeprofiler med mærketilhørsforhold og interesser](enrichment-microsoft-graph.md).

-   **Mål:** Viser, hvis du har konfigureret et eller flere mål for en bestemt type: Målpunkter for kundeattribut. De indeholder beregnede nøgletal omkring dine kunder på de enkelte kundeniveauer. Du kan finde flere oplysninger under [Definér, og administrer målpunkter](measures.md).

-   **Tidslinje for aktivitet:** Viser, om du har konfigureret aktiviteter. Tidslinjevisningen indeholder de kronologiske sorteringsaktiviteter for denne kunde og starter med den seneste aktivitet. Du kan finde flere oplysninger under [Kundeaktiviteter](activities.md).

Vælg **Tilbage til kunder** for at vende tilbage til kundens søgeside.

## <a name="next-steps"></a>Næste trin

[Tilføj flere datakilder](data-sources.md), eller [opret kundesegmenter](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]