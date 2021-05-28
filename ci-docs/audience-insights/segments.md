---
title: Segmenter i målgruppeindsigt
description: Oversigt over segmenter, og hvordan de oprettes og administreres.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034005"
---
# <a name="segments-overview"></a>Oversigter over segmenter

Med segmenter kan du gruppere dine kunder baseret på demografiske, transaktionsrelaterede eller adfærdsattributter. Du kan bruge segmenter til at målrette kampagnefremstød, salgsaktiviteter og kundesupporthandlinger for at nå dine forretningsmæssige mål.

Kundeprofiler, der matcher filtrene i en segmentdefinition, kaldes *medlemmer* af et segment. Der gælder nogle [tjenestebegrænsninger](service-limits.md).

## <a name="create-a-new-segment"></a>Oprette et nyt segment

Der er flere måder, du kan oprette et nyt segment på: 

- Komplekst segment med segmentgenerator: [Tomt segment](segment-builder.md#create-a-new-segment)
- Simple segmenter med én operator: [Hurtigt segment](segment-builder.md#quick-segments)
- AI-baserede måder at finde lignende kunder på: [Lignende kunder](find-similar-customer-segments.md)
- AI-baserede forslag ud fra målinger eller attributter: [Foreslåede segmenter til forbedring af målingerne](suggested-segments.md)
- Forslag baseret på aktiviteter: [Foreslåede segmenter baseret på kundeaktivitet](suggested-segments-activity.md)

## <a name="get-insights-on-existing-segments"></a>Få indsigt i eksisterende segmenter

Opdag flere oplysninger om eksisterende segmenter med [Segmentindsigt](segment-insights.md). Find ud af, hvad der adskiller to segmenter, eller hvad de har til fælles.

## <a name="find-similar-customers"></a>Find lignende kunder

Find kunder, der ligner medlemmerne af et valgt segment, ved hjælp af kunstig intelligens. Se [Lignende kunder](find-similar-customer-segments.md) for at få flere oplysninger.

## <a name="manage-existing-segments"></a>Administrere eksisterende segmenter

Gå til siden **Segmenter** for at få vist alle dine gemte segmenter og administrere dem.

De enkelte segmenter repræsenteres af en række, der indeholder yderligere oplysninger om segmentet.

> [!div class="mx-imgBorder"]
> ![Indstillinger til administration af et eksisterende segment](media/segments-selected-segment.png "Indstillinger til administration af et eksisterende segment")

Følgende handlinger er tilgængelige, når du vælger et segment:

- **Vis** segmentoplysningerne, herunder tendensen for antal medlemmer, et eksempel på segmentmedlemmer.
- **Rediger** segmentet for at ændre dets egenskaber.
- **Opret en dublet** af et segment. Du kan vælge at redigere egenskaberne med det samme eller ganske enkelt gemme dubletten.
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

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
