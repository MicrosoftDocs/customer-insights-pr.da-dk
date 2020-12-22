---
title: Flet objekter i datasamling
description: Flet objekter for at oprette samlede kundeprofiler.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405448"
---
# <a name="merge-entities"></a>Flet objekter

Flettefasen er den sidste fase i datasamlingsprocessen. Dens formål er at afstemme data, der er i konflikt. Af eksempler på data, der er i konflikt, kan nævnes et kundenavn, der findes i to af dine datasæt, men som vises en smule anderledes i hvert sæt ("Claus Madsen" i forhold til "Klaus Madsen") eller et telefonnummer, der adskiller sig i formatet (617-803-091X i forhold til 617803091X). Fletning af disse datapunkter, der er i konflikt, sker på attribut for attribut-basis.

Når du har fuldført [matchfasen](match-entities.md), starter du flettefasen ved at vælge feltet **Flet** på siden **Saml**.

## <a name="review-system-recommendations"></a>Gennemgå systemanbefalinger

På siden **Flet** vælger og udelader du de attributter, der skal flettes i det samlede kundeprofilobjekt (resultatet af konfigurationsprocessen). Nogle attributter flettes automatisk af systemet.

### <a name="view-merged-attributes"></a>Se flettede attributter

Hvis du vil have vist de attributter, der er inkluderet i en af de automatisk flettede attributter, skal du vælge den flettede attribut. De to attributter, der udgør den flettede attribut, vises i to nye rækker under den flettede attribut.

> [!div class="mx-imgBorder"]
> ![Vælge flettet attribut](media/configure-data-merge-profile-attributes.png "Vælge flettet attribut")

### <a name="separate-merged-attributes"></a>Adskille flettede attributter

Hvis du vil adskille eller ophæve fletning af en af de automatisk flettede attributter, skal du finde attributten i tabellen **Profilattributter**.

1. Vælg ellipseknappen ( ... ).
  
2. Vælg **Separate felter** på rullelisten.

### <a name="remove-merged-attributes"></a>Fjerne flettede attributter

Hvis du vil udelade en attribut fra det endelige kundeprofilobjekt , skal du finde den i tabellen **Profilattributter**.

1. Vælg ellipseknappen ( ... ).
  
2. Vælg **Flet ikke** på rullelisten.

   Attributten flyttes til sektionen **Fjernet fra kundepost**.

## <a name="manually-add-a-merged-attribute"></a>Manuelt tilføje en flettet attribut

Hvis du vil tilføje en flettet attribut, skal du gå til siden **Flet**.

1. Vælg **Tilføj flettet attribut**.

2. Angiv et **Navn**, der identificerer den på siden **Flet** senere.

3. Du kan også angive et **Vist navn**, der skal vises i det samlede kundeprofilobjekt.

4. Konfigurer **Vælg duplikerede attributter** for at vælge de attributter, du vil flette fra de matchede objekter. Du kan også søge efter attributter.

5. Angiv **Ranger efter vigtighed** for at prioritere den ene attribut over de andre. Hvis objektet *WebAccountCSV* f.eks. indeholder de mest præcise data om attributten *Fulde navn*, kan du prioritere dette objekt højere end *ContactCSV* ved at vælge *WebAccountCSV*. Resultatet medfører, at *WebAccountCSV* flyttes til første prioritet, mens *ContactCSV* flyttes til anden prioritet, når der udtrækkes værdier til attributten *Fulde navn*.

## <a name="run-your-merge"></a>Køre fletningen

Uanset om du fletter attributter manuelt eller lader systemet flette dem, kan du altid køre fletningen. Vælg **Kør** på siden **Flet** for at starte processen.

> [!div class="mx-imgBorder"]
> ![Gemme og køre datafletning](media/configure-data-merge-save-run.png "Gemme og køre datafletning")

Hvis du vil foretage yderligere ændringer og køre trinnet igen, kan du annullere en igangværende fletning. Vælg **Opdaterer...**, og vælg **Annuller job** i den siderude, der vises.

Når teksten **Opdaterer ...** er ændret til **Gennemført**, er fletningen fuldført, og uoverensstemmelser i dine data i henhold til de politikker, du har defineret, er løst. Flettede og ikke-flettede attributter inkluderes i objektet for den samlede profil. Udeladte attributter inkluderes ikke i objektet for den samlede profil.

Hvis det ikke var første gang, du fuldførte en fletning, køres alle downstream-processer, herunder forbedring, segmentering og målinger, automatisk. Når alle downstream-processer er kørt igen, afspejler kundeprofilerne eventuelle ændringer, du har foretaget.

> [!TIP]
> Opgaver og processer indeholder [seks typer status](system.md#status-types). De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies). Du kan vælge status for en proces for at se statusdetaljer for hele jobbet. Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.

## <a name="next-step"></a>Næste trin

Konfigurer [aktiviteter](activities.md), [forbedring](enrichment-microsoft-graph.md) eller [relationer](relationships.md) for at få mere indsigt i dine kunder.

Hvis du allerede har konfigureret aktiviteter, forbedring eller relationer, eller hvis du har defineret segmenter, behandles de automatisk, så de anvender de nyeste kundedata.


