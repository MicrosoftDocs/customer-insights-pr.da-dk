---
title: Udfyld delvise data ved hjælp af forudsigelser
description: Brug af forudsigelser til at udfylde ufuldstændige kundedata.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 31b9b1b709540896c1dbc19f974df4ab056a7b8d
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692520"
---
# <a name="complete-your-partial-data-with-predictions"></a>Fuldføre delvise data med forudsigelser

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Med forudsigelser kan du nemt oprette forventede værdier, der kan forbedre forståelsen af en kunde. På siden **Intelligens** > **Forudsigelser** kan du vælge **Mine forudsigelser** for at se forudsigelser, som du har konfigureret i andre dele af målgruppen Insights, og give dig mulighed for at tilpasse dem yderligere.

> [!NOTE]
> Du kan ikke bruge denne funktion, hvis dit miljø bruger Azure Data Lake Gen 2-lager.
>
> Funktionen til forudsigelser bruger automatiserede metoder til at evaluere data og foretage forudsigelser på baggrund af disse data, og det er derfor muligt at bruge denne funktion som profileringsmetode, som dette udtryk er defineret i henhold til generel forordning om databeskyttelse ("GDPR"). Kundens brug af denne funktion til behandling af data kan være underlagt GDPR eller andre love eller bestemmelser. Du er ansvarlig for at sikre, at brugen af Dynamics 365 Customer Insights, herunder forudsigelser, overholder alle gældende love og bestemmelser, herunder lovgivning vedrørende beskyttelse af personlige oplysninger, personlige data, biometriske data, databeskyttelse og fortrolighed i kommunikationen.

## <a name="prerequisites"></a>Forudsætninger

Før din organisation kan bruge funktionen til forudsigelser, skal følgende forudsætninger være opfyldt:

1. Din organisation har en forekomst [konfigureret i Microsoft Dataverse](/ai-builder/build-model#prerequisites), og den er i samme organisation som Customer Insights.

2. Dit publikum indsigtsmiljø er knyttet til din Dataverse-instans.

Hvis du [opretter det første miljø](get-started-paid.md), skal du konfigurere det i dialogboksen **Opret et miljø** og vælge **Avanceret**. Hvis du allerede har oprettet et miljø, skal du gå til indstillingerne og vælge **Avanceret**. I begge tilfælde skal du i sektionen **Brug forudsigelser** angive den Dataverse-forekomst for den URL-adresse, du vil tilknytte miljøet til.

## <a name="create-a-prediction-in-the-customer-entity"></a>Opret en forudsigelse i kundeobjektet

1. Gå til **Data** > **Objekter** i målgruppen Insights.

2. Vælg objektet **Kunde**.

3. Vælg fanen **Felter** i objektet **Kunde: CustomerInsights**.

4. Find det attributnavn, du vil forudsige værdier for, og vælg derefter ikonet **Oversigt** i kolonnen **Oversigt**.
   > [!div class="mx-imgBorder"]
   > ![Ikonet Oversigt.](media/intelligence-overviewicon.png "Ikonet Oversigt")

5. Hvis der er et stort antal manglende værdier for attributten, skal du vælge **Forudsige manglende værdier** for at fortsætte med din forudsigelse.
   > [!div class="mx-imgBorder"]
   > ![Oversigtsstatus med knappen Forudsige manglende værdier vist.](media/intelligence-overviewpredictmissingvalues.png "Oversigtsstatus med knappen Forudsige manglende værdier vist")

6. Angiv et **Vist navn** og et **Navn på outputobjekt** for resultaterne af forudsigelsen.

7. En liste med indstillinger, der er udfyldt på forhånd, viser, hvor du kan knytte værdierne til en forudsagt kategori. I dette tilfælde er de eneste kategoriindstillinger 0 eller 1, da de knyttes til den sande/falske eller binære karakter for forudsigelse. I kolonnen Kategori skal du tilknytte de feltværdier, du vil have klassificeret som "0" i den endelige forudsigelse, til "0", og de elementer, du vil klassificere som "1" i den endelige forudsigelse, til "1".
   > [!div class="mx-imgBorder"]
   > ![Eksempel, der viser tilknyttede feltværdier for kategorier.](media/intelligence-categorymapping.png "Eksempel, der viser tilknyttede feltværdier for kategorier")

8. Vælg **Udført**,så forudsigelsen vil blive behandlet. Behandlingen vil tage et stykke tid, afhængigt af datastørrelsen og kompleksiteten af dataene. Resultaterne vil være tilgængelige i et nyt objekt, der er baseret på det **Navn på outputobjekt** for forudsigelsen, du har oprettet.

## <a name="create-a-prediction-while-creating-a-segment"></a>Oprette en forudsigelse under oprettelse af et segment

Det er også muligt at forudsige manglende værdier for en bestemt attribut efter eget valg, når der oprettes et segment. Specielt, når du hurtigt opretter et segment baseret på enten dit samlede kundeobjekt eller Customer_Measure-objektet.

Som en del af dette flow vælger du en bestemt attribut til at basere dit segment på, f.eks. kundetilfredshed eller købsbeløb. Når segmentet oprettes, foreslår systemet en metode til at forudsige manglende værdier for denne attribut.

1. Gå til **Segmenter**, og vælg feltet **Profiler** i målgruppen Insights.

2. Vælg et **Felt**, som du vil oprette et segment på, og vælg en **Operator**, og vælg derefter **Gennemse**.

3. Angiv et **Navn** og et **Vist navn** til segmentet.

4. Vælg **Gem**.

5. Hvis det segment, du har oprettet, har ufuldstændige data i kildefeltet, kan du vælge at forudsige de manglende værdier.
   > [!div class="mx-imgBorder"]
   > ![Knappen Forudsigelse.](media/segments-predictoption.png "Knappen Forudsigelse")

6. Angiv et **Vist navn** og et **Navn på outputobjekt** for resultaterne af forudsigelsen.

7. Vælg **Udført**. Forudsigelsen oprettes hurtigt i et nyt objekt med det navn, du har angivet som **Navn på outputobjekt**.

## <a name="view-a-prediction"></a>Se en forudsigelse

1. Gå til **Intelligens** > **Forudsigelser** > **Mine forudsigelser** i målgruppen Insights.

2. Vælg den forudsigelse, du vil gennemse.

3. Vælg ellipsen i kolonnen **Handlinger**, og vælg **Vis**.

4. Der vises en række datapunkter i visningen af din forudsigelse.
   > [!div class="mx-imgBorder"]
   > ![Siden Forudsigelser.](media/intelligence-predictionsviewpage.png "Siden Forudsigelser")

   - **Forudsigelige værdier** viser den tilknytning, du har oprettet under tilknytningsfasen af feltværdien til kategori. Det er de værdier i dit datasæt, der er knyttet til en bestemt kategori.
   -**Bedste indflydelse** er de faktorer i dit datasæt, som mest sandsynligt vil have indflydelse på forudsigelsens konfidens til, at din feltværdi er knyttet til en bestemt kategori.
   - **Ydeevne** angiver, hvordan forudsigelser udføres. Du kan få mere at vide ved at vælge linket.
   - **Se eksempel** viser eksempler på outputdatasæt fra forudsigelsen og sandsynligheden, eller vores konfidens, for den forudsagte værdi, hvor 0 er usikker, og 1 er sikker.

## <a name="update-a-prediction"></a>Opdatere en forudsigelse

1. Gå til **Intelligens** > **Forudsigelser** > **Mine forudsigelser** i målgruppen Insights.

2. Vælg den forudsigelse, du vil opdatere, og vælg ikonet **Opdater**.

3. Forudsigelsen vil blive planlagt til behandling. Du kan se, hvornår den sidst blev opdateret, i kolonnen **Opdateret** på siden **Forudsigelser**.

## <a name="edit-a-prediction"></a>Redigere en forudsigelse

Når du har oprettet en forudsigelse, kan du tilpasse modellen i AI Builder for at øge effektiviteten for din model.  

1. Gå til **Intelligens** > **Forudsigelser** > **Mine forudsigelser** i målgruppen Insights.

2. Vælg den forudsigelse, som du vil redigere.

3. Vælg ellipsen i kolonnen **Handlinger**, og vælg **Vis**.

4. Vælg **Tilpas i AI Builder**.

5. Opdater din model i AI Builder. [Få mere at vide om administration af modeller i AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

Den næste kørsel af forudsigelsen bruger den opdaterede model, du har oprettet.

> [!NOTE]
> Nye modeller, der er oprettet i AI Builder, vises ikke i målgruppen Insights, medmindre modellen er oprettet ud fra de oplevelser, der er nævnt ovenfor.

## <a name="remove-a-prediction"></a>Fjerne en forudsigelse

1. Gå til **Intelligens** > **Forudsigelser** > **Mine forudsigelser** i målgruppen Insights.

2. Vælg den forudsigelse, du vil slette.

3. Vælg ellipsen i kolonnen **Handlinger**, og vælg **Slet**.

4. Bekræft sletningen.

## <a name="troubleshooting"></a>Fejlfinding

Hvis du ikke kan fuldføre Dataverse-tilknytningsprocessen på grund af en fejl, kan du prøve at fuldføre processen manuelt. Der er to kendte problemer, der kan opstå i tilknytningsprocessen:

- Løsningen til tilføjelsesprogrammet Customer Card er ikke installeret.
    1. Udfør instruktionerne for at [installere og konfigurere løsningen](customer-card-add-in.md).

- App-tilladelser tildeles ikke.
    1. Gå til [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Vælg **Miljøer**.
    1. Vælg ellipsen ud for det miljø, du vil føje til tilladelsen til, og vælg **Indstillinger**.
    1. Udvid **Brugere + tilladelser**, og vælg **Brugere**.
    1. Vælg **+ Ny**, og vælg **Bruger**.
    1. Vælg **Programbruger**, hvis indstillingen ikke allerede er valgt, og angiv følgende oplysninger:
        - **Brugernavn:** cihelp@microsoft.com
        - **Program-id:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Fornavn:** Kunde
        - **Efternavn:** Insights
        - **Primær mail:** cihelp@microsoft.com
    1. Vælg **Gem og luk**.
    1. Vælg den bruger, du lige har oprettet.
    1. Vælg **Administrer roller** på menulinjen foroven.
    1. Vælg **Systemadministrator**, og vælg derefter **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]