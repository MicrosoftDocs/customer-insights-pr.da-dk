---
title: Objekter i Customer Insights
description: Få vist data på siden objekter.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610091"
---
# <a name="entities-in-customer-insights"></a>Objekter i Customer Insights

Når du har [konfigureret datakilderne](data-sources.md), skal du gå til siden **Objekter** for at vurdere kvaliteten af de data, der er indtaget. Objekter anses for at være datasæt. Flere funktioner i Dynamics 365 Customer Insights er opbygget omkring disse objekter. Hvis du gennemgår dem nøje, kan du bedre validere outputtet af disse funktioner.

Når du arbejder med Customer Insights til forbedring af dine data eller oprettelse af målgrupper, mål og aktiviteter, vises de objekter, der er oprettet ud fra disse handlinger, på siden **Objekter**.

## <a name="view-a-list-of-entities"></a>Få vist en liste over objekter

Gå til **Data** > **Objekter** for at få vist en liste over objekter. Følgende oplysninger er tilgængelige for hver begivenhed:

- **Navn**: Navnet på dataobjektet. Hvis du får vist et advarselssymbol ud for et objektnavn, betyder det, at dataene for det pågældende objekt ikke blev indlæst korrekt.
- **Kilde**: Type af datakilde, der indtager objektet.
- **Opdateret**: Det tidspunkt, objektet sidst blev opdateret.
- **Status**: Detaljer om den sidste opdatering af objektet.

## <a name="explore-a-specific-entitys-data"></a>Udforske et bestemt objekts data

1. Gå til **Data** > **Objekter**.
1. Vælg et objekt for at åbne siden med detaljer.  
1. Udforsk de forskellige felter og poster, der findes i det pågældende objekt.

- Fanen **Attributter** er valgt som standard, og der vises detaljer om det valgte objekt, f.eks. feltnavne, datatyper og typer. Kolonnen **Type** viser tilknyttede Common Data Model-typer, som enten identificeres automatisk af systemet eller [tilknyttes manuelt](map-entities.md) af brugere. Disse typer er semantiske typer, der kan adskille sig fra attributters datatyper. Feltet *E-mail* nedenfor har f.eks. datatypen *Streng*, men den (semantiske) Common Data Modeltype kan være *Email*, *EmailAddress* eller *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabellen Felter.":::

   > [!NOTE]
   > På denne side vises kun et eksempel på objektets data. Hvis du vil have vist det komplette datasæt, skal du gå til siden **Datakilder**, vælge et objekt, vælge **Rediger** og derefter få vist dette objekts data med Power Query-editoren som forklaret under [Datakilder](data-sources.md).

   Hvis du vil have mere at vide om de data, der indtages i objektet, kan du finde nogle vigtige karakteristika for dataene i kolonnen **Oversigt**, f.eks. null-værdier, manglende værdier, entydige værdier, antal og fordelinger, som det er relevant for dine data. Vælg ikonet for diagrammet for at få vist en oversigt over dataene.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Dataoversigtstabel.":::

- Under fanen **Data** vises en tabel med oplysninger om individuelle poster i objektet. De viste detaljer afhænger af objektets datatype.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Vælg et objekt.":::

- Under fanen **Rapporter** (der er tilgængelig for visse objekter) kan du visualisere dataene ved at oprette en rapport og inkluderer disse kolonner:

  - **Rapportnavn**: Navn på rapporten.
  - **Oprettet af**: Navnet på den person, der oprettede objektet.
  - **Oprettet**: Dato og klokkeslæt for oprettelse af objektet.
  - **Redigeret af**: Navnet på den person, der har ændret objektet.
  - **Redigeret**: Dato og klokkeslæt for ændring af objektet.

[!INCLUDE [footer-include](includes/footer-banner.md)]
