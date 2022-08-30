---
title: Samle kundefelter for data samling
description: Flet objekter for at oprette samlede kundeprofiler.
recommendations: false
ms.date: 07/27/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 7ebd6ab8fa6ae141f33295a5d7723e96c8dc70ca
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304006"
---
# <a name="unify-customer-fields"></a>Unify customer-felter

I dette trin af processen til samling skal du vælge og udelukke attributter, der skal flettes i objektet for den samlede profil. Hvis tre objekter f.eks. indeholder e-maildata, kan det være en god ide at bevare alle tre separate mailfelter eller flette dem sammen i et enkelt e-mailfelt for den samlede profil. Nogle attributter kombineres automatisk af systemet. Du kan oprette stabile og entydige kunde-id'er. For enkeltkunder kan du gruppere relaterede profiler i en klynge.

:::image type="content" source="media/m3_unify.png" alt-text="Siden Samle kundefelter i processen til datasamling, der viser en tabel med flettede felter, der definerer den samlede kundeprofil.":::

## <a name="review-and-update-the-customer-fields"></a>Gennemse og opdater kundefelter

1. Gennemse den liste over felter, der skal være samlet under fanen **Kundefelter** i tabellen. Foretag eventuelle ændringer.

   1. For ethvert kombineret felt kan du:
      - [Redigér](#edit-a-merged-field)
      - [Omdøb](#rename-fields)
      - [Adskil](#separate-merged-fields)
      - [Udelad](#exclude-fields)
      - [Flytte op eller ned](#change-the-order-of-fields)

   1. For ethvert enkelt felt kan du:
      - [Kombiner felter](#combine-fields-manually)
      - [Kombiner en gruppe af felter](#combine-a-group-of-fields)
      - [Omdøb](#rename-fields)
      - [Udelad](#exclude-fields)
      - [Flytte op eller ned](#change-the-order-of-fields)

1. Du kan også [generere n konfiguration af kunde-id](#configure-customer-id-generation).

1. Alternativt kan du for B-til-C [gruppere profiler i husstande eller klynger](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Næste trin: Gennemse samling](review-unification.md)

### <a name="edit-a-merged-field"></a>Redigere et flettet felt

1. Vælg et flettet felt, og vælg **Rediger**. Ruden Kombiner felter vises.

1. Angiv, hvordan felterne skal kombineres eller flettes fra en af tre indstillinger:
    - **Betydning**: Identificerer vinderværdien på baggrund af den rangordnede betydning, der er angivet for de deltagende felter. Dette er standardfletteindstillingen. Vælg **Flyt op/ned** for at angive prioritetsranglisten.

      > [!NOTE]
      > I Customer Insights bruges den første værdi, der ikke er null. De givne objekter A, B og C lige i den rækkefølge bruges, hvis A.Name og B.Name er null, anvendes værdien fra C.Name.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Indstillingen Prioritet i dialogboksen med brevfletningsfelter.":::

    - **Nyeste**: Identificerer vinderværdien baseret på den mest aktuelle. Kræver en dato eller et numerisk felt for alle deltagende objekter i omfanget af brevfletningsfelterne for at definere rekursen.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Indstillingen Nyhed i dialogboksen med brevfletningsfelter.":::

    - **Mindst nyeste**: Identificerer vinderværdien baseret på den mindst aktuelle. Kræver en dato eller et numerisk felt for alle deltagende objekter i omfanget af brevfletningsfelterne for at definere rekursen.

1. Du kan tilføje flere felter for at deltage i fletteprocessen.

1. Du kan omdøbe det flettede felt.

1. Vælg **Fuldført** for at anvende dine ændringer.

### <a name="rename-fields"></a>Omdøb felter

Rediger visningsnavn for flettede eller separate felter. Du kan ikke ændre navnet på outputobjektet.

1. Vælg feltet, og tryk på **Omdøb**.

1. Angiv det nye viste navn.

1. Vælg **Udført**.

### <a name="separate-merged-fields"></a>Adskille flettede felter

Hvis du vil adskille flettede felter, skal du søge efter attributten i tabellen. Adskilte felter vises som individuelle datapunkter i den samlede kundeprofil.

1. Markér det flettede felt, og vælg **Separate felter**.

1. Bekræft separationen.

### <a name="exclude-fields"></a>Udelade felter

Udelad et flettet eller separat felt fra unified customer profile. Hvis feltet bruges i andre processer, f.eks. i et segment, skal du fjerne det fra disse processer, før det udelades i kundeprofilen.

1. Vælg et flettet felt, og vælg **Udelad**.

1. Bekræft udeladelsen.

Hvis du vil se listen over alle udelukkede felter, skal du vælge **Udeladte felter**. Du kan evt. læse det udeladte felt.

### <a name="change-the-order-of-fields"></a>Ændre rækkefølgen for felter

Nogle objekter indeholder flere detaljer end andre. Hvis et objekt indeholder de nyeste data om et felt, kan du prioritere det frem for andre objekter, når du fletter værdier.

1. Markér feltet.
  
1. Vælg **Flyt op/ned for** at angive rækkefølgen, eller træk og slip dem på den ønskede placering.

### <a name="combine-fields-manually"></a>Kombiner felter manuelt

Du kan kombinere separate felter for at oprette en flettet attribut.

1. Vælg **Kombiner** > **Felter**. Ruden Kombiner felter vises.

1. Angiv vinderpolitik for fletning i rullelisten **Kombiner felter efter**.

1. Vælg **Tilføj felt** for at kombinere flere felter.

1. Angiv et **Navn** og et **Navn på outputfelt**.

1. Vælg **Fuldført** for at anvende ændringerne.

### <a name="combine-a-group-of-fields"></a>Kombiner en gruppe af felter

Behandle en gruppe felter som en enkelt enhed. Hvis vores poster f.eks. indeholder felterne Adresse1, Adresse2, By, Land og Postnr., kan vi ikke flette Adresse2 fra en anden post og tænke på, at dataene bliver mere gennemført.

1. Vælg **Kombiner** > **Gruppe af felter**.

1. Angiv vinderpolitik for fletning i rullelisten **Inddel grupper efter**.

1. Vælg **Tilføj**, og vælg, om du vil føje flere felter eller grupper til felterne.

1. Angiv et **Navn** og et **Outputnavn** for hvert samlet felt.

1. Angiv et **Navn** til gruppen af felter.

1. Vælg **Fuldført** for at anvende ændringerne.

## <a name="configure-customer-id-generation"></a>Konfigurer generering af kunde-id

Definer, hvordan du opretter kunde id-værdier, de entydige kundeprofil-id'er. I trinnet til samling af felter i datasamlingsprocessen oprettes det entydige kundeprofil-id. Id er *CustomerId* i objektet *Customer*, som er resultatet af processen til datasamling.

*CustomerId*  er baseret på en hash med den første værdi af de primære nøgler, der ikke er null-vindere. Nøglerne kommer fra de objekter, der bruges i datasamling, og de påvirkes af match-rækkefølgen.Det oprettede kunde-id kan derfor ændres, når værdien for en primær nøgle ændres i det primære objekt i match-rækkefølgen. Værdien for den primære nøgle repræsenterer derfor ikke altid den samme kunde.

Hvis du konfigurerer et stabilt kunde-id, kan du undgå denne funktionsmåde.

1. Vælg fanen **Nøgler**.

1. Hold musen i rækken **CustomerId**, og vælg **Konfigurer**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrolelement til tilpasning af id-oprettelse.":::

1. Vælg op til fem felter, der udgør et entydigt kunde-id, og som er mere stabilt. Poster, der ikke stemmer overens med konfigurationen, bruger i stedet et systemkonfigureret id.  

1. Vælg **Udført**.

## <a name="group-profiles-into-households-or-clusters"></a>Gruppere profiler i husstande eller klynger

For enkeltkunder kan du definere regler til gruppering af relaterede profiler i en klynge. Der findes i øjeblikket to typer klynger – husstandsklynger og brugerdefinerede klynger. Systemet vælger automatisk en husstand med foruddefinerede regler, hvis objektet *Kunde* indeholder de semantiske felter *Person.LastName* og *Location.Address*. Du kan også oprette en klynge med dine egne regler og betingelser ligesom [matchregler](match-entities.md#define-rules-for-match-pairs).

1. Vælg **Avanceret** > **Opret en klynge**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kontrolelement til oprettelse af en ny klynge.":::

1. Vælg mellem en **Husstand**-klynge eller en **Brugerdefineret** klynge. Hvis de semantiske felter *Person.LastName* og *Location.Address* findes i objektet *Kunde*, vælges husstand automatisk.

1. Angiv et navn til klyngen, og vælg **Udført**.

1. Vælg fanen **Klynger** for at finde den klynge, du har oprettet.

1. Angiv regler og betingelser for at definere klyngen.

1. Vælg **Udført**. Klyngen oprettes, når samlingsprocessen er fuldført. Klynge-id tilføjes som nye felter i objektet *Kunde*.

> [!div class="nextstepaction"]
> [Næste trin: Gennemse samling](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
