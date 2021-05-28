---
title: Flet objekter i datasamling
description: Flet objekter for at oprette samlede kundeprofiler.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085569"
---
# <a name="merge-entities"></a>Flet objekter

Flettefasen er den sidste fase i datasamlingsprocessen. Dens formål er at afstemme data, der er i konflikt. Af eksempler på data, der er i konflikt, kan nævnes et kundenavn, der findes i to af dine datasæt, men som vises en smule anderledes i hvert sæt ("Claus Madsen" i forhold til "Klaus Madsen") eller et telefonnummer, der adskiller sig i formatet (617-803-091X i forhold til 617803091X). Fletning af disse datapunkter, der er i konflikt, sker på attribut for attribut-basis.

:::image type="content" source="media/merge-fields-page.png" alt-text="Siden Flet i processen til datasamling, der viser en tabel med flettede felter, der definerer den samlede kundeprofil.":::

Når du har fuldført [matchfasen](match-entities.md), starter du flettefasen ved at vælge feltet **Flet** på siden **Saml**.

## <a name="review-system-recommendations"></a>Gennemgå systemanbefalinger

I **Data** > **Saml** > **Flet** skal du vælge og udelade attributter, der skal flettes i objektet med den samlede kundeprofil. Den samlede kundeprofil er resultatet af processen til samling af data. Nogle attributter flettes automatisk af systemet.

Hvis du vil have vist de attributter, der er inkluderet i en af dine automatisk flettede attributter, skal du vælge den flettede attribut under fanen **Kundefelter** i tabellen. De attributter, der udgør den flettede attribut, vises i to nye rækker under den flettede attribut.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Adskille, omdøbe, udelade og redigere flettede felter

Du kan ændre, hvordan flettede attributter skal behandles i systemet for at oprette den samlede kundeprofil. Vælg **Vis mere**, og vælg, hvad du vil ændre.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Indstillinger i rullemenuen Vis mere til at administrere flettede attributter.":::

Der er flere oplysninger i følgende afsnit.

## <a name="separate-merged-fields"></a>Adskille flettede felter

Hvis du vil adskille flettede felter, skal du søge efter attributten i tabellen. Adskilte felter vises som individuelle datapunkter i den samlede kundeprofil. 

1. Vælg det flettede felt.
  
1. Vælg **Vis flere**, og vælg **Separate felter**.
 
1. Bekræft separationen.

1. Vælg **Gem** og **Kør** for at behandle ændringerne.

## <a name="rename-merged-fields"></a>Omdøbe flettede felter

Omdøb det viste navn på flettede attributter. Du kan ikke ændre navnet på outputobjektet.

1. Vælg det flettede felt.
  
1. Vælg **Vis flere**, og vælg **Omdøb**.

1. Bekræft det ændrede viste navn. 

1. Vælg **Gem** og **Kør** for at behandle ændringerne.

## <a name="exclude-merged-fields"></a>Udelade flettede felter

Udelad en attribut fra den samlede kundeprofil. Hvis feltet bruges i andre processer, f.eks. i et segment, skal du fjerne det fra disse processer, før det udelades i kundeprofilen. 

1. Vælg det flettede felt.
  
1. Vælg **Vis flere**, og vælg **Udelad**.

1. Bekræft udeladelsen.

1. Vælg **Gem** og **Kør** for at behandle ændringerne. 

Vælg **Udeladte felter** på siden **Flet** for at se listen over alle udeladte felter. Med denne rude kan du tilføje udeladte felter igen.

## <a name="manually-combine-fields"></a>Kombinere felter manuelt

Angiv en flettet attribut manuelt. 

1. Vælg **Kombiner felter** på siden **Flet**.

1. Angiv et **Navn** og et **Navn på outputfelt**.

1. Vælg et felt, der skal tilføjes. Vælg **Tilføj felter** for at kombinere flere felter.

1. Bekræft udeladelsen.

1. Vælg **Gem** og **Kør** for at behandle ændringerne. 

## <a name="change-the-order-of-fields"></a>Ændre rækkefølgen for felter

Nogle objekter indeholder flere detaljer end andre. Hvis et objekt indeholder de nyeste data om et felt, kan du prioritere det frem for andre objekter, når du fletter værdier.

1. Vælg det flettede felt.
  
1. Vælg **Vis flere**, og vælg **Rediger**.

1. Vælg **Flyt op/ned** i ruden **Kombiner felter** for at angive rækkefølgen, eller træk og slip dem til den ønskede placering.

1. Bekræft ændringen.

1. Vælg **Gem** og **Kør** for at behandle ændringerne.

## <a name="run-your-merge"></a>Køre fletningen

Uanset om du fletter attributter manuelt eller lader systemet flette dem, kan du altid køre fletningen. Vælg **Kør** på siden **Flet** for at starte processen.

> [!div class="mx-imgBorder"]
> ![Gemme og køre datafletning](media/configure-data-merge-save-run.png "Gemme og køre datafletning")

Vælg **Kør kun fletning**, hvis du kun vil se outputtet afspejlet i det samlede kundeobjekt. Downstream-processer opdateres som [defineret i opdateringsplanen](system.md#schedule-tab).

Vælg **Kør flettede og downstream-processer** for at opdatere systemet med ændringerne. Alle processer, herunder forbedringer, segmenter og målinger, køres automatisk igen. Når alle downstream-processer er fuldført, afspejler kundeprofilerne eventuelle ændringer, du har foretaget.

Hvis du vil foretage flere ændringer og køre trinnet igen, kan du annullere en igangværende fletning. Vælg **Opdaterer...**, og vælg **Annuller job** i den siderude, der vises.

> [!TIP]
> Opgaver og processer indeholder [seks typer status](system.md#status-types). De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies). Du kan vælge status for en proces for at se statusdetaljer for hele jobbet. Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.

## <a name="next-step"></a>Næste trin

Konfigurer [aktiviteter](activities.md), [forbedring](enrichment-hub.md) eller [relationer](relationships.md) for at få mere indsigt i dine kunder.

Hvis du allerede har konfigureret aktiviteter, forbedringer eller segmenter, behandles de automatisk til at bruge de nyeste kundedata.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
