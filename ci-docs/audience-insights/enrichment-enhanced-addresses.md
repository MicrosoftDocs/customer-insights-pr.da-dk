---
title: Udvidelse af forbedring af adresser (indeholder video)
description: Udvid og normaliser adresseoplysninger om kundeprofiler med Microsofts modeller.
ms.date: 12/16/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: afb1a6b4805702697889bb91ca36a96a714cba3d
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934916"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Udvidelse af kundeprofiler med forbedrede adresser

Adresser i dine data kan være ustrukturerede, ufuldstændige eller forkerte. Brug Microsofts modeller til at normalisere og forbedre dine adresser i [Common Data Model-formatet](/common-data-model/schema/core/applicationcommon/address) for at opnå større nøjagtighed og indsigt.

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

Forbedrede adresser fungerer kun sammen med de værdier, der allerede findes i dine adressedata, der er indtaget. Modellen gør ikke dette: 

1. Kontrollerer, om adressen er en gyldig adresse.
2. Kontrollerer, om nogen af værdierne, f.eks. postnumre eller gadenavne, er gyldige.
3. Skifter værdier, der ikke genkendes.

Modellen bruger maskinel indlæringsbaserede teknikker til at forbedre adresser. Selvom vi anvender en høj tillidstærskel for, hvornår modellen ændrer en inputværdi, som med enhver maskinlæringsbaseret model, er 100 procent nøjagtighed ikke garanteret.

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

Adresser skal indeholde en værdi for land/område. Vi behandler ikke adresser for lande eller områder, der ikke understøttes, og adresser, der ikke har angivet noget land eller område.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**.

1. Vælg **Forbedr mine data** på feltet **Udvidede adresser**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Skærmbillede af feltet Udvidede adresser.":::

1. Vælg **Kundedatasæt**, og vælg det objekt, der indeholder de adresser, du vil forbedre. Du kan vælge objektet *Kunde* for at forbedre adresser i alle dine kundeprofiler eller vælge et segmentobjekt for kun at forbedre adresser i kundeprofiler, der er indeholdt i det pågældende segment.

1. Vælg, hvordan adresser formateres i dit datasæt. Vælg **Adresse med en enkelt attribut**, hvis adresserne i dataene bruger et enkelt felt. Vælg **Multiattributadresse**, hvis adresserne i dataene bruger mere end et enkelt datafelt.

   > [!NOTE]
   > Land/område er obligatorisk i både single-attribute- og multiple-attribute-adresser. Adresser, der ikke indeholder gyldige eller understøttede værdier for land/område, vil ikke blive forbedret.

1.  Tilknyt adressefelterne fra dit samlede kundeobjekt.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Udvidet side til tilknytning af adressefelt.":::

1. Når du har fuldført felttilknytningen, skal du vælge **Næste**.

1. Angiv et navn til forbedringen og outputobjektet.

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

## <a name="enrichment-results"></a>Forbedringsresultater

Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen. Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab). Behandlingstiden afhænger af størrelsen på dine kundedata.

Når forbedringsprocessen er fuldført, kan du gennemgå de netop forbedrede kundeprofildata under **Mine forbedringer**. Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.

Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.

### <a name="overview-card"></a>Oversigtskort

Oversigtskortet viser detaljer om dækningen af forbedringen. 

* **Kunder behandlet og ændret**: Antallet af kundeprofiler, der blev forbedret.

* **Kunder behandlet og ikke ændret**: Antallet af kundeprofiler, der blev genkendt, men ikke ændret. Det sker typisk, når inputdataene er gyldige og ikke kan ændres via forbedringen.

* **Kunder ikke behandlet og ikke ændret**: Antallet af profiler, der ikke blev genkendt. Som regel for inputdata, der er ugyldige eller ikke understøttes af forbedringen.

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
