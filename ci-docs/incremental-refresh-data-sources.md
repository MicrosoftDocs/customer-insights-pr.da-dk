---
title: Trinvis opdatering for Power Query og Azure Data Lake-datakilder
description: Opdater nye og opdaterede data til store datakilder, der er baseret på Power Query eller Azure Data Lake-datakilder.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207130"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Trinvis opdatering for Power Query og Azure Data Lake-datakilder

Trinvis opdatering af datakilder i Power Query eller Azure Data Lake giver følgende fordele:

- **Hurtigere opdateringer** – Kun data, der er ændret, opdateres. Du kan f.eks. nøjes med at opdatere de seneste fem dage i et historisk datasæt.
- **Større pålidelighed** – Med mindre opdateringer har du ikke brug for at opretholde forbindelser til flygtige kildesystemer i så lang tid, hvilket mindsker risikoen for forbindelsesproblemer.
- **Reduceret ressourceforbrug** – Opdatering af et undersæt af dine samlede data giver mere effektiv brug af computerressourcer og reducerer det miljømæssige aftryk.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Konfigurere trinvis opdatering for datakilder baseret på Power Query

Customer Insights gør det muligt at opdatere trinvist for datakilder, der importeres via Power Query, der understøtter trinvis indtagelse. F.eks. Azure SQL-databaser med dato- og klokkeslætsfelter, som angiver, hvornår dataposterne sidst blev opdateret.

1. [Opret en ny datakilde baseret på Power Query](connect-power-query.md).

1. Vælg en datakilde, der understøtter trinvis opdatering, f.eks. [Azure SQL-database](/power-query/connectors/azuresqldatabase).

1. Vælg de objekter eller tabeller, der skal indtages.

1. Fuldfør transformationstrinnene, og vælg **Næste**.

1. Vælg **Konfigurer** i dialogboksen **Konfigurer trinvis opdatering** for at åbne **Indstillinger for trinvis opdatering**. Hvis du vælger **Spring over**, vil datakilden opdatere hele datasættet.
   > [!TIP]
   > Du kan også anvende trinvis opdatering senere ved at redigere en eksisterende datakilde.

1. I **Indstillinger for trinvis opdatering** konfigurerer du den trinvise opdatering for alle de objekter, du har valgt under oprettelsen af datakilden.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurere trinvis opdatering af indstillinger.":::

1. Vælg et objekt, og angiv følgende oplysninger:

   - **Vælg primærnøglen**: Vælg en primærnøgle til objektet eller tabellen.
   - **Definer feltet "sidst opdateret"**: I dette felt vises der kun attributter af typen dato eller klokkeslæt. Vælg en attribut, der angiver, hvornår posterne senest blev opdateret. Den bruges til at identificere de poster, der falder inden for den trinvise opdaterings tidsramme.
   - **Søg efter opdateringer hver**: Angiv, hvor lang tid tidsrammen for den trinvise opdatering skal være.

1. Vælg **Gem** for at fuldføre oprettelsen af datakilden. Den indledende dataopdatering vil være en fuld opdatering. Derefter sker den trinvise dataopdatering som konfigureret i forrige trin.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Konfigurere trinvis opdatering for Azure Data Lake-datakilder

Customer Insights gør det muligt at opdatere trinvist for datakilder, der er knyttet til Azure Data Lake Storage. Hvis du vil bruge trinvis redigering og opdatering for et objekt, skal du konfigurere objektet, når du tilføjer Azure Data Lake-datakilde eller nyere, når du redigerer datakilde. Objektdatamappen skal indeholde følgende mapper:

- **FullData**: Mappen med datafiler indeholder startposter
- **IncrementalData**: Mappe med mapper til dato/klokkeslæt-hierarki **åååå/mm/dd/tt-format**, der indeholder trinvise opdateringer. **tt** repræsenterer UTC-timen for opdateringerne og indeholder mapperne **Upserts** og **Deletes**. **Upserts** indeholder datafiler med opdateringer af eksisterende poster eller nye poster. **Deletes** indeholder datafiler, hvor poster skal fjernes.

1. Når du tilføjer eller redigerer datakilde, skal du navigere til ruden **Attributter** for objektet.

1. Gennemse attributterne. Kontrollér, at en oprettet eller senest opdateret datoattribut er konfigureret med *datetime* **Dataformat** og en *Calendar.Date* **Semantisk type**. Rediger attributten, hvis det er nødvendigt, og vælg **Udført**.

1. Rediger objektet i ruden **Vælg objekter**. Afkrydsningsfeltet **Trinvis indtagelse** er markeret.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Konfigurere objekter i en datakilde til trinvis opdatering.":::

   1. Gå til den rodmappe, der indeholder .csv- eller .parquet-filerne, hvor der søges efter fulde data, trinvise data-upserts og trinvise data, som slettes.
   1. Angiv udvidelsen for de fulde data og begge trinvise filer (\.csv eller \.parquet).
   1. I .csv-filer skal du markere kolonneafgrænseren, og hvis første række i filen skal være en kolonneoverskrift.
   1. Vælg **Gem**.

1. I forbindelse med **Seneste opdatering** skal du vælge datotidsstempelattributten.

1. Hvis den **primære nøgle** ikke er valgt, skal du vælge den primære nøgle. Den primære nøgle er en attribut, der er entydig for objektet. Hvis en attribut skal være en gyldig primær nøgle, må den ikke indeholde dubletværdier, manglende værdier eller null-værdier. Strengattributter, heltalsattributter og GUID-datatypeattributter understøttes som primære nøgler.

1. Vælg **Luk** for at gemme og lukke ruden.

1. Fortsæt med at tilføje eller redigere datakilde.

[!INCLUDE [footer-include](includes/footer-banner.md)]
