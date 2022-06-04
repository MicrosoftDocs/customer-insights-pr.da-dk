---
title: Objekter og datasæt
description: Få vist data på siden objekter.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: c1094bc2f6d137087b317ed20d0615289d6f1187
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646216"
---
# <a name="entities-in-customer-insights"></a>Objekter i Customer Insights

Når du har [konfigureret datakilderne](data-sources.md), skal du gå til siden **Objekter** for at vurdere kvaliteten af de data, der er indtaget. Objekter anses for at være datasæt. Flere funktioner i Dynamics 365 Customer Insights er opbygget omkring disse objekter. Hvis du gennemgår dem nøje, kan du bedre validere outputtet af disse funktioner.

På siden **Objekter** vises objekter, og disse kolonner er inkluderet:

- **Navn**: Navnet på dataobjektet. Hvis du får vist et advarselssymbol ud for et objektnavn, betyder det, at dataene for det pågældende objekt ikke blev indlæst korrekt.
- **Kilde**: Type af datakilde, der indtager objektet.
- **Opdateret**: Det tidspunkt, objektet sidst blev opdateret.
- **Status**: Detaljer om den sidste opdatering af objektet.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Udforske et bestemt objekts data

1. Gå til **Data** > **Objekter**.
1. Vælg et **Objekt** på siden Objekter for at åbne detaljesiden.  
1. Udforsk de forskellige felter og poster, der findes i det pågældende objekt.

- Fanen **Attributter** er valgt som standard, og der vises en tabel, hvor du kan gennemse detaljer om det valgte objekt, f.eks. feltnavne, datatyper og typer. Kolonnen **Type** viser tilknyttede Common Data Model-typer, som enten identificeres automatisk af systemet eller [tilknyttes manuelt](map-entities.md) af brugere. Disse typer er semantiske typer, der kan adskille sig fra attributters datatyper. Feltet *E-mail* nedenfor har f.eks. datatypen *Tekst*, men den (semantiske) Common Data Modeltype kan være *E-mail* eller *EmailAddress*.

> [!div class="mx-imgBorder"]
> ![Tabellen Felter.](media/data-manager-entities-fields.PNG "Tabellen Felter")

> [!NOTE]
> På denne side vises kun et eksempel på objektets data. Hvis du vil have vist det komplette datasæt, skal du gå til siden **Datakilder**, vælge et objekt, vælge **Rediger** og derefter få vist dette objekts data med Power Query-editoren som forklaret under [Datakilder](data-sources.md).

Hvis du vil have mere at vide om de data, der indtages i objektet, kan du finde nogle vigtige karakteristika for dataene i kolonnen **Oversigt**, f.eks. null-værdier, manglende værdier, entydige værdier, antal og fordelinger, som det er relevant for dine data. Vælg ikonet for diagrammet for at få vist en oversigt over dataene.

> [!div class="mx-imgBorder"]
> ![Symbol for oversigt.](media/data-manager-entities-summary.png "Dataoversigtstabel")

- Under fanen **Data** vises en tabel med oplysninger om individuelle poster i objektet. De viste detaljer afhænger af objektets datatype.

> [!div class="mx-imgBorder"]
> ![Vælg et objekt.](media/data-manager-entities-data.png "Vælg et objekt")

- Under fanen **Rapporter** (der er tilgængelig for visse objekter) kan du visualisere dataene ved at oprette en rapport og inkluderer disse kolonner:

  - **Rapportnavn**: Navn på rapporten.
  - **Oprettet af**: Navnet på den person, der oprettede objektet.
  - **Oprettet**: Dato og klokkeslæt for oprettelse af objektet.
  - **Redigeret af**: Navnet på den person, der har ændret objektet.
  - **Redigeret**: Dato og klokkeslæt for ændring af objektet. 

## <a name="entity-specific-information"></a>Objektspecifikke oplysninger

I følgende afsnit finder du oplysninger om nogle systemoprettede objekter.

### <a name="corrupted-data-sources"></a>Beskadigede datakilder

Felter fra en brugerdefineret datakilde kan indeholde beskadigede data. Poster med beskadigede felter vises i systemoprettede objekter. Hvis du kender til beskadigede poster, kan du nemmere identificere, hvilke data der skal gennemses og opdateres på kildesystemet. Efter den næste opdatering af datakilde overføres de korrigerede poster til Customer Insights og overføres til downstreamprocesser. 

Datatypen er f.eks. angivet som 'dato' i kolonnen 'fødselsdag'. En kundepost har fødselsdag angivet som '01/01/1977'. Denne post markeres som beskadiget af systemet. Nogen kan nu ændre fødselsdagen i kildesystemet til '1977'. Efter en automatiseret opdatering af datakilder har feltet nu et gyldigt format, og posten fjernes fra det beskadigede objekt. 

Gå til **Data** > **Objekter**, og søg efter de beskadigede objekter i sektionen **System**. Navngivningsskema for beskadigede objekter: 'DataSourceName_EntityName_corrupt'. Vælg et beskadiget objekt for at identificere alle de beskadigede felter og årsagen på de enkelte postniveau.
> [!div class="mx-imgBorder"]
> ![Årsag til beskadigelse.](media/corruption-reason.png "Årsag til beskadigelse")

I Customer Insights behandles stadig beskadigede poster. De kan dog give problemer, når du arbejder med de ensartede data.

Følgende kontroller køres på de indtagne data for at få vist beskadigede poster: 

- Værdien i et felt stemmer ikke overens med datatypen i kolonnen.
- Felter indeholder tegn, der medfører, at kolonnerne ikke stemmer overens med det forventede skema. Eksempel: forkert formaterede anførselstegn, unescaped anførselstegn eller ny linje-tegn.
- Hvis der er kolonner af samme dato/klokkeslæt, skal formatet angives i modellen, hvis det ikke følger ISO-standardformatet.


[!INCLUDE [footer-include](includes/footer-banner.md)]