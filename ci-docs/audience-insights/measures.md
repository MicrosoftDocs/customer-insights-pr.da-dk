---
title: Oprette og administrere målinger
description: Definer foranstaltninger, der skal analysere og afspejle ydeevnen i virksomheden.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269921"
---
# <a name="define-and-manage-measures"></a>Definere og administrere målinger

Foranstaltninger hjælper dig med at få en bedre forståelse af kundeadfærd og virksomhedens ydeevne ved at hente relevante værdier fra [ensartede profiler](data-unification.md). En virksomhed vil f.eks. se det *samlede forbrug pr. kunde* for at forstå den enkelte kundes købshistorik. Du kan også måle *firmaets samlede* salg for at få en forståelse af den samlede omsætning i hele virksomheden.  

Målinger oprettes ved hjælp af målegeneratoren, en platform til dataforespørgsel med forskellige operatorer og simple tilknytningsindstillinger. Du kan filtrere dataene, gruppere resultater, registrere [objektrelationsstier](relationships.md) og gennemse outputtet.

Brug målegeneratoren til at planlægge forretningsaktiviteter ved at forespørge om kundedata og udtrække indsigt. Hvis du f.eks. opretter et mål for det *samlede forbrug pr. kunde* og det *samlede afkast pr. kunde*, kan du identificere en gruppe kunder med et højt forbrug, men et højt afkast. Du kan [oprette et segment](segments.md) for at opnå de bedste handlinger. 

## <a name="create-a-measure"></a>Oprette en måling

Dette afsnit indeholder en gennemgang af, hvordan du opretter en ny måling fra bunden. Du kan oprette en måling med dataattributter fra dataobjekter, der har en relation konfigureret til at oprette forbindelse til objektet Kunde. 

1. Gå til **Målinger** i målgruppen Insights.

1. Vælg **Ny**.

1. Vælg **Rediger navn**, og angiv et **Navn** til målingen. 
   > [!NOTE]
   > Hvis konfigurationen af den nye måleenhed kun indeholder to felter, f.eks. CustomerID og én beregning, føjes outputtet som en ny kolonne til det systemgenererede objekt, der kaldes Customer_Measure. Du kan også se målingens værdi i den samlede kundeprofil. Andre foranstaltninger opretter deres egne objekter.

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

1. Hvis der er flere stier mellem det dataobjekt, du har tilknyttet, og objektet Kunde, skal du vælge en af de identificerede [objektrelationsstier](relationships.md) Måleresultater kan variere, afhængigt af den valgte sti.
   1. Vælg **Dataindstillinger**, og vælg den objektsti, der skal bruges til at identificere din måling.
   1. Vælg **Udført** for at anvende det valgte. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Vælg objektsti til målingen.":::

1. Hvis du vil tilføje flere beregninger for målingen, skal du vælge **Ny beregning**. Du kan kun bruge objekter på samme objektsti til nye beregninger. Flere beregninger vises som nye kolonner i objektet til måling af output.

1. Vælg **...** i beregningen at **Dupliker**, **Omdøb** eller **Fjern** for en beregning fra en måleenhed.

1. I området **Prøveversion** kan du se dataskemaet for outputobjektet for måleenheden, herunder filtre og dimensioner. Prøveversionen reagerer dynamisk på ændringer i konfigurationen.

1. Vælg **Kør** for at beregne resultaterne for det konfigurerede mål. Vælg **Gem og luk**, hvis du vil bevare den aktuelle konfiguration og køre målingen senere.

1. Gå til **Målinger** for at se den måling, du netop har oprettet, på listen.

## <a name="manage-your-measures"></a>Administrere dine målinger

Efter at [oprette en måling](#create-a-measure) vises en liste over målinger på siden **Målinger**.

Du kan finde oplysninger om målingstype, oprettelsesdato, status og tilstand. Når du vælger en måling på listen, kan du gennemse outputtet og hente en .CSV-fil.

Hvis du vil opdatere alle dine målinger på én gang, skal du vælge **Opdater alle** uden at vælge en bestemt måling.

> [!div class="mx-imgBorder"]
> ![Handlinger til administration af enkelte målinger](media/measure-actions.png "Handlinger til administration af enkelte målinger")

Vælg en måling på listen for følgende indstillinger:

- Vælg målingens navn for at se detaljer om den.
- **Rediger** konfigurationen af målingen.
- **Opdater** målingen på baggrund af de seneste data.
- **Omdøb** målingen.
- **Slet** målingen.
- **Aktivere** eller **deaktivere**. Inaktive målinger opdateres ikke under en [planlagt opdatering](system.md#schedule-tab).

> [!TIP]
> Opgaver og processer indeholder [seks typer status](system.md#status-types). De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies). Du kan vælge status for en proces for at se statusdetaljer for hele jobbet. Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.

## <a name="next-step"></a>Næste trin

Du kan benytte eksisterende foranstaltninger til at oprette [et kundesegment](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]