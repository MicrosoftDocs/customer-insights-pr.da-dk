---
title: Søg og filtrér kundeprofiler
description: Find hurtigt oplysninger om samlede kundeprofiler, og filtrer efter angivne attributter.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 9eaeb0c93481283324f21122c9528ff5896b9866
ms.sourcegitcommit: b9a81c2acd42d774669d2db3d0430c7d81de991c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/02/2021
ms.locfileid: "7469956"
---
# <a name="customer-profiles-search--filter-index"></a>Kundeprofiler: Indeks for søgning og filtrering

Resultatet af at samle dine kundedata er et kundeprofilobjekt, der giver en fælles visning af den samlede kundebase. Hvis du hurtigt vil [finde oplysninger om en bestemt kunde eller gruppe af kunder](customer-profiles.md), kan du konfigurere **Søg**- og **Filter**-funktionerne på siden **Kunder**. Læs videre for at få mere at vide om, hvordan administratorer kan redigere attributterne på siden **Indeks for søgning og filtrering**, som er tilgængelig for brugere i forbindelse med søgning og filtrering.

> [!div class="mx-imgBorder"]
> ![Søgefilter.](media/search-filter.png "Søgefilter")

## <a name="add-fields-and-specify-attributes"></a>Tilføje felter og angive attributter

Hvis det er første gang, du definerer attributter, der kan søges efter, som administrator, skal du definere indekserede felter først. Det anbefales, at du vælger alle attributterne, som brugerne kan benytte til at søge efter og filtrere kunder på siden **Kunder**. Du kan kun angive attributter, der findes i det kundeprofilobjekt, du har oprettet under datasamlingsprocessen.

1. Åbn siden **Kunder**, og vælg **Indeks for søgning og filtrering**.

2. Vælg **+ Tilføj** for at angive de indekserede felter.

3. På listen skal du vælge de attributter, du vil tilføje som indekserede felter. Du kan altid tilføje flere attributter ved at vælge **Tilføj**. Du kan også fjerne valgte attributter ved at vælge **Fjern**-symbolet.

## <a name="explore-the-indexed-customer-fields-table"></a>Undersøge tabellen med indekserede kundefelter

Følgende oplysninger vises i tabellen.

- **Navn**: Repræsenterer attributtens navn, som det vises i objektet Kundeprofil.
- **Datatype**: Angiver, om datatypen er en streng, et tal eller en dato.
- **Inkluderet i søgning**: Angiver, om denne attribut kan bruges til at søge efter kunder på siden **Kunder** ved hjælp af feltet **Søg**.
- **Tilføj filter**: Kontrolelement for at definere, hvordan denne attribut kan bruges til filtrering på siden **Kunder**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Redigering af filtreringsindstillinger for en given attribut

Menuen **Filter** på siden **Kunder** kan indeholde et varierende antal attributniveauer (f.eks. forskellige aldersgrupper til filtrering af kunder).

1. Vælg **Tilføj filter** for en bestemt attribut på siden **Indeks for søgning og filtrering**. Du kan definere antallet af resultater og den rækkefølge, de skal organiseres i. Afhængig af attributtens datatype vises en af følgende ruder.

- Attributter for strengtype: Angiv antallet af ønskede resultater i ruden **Indstillinger for strengfilter** og den rækkefølgepolitik, de skal være organiseret efter.

- Numeriske attributter: Angiv intervallerne i ruden **Indstillinger for antalsfilter** og den rækkefølgepolitik, de skal være organiseret efter.

- Datotypeattributter: Angiv intervallerne i ruden **Indstillinger for datofilter** og den rækkefølgepolitik, de skal være organiseret efter.

2. Vælg **Gem** for at anvende dine ændringer.

3. Vælg **Kør**, når du er klar til at anvende dine indstillinger. Når ændringerne er behandlet, finder du dem i [kundekortene på siden Kunde](customer-profiles.md). 

## <a name="next-steps"></a>Næste trin

Gennemse siden med [ensartede profiler](customer-profiles.md) for at søge efter profiler eller bruge de indekserede felter til at se et undersæt af alle ensartede profiler.


[!INCLUDE[footer-include](../includes/footer-banner.md)]