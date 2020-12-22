---
title: Opret og rediger målinger
description: Definer kunderelaterede målinger for at analysere og afspejle ydeevnen af bestemte forretningsområder.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405451"
---
# <a name="define-and-manage-measures"></a>Definere og administrere målinger

**Målinger** repræsenterer nøgletal (KPI'er), der afspejler ydeevnen og tilstanden af bestemte forretningsområder. Målgruppen Insights giver en intuitiv oplevelse til opbygning af forskellige typer målpunkter ved hjælp af en forespørgselsgenerator, der ikke kræver, at du koder eller validerer dine målpunkter manuelt. Du kan spore dine forretningsmålinger på **startsiden**, se målinger for bestemte kunder på **Kundekort** og bruge målinger til at definere kundesegmenter på siden **Segmenter**.

## <a name="create-a-measure"></a>Oprette en måling

I dette afsnit gennemgås, hvordan du opretter en måling fra bunden. Du kan oprette målinger med data fra flere datakilder, der er forbundet via kundeobjektet. Der gælder nogle [tjenestebegrænsninger](service-limits.md).

1. Gå til **Målinger** i målgruppen Insights.

2. Vælg **Ny måling**.

3. Vælg målingen **Type**:

   - **Kundeattribut**: Et enkelt felt pr. kunde, der afspejler en score, værdi eller tilstand for kunden. Kundeattributter oprettes som attributter i et nyt systemgenereret objekt, der kaldes **Customer_Measure**.

   - **Kundemåling**: Indsigt i kundeadfærd med fordeling efter valgte dimensioner. Der oprettes et nyt objekt for hver måling, der muligvis har flere poster pr. kunde.

   - **Forretningsmæssig måling**: Sporer din virksomheds præstationer og tilstand. Forretningsmæssige målinger kan have to forskellige output: Et numerisk output, der vises på **Startside**, eller et nyt objekt, som du finder på siden **Objekter**.

4. Angiv et **Navn** og et valgfrit **Vist navn**, og vælg derefter **Næste**.

5. I sektionen **Objekt** skal du vælge det første objekt på rullelisten. På dette tidspunkt skal du finde ud af, om der skal bruges yderligere objekter som en del af din målingsdefinition.

   > [!div class="mx-imgBorder"]
   > ![Definition af måling](media/measure-definition.png "Definition af måling")

   Hvis du vil tilføje flere objekter, skal du vælge **Tilføj objekt** og vælge de objekter, du vil bruge til målingen.

   > [!NOTE]
   > Du kan kun vælge objekter, der har en relation til dit startobjekt. Du kan finde flere oplysninger om definition af relationer under [Relationer](relationships.md).

6. Du kan også konfigurere variabler. Vælg **Ny variabel** i sektionen **Variabler**.

   Variabler er beregninger, der er foretaget på de valgte poster. F.eks. opsummering af POS og onlinesalg for hver af dine kunders poster.

7. Angiv et **Navn** til variablen.

8. Vælg et felt i området **Udtryk**, hvor du vil begynde at foretage beregningen.

9. Skriv et udtryk i området **Udtryk**, mens du vælger flere felter, der skal inkluderes i beregningen.

   > [!NOTE]
   > I øjeblikket understøttes kun matematiske udtryk. Variabel beregning understøttes heller ikke for objekter fra forskellige [objektstier](relationships.md).

10. Vælg **Udført**.

11. I sektionen **Definition af måling** kan du definere, hvordan de valgte objekter og beregnede variabler skal samles i et nyt målingsobjekt eller en ny attribut.

12. Vælg **Ny dimension**. Du kan betragte en dimension som en *gruppér efter*-funktion. Dataoutputtet for målingsobjektet eller attributten grupperes efter alle de definerede dimensioner.

    > [!div class="mx-imgBorder"]
    > ![Vælge aggregatcyklus](media/measures-businessreport-measure-definition2.png "Vælge aggregatcyklus")

    Vælg eller angiv følgende oplysninger som en del af dimensionens definition:

    - **Objekt**: Hvis du definerer et målingsobjekt, skal det inkludere mindst én attribut. Hvis du definerer en målingsattribut, medtages der som standard kun én attribut. Denne indstilling bruges til at vælge det objekt, der indeholder den pågældende attribut.
    - **Felt**: Vælg den specifikke attribut, der skal inkluderes, enten i målingsenheden eller -attributten.
    - **Bucket**: Vælg, om du vil samle data på en daglig, månedlig eller årlig basis. Det er kun nødvendigt at bruge feltet, hvis du har valgt en Datotype-attribut.
    - **Som**: Definerer navnet på det nye felt.
    - **Vist navn**: Definerer feltets viste navn.

    > [!NOTE]
    > Din forretningsmåling gemmes som et objekt med et enkelt nummer og vises på **Startsiden**, medmindre du føjer flere dimensioner til målingen. Når der er tilføjet flere dimensioner, vises målingen *ikke* på **Startsiden**.

13. Du kan også vælge at tilføje sammenlægningsfunktioner. Enhver sammenlægning, du opretter, resulterer i en ny værdi i målingsobjektet eller -attributten. Understøttede sammenlægningsfunktioner er: **Min.**, **Maks.**, **Gennemsnit**, **Median**, **Sum**, **Antal entydige**, **Første** (tager den første post i en dimensionsværdi) og **Sidste** (tager den sidste post, der er føjet til en dimensionsværdi).

14. Vælg **Gem** for at gemme dine ændringer af målingen.

## <a name="manage-your-measures"></a>Administrere dine målinger

Når du har oprettet mindst ét mål, kan du se en liste over mål på siden **Mål**.

Du kan finde oplysninger om målingstype, forfatter, oprettelsesdato og -klokkeslæt, sidste redigeringsdato og -klokkeslæt, status (om målingen er aktiv, inaktiv eller mislykket) og dato og klokkeslæt for seneste opdatering. Når du vælger en måling på listen, kan du få vist et eksempel på outputtet.

Hvis du vil opdatere alle dine målinger på én gang, skal du vælge **Opdater alle** uden at vælge en bestemt måling.

> [!div class="mx-imgBorder"]
> ![Handlinger til administration af enkelte målinger](media/measure-actions.png "Handlinger til administration af enkelte målinger")

Du kan også vælge en måling på listen og udføre en af følgende handlinger:

- Vælg målingens navn for at se detaljer om den.
- **Rediger** konfigurationen af målingen.
- **Omdøb** målingen.
- **Slet** målingen.
- Vælg ellipsen (...), og vælg **Opdater** for at starte opdateringsprocessen for målingen.
- Vælg ellipsen (...), og **Hent** for at hente en. CSV-fil for målingen.

> [!TIP]
> Opgaver og processer indeholder [seks typer status](system.md#status-types). De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies). Du kan vælge status for en proces for at se statusdetaljer for hele jobbet. Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.

## <a name="next-step"></a>Næste trin

Du kan bruge eksisterende målinger til at oprette dit første kundesegment på siden **Segmenter**. Du kan finde flere oplysninger under [Segmenter](segments.md).
