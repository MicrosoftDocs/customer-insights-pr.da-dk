---
title: Forhold mellem objekter og objektstier
description: Opret og administrer forhold mellem objekter fra flere datakilder.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595205"
---
# <a name="relationships-between-entities"></a>Relationer mellem objekter

Relationer hjælper dig med at oprette forbindelse mellem objekter og oprette en graf over dine data, når objekter deler en fælles identifikator (fremmed nøgle), der kan henvises til fra et objekt til et andet. Forbundne objekter giver dig mulighed for at definere segmenter og målinger, der er baseret på flere datakilder.

Der findes to typer relationer. ikke-redigerbare systemrelationer, der oprettes automatisk, og brugerdefinerede relationer, som oprettes og konfigureres af brugere.

Under match- og fletteprocesserne oprettes systemrelationer i baggrunden baseret på intelligent matchning. Disse relationer hjælper med at relatere kundeprofilposter til andre tilsvarende objekters poster. I følgende diagram illustreres oprettelsen af tre systemrelationer, når kundeobjektet matches med flere objekter for at producere det endelige kundeprofilobjekt.

> [!div class="mx-imgBorder"]
> ![Oprettelse af relation](media/relationships-entities-merge.png "Oprettelse af relation")

- ***CustomerToContact*-relationen** blev oprettet mellem kundeobjektet og kontaktobjektet. Kundeobjektet får nøglefeltet **Contact_contactId** til at relatere til nøglefeltet **contactId** for kontaktobjektet.
- ***CustomerToAccount*-relationen** blev oprettet mellem kundeobjektet og kontoobjektet. Kundeobjektet får nøglefeltet **Account_accountId** til at relatere til nøglefeltet **accountId** for kontoobjektet.
- ***CustomerToWebAccount*-relationen** blev oprettet mellem kundeobjektet og webkontoobjektet. Kundeobjektet får nøglefeltet **WebAccount_webaccountId** til at relatere til nøglefeltet **webaccountId** for webkontoobjektet.

## <a name="create-a-relationship"></a>Oprette en relation

Definer tilpassede relationer på siden **Relationer**. Hver relation består af et kildeobjekt (det objekt, der indeholder den fremmede nøgle) og et målobjekt (det objekt, som kildeobjektets fremmede nøgle peger på).

1. Gå til **Data** > **Forhold** i målgruppen Insights.

2. Vælg **Ny relation**.

3. Angiv følgende oplysninger i ruden **Tilføj relation**:

   > [!div class="mx-imgBorder"]
   > ![Angive relationsdetaljer](media/relationships-add.png "Angive relationsdetaljer")

   - **Navn på relation**: Navn, der afspejler formålet med relationen (f.eks. **AccountWebLogs**).
   - **Beskrivelse**: Beskrivelsen af relationen.
   - **Kildeobjekt**: Vælg det objekt, der bruges som kilde i relationen (f.eks. WebLog).
   - **Kardinalitet**: Vælg kardinaliteten for kildeobjektposterne. F.eks. betyder "mange", at flere weblogposter er relateret til én webkonto.
   - **Kildenøglefelt**: Det repræsenterer den fremmede nøgle i kildeobjektet. WebLog indeholder f.eks. feltet **accountId** som fremmed nøgle.
   - **Målobjekt**: Vælg det objekt, der bruges som mål i relationen (f.eks. WebAccount).
   - **Målkardinalitet**: Vælg kardinaliteten for målobjektposterne. F.eks. betyder "én", at flere weblogposter er relateret til én webkonto.
   - **Målnøglefelt**: Dette felt repræsenterer nøglefeltet for målobjektet. WebAccount indeholder f.eks. nøglefeltet **accountId**.

> [!NOTE]
> Det er kun mange-til-én- og én-til-én-relationer, der understøttes. Mange-til-mange-relationer kan oprettes ved hjælp af to mange til én-relationer og et linkobjekt (et objekt, der bruges til at oprette forbindelse mellem kildeobjektet og målobjektet).

## <a name="delete-a-relationship"></a>Slette en relation

1. Gå til **Data** > **Forhold** i målgruppen Insights.

2. Markér afkrydsningsfelterne ud for de relationer, der skal slettes.

3. Vælg **Slet** øverst i **Relationer**-tabellen.

4. Bekræft sletningen.

## <a name="next-step"></a>Næste trin

System- og brugerdefinerede relationer bruges til at oprette segmenter baseret på flere datakilder, der ikke længere er i silo. Du kan finde flere oplysninger under [Segmenter](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]