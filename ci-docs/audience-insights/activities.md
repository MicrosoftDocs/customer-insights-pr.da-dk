---
title: Kundeaktiviteter
description: Definer kundeaktiviteter, og se dem på en tidslinje for kundeprofiler.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c250efcd54ec126c0726b22a971cdedd89760d6b
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617962"
---
# <a name="customer-activities"></a>Kundeaktiviteter

Kombiner kundeaktiviteter fra [forskellige datakilder](data-sources.md) i Dynamics 365 Customer Insights for at oprette en tidslinje, der viser aktiviteterne kronologisk. Inkluder tidslinjen i Dynamics 365-apps med [tilføjelsesprogrammet Kundekortløsning](customer-card-add-in.md) eller i et Power BI-dashboard.

## <a name="define-an-activity"></a>Definere en aktivitet

Datakilderne kan inkludere objekter med transaktions- og aktivitetsdata fra flere datakilder. Identificer disse objekter, og vælg de aktiviteter, du vil have vist på kundens tidslinje. Vælg det objekt, der indeholder målaktiviteten eller -aktiviteterne.

Et objekt skal have mindst én attribut af typen **Dato** for at blive medtaget på en kundes tidslinje, og du kan ikke tilføje objekter uden **Dato**-felter. Kontrolelementet **Tilføj aktivitet** deaktiveres, hvis der ikke findes et sådant objekt.

1. Gå til **Data** > **Aktiviteter** i målgruppeindsigt.

1. Vælg **Tilføj aktivitet** for at starte den styrede oplevelse af aktivitetskonfigurationsprocessen.

1. Angiv værdier for følgende felter i datatrinnet **Aktivitetsdata**:

   - **Aktivitetsnavn**: Vælg et navn til aktiviteten.
   - **Objekt**: Vælg et objekt, der indeholder transaktions- eller aktivitetsdata.
   - **Primær nøgle**: Vælg det felt, der entydigt identificerer en post. Den må ikke indeholde dublerede værdier, tomme værdier eller manglende værdier.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Konfigurer aktivitetsdataene med navn, objekt og primær nøgle.":::

1. Vælg **Næste** for at gå til næste trin.

1. I trinnet **Relation** skal du konfigurere detaljerne for at knytte dine aktivitetsdata til den tilhørende kundepost. I dette trin visualiseres forbindelsen mellem objekter.  

   - **Først**: Fremmed felt i aktivitetsobjektet, der bruges til at oprette en relation til et andet objekt.
   - **Andet**: Det tilsvarende kildekundeobjekt, som aktivitetsobjektet er i relation til. Du kan kun relatere til kildekundeobjekter, der bruges i processen til dataenheder.
   - **Tredje**: Hvis der allerede findes en relation mellem dette aktivitetsobjekt og det valgte kildekundeobjekt, er relationsnavnet skrivebeskyttet. Hvis der ikke findes en sådan relation, oprettes der en ny relation med det navn, du angiver i denne boks.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Definere objektrelationen.":::

   > [!TIP]
   > I B2B-miljøer kan du vælge mellem firmaobjekter og andre objekter. Hvis du vælger et firmaobjekt, angives relationsstien automatisk. I forbindelse med andre objekter skal du definere relationsstien hen over et eller flere mellemliggende objekter, indtil du når til et firmaobjekt.

1. Vælg **Næste** for at gå til næste trin. 

1. I **Aktivitetsenhed**-trinnet skal du vælge aktivitetshændelsen og starttiden for aktiviteten. 
   - **Obligatoriske felter**
      - **Hændelsesaktivitet**: Det felt, der er begivenheden for denne aktivitet.
      - **Tidsstempel**: Felt, der repræsenterer starttiderne for aktiviteten.

   - **Valgfrie felter**
      - **Flere detaljer**: Felt med relevante oplysninger om aktiviteten.
      - **Ikon**: Det ikon, der bedst repræsenterer denne aktivitetstype.
      - **Webadresse**: Felt, der indeholder en URL-adresse med oplysninger om aktiviteten. For eksempel det transaktionssystem, der er kilde til aktiviteten. Denne URL-adresse kan være et hvilket som helst felt fra datakilden, eller den kan konstrueres som et nyt felt ved hjælp af en Power Query-transformation. URL-dataene gemmes i objektet *Unified Activity*, som kan forbruges downstream ved hjælp af [API'er](apis.md).

   - **Vis på tidslinje**
      - Vælg, hvad du vil vise for denne aktivitet i tidslinjevisningen for dine kundeprofiler. Vælg **Ja** for at få vist aktiviteten på tidslinjen eller **Nej** for at skjule den.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Angiv kundeaktivitetsdata i et Unified Activity-objekt.":::

1. Vælg **Næste** for at gå til næste trin. Du kan vælge **Afslut og gennemse** for at gemme aktiviteten nu, hvor aktivitetstypen er angivet til **Andet**. 

1. Vælg aktivitetstypen i trinnet **Aktivitetstype**, og vælg eventuelt, om du vil tilknytte nogle af aktivitetstyperne til brug i andre områder af Customer Insights. I øjeblikket kan aktivitetstyperne *Feedback*, *Loyalitet*, *Salgsordre*, *Salgsordrelinje* og *Abonnement* tilknyttes semantisk, når du har accepteret at tilknytte felterne. Hvis en aktivitetstype ikke er relevant for den nye aktivitet, kan du vælge *Andet* eller *Opret nyt* for en brugerdefineret aktivitetstype.

1. Vælg **Næste** for at gå til næste trin. 

1. Kontrollér de indstillinger, du har godkendt i **Gennemse**. Gå tilbage til et af de forrige trin, og opdater oplysningerne, hvis det er nødvendigt.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Gennemse de angivne felter for en aktivitet.":::
   
1. Vælg **Gem aktivitet** for at anvende ændringerne, og vælg **Udført** for at gå tilbage til **Data** > **Aktiviteter**. Her kan du se, hvilke aktiviteter der er angivet til at blive vist på tidslinjen. 

1. Vælg **Kør** på siden **Aktiviteter** for at behandle aktiviteten. 

> [!TIP]
> Opgaver og processer indeholder [seks typer status](system.md#status-types). De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies). Du kan vælge status for en proces for at se statusdetaljer for hele jobbet. Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.


## <a name="manage-existing-activities"></a>Administrer eksisterende aktiviteter

I **Data** > **Aktiviteter** kan du få vist alle de gemte aktiviteter og administrere dem. De enkelte aktiviteter repræsenteres af en række, der også indeholder oplysninger om kilden, objektet og aktivitetstypen.

Følgende handlinger er tilgængelige, når du vælger en aktivitet. 

- **Rediger**: Åbner aktivitetskonfigurationen i gennemsynstrinnet. Du kan ændre en eller alle de aktuelle konfigurationer fra dette trin. Når du har ændret konfigurationen, skal du vælge **Gem aktivitet** og derefter vælge **Kør** for at behandle ændringerne.

- **Omdøb**: Åbner en dialogboks, hvor du kan angive et andet navn til den valgte aktivitet. Vælg **Gem** for at anvende dine ændringer.

- **Slet**: Åbner en dialogboks for at bekræfte sletningen af den valgte aktivitet. Du kan også slette mere end én aktivitet på én gang ved at markere aktiviteterne og derefter vælge sletteikonet. Bekræft sletningen ved at vælge **Slet**.

## <a name="view-activity-timelines-on-customer-profiles"></a>Se aktivitetstidslinjer for kundeprofiler

Når du har konfigureret kundeaktiviteter, skal du vælge **Vis i aktivitetstidslinje** i aktivitetskonfigurationen for at finde alle kundens aktiviteter på kundeprofilen.

Hvis du vil åbne tidslinjen for en kunde, skal du gå til **Kunder** og vælge den kundeprofil, du vil have vist.

Hvis en kunde har deltaget i en aktivitet, som du har konfigureret, kan du finde den i sektionen **Aktivitetstidslinje**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Se konfigurerede aktiviteter i kundeprofiler.":::

Du kan filtrere aktiviteter på flere måder på aktivitetstidslinjen:

- Du kan vælge et eller mange af aktivitetsikonerne for at forfine resultaterne, så kun den eller de valgte typer medtages.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtrer aktiviteter efter type ved hjælp af ikonerne.":::

- Du kan vælge **Filter** for at åbne et filterpanel for at konfigurere dine tidslinjefiltre.

   1. Du kan filtrere efter *Aktivitetstype* og *Dato*
   1. Vælg **Anvend** for at bruge filtrene på aktivitetstidslinjen.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Brug filterpanelet til at konfigurere filterbetingelser.":::

Hvis du vil fjerne filtre, skal du markere **x** ud for hvert filter, der anvendes på tidslinjen, eller vælge **Ryd filtre**.


> [!NOTE]
> Aktivitetsfiltre fjernes, når du forlader en kundeprofil. Du skal anvende dem, hver gang du åbner på en kundeprofil.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
