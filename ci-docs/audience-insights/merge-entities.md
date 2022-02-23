---
title: Flet objekter i datasamling
description: Flet objekter for at oprette samlede kundeprofiler.
ms.date: 01/28/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-merge
ms.openlocfilehash: eb08ab38d23bf22a17896b63c93e6821431b002a
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046556"
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

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Indstillinger i rullemenuen Vis flere for at administrere flettede attributter.":::

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

1. Vælg et flettet felt.
  
1. Vælg **Vis flere**, og vælg **Udelad**.

1. Bekræft udeladelsen.

1. Vælg **Gem** og **Kør** for at behandle ændringerne. 

Vælg **Udeladte felter** på siden **Flet** for at se listen over alle udeladte felter. Med denne rude kan du tilføje udeladte felter igen.

## <a name="edit-a-merged-field"></a>Redigere et flettet felt

1.  Vælg et flettet felt.

1.  Vælg **Vis flere**, og vælg **Rediger**.

1.  Angiv, hvordan felterne skal kombineres eller flettes fra en af tre indstillinger:
    - **Betydning**: Identificerer vinderværdien på baggrund af den rangordnede betydning, der er angivet for de deltagende felter. Dette er standardfletteindstillingen. Vælg **Flyt op/ned** for at angive prioritetsranglisten.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Indstillingen Prioritet i dialogboksen med brevfletningsfelter."::: 
    - **Nyeste**: Identificerer vinderværdien baseret på den mest aktuelle. Kræver en dato eller et numerisk felt for alle deltagende objekter i omfanget af brevfletningsfelterne for at definere rekursen.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Indstillingen Nyhed i dialogboksen med brevfletningsfelter.":::
    - **Mindst nyeste**: Identificerer vinderværdien baseret på den mindst aktuelle. Kræver en dato eller et numerisk felt for alle deltagende objekter i omfanget af brevfletningsfelterne for at definere rekursen.

1.  Du kan tilføje flere felter for at deltage i fletteprocessen.

1.  Du kan omdøbe det flettede felt.

1. Vælg **Fuldført** for at anvende dine ændringer.

1. Vælg **Gem** og **Kør** for at behandle ændringerne. 

## <a name="combine-fields-manually"></a>Kombiner felter manuelt

Angiv en flettet attribut manuelt.

1. Vælg **Kombiner** på siden **Flette**.

1. Vælg indstillingen **Felter**.

1. Angiv vinderpolitik for fletning i rullelisten **Kombiner felter efter**.

1. Vælg et felt, der skal tilføjes. Vælg **Tilføj felter** for at kombinere flere felter.

1. Angiv et **Navn** og et **Navn på outputfelt**.

1. Vælg **Fuldført** for at anvende ændringerne.

1. Vælg **Gem** og **Kør** for at behandle ændringerne. 

## <a name="combine-a-group-of-fields"></a>Kombiner en gruppe af felter

Behandle en gruppe felter som en enkelt enhed. Hvis f.eks. posterne indeholder felterne Adresse1, Adresse2, By, Land og Postnr. Vi vil højst sandsynligt ikke flette adresse2 i en anden post og tænke på, at det ville gøre dataene mere fuldstændige

1. Vælg **Kombiner** på siden **Flette**.

1. Vælg indstillingen **Gruppe af felter**.

1. Angiv vinderpolitik for fletning i rullelisten **Inddel grupper efter**.

1. Vælg **Tilføj**, og vælg, om du vil føje flere felter eller flere grupper til felterne.

1. Angiv et **Navn** og et **Outputnavn** for hvert samlet felt.

1. Angiv et **Navn** til gruppen af felter. 

1. Vælg **Fuldført** for at anvende ændringerne.

1. Vælg **Gem** og **Kør** for at behandle ændringerne.

## <a name="change-the-order-of-fields"></a>Ændre rækkefølgen for felter

Nogle objekter indeholder flere detaljer end andre. Hvis et objekt indeholder de nyeste data om et felt, kan du prioritere det frem for andre objekter, når du fletter værdier.

1. Vælg det flettede felt.
  
1. Vælg **Vis flere**, og vælg **Rediger**.

1. Vælg **Flyt op/ned** i ruden **Kombiner felter** for at angive rækkefølgen, eller træk og slip dem til den ønskede placering.

1. Bekræft ændringen.

1. Vælg **Gem** og **Kør** for at behandle ændringerne.

## <a name="configure-customer-id-generation"></a>Konfigurer generering af kunde-id 

Når du har konfigureret flettefelter, kan du definere, hvordan du opretter CustomerId-værdier, de entydige kundeprofil-id'er. I flettetrinnet i datafletteprocessen oprettes det entydige kundeprofil-id. Id er CustomerId i objektet *Kunde*, som er resultatet af processen til datasamling. 

CustomerId i objektet Kunde er baseret på en hashen med den første værdi af de primære nøgler, der ikke er null-vindere. Nøglerne kommer fra de objekter, der bruges i overensstemmelses- og flettefasen, og de anvendes af overensstemmelsesrækkefølgen.Det oprettede CustomerID kan derfor ændres, når værdien for en primær nøgle ændres i det primære objekt i overensstemmelsesrækkefølgen. Værdien for den primære nøgle repræsenterer derfor ikke altid den samme kunde.

Hvis du konfigurerer et stabilt kunde-id, kan du undgå denne funktionsmåde.

**Konfigurer entydigt kunde-id**

1. Gå til **Unify** > **Flette**.

1. Vælg fanen **Nøgler**. 

1. Hold musen hen over rækken **CustomerId**, og vælg indstillingen **Konfigurer**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrolelement til tilpasning af id-oprettelse.":::

1. Vælg op til fem felter, der udgør et entydigt kunde-id, og som er mere stabilt. Poster, der ikke stemmer overens med konfigurationen, bruger i stedet et systemkonfigureret id.  

1. Vælg **Udført**, og kør fletteprocessen for at anvende ændringerne.

## <a name="group-profiles-into-households-or-clusters"></a>Gruppere profiler i husstande eller klynger

Som en del af konfigurationsprocessen for oprettelse af kundeprofiler kan du definere regler til gruppering af relaterede profiler i en klynge. Der findes i øjeblikket to typer klynger – husstandsklynger og brugerdefinerede klynger. Systemet vælger automatisk en husstand med foruddefinerede regler, hvis objektet *Kunde* indeholder de semantiske felter *Person.LastName* og *Location.Address*. Du kan også oprette en klynge med dine egne regler og betingelser ligesom [matchregler](match-entities.md#define-rules-for-match-pairs).

**Definere en husstand eller en klynge**

1. Gå til **Unify** > **Flette**.

1. Vælg **Avanceret** > **Opret klynge** under fanen **Flet**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kontrolelement til oprettelse af en ny klynge.":::

1. Vælg mellem en **Husstand**-klynge eller en **Brugerdefineret** klynge. Hvis de semantiske felter *Person.LastName* og *Location.Address* findes i objektet *Kunde*, vælges husstand automatisk.

1. Angiv et navn til klyngen, og vælg **Udført**.

1. Vælg fanen **Klynger** for at finde den klynge, du har oprettet.

1. Angiv regler og betingelser for at definere klyngen.

1. Vælg **Kør** for at køre fletteprocessen og oprette klyngen.

Når du har kørt fletteprocessen, tilføjes klynge-id'erne som nye felter i objektet *Kunde*.

## <a name="run-your-merge"></a>Køre fletningen

Uanset om du fletter attributter manuelt eller lader systemet flette dem, kan du altid køre fletningen. Vælg **Kør** på siden **Flet** for at starte processen.

> [!div class="mx-imgBorder"]
> ![Gemme og køre datafletning.](media/configure-data-merge-save-run.png "Gemme og køre datafletning")

Vælg **Kør kun fletning**, hvis du kun vil se outputtet afspejlet i det samlede kundeobjekt. Downstream-processer opdateres som [defineret i opdateringsplanen](system.md#schedule-tab).

Vælg **Kør flettede og downstream-processer** for at opdatere systemet med ændringerne. Alle processer, herunder forbedringer, segmenter og målinger, køres automatisk igen. Når alle downstream-processer er fuldført, afspejler kundeprofilerne eventuelle ændringer, du har foretaget.

Hvis du vil foretage flere ændringer og køre trinnet igen, kan du annullere en igangværende fletning. Vælg **Opdaterer...**, og vælg **Annuller job** i den siderude, der vises.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Nedrulningssti for at få vist procesoplysninger fra linket til opgavestatus.":::

## <a name="next-step"></a>Næste trin

Konfigurer [aktiviteter](activities.md), [forbedring](enrichment-hub.md) eller [relationer](relationships.md) for at få mere indsigt i dine kunder.

Hvis du allerede har konfigureret aktiviteter, forbedringer eller segmenter, behandles de automatisk til at bruge de nyeste kundedata.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
