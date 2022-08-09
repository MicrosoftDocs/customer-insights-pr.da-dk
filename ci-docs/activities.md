---
title: Kundeaktiviteter
description: Definer kundeaktiviteter, og se dem på en tidslinje for kundeprofiler.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188132"
---
# <a name="customer-activities"></a>Kundeaktiviteter

Kundeaktiviteter er handlinger eller hændelser, der udføres af kunder. F.eks. transaktioner, varighed af supportopkald, gennemsyn af websted, indkøb eller returvarer. Disse aktiviteter findes i en eller flere datakilder. Med Customers Insights kan du samle dine kundeaktiviteter fra disse [datakilder](data-sources.md) og knytte dem til kundeprofiler. Disse aktiviteter vises kronologisk på en tidslinje i kundeprofilen. Inkluder tidslinjen i Dynamics 365-apps med [tilføjelsesprogrammet Kundekort](customer-card-add-in.md).

## <a name="define-an-activity"></a>Definere en aktivitet

Et objekt skal have mindst én attribut af typen **Dato** for at blive medtaget på en kundes tidslinje. Kontrolelementet **Tilføj aktivitet** deaktiveres, hvis der ikke findes et sådant objekt.

1. Gå til **Data** > **Aktiviteter**.

1. Vælg **Tilføj aktivitet** for at starte den styrede oplevelse.

1. Skriv følgende oplysninger i trinnet **Aktivitetsdata**.

   - **Aktivitetsnavn**:Navn til aktiviteten.
   - **Aktivitetsobjekt**: Objekt, der indeholder transaktions- eller aktivitetsdata.
   - **Primær nøgle**: Felt, der entydigt identificerer en post. Den må ikke indeholde dublerede værdier, tomme værdier eller manglende værdier.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Konfigurer aktivitetsdataene med navn, objekt og primær nøgle.":::

1. Vælg **Næste**.

1. I trinnet **Relation** skal du vælge **Tilføj relation** for at knytte dine aktivitetsdata til den tilhørende kundepost. I dette trin visualiseres forbindelsen mellem objekter.  

   - **Fremmed nøgle fra objekt**: Felt i aktivitetsobjektet, der bruges til at oprette en relation til et andet objekt.
   - **Til objektnavn**: Det tilsvarende kildekundeobjekt, som aktivitetsobjektet er i relation til. Du kan kun relatere til kildekundeobjekter, der bruges i processen til dataenheder.
   - **Relationsnavn**: Navn, der identificerer relationen mellem objekter. Hvis der allerede findes en relation mellem dette aktivitetsobjekt og det valgte kildekundeobjekt, er relationsnavnet skrivebeskyttet.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definere objektrelationen.":::

   > [!TIP]
   > I B-til-B-miljøer kan du vælge mellem firmaobjekter og andre objekter. Hvis du vælger et firmaobjekt, angives relationsstien automatisk. I forbindelse med andre objekter skal du definere relationsstien hen over et eller flere mellemliggende objekter, indtil du når til et firmaobjekt.

1. Vælg **Anvend** for at oprette relationen.

1. Vælg **Næste**.

1. I **Aktivitetsenhed**-trinnet skal du vælge aktivitetshændelsen og starttiden for aktiviteten.
   - **Obligatoriske felter**
      - **Hændelsesaktivitet**: Det felt, der er begivenheden for denne aktivitet.
      - **Tidsstempel**: Felt, der repræsenterer starttiderne for aktiviteten.

   - **Valgfrie felter**
      - **Flere detaljer**: Felt med relevante oplysninger om aktiviteten.
      - **Ikon**: Det ikon, der bedst repræsenterer denne aktivitetstype.
      - **Webadresse**: Felt, der indeholder en URL-adresse med oplysninger om aktiviteten. For eksempel det transaktionssystem, der er kilde til aktiviteten. Denne URL-adresse kan være et hvilket som helst felt fra datakilde felt, eller den kan oprettes som et nyt felt ved hjælp af en Power Query-transformering. URL-dataene gemmes i objektet *Unified Activity*, som kan forbruges downstream ved hjælp af [API'er](apis.md).

   - **Vis på tidslinje**
      - Vælg, hvad du vil vise for denne aktivitet i tidslinjevisningen for dine kundeprofiler. Vælg **Ja** for at få vist aktiviteten på tidslinjen eller **Nej** for at skjule den.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Angiv kundeaktivitetsdata i et Unified Activity-objekt.":::

1. Vælg **Næste** for at vælge aktivitetstype, eller vælg **Afslut og gennemse** for at gemme aktiviteten med aktivitetstype angivet til **Andet**.

1. Vælg aktivitetstypen i trinnet **Aktivitetstype**, og vælg eventuelt, om du vil tilknytte nogle af aktivitetstyperne til brug i andre områder af Customer Insights. I øjeblikket understøtter aktivitetstyperne *Feedback*, *Loyalitet*, *SalesOrder*, *SalesOrderLine* og *Abonnement* semantik, når de er blevet enige om at tilknytte felterne. Hvis en aktivitetstype ikke er relevant for den nye aktivitet, kan du vælge *Andet* eller *Opret nyt* for en brugerdefineret aktivitetstype.

1. Vælg **Næste**.

1. Kontrollér de indstillinger, du har godkendt i **Gennemse**. Gå tilbage til et af de forrige trin, og opdater oplysningerne, hvis det er nødvendigt.

1. Vælg **Gem aktivitet** for at anvende ændringerne, og vælg **Udført** for at gå tilbage til **Data** > **Aktiviteter**. Den oprettede aktivitet vises.

1. Når du har oprettet alle aktiviteterne, skal du vælge **Kør** for at behandle dem.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Administrer eksisterende aktiviteter

Gå til **Data** > **Aktiviteter** for at få vist de gemte aktiviteter, deres kildeobjekt, aktivitetstypen, og hvis de er inkluderet i kundetidslinjen. Du kan sortere listen over aktiviteter efter en hvilken som helst kolonne eller bruge søgefeltet til at søge efter de aktiviteter, der skal håndteres.

Vælg en aktivitet for at få vist tilgængelige handlinger.

- **Rediger** aktiviteten for at ændre dens konfiguration. Konfigurationen åbner trinnet til gennemsyn. Når du har ændret konfigurationen, skal du vælge **Gem aktivitet** og derefter vælge **Kør** for at behandle ændringerne.
- **Omdøb** aktivitet. Vælg **Gem** for at anvende dine ændringer.
- **Slet** aktiviteten. Du kan også slette mere end én aktivitet på én gang ved at markere aktiviteterne og derefter vælge **Slet**. Bekræft sletningen.

## <a name="view-activity-timelines-on-customer-profiles"></a>Se aktivitetstidslinjer for kundeprofiler

1. Hvis du har valgt **Vis på aktivitetstidslinje** i aktivitetskonfiguration, skal du gå til **Kunder** og vælge en kundeprofil for at vise kundens aktiviteter i sektionen **Aktivitetstidslinje**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Se konfigurerede aktiviteter i kundeprofiler.":::

1. Sådan filtreres aktiviteter på tidslinjen:

   - Vælg et eller flere aktivitetsikoner for at forfine resultaterne, så kun den eller de valgte typer medtages.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrer aktiviteter efter type ved hjælp af ikonerne.":::

   - Vælg **Filter** for at åbne et filterpanel for at konfigurere dine tidslinjefiltre. Filtrer efter *ActivityType* og/eller *Dato*. Vælg **Anvend**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Brug filterpanelet til at konfigurere filterbetingelser.":::

1. Hvis du vil fjerne filtre, skal du markere **Ryd filtre** eller vælge **Filter**, og fjerne markeringen i filterafkrydsningsfeltet.

> [!NOTE]
> Aktivitetsfiltre fjernes, når du forlader en kundeprofil. Du skal anvende dem, hver gang du åbner en kundeprofil.

[!INCLUDE [footer-include](includes/footer-banner.md)]
