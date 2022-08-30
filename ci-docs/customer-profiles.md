---
title: Vis kundeprofiler
description: Få vist de samlede kundedata, herunder brug af søge- og filterdata
ms.date: 06/08/2022
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
ms.openlocfilehash: 0c8edfd8f45ce7770d568811df2b38be1b04e73a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303776"
---
# <a name="view-customer-profiles"></a>Vis kundeprofiler

Kundeprofiler er tilgængelige, når du [opretter det samlede *Kunde*-objekt](data-unification.md). På siden **Kunder** vises en samlet visning af dine samlede kundeprofiler. Kunder kan være enkeltpersoner eller organisationer.

Gå til siden **Kunder** for at få vist dine kunder og deres profiler. Hver kundeprofil repræsenteres ved et felt. Brug kontrolelementerne for sideinddeling til at hente flere poster. På kortet vises felter fra objektet *Kunde* som defineret i **Indeks for søgning og filtrering**. Rækkefølgen af felterne i de enkelte kort udvælges af systemet.

> [!NOTE]
> Hvis du ikke kan se felterne, når du vælger **Kunder** under navigation, skal din administrator [definere mindst én søgbar attribut](search-filter-index.md) i **Indeks for søgning og filtrering**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Siden Kunder, der viser resultatfelter.":::

Vælg en af følgende handlinger:
- [Vis Kundeoplysninger](#view-customer-details)
- [Administrere søge- og filterindekset](search-filter-index.md) (kun administratorer)
- [Filtrere kunder](#filter-customers)
- **Udvide kort** eller **skjule kort** for at udvide eller skjule de oplysninger, der vises i kundefelt
- **Sortere efter** en bestemt attribut
- [Søge efter kunder](#search-for-customers)

  > [!NOTE]
  > Hvis en administrator skal bruge søge- og filterfunktionen, skal de attributter, der kan søges i, konfigureres, og de felter, der kan filtreres, ved hjælp af søge- og filterindekset.

## <a name="search-for-customers"></a>Søge efter kunder

Søg efter kunder ved at angive et navn eller en anden attribut i **Søg kunder**. De attributter, der kan søges i, defineres af administratoren og kommer fra det samlede *kunde*-objekt.

> [!NOTE]
> **Streng** er den eneste datatype, der medtages i søgningen. Brug den i feltet **Søg efter kunder** på siden Kunder til at søge efter kunder.

## <a name="filter-customers"></a>Filtrere kunder

Filtrer kunderne efter objektfelterne *Kunde*. Felter, der kan filtreres, defineres af administratoren.

1. Vælg **Vis filtre** på siden **Kunder**. Filterruden vises.

1. Markér afkrydsningsfelterne ud for de attributter, som du vil filtrere kunder efter.

1. Fjern alle filtre ved at markere **Ryd filtre**, eller fjern markeringen i et afkrydsningsfelt ud for den valgte attribut.

1. Vælg **Skjul filtre** for at lukke filterruden.

1. Vælg **Gem filtre som segment** for at gemme filterresultaterne som et [segment](segments.md).
   1. Angiv et navn til segmentet.
   1. Vælg **Gem** for at gemme segmentet.
   1. Vælg, om du vil køre segmentet nu, ved at vælge **Aktivér** eller kør det **senere**.

## <a name="view-customer-details"></a>Vis Kundeoplysninger

Vælg en kunderude for at få vist detaljer for en bestemt kunde på siden **kunder**.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Siden Kundeoplysninger.":::

Kundeoplysninger indeholder:

**Feltet Kundeprofil**: viser de forskellige værdier fra det samlede objekt *Kunde*. Hvis et felt ikke har nogen værdi for den valgte kundeprofil, vises det ikke undtagen for adressefeltet. Feltet er struktureret i sektioner:

- I første sektion vises et foruddefineret sæt felter efterfulgt af alle de felter, der er en del af søge- og filterindekset. Alle adresserelaterede felter kombineres i en enkelt linje, der vises selv hvis profilen ikke indeholder adresseoplysninger.
- **Kontakter for denne kunde** vises i miljøer for forretningskonti (B-til-B). Hver kontakt vises med egne felter. Tomme felter er skjulte.
- **Yderligere felter**: viser de resterende felter i den valgte kunde undtagen id'er.
- **Id'er**: viser alle id'er under deres tilsvarende objektnavn. Felter identificeres som id efter semantik.

**Aktivitetstidslinje** viser data, hvis du har konfigureret [aktiviteter](activities.md). Tidslinjevisningen indeholder kronologisk sorterede aktiviteter for den valgte kunde og starter med den seneste aktivitet.

**Indsigt**:

- **Måling**: viser, om du har konfigureret [kundeattributmålinger](measures.md). De indeholder beregnede nøgletal omkring dine kunder på de enkelte kundeniveauer.

- **Potentielle interesser, potentielle brands** viser, om du har konfigureret et [brand eller en forbedring af interessetilhørsforhold](enrichment-microsoft.md). Den repræsenterer potentielle interesser og tilhørsforhold for brands, der er baseret på andre kunder, hvis profil svarer til den valgte kundeprofil.

Vælg **Returner til kunder** for at vende tilbage til **Kunder**.

## <a name="next-steps"></a>Næste trin

[Du kan tilføje flere datakilder](data-sources.md), [forbedre samlede profiler](enrichment-hub.md) eller [oprette segmenter](segments.md) for at arbejde med samlede kundeprofiler i andre programmer.

[!INCLUDE [footer-include](includes/footer-banner.md)]
