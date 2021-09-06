---
title: Oprette og administrere målinger
description: Definer foranstaltninger, der skal analysere og afspejle ydeevnen i virksomheden.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3593a02ce89233cf1e66c6beee669dd6dd261ba3b0e1d2d0cc966731349d7d0b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7037001"
---
# <a name="define-and-manage-measures"></a>Definere og administrere målinger

Foranstaltninger hjælper dig med at få en bedre forståelse af kundernes adfærd og virksomhedens præstation. De ser på relevante værdier fra [ensartede profiler](data-unification.md). En virksomhed vil f.eks. se det *samlede forbrug pr. kunde* for at forstå en enkelt kundes købsoversigt eller måle firmaets samlede salg for at forstå den *samlede omsætning i hele virksomheden*.  

Målinger oprettes ved hjælp af målegeneratoren, en platform til dataforespørgsel med forskellige operatorer og simple tilknytningsindstillinger. Du kan filtrere dataene, gruppere resultater, registrere [objektrelationsstier](relationships.md) og gennemse outputtet.

Brug målegeneratoren til at planlægge forretningsaktiviteter ved at forespørge om kundedata og udtrække indsigt. Hvis du f.eks. opretter et mål for det *samlede forbrug pr. kunde* og det *samlede afkast pr. kunde*, kan du identificere en gruppe kunder med et højt forbrug, men et højt afkast. Du kan [oprette et segment](segments.md) for at opnå de bedste handlinger. 

## <a name="build-your-own-measure-from-scratch"></a>Opret din egen måling fra bunden

Dette afsnit indeholder en gennemgang af, hvordan du opretter en ny måling fra bunden. Du kan oprette en måling med dataattributter fra dataobjekter, der har en relation konfigureret til at oprette forbindelse til objektet Kunde. 

1. Gå til **Målinger** i målgruppen Insights.

1. Vælg **Ny**, og vælg **Opret din egen**.

1. Vælg **Rediger navn**, og angiv et **Navn** til målingen. 
   > [!NOTE]
   > Hvis konfigurationen af den nye måling kun indeholder to felter, f.eks. CustomerID og én beregning, tilføjes outputtet som en ny kolonne i det systemgenererede objekt, der kaldes Customer_Measure. Du kan også se målingens værdi i den samlede kundeprofil. Andre foranstaltninger opretter deres egne objekter.

1. Vælg aggregeringsfunktionen i rullemenuen **Vælg funktion** i konfigurationsområdet. Aggregeringsfunktionerne omfatter: 
   - **Sum**
   - **Gennemsnitlig**
   - **Tælling**
   - **Antal entydige**
   - **Maks.**
   - **Min**
   - **Først**: Tager den første værdi af dataposten
   - **Sidste**: Tager den sidste værdi, der er tilføjet dataposten

   :::image type="content" source="media/measure-operators.png" alt-text="Operatorer til måleberegninger.":::

1. Vælg **Tilføj attribut** for at vælge de data, du skal bruge for at oprette denne måling.
   
   1. Vælg fanen **Attributter**. 
   1. Dataobjekt: Vælg det objekt, der indeholder den attribut, du vil måle. 
   1. Dataattribut: Vælg den attribut, du vil bruge i aggregeringsfunktionen for at beregne målingen. Du kan kun vælge én attribut ad gangen.
   1. Du kan også vælge en dataattribut fra en eksisterende måleenhed ved at vælge fanen **Mål**. Du kan også søge efter navnet på et objekt eller en måleenhed. 
   1. Vælg **Tilføj** for at føje den valgte attribut til målingen.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Vælg en attribut, der skal bruges i beregninger.":::

1. Hvis du vil oprette mere komplekse målinger, kan du tilføje flere attributter eller bruge matematikoperatorer på målfunktionen.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Opret en kompleks måling med matematikoperatorer.":::

1. Hvis du vil tilføje filtre, skal du vælge **Filter** i konfigurationsområdet. 
  
   1. Vælg den attribut, du vil bruge til at oprette filtre, i sektionen **Tilføj attribut** i ruden **Filtre**.
   1. Angiv filteroperatørerne for at definere filteret for alle valgte attributter.
   1. Vælg **Tilføj** for at tilføje filtrene til målingen.

1. Hvis du vil tilføje dimensioner, skal du vælge **Dimension** i konfigurationsområdet. Dimensionerne vises som kolonner i objektet til måling af output.
 
   1. Vælg **Rediger dimensioner** for at tilføje dataattributter, som du vil gruppere måleværdierne efter. Det kan f.eks. være by eller køn. Som standard vælges dimensionen *CustomerID* for at oprette *mål på kundeniveau*. Du kan fjerne standarddimensionen, hvis du vil oprette *mål på virksomhedsniveau*.
   1. Vælg **Gennemført** for at tilføje dimensioner til målingen.

1. Hvis der er værdier i dataene, som skal erstattes af et heltal, f.eks. erstat *null* med *0*, skal du vælge **Regler**. Konfigurer reglen, og sørg for kun at vælge hele tal som erstatninger.

1. Hvis der er flere stier mellem det dataobjekt, du har tilknyttet, og objektet *Kunde*, skal du vælge en af de identificerede [objektrelationsstier](relationships.md). Måleresultater kan variere, afhængigt af den valgte sti. 
   
   1. Vælg **Dataindstillinger**, og vælg den objektsti, der skal bruges til at identificere din måling. Hvis der kun er en enkelt sti til objektet *Kunde*, vises dette kontrolelement ikke.
   1. Vælg **Udført** for at anvende det valgte. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Vælg objektsti til målingen.":::

1. Hvis du vil tilføje flere beregninger for målingen, skal du vælge **Ny beregning**. Du kan kun bruge objekter på samme objektsti til nye beregninger. Flere beregninger vises som nye kolonner i objektet til måling af output.

1. Vælg **...** i beregningen at **Dupliker**, **Omdøb** eller **Fjern** for en beregning fra en måleenhed.

1. I området **Prøveversion** kan du se dataskemaet for outputobjektet for måleenheden, herunder filtre og dimensioner. Prøveversionen reagerer dynamisk på ændringer i konfigurationen.

1. Vælg **Kør** for at beregne resultaterne for det konfigurerede mål. Vælg **Gem og luk**, hvis du vil bevare den aktuelle konfiguration og køre målingen senere.

1. Gå til **Målinger** for at se den måling, du netop har oprettet, på listen.

## <a name="use-a-template-to-build-a-measure"></a>Bruge en skabelon til at oprette en måleenhed

Du kan bruge foruddefinerede skabeloner med almindeligt anvendte foranstaltninger til at oprette dem. Detaljerede beskrivelser af skabelonerne og en styret oplevelse hjælper dig med at oprette effektive måleenheder. Skabeloner bygger på tilknyttede data fra objektet *Unified Activity*. Sørg derfor for, at du har konfigureret [kundeaktiviteter](activities.md), før du opretter en måleenhed ud fra en skabelon.

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

I følgende procedure beskrives trinnene til opbygning af en ny måleenhed ved hjælp af en skabelon.

1. Gå til **Målinger** i målgruppen Insights.

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

   :::image type="content" source="media/measure-template-configured.png" alt-text="Skærmbillede af konfigurationen af skabelonen til en fuldført måling.":::

1. Du kan nu vælge **Kør** for at beregne resultaterne af målingen. Hvis du vil finjustere den senere, skal du vælge **Gem kladde**.

## <a name="manage-your-measures"></a>Administrere dine målinger

Du kan finde listen over mål på siden **Målinger**.

Du kan finde oplysninger om målingstype, oprettelsesdato, status og tilstand. Når du vælger et mål på listen, kan du gennemse outputtet og hente en CSV-fil.

Hvis du vil opdatere alle dine målinger på én gang, skal du vælge **Opdater alle** uden at vælge en bestemt måling.

> [!div class="mx-imgBorder"]
> ![Handlinger til administration af enkelte målinger.](media/measure-actions.png "Handlinger til administration af enkelte målinger.")

Vælg en måling på listen for følgende indstillinger:

- Vælg målingens navn for at se detaljer om den.
- **Rediger** konfigurationen af målingen.
- **Opdater** målingen på baggrund af de seneste data.
- **Omdøb** målingen.
- **Slet** målingen.
- **Aktivere** eller **deaktivere**. Inaktive målinger opdateres ikke under en [planlagt opdatering](system.md#schedule-tab).

> [!TIP]
> Opgaver og processer indeholder [seks typer status](system.md#status-types). De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies). Du kan vælge status for en proces for at se statusdetaljer for hele jobbet. Når du har valgt **Se detaljer** for en af jobbets opgaver, finder du yderligere oplysninger: behandlingstid, sidste behandlingsdato og alle fejl og advarsler, der er knyttet til opgaven.

## <a name="next-step"></a>Næste trin

Du kan bruge eksisterende mål til at oprette [et kundesegment](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
