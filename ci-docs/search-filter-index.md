---
title: Administrere søge- og filterindekset for kundeprofiler
description: Find hurtigt oplysninger om samlede kundeprofiler, og filtrer efter angivne attributter.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187902"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Administrere søge- og filterindekset for kundeprofiler

Resultatet af at samle dine kundedata er et *kundeprofilobjekt*, der giver en fælles visning af den samlede kundebase. Hvis du hurtigt vil [finde oplysninger om en bestemt kunde eller gruppe af kunder](customer-profiles.md), kan en administrator konfigurere funktionerne **Søg** og **Filter** på siden **Kunder**.

   :::image type="content" source="media/search-filter.png" alt-text="Søgefilter":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definere attributter, der kan søges i, og indekserede felter

Hvis det er første gang, du definerer attributter, der kan søges efter, som administrator, skal du definere indekserede felter først. Det anbefales, at du vælger alle attributterne, som brugerne kan benytte til at søge efter og filtrere kunder på siden **Kunder**. Du kan kun angive attributter, der findes i det *kundeprofilobjekt*, du har oprettet under datasamlingsprocessen.

1. Åbn siden **Kunder**, og vælg **Indeks for søgning og filtrering**.

1. Vælg **+ Tilføj**.

1. På listen skal du vælge de attributter, du vil tilføje som indekserede felter, og klik på **Apply**.

1. Vælg **Tilføj** for at tilføje mere flere attributter. Hvis du vil fjerne en attribut, skal du markere attributten i gitteret og vælge **Fjern**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Indeks for søgning og filtrering":::

1. Vælg **Kør**, når du er klar til at anvende dine indstillinger. Når ændringerne er behandlet, finder du dem i [kundekortene på siden Kunde](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Definere filtreringsindstillinger for en given attribut

Angiv de felter, der bruges til søgning og filtrering på siden **Kunder**.

1. Åbn siden **Kunder**, og vælg **Indeks for søgning og filtrering**.

1. Vælg en attribut og **Tilføj Filter**. Definere antallet af resultater og den rækkefølge, de skal organiseres i. Afhængig af attributtens datatype vises en af følgende ruder.

   - Attributter for strengtype: Angiv antallet af ønskede resultater i ruden **Strengfilter** og den rækkefølgepolitik, de skal være organiseret efter.

   - Numeriske attributter: Angiv intervallerne i ruden **Indstillinger for antalsfilter** og den rækkefølgepolitik, de skal være organiseret efter.

   - Datotypeattributter: Angiv intervallerne i ruden **Indstillinger for datofilter** og den rækkefølgepolitik, de skal være organiseret efter.

1. Vælg **OK**. Gentag for alle de attributter, du vil filtrere efter.

1. Vælg **Kør**, når du er klar til at anvende dine indstillinger. Når ændringerne er behandlet, finder du dem i [kundekortene på siden Kunde](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Vis Indekserede kundefelter

På siden **Søg og filterindeks** vises følgende oplysninger:

- **Navn**: Repræsenterer attributtens navn, som det vises i objektet *Kunde*.
- **Datatype**: Angiver, om datatypen er en streng, et tal eller en dato.
- **Inkluderet i søgning**: Angiver, om denne attribut kan bruges til at søge efter kunder på siden **Kunder** ved hjælp af feltet **Søg**.
- **Tilføj filter**: Kontrolelement for at definere, hvordan denne attribut kan bruges til filtrering på siden **Kunder**.

## <a name="next-steps"></a>Næste trin

Gennemse siden med [ensartede profiler](customer-profiles.md) for at søge efter profiler eller bruge de indekserede felter til at se et undersæt af alle ensartede profiler.

[!INCLUDE [footer-include](includes/footer-banner.md)]
