---
title: Forbedrede virksomhedsdata
description: Forbedre og normalisere virksomhedsdata med Microsofts modeller.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953942"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Forbedring af virksomhedsprofiler med forbedrede virksomhedsdata

Brug Microsofts modeller og kompilerede virksomhedsdata til at korrigere, supplere og standardisere dine virksomhedsprofiler. Vi bruger formatet [Common Data Model](/common-data-model/schema/core/applicationcommon/account) for at opnå større præcision og indsigt.

Du kan også [forbedre firmadata på datakilder](data-sources-enrichment.md) for at gøre dataene mere nøjagtige i processen til overensstemmelse med hinanden.

For offentlige virksomheder i USA er der tilgængelige oplysninger som omsætning, aktieaktie, branche og meget mere.  

## <a name="how-we-enhance-company-data"></a>Sådan forbedrer vi virksomhedsdata

Vores model gennemgår en proces i to trin for at forbedre en virksomhedsprofil. Først normaliseres virksomhedsnavnet. *Microsoft Corp* korrigeres og standardiseres f.eks. til *Microsoft Corporation*. Den forsøger at finde et match i Microsofts kompilerede virksomhedsdata. Hvis der blev fundet et match, forbedrer vi virksomhedsprofilen med oplysninger fra vores kompilerede virksomhedsdata, herunder firmanavnet.

### <a name="example"></a>Eksempel

Firmaoplysningerne følger muligvis ikke et standardiseret format og indeholder stavefejl. Modellen forsøger at løse disse problemer og oprette ensartede oplysninger.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Begrænsninger

Modellen gør ikke dette:

- Bekræft firmaets identitet. Vi kontrollerer ikke, om inputtet er en eksisterende organisation, eller om en virksomhed bruger outputtet som standardnavn.
- Omfattende dækning af virksomheder globalt. Microsofts kompilerede virksomhedsdata har global dækning, men tilbyder mest dækning i Australien, Canada, Storbritannien og USA.
- Standardiser virksomhedsadresser globalt. Vi understøtter i øjeblikket standardiserede adresser i disse lande eller områder: Australien, Canada, Frankrig, Tyskland, Italien, Japan, Storbritannien og USA.
- Garanterer nøjagtigheden eller opdatering af data. Da forretningsoplysninger ofte ændres, kan vi ikke garantere, at de forbedrede virksomhedsdata altid er nøjagtige eller opdaterede.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Forbedring af data** i feltet **Forbedrede virksomhedsdata**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Felter med lige adgang i hubben til virksomhedsdata.":::

1. Gennemse oversigten, og vælg derefter **Næste**.

1. Vælg **Kundedatasæt**, og vælg den profil eller det segment, du vil forbedre. Objektet *Kunde* forbedrer alle dine kundeprofiler, hvorimod et segment kun forbedrer de kundeprofiler, der findes i dette segment.

1. Vælg, hvilken type felter i virksomhedsprofilerne der skal bruges til at sammenholde med Microsofts kompilerede virksomhedsdata. Denne indstilling påvirker de tilknytningsfelter, du har adgang til i næste trin.

1. Vælg **Næste**.

1. Knyt firmafelterne til firmadataene fra Microsoft. Tilføj flere felter for at opnå en mere nøjagtig overensstemmelse.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Trin til datatilknytning, når virksomhedens forbedring konfigureres.":::

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Angiv et **Navn** til forbedringen og **outputobjektet**.

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

1. Vælg **Kør** for at starte forbedringsprocessen, eller luk for at vende tilbage til siden **Forbedringer**.

## <a name="enrichment-results"></a>Forbedringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Oversigtskort

Feltet **Ændringer i oversigtskort** viser detaljer om dækningen af forbedringen

- **Firmaer behandlet og ændret**: Antallet af kundefirmaprofiler, der blev forbedret.
- **Firmaer behandlet og ikke ændret**: Antallet af kundefirmaprofiler, der blev genkendt, men ikke ændret. Det sker typisk, når inputdataene er gyldige og ikke kan ændres via forbedringen.
- **Firmaer ikke behandlet og ikke ændret**: Antallet af kundefirmaprofiler, der ikke blev genkendt. Det sker som regel for inputdata, der er ugyldige eller ikke understøttes af forbedringen.

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
