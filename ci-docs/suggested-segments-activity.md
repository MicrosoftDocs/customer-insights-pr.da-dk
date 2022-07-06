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
ms.openlocfilehash: e98aea3b3f3a2c4788346deab1b7ad7d1167110d
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054333"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Foreslåede segmenter baseret på aktivitetsdata (forhåndsversion).

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
Hvis du arbejder inden for sundhedssektoren med folkesundhed, og dit mål er at minimere udgifterne for de enkelte patienter. Det kan du gøre ved at reducere antallet af tilbagevendende besøg ved at yde den bedst mulige behandling på så få besøg som muligt. I dette tilfælde er dit mål at holde besøgshyppigheden lav og minimere tilbagevendende omkostninger for patienterne. Du kan også identificere de segmenter af patienter, der ofte har aftaler, og høje tilbagevendende omkostninger og analysere disse sager for at forbedre behandlingen for den enkelte person. 

## <a name="required-data"></a>Påkrævede data

Forslag oprettes på baggrund af de valgte inputdata. 

- Kundeprofiler: Alle kunder eller medlemmer af et bestemt segment. 

- Tidsperiode: Sidste måned, sidste år eller en brugerdefineret tidsramme.

- Aktivitetstype: køb, detailtransaktioner, onlinetransaktioner, kundesupportsager, abonnementer osv.  

- Objekt i Customer Insights, der indeholder aktivitetsdataene: Objektet UnifiedActivity eller objektet for en bestemt aktivitet. 

- Dimensioner, der skal inkluderes: seneste dato, hyppighed eller pengebeløb, afhængigt af virksomhedens behov.

## <a name="generate-suggested-segments"></a>Generér foreslåede målgrupper

1. Gå til **Segmenter**

1. Vælg fanen **Forslag (prøveversion)**.

1. Vælg **Søg efter nye forslag**, og vælg **Se eller forudse kundeadfærd**. Vælg **Start** for at køre den styrede oplevelse.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Første trin i guiden Konfiguration for et foreslået segment baseret på aktivitet.":::

1. Angiv de nødvendige inputdata, og vælg **Næste** for at fortsætte.

   - Vælg kunder: Medtag alle kunder eller et bestemt segment.
   - Vælg aktivitet: Vælg aktivitetstypen og de objekter, der beskriver aktiviteten.
   - Præferencer: Angiv den tidsperiode, der skal overvejes, faktorerne til forslag, og tilknyt attributterne.

1. Gennemse dit input, og vælg **Kør** for at køre modellen og oprette forslag.

1. Afhængigt af antallet af kundeprofiler og valgte aktiviteter kan det tage et par minutter at fuldføre. 

Når du har genereret forslagene, kan du filtrere dem efter den dimension eller værdi, du er mest interesseret i. 

## <a name="view-details-of-a-suggested-segment"></a>Vise oplysninger om foreslået segment

Når forslagene er genereret, vises de i afsnittet **Aktivitetsbaserede forslag**, som vises i **Segmenter** > **Forslag (forhåndsversion)**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Udvidet siderude, der viser detaljerede data for et foreslået segment.":::

Vælg **Se forslag** på et foreslået segment for at få vist detaljerne for det pågældende segment. Sideruden indeholder detaljer som omfanget af de enkelte dimensioner i sammenligning med målgruppen. Der fremhæves også antallet af potentielle medlemmer i segmentet og den tilsvarende procentdel af de samlede kunder. Hvis du vil bevare forslag som et segment, skal du vælge **Opret segment**.    

## <a name="save-a-suggestion-as-a-segment"></a>Gemme et forslag som et segment

1. Gå til **Segmenter** > **Forslag (prøveversion)**.

1. Vælg det segment, du vil gemme. 

1. Vælg **Opret segment** i sideruden. 

1. Når du har gemt segmentet, vises det på listen over segmenter under fanen **Alle segmenter**. Det kan nu [opdateres eller slettes på samme måde som et hvilket som helst andet segment](segments.md). Du kan ikke redigere detaljer om segmentet. Du kan dog ændre inputkriterierne for forslagene og oprette forskellige forslag.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Opdatere eller redigere et sæt forslag

1. Gå til **Segmenter** > **Forslag (forhåndsversion)**, og søg efter segmentet i sektionen **Aktivitetsbaserede forslag**.

1. Vælg **Opdater forslag** for at opdatere forslagene, mens du bevarer konfigurerede attributter. Du kan også vælge **Rediger forslag** for at ændre de konfigurerede attributter. Systemet kører processen igen, opretter segmentforslag baseret på de nyeste data og erstatter de aktuelle forslag.

[!INCLUDE [footer-include](includes/footer-banner.md)]
