---
title: Oversigter over segmenter
description: Oversigt over segmenter, og hvordan de oprettes og administreres.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: d4de3a6af6bc7d54305a23e3fbd3cc95d464d352
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304788"
---
# <a name="segments-overview"></a>Oversigter over segmenter

Med segmenter kan du gruppere dine kunder baseret på demografiske, transaktionsrelaterede eller adfærdsattributter. Du kan bruge segmenter til at målrette kampagnefremstød, salgsaktiviteter og kundesupporthandlinger for at nå dine forretningsmæssige mål.

Kunde- eller kontaktprofiler, der matcher filtrene i en segmentdefinition, kaldes *medlemmer* af et segment. Der gælder nogle [tjenestebegrænsninger](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Opret et segment

Vælg, hvordan du vil oprette et segment på baggrund af publikum.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

- Komplekst segmenter med segmentgenerator: [Byg din egen](segment-builder.md)
- Simple segmenter med én operator: [Hurtigt segment](segment-quick.md)
- AI-baserede måder at finde lignende kunder på: [Lignende kunder](find-similar-customer-segments.md)
- AI-baserede forslag ud fra målinger eller attributter: [Foreslåede segmenter baseret på målingerne](suggested-segments.md)
- Forslag baseret på aktiviteter: [Foreslåede segmenter baseret på kundeaktivitet](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

Segment af firmaer eller segmenter af kontakter (forhåndsversion) med segmentgenerator: [Byg dit eget](segment-builder.md)

> [!NOTE]
> De fleste eksportmål kræver kontaktoplysninger i forbindelse med marketing. Opret derfor kontaktsegmenter, der kan bruges til disse eksporter.

---

## <a name="manage-existing-segments"></a>Administrere eksisterende segmenter

Gå til siden **Segmenter** for at se de segmenter, du har oprettet, deres status og tilstand, og sidste gang dataene blev opdateret. Du kan sortere listen over segmenter efter en hvilken som helst kolonne eller bruge det segment der skal håndteres.

> [!TIP]
> I B-til-B-miljøer identificerer kolonnen **Publikumstype**, om et segment er baseret på firmaer eller kontakter.

Vælg et segment for at få vist tilgængelige handlinger.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valgt segment med rulleliste med indstillinger og tilgængelige indstillinger." lightbox="media/segments-selected-segment.png":::

- [**Vis**](#view-segment-details) segmentoplysningerne, herunder tendensen for antal medlemmer, og forhåndsversion af segmentmedlemmer.
- **Hent** listen over medlemmer som en .CSV-fil.
- **Rediger** segmentet for at ændre dets egenskaber.
- **Opret en dublet** af et segment. Du kan vælge at redigere egenskaberne med det samme eller gemme dubletten.
- [**Opdater**](#refresh-segments) segmentet, så det indeholder de seneste data.
- **Aktivér** eller **Deaktiver** segmentet. Inaktive segmenter kan ikke opdateres under en [planlagt opdatering](schedule-refresh.md) og har **Status** angivet som **Sprunget over** som tegn på, at en opdatering ikke er forsøgt udført. Aktive segmenter opdateres baseret på deres type: statiske eller dynamiske.
- Gør segmenttypen **statisk** eller **dynamisk**. Statiske segmenter kan ikke opdateres manuelt. Dynamiske segmenter opdateres automatisk under en systemopdatering.
- [**Find lignende kunder**](find-similar-customer-segments.md) fra segmentet.
- **Omdøb** segmentet.
- **Kode** til [administration af koder](work-with-tags-columns.md#manage-tags) for segmentet.
- [**Administrer eksport**](#export-segments) for at få vist eksportrelaterede segmenter og administrere dem. [Få mere at vide om eksporter](export-destinations.md)
- **Slet** segmentet.
- **Kolonner** til [tilpasning af de kolonner](work-with-tags-columns.md#customize-columns), der vises.
- **Filtrer** til [filter på koder](work-with-tags-columns.md#filter-on-tags).
- **Søgenavn** til at søge efter segmentnavn.

## <a name="view-segment-details"></a>Få vist oplysninger om et segment

Vælg et segment på siden **Segmenter** for at få vist behandlingsoversigten og medlemmerne af segmentet.

Den øverste del af siden indeholder en tendensgraf, der viser ændringer i medlemsantal. Peg på datapunkter for at få vist medlemsantallet på en bestemt dato. Ændre tidsrammen i visualiseringen.

:::image type="content" source="media/segment-time-range.png" alt-text="Tidsinterval for segment.":::

Den nederste del indeholder en liste over segmentmedlemmerne.

> [!NOTE]
> Felter, der vises på denne liste, er baseret på attributterne for objekterne i dit segment.
>
> Listen er et eksempel på de matchende segmentmedlemmer og viser de første 100 poster i dit segment, så du hurtigt kan evaluere det og gennemgå dets definitioner, hvis det er nødvendigt. Hvis du vil se alle matchende poster, skal du vælge **Se mere**, der åbner siden [**Objekter**](entities.md) eller [eksporterer segmentet](export-destinations.md).

## <a name="refresh-segments"></a>Opdatere segmenter

Segmenter kan opdateres automatisk i en automatisk planlægning eller opdateres manuelt efter behov. Hvis du manuelt vil opdatere et eller flere segmenter, skal du vælge dem og vælge **Opdater**.

Hvis du vil [planlægge en automatisk opdatering](schedule-refresh.md), skal du gå til **Administrator** > **System** > **Plan**. Der gælder følgende regler:

- Alle segmenter med typen **Dynamisk** eller **Udvidelse** opdateres automatisk med den indstillede hyppighed. Når opdateringen er fuldført, fortæller **Status**, om der var problemer med opdatering af segmentet. I det **senest opdaterede felt** vises et tidsstempel for den seneste vellykkede opdatering. Hvis der opstår en fejl, skal du vælge fejlen for at få vist detaljer om, hvad der er sket.
- Segmenter med typen **Statisk** opdateres *ikke* automatisk. I det **senest opdaterede** felt vises et tidsstempel for det seneste tidspunkt, hvor de statiske segmenter blev kørt eller opdateret manuelt.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Eksportere segmenter

Eksportér segmenter til andre apps for yderligere at bruge dataene. Eksportere et segment fra segmentsiden eller [eksportsiden](export-destinations.md).

1. Vælg det segment, du vil eksportere, på siden **Segmenter**.

1. Vælg **Administrer eksport**. Siden **Eksporter (forhåndsversion) for segment** åbnes. Du kan se alle konfigurerede eksporter grupperet efter, om de indeholder det aktuelle segment eller ej.

   1. Hvis du vil føje det valgte segment til en eksport, skal du **redigere** den pågældende eksport for at vælge det tilknyttede segment og derefter gemme. I miljøer for individuelle kunder kan du i stedet vælge eksporten på listen og vælge **Tilføj segment** for at opnå det samme resultat.

   1. Hvis du vil oprette en ny eksport med det valgte segment, skal du vælge **Tilføj eksport**. Du kan finde flere oplysninger om oprettelse af eksport i [Konfigurere en ny eksport](export-destinations.md#set-up-a-new-export).

1. Vælg **Tilbage** for at vende tilbage til hovedsiden for segmenter.

## <a name="track-usage-of-a-segment"></a>Spore brugen af et segment

Hvis du bruger segmenter i apps, som er baseret på den samme Microsoft Dataverse-organisation, der er knyttet til Customer Insights, kan du spore brugen af et segment. I forbindelse med [Customer Insights-segmenter, der bruges i kundekampagneforløb i Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), informerer systemet dig om brugen af dette segment.

Når du redigerer et segment, der bruges i Customer Insights-miljøet eller i et kundekampagneforløb i Marketing, giver et banner i [segmentgeneratoren](segment-builder.md) dig besked om afhængighederne. Du kan inspicere oplysningerne om afhængigheder direkte fra banneret eller ved at vælge **Brug** i segmentgeneratoren.

I ruden **Segmentbrug** vises detaljerne om brugen af dette segment i Dataverse-baserede apps. I forbindelse med segmenter, der bruges i kundekampagneforløb, kan du finde et link til at inspicere forløbet i Marketing, hvor dette segment bruges. Hvis du har adgangstilladelse til appen Marketing, kan du finde flere oplysninger der.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Sideruden med oplysninger om brugen af segmentet i segmentgeneratoren.":::

Systemet giver dig besked om brugen af et sporet segment, når du forsøger at slette det. Hvis det segment, du vil slette, bruges i et kundekampagneforløb i Marketing, standser forløbet for alle brugere i dette segment. Hvis forløbet er en del af en marketingkampagne, påvirker sletningen selve kampagnen. Du kan dog stadig slette segmentet på trods af advarslerne.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialogboksen til bekræftelse af sletning af et segment, når der bruges et segment i et Dataverse-program.":::

### <a name="supported-apps"></a>Understøttede apps

Brug spores i øjeblikket i følgende Dataverse-baserede apps:

- [Kundekampagneforløb i Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
