---
title: Forbedrede virksomhedsdata
description: Forbedre og normalisere virksomhedsdata med Microsofts modeller.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
---

# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Forbedring af virksomhedsprofiler med forbedrede virksomhedsdata

Brug Microsofts modeller og kompilerede virksomhedsdata til at korrigere, supplere og standardisere dine virksomhedsprofiler. Vi bruger formatet [Common Data Model](/common-data-model/schema/core/applicationcommon/account) for at opnå større præcision og indsigt.

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

Der er nogle få begrænsninger i forbindelse med de forbedrede data. Elementerne på listen nedenfor understøttes ikke af modellen.

1.  Bekræft firmaets identitet. Vi kontrollerer ikke, om inputtet er en eksisterende organisation, eller om en virksomhed bruger outputtet som standardnavn.
2.  Omfattende dækning af virksomheder globalt. Microsofts kompilerede virksomhedsdata har global dækning, men tilbyder mest dækning i Australien, Canada, Storbritannien og USA.
3.  Standardiser virksomhedsadresser globalt. Vi understøtter i øjeblikket standardiserede adresser i disse lande eller områder: Australien, Canada, Frankrig, Tyskland, Italien, Japan, Storbritannien og USA.
4.  Garanterer nøjagtigheden eller opdatering af data. Da forretningsoplysninger ofte ændres, kan vi ikke garantere, at de forbedrede virksomhedsdata altid er nøjagtige eller opdaterede.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**.

1. Vælg **Forbedring af data** i feltet **Forbedrede virksomhedsdata**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Felter med lige adgang i hubben til virksomhedsdata.":::

1. Vælg **Kundedatasæt**, og vælg det objekt, der indeholder de adresser, du vil forbedre. Du kan vælge objektet *Kunde* for at forbedre adresser i alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre adresser i kundeprofiler, der er indeholdt i det pågældende segment.

1. Vælg, hvilken type felter i virksomhedsprofilerne der skal bruges til sammenholdelse med Microsofts kompilerede virksomhedsdata. Denne indstilling påvirker de tilknytningsfelter, du har adgang til i næste trin.

1.  Tilknyt firmafelterne fra det samlede kundeobjekt. Jo flere nøgle-id'er og felter, du tilknytter, jo større er sandsynligheden for en højere overensstemmelseshastighed.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Trin til datatilknytning, når virksomhedens forbedring konfigureres.":::

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Angiv et navn til forbedringen og outputobjektet.

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

## <a name="enrichment-results"></a>Forbedringsresultater

Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen. Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab). Behandlingstiden afhænger af størrelsen på dine kundedata.

Når forbedringsprocessen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**. Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.

Du kan se et eksempel på de forbedrede data i **Forbedrede kunders forhåndsversion**-feltet. Vælg **Se mere**, og vælg fanen **Data** for at få adgang til en detaljeret visning af hver enkelt forbedret profil.

### <a name="overview-card"></a>Oversigtskort

Oversigtskortet viser detaljer om dækningen af forbedringen. 

* **Firmaer behandlet og ændret**: Antallet af kundefirmaprofiler, der blev forbedret.

* **Firmaer behandlet og ikke ændret**: Antallet af kundefirmaprofiler, der blev genkendt, men ikke ændret. Det sker typisk, når inputdataene er gyldige og ikke kan ændres via forbedringen.

* **Firmaer ikke behandlet og ikke ændret**: Antallet af kundefirmaprofiler, der ikke blev genkendt. Det sker som regel for inputdata, der er ugyldige eller ikke understøttes af forbedringen.

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
