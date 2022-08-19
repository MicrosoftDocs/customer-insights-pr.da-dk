---
title: Vis systemkonfiguration
description: Få mere at vide om systemindstillinger i Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246240"
---
# <a name="view-system-configuration"></a>Vis systemkonfiguration

Få vist systemoplysninger, systemstatus og brug af API.

## <a name="view-api-usage"></a>Vis API-forbrug

Vis detaljer om brugen af API i realtid, og se, hvilke hændelser der er sket i en bestemt tidsramme.

1. Gå til **Administration** > **System**, og vælg fanen **API-forbrug**.

1. **Vælg en tidsramme** for visning.

   **API-brug**-siden indeholder tre sektioner:

   - **API-kald** - et diagram, der visualiserer det samlede antal kald til API'en i den valgte tidsramme.
   - **Dataoverførsel** - et diagram, der viser den mængde data, der er overført via API'en i den valgte tidsramme.
   - **Handlinger** - en tabel med rækker for hver tilgængelig API-handling og oplysninger om brugen af handlingerne. Vælg et handlingsnavn for at gå til [API-referencen](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Handlinger, der bruger [dataindtag i realtid](real-time-data-ingestion.md), indeholder et kikkert-symbol for at få vist brugen af API i realtid.

   1. Vælg kikkerten for at åbne en rude **Brug af realtids-API** med detaljer om forbrug for handlingen.
   1. **Vælg en tidsramme** for visning.
   1. Brug feltet **Gruppe efter** for at vælge, hvordan dine interaktioner i realtid skal vises bedst. Grupper dataene efter **API-metode**, **kvalificeret navn på objekt** (indtaget objekt), **oprettet af** (kilden for hændelsen), **resultat** (vellykket eller mislykket) eller **fejlkoder**. Dataene er tilgængelige som et historikdiagram og en tabel.

## <a name="view-system-information"></a>Vis systemoplysninger

Få vist visningsnavn, id, område, type og sessions-id.

1. Gå til **Administration** > **System**, og vælg fanen **Om**.

1. Hvis du vil have vist sproget og landet/området, skal du vælge fanen **Generelt**.

### <a name="update-preferred-language-or-countryregion"></a>Opdater foretrukket sprog eller land/område

Customer Insights [understøtter mange sprog](/dynamics365/get-started/availability). Appen bruger dit foretrukne sprog til at vise elementer som menuen, etikettetekst og systemmeddelelser på dit foretrukne sprog.

Importerede data og oplysninger, du har angivet manuelt, oversættes ikke.

1. Gå til **Administration** > **System**, og vælg fanen **Generelt**.

1. Hvis du vil ændre dit foretrukne sprog, skal du vælge et **Sprog** på rullelisten.

1. Hvis du vil ændre den foretrukne formatering for datoer, klokkeslæt og tal, skal du bruge rullelisten **Format for land/område**. Der vises en formaterings-forhåndsversion. Der foreslås automatisk en markering i systemet, når du vælger et nyt sprog.

1. Vælg **Gem**.

## <a name="view-system-status"></a>Vis systemstatus

Spor status for opgaver, datatab, dataeksport og flere andre vigtige produktprocesser. Gennemgå oplysningerne for at sikre, at dine aktive opgaver og processer er fuldstændige.

1. Gå til **Administration** > **System**, og vælg fanen **Status**.

   Status og behandlingsoplysninger til forskellige processer vises. Vis **navnet** på opgaven og dens tilsvarende objekt, **Status** for den seneste kørsel, og hvornår den blev **Sidst opdateret**.

1. Du kan få vist detaljerne om de sidste mange kørsler ved at vælge opgave- eller procesnavnet.

1. Hvis du vil se udviklingsdetaljer for en opgave, skal du vælge status. Ruden **Udviklingsdetaljer** vises.

   :::image type="content" source="media/system-progress-details.png" alt-text="Ruden Detaljer om systemstatus":::

1. Hvis du vil have vist statusoplysninger for alle opgaver, skal du vælge **Hele arbejdsprocessen**.

### <a name="status-definitions"></a>Statusdefinitioner

Systemet bruger følgende statusser til opgaver og processer:

|Status  |Definition  |
|---------|---------|
|Annullerede |Opgave eller proces blev annulleret af brugeren, før den blev afsluttet.   |
|Mislykket   |Der er opstået fejl i opgaver eller processer.         |
|Fejl  |Det er ikke lykkedes at udføre opgaver eller processer.  |
|Ikke startet   |Datakilde har ingen data, der er indsat endnu, eller opgaven er stadig i kladdetilstand.         |
|Forarbejdning  |Opgave eller proces er i gang.  |
|Opdaterer    |Opgave eller proces er i gang. Vælg **Opdatering** og **Annuller job** for at annullere handlingen. Hvis du stopper opdateringen af en handling eller proces, gendannes den til den seneste opdateringstilstand.       |
|Sprunget over  |Opgave eller proces er sprunget over. En eller flere af de downstream-processer, som denne opgave afhænger af, er mislykket eller er blevet sprunget over.|
|Gennemført  |Opgave eller proces blev fuldført. I forbindelse med datakilder angives det, at dataene er blevet gemt korrekt, hvis der nævnes et tidspunkt i kolonnen **Opdateret**.|
|I kø | Behandlingen sættes i kø og starter, når alle opgaver og processer i upstream er fuldført. Du kan finde flere oplysninger under [Opdater processer](#refresh-processes).|

### <a name="refresh-processes"></a>Opdater processer

Opdatering af opgaver og processer køres i overensstemmelse med [konfigureret tidsplan](schedule-refresh.md).

|Behandl  |Beskrivelse  |
|---------|---------|
|Aktivitet  |Kører manuelt (opdatering enkelt gang). Afhænger af fletteprocessen. Indsigt afhænger af behandlingen.|
|Analysesammenkædning |Kører manuelt (opdatering enkelt gang). Afhænger af segmenter.  |
|Forberedelse af analyse |Kører manuelt (opdatering enkelt gang). Afhænger af segmenter.  |
|Dataforberedelse   |Der skal køres et objekt på. Datakildeobjekter afhænger af indtagelse. Forbedrede objekter afhænger af forbedringer. Objektet Kunde afhænger af fletning.  |
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


[!INCLUDE [footer-include](includes/footer-banner.md)]
