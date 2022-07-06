---
title: Forbedre kundeprofiler med forbedrede adresser (indeholder video)
description: Udvid og normaliser adresseoplysninger om kundeprofiler med Microsofts modeller.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080967"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Forbedre kundeprofiler med forbedrede adresser

Adresser i dine data kan være ustrukturerede, ufuldstændige eller forkerte. Brug Microsofts modeller til at normalisere og forbedre dine adresser i [Common Data Model-formatet](/common-data-model/schema/core/applicationcommon/address) for at opnå større nøjagtighed og indsigt.

Du kan også [forbedre adresser på datakilder](data-sources-enrichment.md) for at gøre dataene mere nøjagtige i processen til overensstemmelse med hinanden. 

## <a name="how-we-enhance-addresses"></a>Sådan forbedrer vi adresser

Vores model gennemgår en to-trinnet proces for at forbedre en adresse. For det første analyserer den adressen for at identificere dens komponenter og sætter dem i et struktureret format. Derefter bruger vi AI til at rette, fuldføre og standardisere værdierne i adressen.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Eksempel

Adresseoplysningerne kan være i et format, der ikke er standardformat, og indeholde stavefejl. Modellen kan løse disse problemer og oprette ensartede adresser i samlede kundeprofiler.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Begrænsninger

Forbedrede adresser fungerer kun med de værdier, der allerede findes i de adresserede adressedata. Modellen gør ikke dette:

1. Kontrollerer, om adressen er en gyldig adresse.
2. Kontrollerer, om nogen af værdierne, f.eks. postnumre eller gadenavne, er gyldige.
3. Skifter værdier, der ikke genkendes.

Modellen bruger maskinel indlæringsbaserede teknikker til at forbedre adresser. Som med enhver anden model, der er baseret på maskinel indlæring, er 100 % præcision ikke sikker.

## <a name="supported-countries-or-regions"></a>Understøttede lande eller områder

Vi understøtter i øjeblikket forbedrede adresser i disse lande eller områder:

- Australien
- Canada
- Frankrig
- Tyskland
- Italien
- Japan
- Storbritannien
- USA

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Forbedr mine data** på feltet **Udvidede adresser**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Skærmbillede af feltet Udvidede adresser.":::

1. Gennemse oversigten, og vælg derefter **Næste**.

1. Vælg **Kundedatasæt**, og vælg den profil eller det segment, du vil forbedre. Objektet *Kunde* forbedrer alle dine kundeprofiler, hvorimod et segment kun forbedrer de kundeprofiler, der findes i dette segment.

1. Vælg, hvordan adresser formateres i dit datasæt. Vælg **Adresse med en enkelt attribut**, hvis adresserne i dataene bruger et enkelt felt. Vælg **Multiattributadresse**, hvis adresserne i dataene bruger mere end et enkelt datafelt.

1. Vælg **Næste**, og tilknyt adressefelterne fra det samlede kundeobjekt.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Udvidet side til tilknytning af adressefelt.":::

   > [!NOTE]
   > Land/område er obligatorisk i både single-attribute- og multiple-attribute-adresser. Adresser, der ikke indeholder gyldige eller understøttede værdier for land/område, vil ikke blive forbedret.

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Angiv et **Navn** til forbedringen og **outputobjektet**.

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

## <a name="view-enrichment-results"></a>Vise forbedringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Antal kunder, der er forbedret med felt** angiver en detailudledning i dækningen af hvert enkelt forbedret felt.

### <a name="overview-card"></a>Oversigtskort

Kortet **Ændringer i oversigtskort** viser detaljer om dækningen af forbedringen:

- **Adresser behandlet og ændret**: Antallet af kundeprofiler med adresser, der blev forbedret.
- **Adresser behandlet og ikke ændret**: Antallet af kundeprofiler med adresser, der blev genkendt, men ikke ændret. Det sker typisk, når inputdataene er gyldige og ikke kan ændres via forbedringen.
- **Adresser ikke behandlet og ikke ændret**: Antallet af kundeprofiler med adresser, der ikke blev genkendt. Som regel for inputdata, der er ugyldige eller ikke understøttes af forbedringen.

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
