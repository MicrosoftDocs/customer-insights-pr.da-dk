---
title: Systemkonfiguration i målgruppen Insights
description: Få mere at vide om systemindstillinger i Dynamics 365 Customer Insights-funktionen i målgruppen Insights.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1b790106f8b9617d0c1f244e1d15a74c7ef9a82b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732354"
---
# <a name="system-configuration"></a>Systemkonfiguration

Hvis du vil have adgang til systemkonfigurationer i målgruppeindsigt, skal du vælge **Administration** > **System** i venstre navigationslinje for at få vist en liste over systemopgaver og -processer.

Siden **System** indeholder følgende faner:
- [Status](#status-tab)
- [Planlæg](#schedule-tab)
- [API-anvendelse](#api-usage-tab)
- [Om](#about-tab)
- [Generelt](#general-tab)
- [Sikkerhed](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Faner med indstillinger på systemsiden.":::

## <a name="status-tab"></a>Fanen Status

Under fanen **Status** kan du spore status for opgaver, datatab, dataeksport og flere andre vigtige produktprocesser. Gennemgå oplysningerne under denne fane for at sikre, at dine aktive opgaver og processer er fuldstændige.

Denne fane indeholder tabeller med status og behandlingsoplysninger til forskellige processer. I hver tabel registreres **navnet** på opgaven og dens tilsvarende objekt, **Status** for den seneste kørsel, og hvornår den blev **Sidst opdateret**. Du kan få vist detaljerne om de sidste mange kørsler ved at vælge opgave- eller procesnavnet. 

Vælg statusved siden af opgaven eller processen i kolonnen **Status** for at åbne ruden **Statusdetaljer**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Ruden Detaljer om systemstatus":::

### <a name="status-definitions"></a>Statusdefinitioner

Systemet bruger følgende statusser til opgaver og processer:

|Status  |Definition  |
|---------|---------|
|Annullerede |Behandlingen blev annulleret af brugeren, før den blev afsluttet.   |
|Mislykket   |Der opstod fejl under indtagelse af data.         |
|Fejl  |Processen mislykkedes.  |
|Ikke startet   |Datakilde har ingen data, der er indsat endnu, eller er stadig i kladdetilstand.         |
|Forarbejdning  |Opgave eller proces er i gang.  |
|Opdaterer    |Dataindtagelse er i gang. Du kan annullere denne handling ved at vælge **Stop opdatering** i kolonnen **Handlinger**. Hvis du stopper opdateringen af en datakilde, gendannes den til den seneste opdateringstilstand.       |
|Sprunget over  |Opgave eller proces er sprunget over. En eller flere af de downstream-processer, som denne opgave afhænger af, er mislykket eller er blevet sprunget over.|
|Gennemført  |Opgave eller proces blev fuldført. I forbindelse med datakilder angives det, at dataene er blevet gemt korrekt, hvis der nævnes et tidspunkt i kolonnen **Opdateret**.|
|I kø | Behandlingen sættes i kø og starter, når alle opgaver og processer i upstream er fuldført. Du kan finde flere oplysninger under [Opdater processer](#refresh-processes).|

### <a name="refresh-processes"></a>Opdater processer

Opdatering af opgaver og processer køres i overensstemmelse med [konfigureret tidsplan](#schedule-tab). 

|Behandl  |Beskrivelse  |
|---------|---------|
|Aktivitet  |Kører manuelt (opdatering enkelt gang). Afhænger af fletteprocessen. Indsigt afhænger af behandlingen.|
|Analysesammenkædning |Kører manuelt (opdatering enkelt gang). Afhænger af segmenter.  |
|Forberedelse af analyse |Kører manuelt (opdatering enkelt gang). Afhænger af segmenter.  |
|Dataforberedelse   |Afhænger af flette.   |
|Datakilder   |Er ikke afhængig af andre processer. Match afhænger af, at processen er fuldført korrekt.  |
|Forbedringer   |Kører manuelt (opdatering enkelt gang). Afhænger af fletteprocessen. |
|Eksporterer destinationer |Kører manuelt (opdatering enkelt gang). Afhænger af segmenter.  |
|Indsigt |Kører manuelt (opdatering enkelt gang). Afhænger af segmenter.  |
|Intelligens   |Afhænger af flette.   |
|Resultat |Afhænger af behandlingen af de datakilder, der bruges i sammenligningsdefinitionen.      |
|Målinger  |Kører manuelt (opdatering enkelt gang). Afhænger af fletteprocessen.  |
|Fletning   |Afhænger af, at matchprocessen er fuldført korrekt. Segmenter, målinger, forbedring, søgning, aktiviteter, forudsigelser og dataforberedelse afhænger af, at denne proces er fuldført korrekt.   |
|Profiler   |Kører manuelt (opdatering enkelt gang). Afhænger af fletteprocessen. |
|Søge   |Kører manuelt (opdatering enkelt gang). Afhænger af fletteprocessen. |
|Segmenter  |Kører manuelt (opdatering enkelt gang). Afhænger af fletteprocessen. Indsigt afhænger af behandlingen.|
|System   |Afhænger af, at matchprocessen er fuldført korrekt. Segmenter, målinger, forbedring, søgning, aktiviteter, forudsigelser og dataforberedelse afhænger af, at denne proces er fuldført korrekt.   |
|Bruger  |Kører manuelt (opdatering enkelt gang). Afhænger af objekter.  |

Vælg status for en proces for at se statusoplysninger for hele jobbet. Ovenstående opdateringsprocesser kan være med til at forstå, hvad du kan gøre for at løse opgaver eller processer, der er **sprunget over** eller **sat i kø**.

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

Du kan ændre sproget og lande-/områdeformatet under fanen **Generelt**.

Customer Insights [understøtter mange sprog](/dynamics365/get-started/availability). Appen bruger dit foretrukne sprog til at vise elementer som menuen, etikettetekst og systemmeddelelser på dit foretrukne sprog.

Importerede data og oplysninger, du har angivet manuelt, oversættes ikke.

### <a name="update-the-settings"></a>Opdater indstillingerne

Hvis du vil ændre dit foretrukne sprog, skal du vælge et **Sprog** på rullelisten.

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

## <a name="security-tab"></a>Sikkerhedsfane

Under fanen **Sikkerhed** kan du kæde og administrere din egen [Azure-nøgleboks](/azure/key-vault/general/basic-concepts) til miljøet.
Den dedikerede Key Vault kan bruges til at oprette og bruge hemmeligheder i en organisations grænse for overholdelse af angivne standarder. Målgruppeindsigt kan bruge hemmelighederne i Azure Key Vault til at [konfigurere forbindelser](connections.md) til tredjepartssystemer.

Du kan finde flere oplysninger i [Medbring dit eget Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
