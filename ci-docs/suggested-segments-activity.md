---
title: Foreslåede segmenter baseret på aktivitet (forhåndsversion)
description: Lad maskinel indlæring hjælpe dig med at finde nye interessante segmenter baseret på kundeaktivitet.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170582"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Foreslåede segmenter baseret på aktivitet (forhåndsversion)

Opdag interessante segmenter af kunder, der er baseret på kundeaktivitetsdata, som er indtaget i Customer Insights. Eksempler på aktivitetsdata er transaktioner, varighed af supportopkald, indkøb eller returvarer. For at foreslå segmenter analyseres aktivitetsdata for nyhed, hyppighed og pengeværdi (eller varighed). Du kan også oprette [foreslåede segmenter for at forbedre målingen eller få en bedre forståelse af, hvad der påvirker en attribut](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Fanen Foreslåede segmenter, der viser segmentforslag til aktivitetsbaserede og attributbaserede segmenter.":::

## <a name="categorize-customers-by-activity"></a>Kategorisere kunder efter aktivitet

Med [aktivitetsdata](activities.md) tilgængelige i Customer Insights kan vi generere forslag, der repræsenterer kundegrupper:

- mest aktive kunder 
- kunder, der har foretaget de fleste køb 
- kunder, der genererede den største omsætning 
- kunder, der ikke har været aktive for nylig 
- kunder, der ofte interagerer med din virksomhed  

Hvis du har en detailvirksomhed, kan du finde ud af, hvilke kunder der genererer den største omsætning, og belønne dem med en værdikupon. Du kan også identificere lejlighedsvise kunder og tilbyde dem at tilmelde sig et belønningsprogram, så de besøger din virksomhed oftere.
Hvis du yder offentlig behandling, og dit mål er at minimere udgifterne for de enkelte besøg, kan du prøve at reducere tilbagevendende besøg ved at yde den bedst mulige behandling ved så få besøg som muligt. I dette tilfælde er dit mål at holde besøgshyppigheden lav og minimere tilbagevendende omkostninger for patienterne. Du kan også identificere de segmenter af patienter, der ofte har aftaler, og høje tilbagevendende omkostninger og analysere disse sager for at forbedre behandlingen for den enkelte person.

## <a name="required-data"></a>Påkrævede data

Forslag oprettes på baggrund af de valgte inputdata.

- Kundeprofiler: Alle kunder eller medlemmer af et bestemt segment.

- Tidsperiode: Sidste måned, sidste år eller en brugerdefineret tidsramme.

- Aktivitetstype: køb, detailtransaktioner, onlinetransaktioner, kundesupportsager, abonnementer osv.  

- Objekt i Customer Insights, der indeholder aktivitetsdataene: Objektet UnifiedActivity eller objektet for en bestemt aktivitet.

- Dimensioner, der skal inkluderes: seneste dato, hyppighed eller pengebeløb, afhængigt af virksomhedens behov.

## <a name="generate-suggested-segments"></a>Generér foreslåede målgrupper

1. Gå til **Segmenter**, og vælg fanen **Forslag (forhåndsversion)**.

1. Vælg **Søg efter nye forslag**, og vælg **Se eller forudse kundeadfærd**. Vælg **Start**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Første trin i guiden Konfiguration for et foreslået segment baseret på aktivitet.":::

1. Angiv de nødvendige inputdata, og vælg **Næste**.

   - Vælg kunder: Medtag alle kunder eller et bestemt segment.
   - Vælg aktivitet: Vælg aktivitetstypen og de objekter, der beskriver aktiviteten.
   - Præferencer: Angiv den tidsperiode, der skal overvejes, faktorerne til forslag, og tilknyt attributterne.

1. Gennemse dit input, og vælg **Kør** for at køre modellen og oprette forslag.

Afhængigt af antallet af kundeprofiler og valgte aktiviteter kan det tage et par minutter at fuldføre.

Når du har genereret forslagene, kan du filtrere dem efter den dimension eller værdi, du er mest interesseret i.

## <a name="manage-suggested-segments"></a>Administrere foreslåede segmenter

Gå til **Segmenter**, og vælg fanen **Forslag (forhåndsversion)**. Vælg et foreslået segment i sektionen i **Aktivitetsbaserede forslag** for at få vist tilgængelige handlinger.

- **Se forslag** for at se detaljer til segmentet som omfanget af de enkelte dimensioner i sammenligning med målgruppen. Der fremhæves også antallet af potentielle medlemmer i segmentet og den tilsvarende procentdel af de samlede kunder.
- **Opret segment** for at gemme det foreslåede som et segment. Den vises under fanen **Alle segmenter** og kan [opdateres eller slettes](segments.md). Du kan ikke redigere detaljer om segmentet. Du kan dog ændre inputkriterierne for forslagene og oprette forskellige forslag.
- **Rediger forslag** for at tilpasse de konfigurerede attributter, som erstatter de aktuelle forslag.
- **Opdater forslag** for at opdatere forslagene, mens du bevarer konfigurerede attributter.

[!INCLUDE [footer-include](includes/footer-banner.md)]
