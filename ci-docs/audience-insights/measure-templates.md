---
title: Oprette målinger fra skabeloner
description: Definere foranstaltninger ved hjælp af skabeloner til almindelige sager.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 0fe846691825b93732cbbe6d1c942a79e4a3934f
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359899"
---
# <a name="use-a-template-to-build-a-measure"></a>Bruge en skabelon til at oprette en måleenhed

Du kan bruge foruddefinerede skabeloner med almindeligt anvendte [foranstaltninger](measures.md) til at oprette dem. Detaljerede beskrivelser af skabelonerne og en styret oplevelse hjælper dig med at oprette effektive måleenheder. Skabeloner bygger på tilknyttede data fra objektet *Unified Activity*. Sørg derfor for, at du har konfigureret [kundeaktiviteter](activities.md), før du opretter en måleenhed ud fra en skabelon.

Hvis du vil oprette brugerdefinerede mål, kan du gå til [Brug af målergenerator til at oprette mål fra bunden](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

Tilgængelige måleskabeloner. 
- Gennemsnitlig transaktionsværdi (ATV)
- Samlet transaktionsværdi
- Gennemsnitlig dagsomsætning
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

1. Angiv navnet på målingen og outputobjektet i ruden **Rediger navn**. 

1. Vælg **Udført**.

1. Definer tidsrammen for de data, der skal bruges i **Angiv tidsperiode**. Vælg, om den nye måleenhed skal dække hele datasæt, ved at vælge **Alle tider**, eller hvis målingen skal fokusere på en **Bestemt tidsperiode**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Skærmbillede, der viser sektionen tidsperiode, når du konfigurerer en måling ud fra en skabelon.":::

1. I næste afsnit skal du vælge **Tilføj data** for at vælge aktiviteterne og tilknytte de tilhørende data fra objektet *Unified Activity*.

    1. Trin 1 af 2: Vælg den type objekt, du vil bruge under **Aktivitetstype**. I forbindelse med **Aktiviteter** skal du markere de objekter, du vil tilknytte.
    1. Trin 2 af 2: Vælg attributten fra objektet *Unified Activity* for den komponent, der kræves af formlen. I forbindelse med gennemsnitlig transaktionsværdi er det f.eks. den attribut, der repræsenterer transaktionsværdien. I forbindelse med **Aktivitetstidsstempel** skal du vælge attributten fra objektet Unified Activity, der repræsenterer dato og klokkeslæt for aktiviteten.
   
1. Når datatilknytningen er vellykket, kan du se status som **Fuldført** og navnet på de tilknyttede aktiviteter og attributter.

1. Du kan nu vælge **Kør** for at beregne resultaterne af målingen. Hvis du vil finjustere den senere, skal du vælge **Gem kladde**.

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

Denne funktion er kun tilgængelig for målinger, der er oprettet i miljøer med individuelle kunder som primær målgruppe.

---