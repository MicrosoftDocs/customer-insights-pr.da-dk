---
title: Systemkonfiguration i målgruppen Insights
description: Få mere at vide om systemindstillinger i Dynamics 365 Customer Insights-funktionen i målgruppen Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405452"
---
# <a name="system-configuration"></a>Systemkonfiguration

Siden **System** indeholder fire faner: **Status**, **Planlæg**, **Om** og **Generelt**.

> [!div class="mx-imgBorder"]
> ![Systemside](media/system-tabs.png "Systemside")

## <a name="status-tab"></a>Fanen Status

Fanen **Status** giver dig mulighed for at spore status for dataindtagelse, dataeksporter og flere vigtige produktprocesser. Gennemse oplysningerne under denne fane for at sikre, at aktive processer er komplette.

Denne fane indeholder statustabeller for **Datakilder**, **Systemprocesser** og **Dataforberedelse**. I hver tabel registreres **navnet** på opgaven og dens tilsvarende objekt, **Status** for den seneste kørsel, og hvornår den blev **Sidst opdateret**.

Du kan se detaljerne om opgavens sidste mange kørsler at vælge dens navn.

### <a name="status-types"></a>Statustyper

Der er seks typer status for opgaver. Følgende statustyper vises også på siderne *Match*, *Flet*, *Datakilder*, *Segmenter*, *Målinger*, *Forbedring*, *Aktiviteter* og *Forudsigelser*:

- **Behandler:** Opgaven er i gang. Statussen kan ændres til Gennemført eller Mislykket.
- **Gennemført:** Opgaven blev fuldført.
- **Sprunget over:** Opgaven blev sprunget over. En eller flere af de downstream-processer, som denne opgave afhænger af, er mislykket eller er blevet sprunget over.
- **Mislykket:** Der opstod fejl under behandlingen af opgaven.
- **Annulleret:** Behandlingen blev annulleret af brugeren, før den var fuldført.
- **Sat i kø:** Behandlingen er sat i kø og starter, når alle downstream-opgaver er fuldført. Du kan finde flere oplysninger i [Opdateringspolitikker](#refresh-policies).

### <a name="refresh-policies"></a>Opdateringspolitikker

På denne liste vises opdateringspolitikkerne for hver enkelt hovedproces:

- **Datakilder:** Kører i henhold til den [konfigurerede tidsplan](#schedule-tab). Er ikke afhængig af andre processer. Match afhænger af, at processen er fuldført korrekt.
- **Match:** Kører i henhold til den [konfigurerede tidsplan](#schedule-tab). Afhænger af behandlingen af de datakilder, der bruges i sammenligningsdefinitionen. Fletning afhænger af, at processen er fuldført korrekt.
- **Fletning:** Kører i henhold til den [konfigurerede tidsplan](#schedule-tab). Afhænger af, at matchprocessen er fuldført korrekt. Segmenter, målinger, forbedring, søgning, aktiviteter, forudsigelser og dataforberedelse afhænger af, at denne proces er fuldført korrekt.
- **Segmenter**: Kører manuelt (en enkelt opdatering) og i henhold til den [konfigurerede tidsplan](#schedule-tab). Afhænger af Fletning. Indsigt afhænger af behandlingen.
- **Målinger**: Kører manuelt (en enkelt opdatering) og i henhold til den [konfigurerede tidsplan](#schedule-tab). Afhænger af Fletning.
- **Aktiviteter**: Kører manuelt (en enkelt opdatering) og i henhold til den [konfigurerede tidsplan](#schedule-tab). Afhænger af Fletning.
- **Forbedring**: Kører manuelt (en enkelt opdatering) og i henhold til den [konfigurerede tidsplan](#schedule-tab). Afhænger af Fletning.
- **Søgning**: Kører manuelt (en enkelt opdatering) og i henhold til den [konfigurerede tidsplan](#schedule-tab). Afhænger af Fletning.
- **Dataforberedelse**: Kører i henhold til den [konfigurerede tidsplan](#schedule-tab). Afhænger af Fletning.
- **Indsigt**: Kører manuelt (en enkelt opdatering) og i henhold til den [konfigurerede tidsplan](#schedule-tab). Afhænger af Segmenter.

Vælg en opgaves status for at se statusdetaljer for hele det job, opgaven var en del af. Opdateringspolitikkerne ovenfor kan gøre det lettere at forstå, hvad du kan gøre for at adressere en opgaver, der er **Sprunget over** eller **Sat i kø**.

## <a name="schedule-tab"></a>Fanen Tidsplan

Brug fanen **Planlægning** til at planlægge automatisk opdatering af alle dine [indsatte datakilder](data-sources.md). Automatiske opdateringer er med til at sikre, at opdateringer fra dine datakilder afspejles i dine samlede kundeprofiler.

1. Gå til **Admin** > **System**, og vælg fanen **Planlægning** i målgruppen Insights.

2. Standardtilstanden for den planlagte opdatering er **Fra**. Hvis du vil aktivere planlagte opdateringer, skal du ændre indstillingen øverst på skærmen til **Til**.

3. Vælg mellem **Ugentlig** (standard) og **Daglig** opdatering. Hvis du vil planlægge ugentlige opdateringer, skal du vælge en eller flere dage, hvor du vil køre opdateringen.

4. Angiv din **Tidszone**, og brug derefter **Tid**-rullelisten til at angive timingen af opdatering. Vælg **Angiv**, når du er færdig. Hvis du vil planlægge flere opdateringer på en enkelt dag, skal du vælge **Tilføj et andet tidspunkt**.

5. Vælg **Gem** for at anvende dine ændringer.

## <a name="about-tab"></a>Fanen Om

Fanen **Om** indeholder din organisations **Vist navn**, det aktive **Miljø-id**, **Område** og dit **Sessions-id**. Hvis du har mere end ét arbejdsmiljø, skal du give hver en let identificerbar visningsnavn.

## <a name="general-tab"></a>Fanen Generelt

Der er to indstillinger under fanen **Generelt**, **Sprog** og **Format for land/område**.

Appen [understøtter flere forskellige sprog](supported-languages.md). Hvis du vil ændre dit foretrukne sprog, skal du vælge et **Sprog** på rullelisten.

Hvis du vil ændre den foretrukne formatering for datoer, klokkeslæt og tal, skal du bruge rullelisten **Format for land/område**. Der vises et formateringseksempel under dette felt. Der foreslås automatisk en markering i systemet, når du vælger et nyt sprog.

Vælg **Gem** for at bekræfte dine valg.

## <a name="api-usage-tab"></a>Fanen API-forbrug

Find oplysninger om API-forbruget i realtid, og se, hvilke hændelser der er sket inden for et givent tidsinterval. Du kan finde flere oplysninger under [Dataindtagelse i realtid](real-time-data-ingestion.md).
