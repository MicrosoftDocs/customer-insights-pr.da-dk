---
title: Trinvis opdatering af Power Query-baserede datakilder
description: Opdater nye og opdaterede data for store datakilder baseret på Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405443"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Trinvis opdatering af datakilder, der er baseret på Power Query

Den trinvise opdatering af datakilder giver følgende fordele:

- **Hurtigere opdateringer** – Kun data, der er ændret, opdateres. Du kan f.eks. nøjes med at opdatere de seneste fem dage i et historisk datasæt.
- **Større pålidelighed** – Med mindre opdateringer har du ikke brug for at opretholde forbindelser til flygtige kildesystemer i så lang tid, hvilket mindsker risikoen for forbindelsesproblemer.
- **Reduceret ressourceforbrug** – Opdatering af et undersæt af dine samlede data giver mere effektiv brug af computerressourcer og reducerer det miljømæssige aftryk.

## <a name="configure-incremental-refresh"></a>Konfigurer trinvis opdatering

Målgruppen Insights muliggør trinvis opdatering af datakilder, der importeres via Power Query, der understøtter den trinvise indsættelse. F.eks. Azure SQL-databaser med dato- og klokkeslætsfelter, som angiver, hvornår dataposterne sidst blev opdateret.

1. [Oprette en ny datakilde, der er baseret på Power Query](connect-power-query.md).

1. Angiv et navn til datakilden.

1. Vælg en datakilde, der understøtter trinvis opdatering, f.eks. Azure SQL Database.

1. Vælg de objekter eller tabeller, der skal indtages.

1. Fuldfør transformationstrinnene, og vælg **Næste**.

1. Vælg **Konfigurer** i dialogboksen **Konfigurer trinvis opdatering** for at åbne **Indstillinger for trinvis opdatering**. Hvis du vælger **Spring over**, vil datakilden opdatere hele datasættet.
   > [!TIP]
   > Du kan også anvende trinvis opdatering senere ved at redigere en eksisterende datakilde.

1. I **Indstillinger for trinvis opdatering** konfigurerer du den trinvise opdatering for alle de objekter, du har valgt under oprettelsen af datakilden.

   > [!div class="mx-imgBorder"]
   > ![Konfigurere objekter i en datakilde til trinvis opdatering](media/incremental-refresh-settings.png "Konfigurere objekter i en datakilde til trinvis opdatering")

1. Vælg et objekt, og angiv følgende oplysninger:

   - **Vælg primærnøglen**: Vælg en primærnøgle til objektet eller tabellen.
   - **Definer feltet "sidst opdateret"**: I dette felt vises der kun attributter af typen dato eller klokkeslæt. Vælg en attribut, der angiver, hvornår posterne senest blev opdateret. Den bruges til at identificere de poster, der falder inden for den trinvise opdaterings tidsramme.
   - **Søg efter opdateringer hver**: Angiv, hvor lang tid tidsrammen for den trinvise opdatering skal være.

1. Vælg **Gem** for at fuldføre oprettelsen af datakilden. Den indledende dataopdatering vil være en fuld opdatering. Derefter sker den trinvise dataopdatering som konfigureret i forrige trin.
