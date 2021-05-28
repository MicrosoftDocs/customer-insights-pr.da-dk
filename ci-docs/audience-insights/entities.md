---
title: Objekter og datasæt
description: Få vist data på siden objekter.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049387"
---
# <a name="entities-in-audience-insights"></a>Objekter i målgruppeindsigt

Når du har [konfigureret datakilderne](data-sources.md), skal du gå til siden **Objekter** for at vurdere kvaliteten af de data, der er indtaget. Objekter anses for at være datasæt. Flere funktioner i Dynamics 365 Customer Insights er opbygget omkring disse objekter. Hvis du gennemgår dem nøje, kan du bedre validere outputtet af disse funktioner.

På siden **Objekter** vises objekter, og der findes flere kolonner:

- **Navn**: Navnet på dataobjektet. Hvis du får vist et advarselssymbol ud for et objektnavn, betyder det, at dataene for det pågældende objekt ikke blev indlæst korrekt.
- **Kilde**: Den type af datakilde, der har indtaget objektet
- **Oprettet af**: Navnet på den person, der oprettede objektet
- **Oprettet**: Dato og klokkeslæt for oprettelse af objektet
- **Opdateret af**: Navnet på den person, der opdaterede objektet
- **Senest opdateret**: Dato og klokkeslæt for seneste opdatering af objektet
- **Seneste opdatering**: Dato og klokkeslæt for den seneste dataopdatering

## <a name="exploring-a-specific-entitys-data"></a>Udforske et bestemt objekts data

Vælg et objekt for at udforske de forskellige felter og poster, der findes i det pågældende objekt.

> [!div class="mx-imgBorder"]
> ![Vælg et objekt](media/data-manager-entities-data.png "Vælge et objekt")

- Under fanen **Data** vises en tabel med oplysninger om individuelle poster i objektet.

> [!div class="mx-imgBorder"]
> ![Tabellen Felter](media/data-manager-entities-fields.PNG "Tabellen Felter")

- Fanen **Attributter** er valgt som standard, og der vises en tabel, hvor du kan gennemse detaljer om det valgte objekt, f.eks. feltnavne, datatyper og typer. Kolonnen **Type** viser tilknyttede Common Data Model-typer, som enten identificeres automatisk af systemet eller [tilknyttes manuelt](map-entities.md) af brugere. Disse er semantiske typer, der kan være forskellige fra datatyperne for attributter – f.eks. har feltet *Email* herunder datatypen *Tekst*, men dets (semantiske) Common Data Model -type kan f.eks. være *Email* eller *EmailAddress*.

> [!NOTE]
> I begge tabeller vises der kun et eksempel på objektets data. Hvis du vil have vist det komplette datasæt, skal du gå til siden **Datakilder**, vælge et objekt, vælge **Rediger** og derefter få vist dette objekts data med Power Query-editoren som forklaret under [Datakilder](data-sources.md).

Hvis du vil have mere at vide om de data, der indtages i objektet, kan du finde nogle vigtige karakteristika for dataene i kolonnen **Oversigt**, f.eks. null-værdier, manglende værdier, entydige værdier, antal og fordelinger, som det er relevant for dine data.

Vælg ikonet for diagrammet for at få vist en oversigt over dataene.

> [!div class="mx-imgBorder"]
> ![Symbol for oversigt](media/data-manager-entities-summary.png "Dataoversigtstabel")

### <a name="next-step"></a>Næste trin

Se emnet [Samle](data-unification.md) for at lære at *tilknytte*, *matche* og *flette* de data, der er indtaget.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
