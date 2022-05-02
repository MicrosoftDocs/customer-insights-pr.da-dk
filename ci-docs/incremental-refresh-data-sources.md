---
title: Trinvis opdatering for Power Query-baserede datakilder
description: Opdatere nye og opdaterede data til store datakilder baseret på Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646328"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Trinvis opdatering for Power Query-baserede datakilder

I denne artikel beskrives, hvordan du kan konfigurere trinvis opdatering for datakilder baseret på Power Query.

Den trinvise opdatering af datakilder giver følgende fordele:

- **Hurtigere opdateringer** – Kun data, der er ændret, opdateres. Du kan f.eks. nøjes med at opdatere de seneste fem dage i et historisk datasæt.
- **Større pålidelighed** – Med mindre opdateringer har du ikke brug for at opretholde forbindelser til flygtige kildesystemer i så lang tid, hvilket mindsker risikoen for forbindelsesproblemer.
- **Reduceret ressourceforbrug** – Opdatering af et undersæt af dine samlede data giver mere effektiv brug af computerressourcer og reducerer det miljømæssige aftryk.

## <a name="configure-incremental-refresh"></a>Konfigurere trinvis opdatering

Customer Insights gør det muligt at opdatere trinvist for datakilder, der importeres via Power Query, der understøtter trinvis indtagelse. F.eks. Azure SQL-databaser med dato- og klokkeslætsfelter, som angiver, hvornår dataposterne sidst blev opdateret.

1. [Opret en ny datakilde baseret på Power Query](connect-power-query.md).

1. Angiv et **Navn** til datakilden.

1. Vælg en datakilde, der understøtter trinvis opdatering, f.eks. [Azure SQL-database](/power-query/connectors/azuresqldatabase).

1. Vælg de objekter eller tabeller, der skal indtages.

1. Fuldfør transformationstrinnene, og vælg **Næste**.

1. Vælg **Konfigurer** i dialogboksen **Konfigurer trinvis opdatering** for at åbne **Indstillinger for trinvis opdatering**. Hvis du vælger **Spring over**, vil datakilden opdatere hele datasættet.
   > [!TIP]
   > Du kan også anvende trinvis opdatering senere ved at redigere en eksisterende datakilde.

1. I **Indstillinger for trinvis opdatering** konfigurerer du den trinvise opdatering for alle de objekter, du har valgt under oprettelsen af datakilden.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurere objekter i en datakilde til trinvis opdatering.":::

1. Vælg et objekt, og angiv følgende oplysninger:

   - **Vælg primærnøglen**: Vælg en primærnøgle til objektet eller tabellen.
   - **Definer feltet "sidst opdateret"**: I dette felt vises der kun attributter af typen dato eller klokkeslæt. Vælg en attribut, der angiver, hvornår posterne senest blev opdateret. Den bruges til at identificere de poster, der falder inden for den trinvise opdaterings tidsramme.
   - **Søg efter opdateringer hver**: Angiv, hvor lang tid tidsrammen for den trinvise opdatering skal være.

1. Vælg **Gem** for at fuldføre oprettelsen af datakilden. Den indledende dataopdatering vil være en fuld opdatering. Derefter sker den trinvise dataopdatering som konfigureret i forrige trin.


[!INCLUDE [footer-include](includes/footer-banner.md)]
