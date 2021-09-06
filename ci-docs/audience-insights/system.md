---
title: Systemkonfiguration i målgruppen Insights
description: Få mere at vide om systemindstillinger i Dynamics 365 Customer Insights-funktionen i målgruppen Insights.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2af8728009b4f1d53ebc2557bab8c79537a0dc5dda54477493ab1ad16f3f9a8a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035891"
---
# <a name="system-configuration"></a>Systemkonfiguration

Siden **System** indeholder følgende faner:
- [Status](#status-tab)
- [Planlæg](#schedule-tab)
- [API-anvendelse](#api-usage-tab)
- [Om](#about-tab)
- [Generelt](#general-tab)

> [!div class="mx-imgBorder"]
> ![Systemside.](media/system-tabs.png "Systemside")

## <a name="status-tab"></a>Fanen Status

Under fanen **Status** kan du spore status for dataindtag, dataeksport og flere andre vigtige produktprocesser. Gennemse oplysningerne under denne fane for at sikre, at aktive processer er komplette.

Denne fane indeholder tabeller med status og behandlingsoplysninger til forskellige processer. I hver tabel registreres **navnet** på opgaven og dens tilsvarende objekt, **Status** for den seneste kørsel, og hvornår den blev **Sidst opdateret**.

Du kan se detaljerne om opgavens sidste mange kørsler at vælge dens navn.

### <a name="status-types"></a>Statustyper

Der er seks typer status for opgaver. Følgende statustyper vises også på siderne *Match*, *Flet*, *Datakilder*, *Segmenter*, *Målinger*, *Forbedring*, *Aktiviteter* og *Forudsigelser*:

- **Behandler:** Opgaven er i gang. Statussen kan ændres til Gennemført eller Mislykket.
- **Gennemført:** Opgaven blev fuldført.
- **Sprunget over:** Opgaven blev sprunget over. En eller flere af de downstream-processer, som denne opgave afhænger af, er mislykket eller er blevet sprunget over.
- **Mislykket:** Der opstod fejl under behandlingen af opgaven.
- **Annulleret:** Behandlingen blev annulleret af brugeren, før den var fuldført.
- **I kø:** Behandling sættes i kø og startes, når alle upstream-opgaver er fuldført. Du kan finde flere oplysninger i [Opdateringspolitikker](#refresh-policies).

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

Find detaljer om brugen af API i realtid, og se, hvilke hændelser der er sket i en bestemt tidsramme. Du vælger tidsramme i rullemenuen **Vælg en tidsramme**. 

**API-brug** indeholder tre sektioner: 
- **API-kald** - et diagram, der visualiserer det samlede antal kald til API'en i den valgte tidsramme.

- **Dataoverførsel** - et diagram, der viser den mængde data, der er overført via API'en i den valgte tidsramme.

-  **Handlinger** - en tabel med rækker for hver tilgængelig API-handling og oplysninger om brugen af handlingerne. Du kan vælge et handlingsnavn for at gå til [API-referencen](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Handlinger, der bruger [dataindtag i realtid](real-time-data-ingestion.md), indeholder en knap med et kikkert-symbol for at få vist brugen af API i realtid. Vælg knappen for at åbne en siderude med detaljer om forbrug for API-anvendelsen i realtid i det aktuelle miljø.   
   Brug feltet **Gruppe efter** i ruden til **Brug af realtids-API** for at vælge, hvordan dine interaktioner i realtid skal vises bedst. Du kan gruppere dataene efter API-metode, kvalificeret navn på objekt (indtaget objekt), oprettet af (kilden for hændelsen), resultat (vellykket eller mislykket) eller fejlkoder. Dataene er tilgængelige som et historikdiagram og en tabel.


[!INCLUDE[footer-include](../includes/footer-banner.md)]