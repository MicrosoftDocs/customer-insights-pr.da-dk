---
title: Oprette og administrere segmenter
description: Opret segmenter med kunder for at gruppere dem på baggrund af forskellige attributter.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270349"
---
# <a name="create-and-manage-segments"></a>Oprette og administrere segmenter

Med segmenter kan du gruppere dine kunder baseret på demografiske, transaktionsrelaterede eller adfærdsattributter. Du kan bruge segmenter til at målrette kampagnefremstød, salgsaktiviteter og kundesupporthandlinger for at nå dine forretningsmæssige mål.

Du kan definere komplekse filtre for objektet Kundeprofil og dets relaterede objekter. Hvert enkelt segment vil efter behandling oprette et sæt kundeposter, som du kan eksportere og udføre handlinger på. Der gælder nogle [tjenestebegrænsninger](service-limits.md).

Medmindre andet er angivet, er alle segmenter **Dynamic-segmenter**, som opdateres med en tilbagevendende plan.

I følgende eksempel vises segmenteringsfunktionen. Vi har defineret et segment for kunder, der har bestilt mindst $500 varer over de seneste 90 dage, *og* som har været en del af et kundeserviceopkald, der blev eskaleret.

> [!div class="mx-imgBorder"]
> ![Flere grupper](media/segmentation-group1-2.png "Flere grupper")

## <a name="create-a-new-segment"></a>Oprette et nyt segment

Segmenter administreres på siden **Segmenter**.

1. Gå siden **Segmenter** i målgruppen Insights.

2. Vælg **Ny** > **Tomt segment**.

3. Vælg en segmenttype i ruden **Nyt segment**, og angiv et **Navn**.

   Du kan også angive et vist navn og en beskrivelse, der hjælper med at identificere segmentet.

4. Vælg **Næste** for at gå til siden **Segmentgenerator**, hvor du definerer en gruppe. En gruppe er et sæt kunder.

5. Vælg det objekt, der indeholder den attribut, du vil segmentere efter.

6. Vælg den attribut, der skal segmenteres efter. Denne attribut kan have en af fire værdityper: numerisk, streng, dato eller boolesk.

7. Vælg en operator og en værdi for den valgte attribut.

   > [!div class="mx-imgBorder"]
   > ![Brugerdefineret gruppefilter](media/customer-group-numbers.png "Kundegruppefilter")

   |Antal |Definition  |
   |---------|---------|
   |1     |Entity          |
   |2     |Attribut          |
   |3    |Operatør         |
   |4    |Værdi         |

8. Hvis objektet er knyttet til det samlede kundeobjekt via [Relationer](relationships.md), skal du definere relationsstien for at oprette et gyldigt segment. Tilføj objekterne fra relationsstien, indtil du kan vælge objektet **Kunde: CustomerInsights** på rullelisten. Vælg derefter **Alle poster** for hver betingelse.

   > [!div class="mx-imgBorder"]
   > ![Relationsstien under oprettelse af segmenter](media/segments-multiple-relationships.png "Relationsstien under oprettelse af segmenter")

9. Vælg **Gem** for at gemme dit segment. Dit segment gemmes og behandles, hvis alle krav valideres. Ellers gemmes det som en kladde.

10. Vælg **Tilbage til segmenter** for at gå tilbage til siden **Segmenter**.

## <a name="manage-existing-segments"></a>Administrere eksisterende segmenter

På siden **Segmenter** kan du få vist alle gemte segmenter og administrere dem.

De enkelte segmenter repræsenteres af en række, der indeholder yderligere oplysninger om segmentet.

Du kan sortere segmenterne i en kolonne ved at markere kolonneoverskriften.

Brug feltet **Søg** i øverste højre hjørne til at filtrere segmenterne.

> [!div class="mx-imgBorder"]
> ![Indstillinger til administration af et eksisterende segment](media/segments-selected-segment.png "Indstillinger til administration af et eksisterende segment")

Følgende handlinger er tilgængelige, når du vælger et segment:

- **Vis** segmentoplysningerne, herunder tendensen for antal medlemmer, et eksempel på segmentmedlemmer.
- **Rediger** segmentet for at ændre dets egenskaber.
- **Opdater** segmentet, så det indeholder de seneste data.
- **Aktivér** eller **Deaktiver** segmentet. Segmenter har to mulige tilstande - aktiv og inaktiv. Disse tilstande er praktiske, når du redigerer et segment. I forbindelse med inaktive segmenter findes der en definition af segmentet, men den indeholder ikke nogen kunder endnu. Når du aktiverer et segment, ændres dets tilstand fra 'inaktiv' til "aktiv", og der starter en søgning efter de kunder, der opfylder segmentdefinitionen. Hvis der er konfigureret en [planlagt opdatering](system.md#schedule-tab), har vises **Status** for inaktive segmenter som **Sprunget over** som tegn på, at en opdatering ikke er forsøgt udført. Når et inaktivt segment aktiveres, opdateres det og inkluderes i de planlagte opdateringer.
  Du kan også bruge **Planlæg senere** i rullemenuen **Aktivér/deaktiver** til at angive fremtidig dato og klokkeslæt for aktivering og deaktivering af et bestemt segment.
- **Omdøb** segmentet.
- **Hent** listen over medlemmer som en .CSV-fil.
- **Føj til**-indstillingen sender listen over kunde-id'er i segmentet til behandling i et andet program.
- **Slet** segmentet.

## <a name="refresh-segments"></a>Opdatere segmenter

Du kan opdatere alle segmenter på én gang ved at vælge **Opdater alle** på siden **Segmenter**, eller du kan opdatere et eller flere segmenter, når du vælger dem, og vælge **Opdater** fra indstillingerne. Du kan også konfigurere en tilbagevendende opdatering i **Admin** > **System** > **Planlæg**.

> [!TIP]
> Opgaver og processer indeholder [seks typer status](system.md#status-types). De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies). Du kan vælge status for en proces for at se statusdetaljer for hele jobbet. Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.

## <a name="download-and-export-segments"></a>Hente og eksportere segmenter

Du kan hente dine segmenter i en CSV-fil eller eksportere dem til Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Overføre segmenter til en CSV-fil

1. Gå siden **Segmenter** i målgruppen Insights.

2. Vælg ellipsen i et specifikt segments felt.

3. Vælg **Download som CSV** på rullelisten med handlinger.

### <a name="export-segments-to-dynamics-365-sales"></a>Eksportér segmenter til Dynamics 365 Sales

Før du eksporterer segmenter til Dynamics 365 Sales, skal en administrator [oprette eksportdestinationen](export-destinations.md) til Dynamics 365 Sales.

1. Gå siden **Segmenter** i målgruppen Insights.

2. Vælg ellipsen i et specifikt segments felt.

3. Vælg **Føj til** på rullelisten over handlinger, og vælg den eksportdestination, som du vil sende dataene til.

## <a name="draft-mode-for-segments"></a>Kladdetilstand for segmenter

Hvis ikke alle krav til behandling af et segment er opfyldt, kan du gemme segmentet som en kladde og få adgang til det fra siden **Segmenter**.

Dataene gemmes som et inaktivt segment og kan ikke aktiveres, før det er gyldigt.

## <a name="add-more-conditions-to-a-group"></a>Føje flere betingelser til en gruppe

Hvis du vil føje flere betingelser til en gruppe, kan du bruge to logiske operatorer:

- **OG**-operator: Begge betingelser skal overholdes som en del af segmenteringsprocessen. Denne indstilling er mest nyttig, når du definerer betingelser på tværs af forskellige objekter.

- **ELLER**-operator: Den ene eller anden betingelse skal overholdes som en del af segmenteringsprocessen. Denne indstilling er mest nyttig, når du definerer flere betingelser for det samme objekt.

   > [!div class="mx-imgBorder"]
   > ![ELLER-operator, hvor en af betingelserne skal overholdes](media/segmentation-either-condition.png "ELLER-operator, hvor en af betingelserne skal overholdes")

Det er aktuelt muligt at indlejre en **ELLER**-operator under en **OG**-operator, men ikke den anden vej rundt.

## <a name="combine-multiple-groups"></a>Kombinere flere grupper

Hver gruppe producerer et bestemt sæt kunder. Du kan kombinere disse grupper, så de inkluderer de kunder, der er nødvendige for din virksomhedscase.

1. Gå til siden **Segmenter**, og vælg et segment i målgruppen Insights.

2. Vælg **Tilføj gruppe**.

   > [!div class="mx-imgBorder"]
   > ![Tilføje kundegruppe](media/customer-group-add-group.png "Tilføje kundegruppe")

3. Vælg en af følgende sæt operatorer: **Foreningsmængde**, **Overlapning** eller **Undtagen**.

   > [!div class="mx-imgBorder"]
   > ![Tilføje foreningsmængde af kundegruppe](media/customer-group-union.png "Tilføje foreningsmængde af kundegruppe")

   Vælg en sætoperator for at definere en ny gruppe. Gem forskellige grupper for at bestemme, hvilke data der bliver bevaret:

   - **Foreningsmængde** forener de to grupper.

   - **Overlapning** overlapper de to grupper. Kun data, der *er fælles* for begge grupper, bevares i den samlede gruppe.

   - **Undtagen** kombinerer de to grupper. Kun data i gruppe A, der *ikke er fælles* med data i gruppe B, bevares.

## <a name="view-processing-history-and-segment-members"></a>Se behandlingshistorik og segmentmedlemmer

Du kan se konsoliderede data om et segment ved at gennemgå dets detaljer.

Vælg det segment, du vil gennemgå, på siden **Segmenter**.

Den øverste del af siden indeholder en tendensgraf, der viser ændringer i medlemsantal. Peg på datapunkter for at få vist medlemsantallet på en bestemt dato.

Du kan opdatere tidsrammen i visualiseringen.

> [!div class="mx-imgBorder"]
> ![Tidsinterval for segment](media/segment-time-range.png "Tidsinterval for segment")

Den nederste del indeholder en liste over segmentmedlemmerne.

> [!NOTE]
> Felter, der vises på denne liste, er baseret på attributterne for objekterne i dit segment.
>
>Listen er et eksempel på de matchende segmentmedlemmer og viser de første 100 poster i dit segment, så du hurtigt kan evaluere det og gennemgå dets definitioner, hvis det er nødvendigt. Hvis du vil se alle matchende poster, skal du [eksportere segmentet](export-destinations.md).

## <a name="quick-segments"></a>Hurtige segmenter

Ud over segmentbyggeren er der en anden vej til at oprette segmenter. Hurtige segmenter giver dig mulighed for hurtigt at opbygge simple segmenter med en enkelt operator og med øjeblikkelig indsigt.

1. På siden **Segmenter** skal du vælge **Nyt** > **Opret hurtigt fra**.

   - Vælg indstillingen **Profiler** for at oprette et segment, der er baseret på det samlede kundeobjekt.
   - Vælg indstillingen **Målinger** for at oprette et segment omkring de enkelte kundeattributtyper af målinger, du tidligere har oprettet på siden **Målinger**.
   - Vælg indstillingen **Intelligens** for at oprette en segment omkring en af de outputenheder, du har oprettet ved hjælp af funktionerne **Forudsigelser** eller **Brugerdefinerede modeller**.

2. Vælg en attribut på rullelisten **Felt** i dialogboksen **Nyt hurtigt segment**.

3. Der gives yderligere indsigt i systemet, som kan hjælpe dig med at oprette bedre segmenter af dine kunder.
   - I forbindelse med kategoriske felter vises de 10 bedste kundeantal. Vælg en **Værdi**, og vælg **Gennemse**.

   - I forbindelse med en numerisk attribut viser systemet, hvilken attributværdi der er omfattet af hver enkelt kundes percentil. Vælg en **Operator** og en **Værdi**, og vælg derefter **Gennemse**.

4. Systemet vil give dig en **Anslået segmentstørrelse**. Du kan vælge, om du vil oprette det segment, du har defineret, eller først vil gå til det igen for at få en anden segmentstørrelse.

    > [!div class="mx-imgBorder"]
    > ![Navn og estimering for et hurtigt segment](media/quick-segment-name.png "Navn og estimering for et hurtigt segment")

5. Angiv et **Navn** til dit segment. Angiv eventuelt et **Vist navn**.

6. Vælg **Gem** for at oprette dit segment.

7. Når segmentet er færdigbehandlet, kan du se det på samme måde som andre segmenter, du har oprettet.

I forbindelse med følgende situationer anbefaler vi, at du bruger segmentgeneratoren i stedet for de anbefalede segmentfunktioner:

- Oprette segmenter med filtre på kategoriske felter, hvor operatoren er anderledes end operatoren **Er**
- Oprette segmenter med filtre på numeriske felter, hvor operatoren er forskellig fra operatorerne **Mellem**, **Større end** og **Mindre end**
- Oprette segmenter med filtre i datotypefelter

## <a name="next-steps"></a>Næste trin

[Eksportere et segment](export-destinations.md) og udforske [kundekort](customer-card-add-in.md) og [connectorer](export-power-bi.md) for at få indsigt i kundeniveauet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]