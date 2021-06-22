---
title: Forudsigelse af abonnementsafgang
description: Du kan forudsige, om der er risiko for, at en kunde ikke længere vil bruge dit firmas produkter eller services.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 4e7065b61940ef0d7b2a30f96f6225df29e30383
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095641"
---
# <a name="subscription-churn-prediction-preview"></a>Forudsigelse af abonnementsafgang (prøveversion)

Forudsigelse af abonnementsafgang hjælper dig med at forudsige, om der er risiko for, at en kunde ikke længere vil bruge dit firmas produkter eller services. Du kan oprette en ny forudsigelse af abonnementsafgang på siden **Intelligens** > **Forudsigelser**. Vælg **Mine forudsigelser** for at få vist andre forudsigelser, du har oprettet.

> [!TIP]
> Prøv selvstudiet for at få en abonnementsrelateret afgangsforudsigelse ved at bruge eksempeldata: [Abonnementsrelateret forudsigelse om afgang (prøveversion) eksempelvejledning](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Forudsætninger

- Mindst [Bidragyder-tilladelser](permissions.md).
- Forretningsviden for at forstå, hvad afgang betyder for din virksomhed. Vi understøtter tidsbaserede afgangsdefinitioner, hvilket vil sige, at en kundes afgang forventes et stykke tid efter, at abonnementet er ophørt.
- Data om dine abonnementer og deres historik:
    - Abonnements-id'er for at skelne mellem abonnementer.
    - Kunde-id'er, der matcher dine kunders abonnementer.
    - De abonnementshændelsesdatoer, der definerer startdatoer, slutdatoer og de datoer, hvor abonnementshændelserne forekom.
    - Abonnementsoplysninger for at angive, om det er et tilbagevendende abonnement, og hvor ofte det skal fornys.
    - Semantisk dataskema for abonnementer kræver følgende oplysninger:
        - **Abonnements-id:** Et entydigt id for et abonnement.
        - **Abonnementets slutdato:** Den dato, abonnementet udløber for kunden.
        - **Abonnementets startdato:** Den dato, abonnementet starter for kunden.
        - **Transaktionsdato:** Den dato, hvor et abonnement er ændret. F.eks. køber eller opsiger en kunde et abonnement.
        - **Er det et tilbagevendende abonnement:** Et boolesk sand/falsk-felt, der bestemmer, om abonnementet fornyes med det samme abonnements-id uden kundens indgriben.
        - **Gentagelseshyppighed (i måneder):** For tilbagevendende abonnementer er det perioden, som abonnementet fornyes for. Den repræsenteres i antal måneder. Et årsabonnement, der automatisk fornys for en kunde hvert år for endnu et andet, har værdien 12.
        - (Valgfrit) **Abonnementsbeløb:** Det valutabeløb, kunden betaler i forbindelse med fornyelsen af abonnementet. Det kan være med til at identificere mønstre for forskellige niveauer af abonnementer.
- Data om kundeaktiviteter:
    - Aktivitets-id'er, der skal skelne mellem aktiviteter af samme type.
    - Kunde-id'er, der knytter aktiviteter til dine kunder.
    - Aktivitetsoplysninger, der indeholder navnet på og datoen for aktiviteten.
    - Det semantiske dataskema for kundeaktiviteter omfatter:
        - **Primær nøgle:** Et entydigt id for en aktivitet. Et besøg på et websted eller en forbrugspost, der viser, at kunden har set et afsnit af et TV-show.
        - **Tidsstempel:** Dato og klokkeslæt for hændelsen, der identificeres af den primære nøgle.
        - **Hændelse:** Navnet på den hændelse, du vil bruge. Et felt kaldes f.eks. "UserAction" i en videostreamingsservice med værdien "Set".
        - **Detaljer:** Detaljerede oplysninger om hændelsen. Et felt kaldes f.eks. "ShowTitle" i en videostreamingsservice med værdien af en video, som en kunde har set.
- Forslåede datakarakteristika:
    - Tilstrækkelige historiske data: Abonnementsdata for mindst det dobbelte af det valgte tidsvindue. Helst to til tre års abonnementsdata.
    - Abonnementsstatus: Data omfatter aktive og inaktive abonnementer for hver kunde, så der er flere poster pr. kunde-id.
    - Antal kunder: Mindst 10 kundeprofiler, helst mere end 1.000 entydige kunder. Modellen kan ikke bruges af færre end 10 kunder og med utilstrækkelige historiske data.
    - Datafuldførelse: Mindre end 20 % af de manglende værdier i datafeltet for det angivne objekt.
   
   > [!NOTE]
   > Du skal bruge mindst to aktivitetsposter på 50 % af de kunder, du vil beregne kundeafgang for.

## <a name="create-a-subscription-churn-prediction"></a>Oprette en abonnementsafgang (prøveversion)

1. Gå til **Intelligens** > **Forudsigelser** i målgruppen insights.
1. Vælg feltet **Model for abonnementsafgang (prøveversion)**, og vælg **Brug denne model**.
   > [!div class="mx-imgBorder"]
   > ![Modelfelt for abonnementsafgang med knappen Brug denne model](media/subscription-churn-usethismodel.PNG "Modelfelt for abonnementsafgang med knappen Brug denne model")

### <a name="name-model"></a>Navngiv model

1. Angiv et navn til modellen for at adskille den fra andre modeller.
1. Angiv et navn til outputenheden udelukkende med bogstaver og tal uden mellemrum. Det er det navn, som modelobjektet skal bruge. Vælg derefter **Næste**.

### <a name="define-customer-churn"></a>Definer kundeafgang

1. Angiv antallet af **Dage, siden abonnement sluttede**, som din virksomhed betragter som en kunde, der ikke længere er kunde. Denne periode er typisk velegnet til forretningsaktiviteter som tilbud eller andre marketingtiltag, der forsøger at forhindre tab af kunden.
1. Angiv det antal **Dage, der skal undersøges for at forudsige kundeafgang** for at angive et interval, hvor kundeafgang skal forudsiges. F.eks. for at forudsige risikoen for kundeafgang i løbet af de næste 90 dage for at justere din marketingindsats. Forudsigelse af afgangsrisiko i kortere eller længere perioder kan gøre det mere problematisk at adressere faktorer i din afgangsrisikoprofil, afhængigt at dine specifikke forretningskrav. Vælge **Næste** for at fortsætte
   >[!TIP]
   > Du kan til enhver tid vælge **Gem og Luk** for at gemme forudsigelsen som en kladde. Du kan se kladdeforudsigelsen under fanen **Mine forudsigelser** for at fortsætte.

### <a name="add-required-data"></a>Tilføj påkrævede data

1. Vælg **Tilføj data** for **Abonnementshistorik**, og vælg det objekt, der indeholder de oplysninger om abonnements historik, som er beskrevet i [forudsætningerne](#prerequisites).
1. Hvis nedenstående felter ikke er udfyldt, skal du konfigurere relationen fra dit abonnementshistorikobjekt til kundeobjektet.
    1. Vælg objektet **Abonnementshistorik**.
    1. Vælg det **Felt**, der identificerer kunden i objektet for abonnementshistorik. Det skal relateres til kundeobjektets primære kunde-id.
    1. Vælg det **Kundeobjekt**, der stemmer overens med dit primære kundeobjekt.
    1. Angiv et navn, der beskriver relationen.
       > [!div class="mx-imgBorder"]
       > ![Siden med abonnementshistorik, der viser oprettelsen af en relation til en kunde](media/subscription-churn-subscriptionhistoryrelationship.PNG "Siden med abonnementshistorik, der viser oprettelsen af en relation til en kunde")
1. Vælg **Næste**.
1. Knyt de semantiske felter til attributter i dit abonnementshistorikobjekt, og vælg **Gem**. Du kan finde beskrivelser af felterne under [forudsætningerne](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Siden med abonnementshistorik, der viser semantiske attributter, som er knyttet til felter i det valgte objekt for abonnementshistorik](media/subscription-churn-subscriptionhistorymapping.PNG "Siden med abonnementshistorik, der viser semantiske attributter, som er knyttet til felter i det valgte objekt for abonnementshistorik")
1. Vælg **Tilføj data** for **Kundeaktiviteter**, og vælg det objekt, der indeholder de oplysninger om kundeaktiviteter, som er beskrevet i forudsætningerne.
1. Vælg en aktivitetstype, der svarer til den type kundeaktivitet, du konfigurerer.  Vælg **Opret ny**, og angiv et navn, hvis du ikke kan se en indstilling, der svarer til den aktivitetstype, du har brug for.
1. Du skal konfigurere relationen fra kundeaktivitetsobjektet til kundeobjektet.
    1. Vælg det felt, der identificerer kunden i tabellen for kundeaktivitet, som kan relateres direkte til det primære kunde-id for kundeobjektet.
    1. Vælg det kundeobjekt, der stemmer overens med dit primære kundeobjekt.
    1. Angiv et navn, der beskriver relationen.
1. Vælg **Næste**.
1. Knyt de semantiske felter til attributter i dit kundeaktivitetsobjekt, og vælg **Gem**. Du kan finde beskrivelser af felterne under [forudsætningerne](#prerequisites).
1. (Valgfrit) Hvis du har andre kundeaktiviteter, som du vil medtage, skal du gentage trinnene ovenfor.
   > [!div class="mx-imgBorder"]
   > ![Definere objektrelationen](media/subscription-churn-customeractivitiesmapping.PNG "Siden med kundeaktiviteter, der viser semantiske attributter, som er knyttet til felter i det valgte objekt for kundeaktivitet")
1. Vælg **Næste**.

### <a name="set-schedule-and-review-configuration"></a>Angive konfiguration for planlægning og evaluering

1. Angiv en hyppighed for at omskole modellen. Denne indstilling er vigtig, hvis du vil opdatere nøjagtigheden af forudsigelserne, efterhånden som nye data indsættes i målgruppen Insights. De fleste virksomheder kan omskole én gang om måneden og opnå en god præcision af deres forudsigelse.
1. Vælg **Næste**.
1. Gennemgå konfigurationen. Du kan gå tilbage til en hvilken som helst del af forudsigelseskonfigurationen ved at vælge **Rediger** under den viste værdi. Du kan også vælge et konfigurationstrin i statusindikatoren.
1. Hvis alle værdier er konfigureret korrekt, skal du vælge **Gem og kør** for at starte forudsigelsesprocessen. Du kan se statussen for dine forudsigelser under fanen **Mine forudsigelser**. Det kan tage flere timer, før processen er fuldført, afhængigt af mængden af data, der bruges i forudsigelsen.

## <a name="review-a-prediction-status-and-results"></a>Gennemgå en forudsigelses status og resultater

1. Gå til fanen **Mine forudsigelser** i **Intelligens** > **forudsigelser**.
   > [!div class="mx-imgBorder"]
   > ![Visning af siden Mine forudsigelser](media/subscription-churn-mypredictions.PNG "Visning af siden Mine forudsigelser")
1. Vælg den forudsigelse, du vil gennemse.
   - **Forudsigelsesnavn:** Navnet på forudsigelsen, der blev angivet under oprettelsen.
   - **Forudsigelsestype:** Den type model, der bruges til forudsigelsen
   - **Outputobjekt:** Navnet på det objekt, som outputtet af forudsigelsen skal gemmes i. Du kan finde et objekt med dette navn på **Data** > **Objekter**.    
     I outputobjektet er *ChurnScore* den anslåede sandsynlighed for kundeafgang, og *IsChurn* er en binær etiket baseret på *ChurnScore* med en tærskelværdi på 0,5. Standardgrænsen fungerer muligvis ikke i dit scenarie. [Opret et nyt segment](segments.md#create-a-new-segment) med din foretrukne grænseværdi.
   - **Forudsagt felt:** Dette felt udfyldes kun for visse typer forudsigelser og bruges ikke i abonnementets afgangsforudsigelse.
   - **Status:** Den aktuelle status for forudsigelsens kørsel.
        - **Sat i kø:** Forudsigelsen venter i øjeblikket på, at andre processer skal køre.
        - **Opdaterer:** Forudsigelse kører i øjeblikket "score"-fasen i behandlingen af de resultater, der vil blive overført til outputenheden.
        - **Mislykkedes:** Forudsigelsen mislykkedes. Vælg **Logge** for at få flere oplysninger.
        - **Lykkedes:** Forudsigelsen blev fuldført. Vælg **Vis** under de lodrette ellipser for at gennemgå forudsigelse.
   - **Redigeret:** Den dato, hvor konfigurationen af forudsigelse blev ændret.
   - **Sidst opdateret:** Den dato, hvor forudsigelsen opdaterede resultater i outputenheden.
1. Vælg de lodrette ellipser ud for den forudsigelse, du vil gennemgå resultaterne for, og vælg **Vis**.
   > [!div class="mx-imgBorder"]
   > ![Visning af indstillinger i menuen med lodrette ellipser for en forudsigelse, herunder redigering, opdatering, visning, logfiler og sletning](media/subscription-churn-verticalellipses.PNG "Visning af indstillinger i menuen med lodrette ellipser for en forudsigelse, herunder redigering, opdatering, visning, logfiler og sletning")
1. Der findes tre primære sektioner med data på resultatsiden:
    1. **Træningsmodellens ydeevne:** A, B eller C er mulige scorer. Denne score ydeevnen af forudsigelsen og kan hjælpe dig med at træffe beslutningen om at bruge de resultater, der er gemt i outputobjektet.
        - Scorer bestemmes ud fra følgende regler:
            - **A**, når modellen præcist har forudset mindst 50 % af det samlede antal forudsigelser, og når procentsatsen for præcise forudsigelser for kunder, der er mistet, er større end den historiske gennemsnitlige tabssats på mindst 10 % af den historiske gennemsnitlige tabssats.
            - **B**, når modellen præcist har forudset mindst 50 % af det samlede antal forudsigelser, og når procentsatsen for præcise forudsigelser for kunder, der er mistet, er op til 10 % større end den historiske gennemsnitlige tabssats af den historiske gennemsnitlige tabssats.
            - **C** når modellen præcist har forudset mindre end 50 % af det samlede antal forudsigelser, eller når procentsatsen for præcise forudsigelser for kunder, der er mistet, er mindre end den historiske gennemsnitlige tabssats.
               > [!div class="mx-imgBorder"]
               > ![Visning af modellens ydeevneresultat](media/subscription-churn-modelperformance.PNG "Visning af modellens ydeevneresultat")
    1. **Sandsynlighed for afgang (antal kunder):** Kundegrupper baseret på deres forudsagte risiko for afgang. Du kan senere bruge disse data, hvis du vil oprette et kundesegment med stor risiko for afgang. Sådanne segmenter hjælper dig med at forstå, hvor din grænse skal være for segmentmedlemskab.
       > [!div class="mx-imgBorder"]
       > ![Graf, der viser fordelingen af afgangsresultater, opdelt i intervaller fra 0 - 100 %](media/subscription-churn-resultdistribution.PNG "Graf, der viser fordelingen af afgangsresultater, opdelt i intervaller fra 0 - 100 %")
    1. **Mest indflydelsesrige faktorer:** Der er mange faktorer, som tages i betragtning ved oprettelsen af din forudsigelse. Hver af faktorerne får beregnet deres betydning for de samlede forudsigelser, som en model opretter. Du kan bruge disse faktorer til at validere dine forudsigelsesresultater. Du kan også bruge oplysningerne senere til at [oprette segmenter](segments.md), der kan være med til at påvirke afgangsrisikoen for kunderne.
       > [!div class="mx-imgBorder"]
       > ![Liste, der viser indflydelsesrige faktorer og deres betydning ved forudsigelse af afgangsresultatet](media/subscription-churn-influentialfactors.PNG "Liste, der viser indflydelsesrige faktorer og deres betydning ved forudsigelse af afgangsresultatet")

## <a name="manage-predictions"></a>Administrere forudsigelser

Det er muligt at optimere, foretage fejlfinding, opdatere eller slette forudsigelser. Gennemgå en rapport om dataanvendelighed for at finde ud af, hvordan du gør en forudsigelse hurtigere og mere pålidelig. Du kan finde flere oplysninger under [Administrere forudsigelser](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
