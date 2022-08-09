---
title: Oprette målinger fra skabeloner
description: Definere foranstaltninger ved hjælp af skabeloner til almindelige sager.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170766"
---
# <a name="create-measures-from-templates"></a>Oprette målinger fra skabeloner

Brug foruddefinerede skabeloner med almindeligt anvendte [foranstaltninger](measures.md) til at oprette dem. Skabeloner bygger på tilknyttede data fra objektet *Unified Activity*. Sørg derfor for, at du har konfigureret [kundeaktiviteter](activities.md), før du opretter en måleenhed ud fra en skabelon.

Måling af skabeloner understøttes kun i miljøer for **individuelle kunder**. Hvis du vil oprette brugerdefinerede mål eller oprette målinger for B to B, kan du gå til [Brug af målergenerator](measure-builder.md).

Tilgængelige måleskabeloner.
- Gennemsnitlig transaktionsværdi (ATV)
- Samlet transaktionsværdi
- Gennemsnitlig dagsomsætning
- Gennemsnitlig månedlig omsætning
- Gennemsnitlig åromsætning
- Antal transaktioner
- Optjente loyalitetspoint
- Indløste loyalitetspoint
- Saldo for loyalitetspoint
- Aktiv kundelevetid
- Varighed af medlemskab for loyalitetskunde
- Tid siden seneste køb

## <a name="build-a-new-measure-using-a-template"></a>Oprette en ny måleenhed ved hjælp af en skabelon

1. Gå til **Målinger**.

1. Vælg **Ny**, og vælg **Vælg en skabelon**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Skærmbillede af rullemenuen, når du opretter en ny måleenhed med fremhævning på skabelon.":::

1. Find den skabelon, der passer til dine behov, og vælg **Vælg skabelon**.

1. Gennemse de nødvendige data, og vælg **Start her**, hvis alle dataene er på plads.

1. Vælg **Rediger detaljer** ud for Måling-navnet. Angiv et navn for målingen. Du kan også tilføje [koder](work-with-tags-columns.md#manage-tags) til den nye måling.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogboksen Rediger detaljer.":::

1. Vælg **Udført**.

1. Definer tidsrammen for de data, der skal bruges i **Angiv tidsperiode**. Vælg, om den nye måleenhed skal dække hele datasæt, ved at vælge **Alle tider**, eller hvis målingen skal fokusere på en **Bestemt tidsperiode**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Skærmbillede, der viser sektionen tidsperiode, når du konfigurerer en måling ud fra en skabelon.":::

1. I næste afsnit skal du vælge **Tilføj data** for at vælge aktiviteterne og tilknytte de tilhørende data fra objektet *Unified Activity*.

    1. Trin 1 af 2: Vælg den type objekt, du vil bruge under **Aktivitetstype**. I forbindelse med **Aktiviteter** skal du markere de objekter, du vil tilknytte, og vælge **Næste**.
    1. Trin 2 af 2: Vælg attributten fra objektet *Unified Activity* for den komponent, der kræves af formlen. I forbindelse med gennemsnitlig transaktionsværdi er det f.eks. den attribut, der repræsenterer transaktionsværdien. I forbindelse med **Aktivitetstidsstempel** skal du vælge attributten fra objektet *Unified Activity*, der repræsenterer dato og klokkeslæt for aktiviteten.
    1. Vælg **Gem**.

    Når datatilknytningen er vellykket, kan du se status som **Fuldført** og navnet på de tilknyttede aktiviteter og attributter.

1. Du kan nu vælge **Kør** for at beregne resultaterne af målingen. Vælg **Gem kladde**, hvis du vil bevare den aktuelle konfiguration og køre målingen senere. Siden **Målinger** vises.

## <a name="next-step"></a>Næste trin

Brug eksisterende mål til at oprette [et kundesegment](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
