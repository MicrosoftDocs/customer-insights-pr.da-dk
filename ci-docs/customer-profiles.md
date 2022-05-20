---
title: Vis kundeprofiler
description: Få en kombineret visning af dine samlede kundedata.
ms.date: 05/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 9bb7abc04afe38d73e1df9b252e1864fa6570d7e
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755775"
---
# <a name="customer-profiles"></a>Kundeprofiler

På siden **Kunder** vises en samlet visning af dine samlede kundeprofiler. Kundeprofilerne er tilgængelige, når du har [oprettet det samlede kundeobjekt](data-unification.md). På siden kan du søge efter kunder og definere indekset for den pågældende søgning.

Kunder kan være enkeltpersoner eller organisationer. Hver kundeprofil repræsenteres ved et felt. Brug kontrolelementerne for sideinddeling til at hente flere poster. På kortet vises felter fra objektet *Kunde* som defineret i **Indeks for søgning og filtrering**. Rækkefølgen af felterne i de enkelte kort udvælges af systemet.

Vælg et felt for at få vist data for den valgte kunde på en dedikeret side med navnet [Kundeoplysninger](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"]
> ![Siden Kunder, der viser resultatfelter](media/customers-page-result-tiles-B2C.png "Siden Kunder, der viser resultatfelter")

> [!NOTE]
> Hvis du ikke kan se felterne, når du vælger **Kunder** under navigation, skal din administrator [definere mindst én søgbar attribut](search-filter-index.md) i **Indeks for søgning og filtrering**.

## <a name="search-for-customers"></a>Søge efter kunder

Søg efter kunder ved at angive et navn eller en anden attribut i søgefeltet. Søgningen fungerer kun inden for objektet *Kunde*, der oprettes under processen til datasamling.

Som administrator kan du konfigurere søgbare attributter på siden **Indeks for søgning og filtrering**. Du kan finde flere oplysninger i [Administrere indeks for søgning og filtrering](search-filter-index.md).

## <a name="filter-customers"></a>Filtrere kunder

Du kan filtrere kunderne efter objektfelterne *Kunde*. På samme måde som for søgning skal administratoren først definere felterne som filtrerbare på siden **Indeks for søgning og filtrering**.

1. Vælg **Vis filtre** på siden **Kunder**.

1. Markér afkrydsningsfelterne ud for de attributter, som du vil filtrere kunder efter.

1. Fjern dine filtre ved at vælge **Ryd filtre** på siden **Kunder**.

## <a name="customer-details-page"></a>Siden Kundeoplysninger

Vælg et af kundefelterne for at åbne siden **Kundeoplysninger**. Denne visning indeholder en samlet oplysning for den valgte kunde. Kundeoplysninger omfatter følgende indhold:

**Feltet Kundeprofil**: I dette felt vises de forskellige værdier fra det samlede objekt *Kunde*. Hvis et felt ikke har nogen værdi for den valgte kundeprofil, vises det ikke. Feltet er struktureret i sektioner:

- I første sektion vises et foruddefineret sæt felter efterfulgt af alle de felter, der er en del af søge- og filterindekset. Alle adresserelaterede felter kombineres i en enkelt linje, hvis profilen indeholder sådanne felter.
- **Kontakter for denne kunde**: I miljøer for forretningskonti kan du se alle relaterede kontakter for denne kunde som anden sektion. Hver kontakt vises med egne felter. Tomme felter er skjulte.
- **Yderligere felter**: Viser de resterende felter i den valgte kunde undtagen id'er.
- **Id'er**: Viser alle id'er under deres tilsvarende objektnavn. Felter identificeres som id'er efter semantik, der kategoriserer dem som sådanne.

**Aktivitetstidslinje**: Viser data, hvis du har konfigureret aktiviteter. Tidslinjevisningen indeholder kronologisk sorterede aktiviteter for den valgte kunde og starter med den seneste aktivitet. Du kan finde flere oplysninger i [Kundeaktiviteter](activities.md).

**Indsigt**:

- **Målinger**: Viser, om du har konfigureret en eller flere målinger for kundeattributten. De indeholder beregnede nøgletal omkring dine kunder på de enkelte kundeniveauer. Du kan finde flere oplysninger ved at gå til [Definere og administrere målinger](measures.md).

- **Potentielle interesser, potentielle brands**: Viser, om du har konfigureret et brand eller en forbedring af interessetilhørsforhold. Den repræsenterer potentielle interesser og tilhørsforhold for brands, der er baseret på andre kunder, hvis profil svarer til den valgte kundeprofil. Du kan finde flere oplysninger ved at gå til [Forbedre kundeprofiler med brand- og interessetilhørsforhold](enrichment-microsoft.md).

Vælg **Tilbage til kunder** for at vende tilbage til søgesiden for kunder.

## <a name="next-steps"></a>Næste trin

[Du kan tilføje flere datakilder](data-sources.md), [forbedre samlede profiler](enrichment-hub.md) eller [oprette segmenter](segments.md) for at arbejde med samlede kundeprofiler i andre programmer.

[!INCLUDE [footer-include](includes/footer-banner.md)]
