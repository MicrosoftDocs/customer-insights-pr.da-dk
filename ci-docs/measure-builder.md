---
title: Oprette nye måleenheder med målergeneratoren
description: Opbyg målinger fra bunden for at analysere målepunkter om virksomheden.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: f3ec86806074a12c1107648303ed2d65e97ebc69
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081182"
---
# <a name="create-new-measures-with-the-measure-builder"></a>Oprette nye måleenheder med målergeneratoren

I denne artikel forklares, hvordan du kan oprette en [ny måleenhed](measures.md) fra bunden. Med målgeneratoren kan du definere beregninger ved hjælp af regneoperatører, aggregeringsfunktioner og filtre. Du kan oprette en måleenhed med attributter fra objekter, der er relateret til objektet samlet *Kunde*.

Oprettelse af foranstaltninger i B-til-C- og B-til-B-miljøer fungerer på samme måde. Men hvis du i B-til-B-miljøet [bruger firmaer med hierarkier](relationships.md#set-up-account-hierarchies), kan du vælge at aggregere målingen på tværs af relaterede underkonti.

Du kan også hurtigt oprette en måleenhed ved at vælge mellem almindeligt anvendte og foruddefinerede mål. Du kan finde flere oplysninger under [Brug af skabelon til at opbygge målinger](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

Du kan oprette måleenheder på niveau med individuelle kunder (kundeattribut, kundemål) eller på niveauet for virksomheden/organisationen (forretningsmålet). Kundeattributten og kundemålet er to typer, du kan bruge til at spore præstationen pr. kunde. Det kan f.eks. være de samlede udgifter for hver kunde. Ved at bruge forretningsforanstaltninger kan du spore resultaterne pr. virksomhed. Det kan f.eks. være firmaets samlede omsætning.

- Kundeattribut: Opretter output som en ny attribut, der gemmes som en ny kolonne i det systemgenererede objekt, *Customer_Measure*. Når en kundeattribut opdateres, opdateres alle de andre kundeattributter i objektet *Customer_Measure* samtidig. Derudover vises kundeattributter i kundeprofilkortet. Når kundeattributten er kørt eller gemt, kan du ikke ændre den til en kundemåleenhed.

- Kundemåleenhed: Genererer output som sit eget objekt, og du kan ikke ændre det til en kundeattribut, når det er kørt eller gemt. Kundetiltag vises ikke på kundeprofilkortet.

- Forretningsmål: Genererer output som sit eget objekt og vises på startsiden i dit Customer Insights-miljø.

1. Gå til **Målinger**.

1. Vælg **Ny**, og vælg **Opret din egen**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tom konfigurationsskærm for en B-til-C-måleenhed. " lightbox="media/measure-b2c.png":::

1. Hvis du vil spore resultaterne på virksomhedsniveau, skal du skifte mellem **Måltype** og **Virksomhedsniveau**. **Kundeniveau** er valgt som standard. **Kundeniveau** tilføjer automatisk *Kunde-id*-attributten til Dimensioner, mens **Virksomhedsniveau** automatisk fjerner den.

1. Vælg aggregeringsfunktionen i rullemenuen **Vælg funktion** i konfigurationsområdet. Aggregeringsfunktionerne omfatter:
   - **Sum**
   - **Gennemsnitlig**
   - **Tælling**
   - **Antal entydige**
   - **Maks.**
   - **Min**
   - **Først**: Tager den første værdi af dataposten
   - **Sidste**: Tager den sidste værdi, der er tilføjet dataposten
   - **ArgMax**: finder den datapost, der giver maksimumværdien fra en målfunktion
   - **ArgMin**: finder den datapost, der giver minimumværdien fra en målfunktion

1. Vælg **Tilføj attribut** for at vælge de data, du skal bruge for at oprette denne måling.

   1. Vælg fanen **Attributter**.
   1. Dataobjekt: Vælg det objekt, der indeholder den attribut, du vil måle.
   1. Dataattribut: Vælg den attribut, du vil bruge i aggregeringsfunktionen for at beregne målingen. Du kan kun vælge én attribut ad gangen.
   1. Du kan også vælge en dataattribut fra en eksisterende måleenhed ved at vælge fanen **Målinger**, eller du kan også søge efter navnet på et objekt eller en måling.
   1. Vælg **Tilføj** for at føje den valgte attribut til målingen.

1. Hvis du vil oprette mere komplekse målinger, kan du tilføje flere attributter eller bruge matematikoperatorer på målfunktionen.

1. Hvis du vil tilføje filtre, skal du vælge **Filter** i konfigurationsområdet. Ved anvendelse af filtre bruges kun de poster, der svarer til filtrene, til at beregne måleenheden.
  
   1. Vælg den attribut, du vil bruge til at oprette filtre, i sektionen **Tilføj attribut** i ruden **Filtre**.
   1. Angiv filteroperatørerne for at definere filteret for alle valgte attributter.
   1. Vælg **Tilføj** for at tilføje filtrene til målingen.

1. Vælg **Dimension** for at vælge flere felter, der skal føjes som kolonner til objektet Output.

   1. Vælg **Rediger dimensioner** for at tilføje dataattributter, som du vil gruppere måleværdierne efter. Det kan f.eks. være by eller køn.
   > [!TIP]
   > Hvis du har valgt **Kundeniveau** som **Måltype** er attributten *Kunde-id* allerede tilføjet. Hvis du fjerner attributten, skifter **Måltype** til **Forretningsniveau**.
   1. Vælg **Gennemført** for at tilføje dimensioner til målingen.

1. Hvis der er værdier i dataene, som du skal erstatte med et heltal, skal du vælge **Regler**. Konfigurer reglen, og sørg for kun at vælge hele tal som erstatninger. Erstat f.eks. *null* med *0*.

1. Hvis der er flere stier mellem det dataobjekt, du har tilknyttet, og objektet *Kunde*, skal du vælge en af de identificerede [objektrelationsstier](relationships.md). Måleresultater kan variere, afhængigt af den valgte sti.

   1. Vælg **Relationssti**, og vælg den objektsti, der skal bruges til at identificere målingen. Hvis der kun er en enkelt sti til objektet *Kunde*, vises dette kontrolelement ikke.
   1. Vælg **Udført** for at anvende det valgte.

1. Hvis du vil tilføje flere beregninger for målingen, skal du vælge **Ny beregning**. Du kan kun bruge objekter på samme objektsti til nye beregninger. Flere beregninger vises som nye kolonner i objektet til måling af output.

1. Vælg den lodrette ellipse (&vellip;) i beregningen for at **duplikere**, **omdøbe** eller **fjerne** en beregning fra en måling.

1. I området **Prøveversion** kan du se dataskemaet for outputobjektet for måleenheden, herunder filtre og dimensioner. Prøveversionen reagerer dynamisk på ændringer i konfigurationen.

1. Vælg **Rediger detaljer** ud for Ikke-navngivet mål. Angiv et navn for målingen. Du kan også tilføje [koder](work-with-tags-columns.md#manage-tags) til den nye måling.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogboksen Rediger detaljer.":::

1. Vælg **Kør** for at beregne resultaterne for det konfigurerede mål. Vælg **Gem og luk**, hvis du vil bevare den aktuelle konfiguration og køre målingen senere.

1. Gå til **Målinger** for at se den måling, du netop har oprettet, på listen.

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

Du kan oprette måleenheder på niveau med individuelle kunder (kundemål) eller på niveauet for alle firmaer (forretningsmål).

- Kundemåleenhed: Genererer output som sit eget objekt. Kundetiltag vises ikke på kundeprofilkortet.

- Forretningsmål: Genererer output som sit eget objekt og vises på startsiden i dit Customer Insights-miljø.

1. Gå til **Målinger**.

1. Vælg **Ny**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tom konfigurationsskærm for en B-til-B-måleenhed. ":::

1. Vælg aggregeringsfunktionen i rullemenuen **Vælg funktion** i konfigurationsområdet. Aggregeringsfunktionerne omfatter:
   - **Sum**
   - **Gennemsnitlig**
   - **Tælling**
   - **Antal entydige**
   - **Maks.**
   - **Min**
   - **Først**: Tager den første værdi af dataposten
   - **Sidste**: Tager den sidste værdi, der er tilføjet dataposten

1. Vælg **Tilføj attribut** for at vælge de data, du skal bruge for at oprette denne måling.

   1. Vælg fanen **Attributter**.
   1. Dataobjekt: Vælg det objekt, der indeholder den attribut, du vil måle.
   1. Dataattribut: Vælg den attribut, du vil bruge i aggregeringsfunktionen for at beregne målingen. Du kan kun vælge én attribut ad gangen.
   1. Du kan også vælge en dataattribut fra en eksisterende måleenhed ved at vælge fanen **Målinger**, eller du kan også søge efter navnet på et objekt eller en måling.
   1. Vælg **Tilføj** for at føje den valgte attribut til målingen.

1. Hvis du vil oprette mere komplekse målinger, kan du tilføje flere attributter eller bruge matematikoperatorer på målfunktionen.

1. Hvis du vil tilføje filtre, skal du vælge **Filter** i konfigurationsområdet. Ved anvendelse af filtre bruges kun de poster, der svarer til filtrene, til at beregne måleenheden.
  
   1. Vælg den attribut, du vil bruge til at oprette filtre, i sektionen **Tilføj attribut** i ruden **Filtre**.
   1. Angiv filteroperatørerne for at definere filteret for alle valgte attributter.
   1. Vælg **Tilføj** for at tilføje filtrene til målingen.

1. Vælg **Dimension** for at vælge flere felter, der skal føjes som kolonner til objektet Output.

   1. Vælg **Rediger dimensioner** for at tilføje dataattributter, som du vil gruppere måleværdierne efter. Det kan f.eks. være by eller køn.
      > [!TIP]
      > Hvis du har valgt **Kundeniveau** som **Måltype** er attributten *Kunde-id* allerede tilføjet. Hvis du fjerner attributten, skifter **Måltype** til **Forretningsniveau**.
   1. Vælg **Gennemført** for at tilføje dimensioner til målingen.

1. Hvis der er værdier i dataene, som du skal erstatte med et heltal, skal du vælge **Regler**. Konfigurer reglen, og sørg for kun at vælge hele tal som erstatninger. Erstat f.eks. *null* med *0*.

1. Du kan bruge indstillingen **Akkumuler underordnede firmaer**, hvis du [bruger firmaer med hierarkier](relationships.md#set-up-account-hierarchies).
   - Hvis den er angivet til **Fra**, beregnes målingen for hvert firma. Hver konto får eget resultat.
   - Hvis den er angivet til **Til**, skal du vælge **Rediger** for at vælge firmahierarkiet i henhold til de hierarkier, der er indtaget. Målingen giver kun ét resultat, fordi den samles med underordnede firmaer.

1. Hvis der er flere stier mellem det dataobjekt, du har tilknyttet, og objektet *Kunde*, skal du vælge en af de identificerede [objektrelationsstier](relationships.md). Måleresultater kan variere, afhængigt af den valgte sti.

   1. Vælg **Relationssti**, og vælg den objektsti, der skal bruges til at identificere målingen. Hvis der kun er en enkelt sti til objektet *Kunde*, vises dette kontrolelement ikke.
   1. Vælg **Udført** for at anvende det valgte.

1. Vælg den lodrette ellipse (&vellip;) i beregningen for at **duplikere**, **omdøbe** eller **fjerne** en beregning fra en måling.

1. I området **Prøveversion** kan du se dataskemaet for outputobjektet for måleenheden, herunder filtre og dimensioner. Prøveversionen reagerer dynamisk på ændringer i konfigurationen.

1. Vælg **Rediger detaljer** ud for Ikke-navngivet mål. Angiv et navn for målingen. Du kan også tilføje [koder](work-with-tags-columns.md#manage-tags) til den nye måling.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogboksen Rediger detaljer.":::

1. Vælg **Kør** for at beregne resultaterne for det konfigurerede mål. Vælg **Gem og luk**, hvis du vil bevare den aktuelle konfiguration og køre målingen senere.

1. Gå til **Målinger** for at se den måling, du netop har oprettet, på listen.
