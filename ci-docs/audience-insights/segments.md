---
title: Segmenter i målgruppeindsigt
description: Oversigt over segmenter, og hvordan de oprettes og administreres.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 740d293b21f43b50201f23fcba109318823ef3af
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978052"
---
# <a name="segments-overview"></a>Oversigter over segmenter

Med segmenter kan du gruppere dine kunder baseret på demografiske, transaktionsrelaterede eller adfærdsattributter. Du kan bruge segmenter til at målrette kampagnefremstød, salgsaktiviteter og kundesupporthandlinger for at nå dine forretningsmæssige mål.

Kundeprofiler, der matcher filtrene i en segmentdefinition, kaldes *medlemmer* af et segment. Der gælder nogle [tjenestebegrænsninger](service-limits.md).

## <a name="create-a-new-segment"></a>Oprette et nyt segment

Der er flere måder, du kan oprette et nyt segment på: 

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

- Komplekst segment med segmentgenerator: [Byg din egen](segment-builder.md#create-a-new-segment) 
- Simple segmenter med én operator: [Hurtigt segment](segment-builder.md#quick-segments) 
- AI-baserede måder at finde lignende kunder på: [Lignende kunder](find-similar-customer-segments.md) 
- AI-baserede forslag ud fra målinger eller attributter: [Foreslåede segmenter til forbedring af målingerne](suggested-segments.md) 
- Forslag baseret på aktiviteter: [Foreslåede segmenter baseret på kundeaktivitet](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

- Komplekst segment med segmentgenerator: [Byg din egen](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Administrere eksisterende segmenter

Gå til siden **Segmenter** for at få vist alle dine gemte segmenter og administrere dem.

De enkelte segmenter repræsenteres af en række, der indeholder yderligere oplysninger om segmentet.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valgt segment med rulleliste med indstillinger og tilgængelige indstillinger.":::

Følgende handlinger er tilgængelige, når du vælger et segment:

- **Vis** segmentoplysningerne, herunder tendensen for antal medlemmer, et eksempel på segmentmedlemmer.
- **Rediger** segmentet for at ændre dets egenskaber.
- **Opret en dublet** af et segment. Du kan vælge at redigere egenskaberne med det samme eller ganske enkelt gemme dubletten.
- **Opdater** segmentet, så det indeholder de seneste data.
- **Aktivér** eller **Deaktiver** segmentet. Segmenter har to mulige tilstande - aktiv og inaktiv. Disse tilstande er praktiske, når du redigerer et segment. I forbindelse med inaktive segmenter findes der en definition af segmentet, men den indeholder ikke nogen kunder endnu. Når du aktiverer et segment, ændres dets tilstand fra 'inaktiv' til "aktiv", og der starter en søgning efter de kunder, der opfylder segmentdefinitionen. Hvis der er konfigureret en [planlagt opdatering](system.md#schedule-tab), har vises **Status** for inaktive segmenter som **Sprunget over** som tegn på, at en opdatering ikke er forsøgt udført. Når et inaktivt segment aktiveres, opdateres det og inkluderes i de planlagte opdateringer.
  Du kan også bruge **Planlæg senere** i rullemenuen **Aktivér/deaktiver** til at angive fremtidig dato og klokkeslæt for aktivering og deaktivering af et bestemt segment.
- **Omdøb** segmentet.
- **Hent** listen over medlemmer som en .CSV-fil.
- **Administrer eksport** for at få vist eksportrelaterede segmenter og administrere dem. [Få mere at vide om eksporter](export-destinations.md)
- **Slet** segmentet.

## <a name="refresh-segments"></a>Opdatere segmenter

Du kan opdatere alle segmenter på én gang ved at vælge **Opdater alle** på siden **Segmenter**, eller du kan opdatere et eller flere segmenter, når du vælger dem, og vælge **Opdater** fra indstillingerne. Du kan også konfigurere en tilbagevendende opdatering i **Admin** > **System** > **Planlæg**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Eksportere segmenter

Du kan eksportere et segment fra segmentsiden eller [eksportsiden](export-destinations.md). 

1. Gå til siden **Segmenter**.

1. Vælg **Vis mere [...]** for det segment, du vil eksportere.

1. Vælg **Administrer eksport** fra rullelisten Handlinger.

1. Siden **Eksporter (forhåndsversion) for segment** åbnes. Du kan se alle konfigurerede eksporter grupperet efter, om de indeholder det aktuelle segment eller ej.

   1. Hvis du vil føje det valgte segment til en eksport, skal du **redigere** den pågældende eksport for at vælge det tilknyttede segment og derefter gemme. I miljøer for individuelle kunder kan du i stedet vælge eksporten på listen og vælge **Tilføj segment** for at opnå det samme resultat.

   1. Hvis du vil oprette en ny eksport med det valgte segment, skal du vælge **Tilføj eksport**. Du kan finde flere oplysninger om oprettelse af eksport i [Konfigurere en ny eksport](export-destinations.md#set-up-a-new-export).

1. Vælg **Tilbage** for at vende tilbage til hovedsiden for segmenter.

## <a name="view-processing-history-and-segment-members"></a>Se behandlingshistorik og segmentmedlemmer

Du kan se konsoliderede data om et segment ved at gennemgå dets detaljer.

Vælg det segment, du vil gennemgå, på siden **Segmenter**.

Den øverste del af siden indeholder en tendensgraf, der viser ændringer i medlemsantal. Peg på datapunkter for at få vist medlemsantallet på en bestemt dato.

Du kan opdatere tidsrammen i visualiseringen.

> [!div class="mx-imgBorder"]
> ![Tidsinterval for segment.](media/segment-time-range.png "Tidsinterval for segment")

Den nederste del indeholder en liste over segmentmedlemmerne.

> [!NOTE]
> Felter, der vises på denne liste, er baseret på attributterne for objekterne i dit segment.
>
>Listen er et eksempel på de matchende segmentmedlemmer og viser de første 100 poster i dit segment, så du hurtigt kan evaluere det og gennemgå dets definitioner, hvis det er nødvendigt. Hvis du vil se alle matchende poster, skal du [eksportere segmentet](export-destinations.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)] 
