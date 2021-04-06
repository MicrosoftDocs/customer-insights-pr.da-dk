---
title: Forudsige produktanbefalinger
description: Forudsige de produkter, en kunde køber eller kommunikerer med.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598056"
---
# <a name="product-recommendation-prediction-preview"></a>Forudsige produktanbefalinger (prøveversion)

Produktanbefalingsmodellen opretter produktanbefalinger for forudsigelse. Anbefalinger er baseret på tidligere købsmåder og kunder med lignende købsmønstre. Du kan oprette forudsigelser om nye produktanbefalinger siden **Intelligens** > **Forudsigelse**. Vælg **Mine forudsigelser** for at få vist andre forudsigelser, du har oprettet.

Produktanbefalinger kan være underlagt lokale love og regler samt kundernes forventninger, som modellen ikke er udviklet til specifikt at tage højde for.  Som bruger af denne gode funktion **skal du gennemgå anbefalingerne, inden du leverer dem til dine kunder**, for at sikre, at du overholder alle gældende love eller regler samt kundernes forventninger til det, du kan anbefales. 

Derudover vil outputtet fra denne model give dig anbefalinger baseret på produkt-id. Din leveringsmekanisme skal tage produkt-id'er og knytte dem til det relevante indhold, som dine kunder har adgang til, for at tage højde for lokalisering, billedindhold og andet forretningsspecifikt indhold eller forretningsspecifikt indhold.

## <a name="sample-guide"></a>Eksempelvejledning

Hvis du er interesseret i at prøve denne funktion, men ikke har data, der opfylder kravene nedenfor, kan du [oprette et eksempel på en implementering](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Forudsætninger

- Mindst [bidragydertilladelser](permissions.md) i Customer Insights.
- Forretningsviden om at forstå forskellige typer produkter i virksomheden, og hvordan kunderne kommunikerer med dem. Vi anbefaler produkter, der tidligere er købt af dine kunder, eller anbefalinger til nye produkter.
- Data om dine transaktioner, køb og deres oversigt:
    - Transaktions-id'er for at skelne mellem køb og transaktioner.
    - Kunde-id'er til tilknytning af transaktioner til dine kunder.
    - Datoer for posteringshændelser, som definerer de datoer, transaktionen forekom i.
    - (Valgfrit) Produkt-id-oplysninger for transaktionen.
    - (Valgfrit) Hvis en transaktion er en returnering eller ej.
    - Semantisk dataskema kræver følgende oplysninger:
        - **Transaktions-id:** Et entydigt id for et køb eller en transaktion.
        - **Transaktionsdato:** Datoen for købet eller transaktionen.
        - **Værdi for transaktion:** Den numeriske værdi for købet eller transaktionen.
        - **Entydigt produkt-id:** Id for det produkt eller den tjeneste, du har købt, hvis dataene befinder sig på linjeelementniveau.
        - (Valgfrit) **Køb eller returnering:** Et sandt/falsk-felt, der identificerer, om posteringen var en returvare eller ej. Hvis **Værdi for transaktion** er negativ, bruger vi også disse oplysninger til at udlede et returvare.


## <a name="create-a-product-recommendation-prediction"></a>Oprette forudsigelse om produktanbefalinger

1. Gå til **Intelligens** > **Forudsigelser** i Customer Insights.

1. Vælg **Produktanbefalinger for model (prøveversion)**, og vælg **Brug denne model**.
   > [!div class="mx-imgBorder"]
   > ![Produktanbefalingsmodel med knappen Brug denne model](media/product-recommendation-usethismodel.PNG "Produktanbefalingsmodel med knappen Brug denne model")

1. Gennemse oplysningerne om modelkravene. Hvis du har de påkrævede data, skal du vælge **Start her**.

### <a name="name-model"></a>Navngiv model

1. Angiv et navn til modellen for at adskille den fra andre modeller.

1. Angiv kun et navn på outputobjektet med bogstaver og tal uden mellemrum. Det er det navn, som modelobjektet skal bruge. Vælg derefter **Næste**.

### <a name="define-product-recommendation-configuration"></a>Konfiguration af produktanbefaling

1. Angiv det **antal produkter**, der skal anbefales til en kunde. Værdien afhænger af, hvordan leveringsmetoden udfylder data. Hvis du kan anbefale tre produkter, skal du angive denne værdi i overensstemmelse hermed.
   
   >[!TIP]
   > Du kan til enhver tid vælge **Gem og Luk** for at gemme forudsigelsen som en kladde. Du kan se forudsigelse under fanen **Mine forudsigelser**.

1. Vælg, om du ønsker at **Foreslå produkter, som kunder har købt for nylig**.

1. Hvis du har valgt *ikke* at anbefale produkter, du har købt for nylig, skal du indstille **tilbagebliksvinduet**. Denne indstilling angiver den tidsramme, modellen overvejer, før den anbefaler produktet til brugeren igen. Du kan f.eks. angive, at en kunde køber en bærbar computer hvert andet år. I dette vindue kigges der på købsoversigten for de seneste to år, og hvis de finder et element, filtreres elementet efter anbefalingerne.

1. Vælg **Næste** 

### <a name="add-required-data"></a>Tilføj påkrævede data

1. Vælg **Tilføj data** til **Kundetransaktionshistorik**, og vælg det objekt, der indeholder oplysninger om transaktionen/indkøbshistorikken, som beskrevet i [forudsætninger](#prerequisites).

1. Tilknyt de semantiske felter til attributter i objektet indkøbsoversigt, og vælg **Næste**. Du kan finde beskrivelser af felterne under [forudsætningerne](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Definere objektrelationen](media/product-recommendation-purchasehistorymapping.PNG "Siden Købshistorik, der viser semantiske attributter, som er knyttet til felter i det valgte objekt for købsobjektet")

1. Hvis nedenstående felter ikke er udfyldt, skal du konfigurere relationen fra dit indkøbsoversigtsobjekt til objektet *Kunde*.
    1. Vælg **Indkøbsoversigtsobjekt**.
    1. Vælg det **Felt**, der identificerer kunden i objektet indkøbsoversigt. Det skal relateres til primære kunde-id i objektet *Kunde*.
    1. Vælg det **Kundeobjekt**, der stemmer overens med dit primære kundeobjekt.
    1. Angiv et navn, der beskriver relationen.
       > [!div class="mx-imgBorder"]
       > ![Siden Indkøbshistorik, der viser oprettelsen af en relation til kunde](media/model-purchase-join.png "Siden Indkøbshistorik, der viser oprettelsen af en relation til kunde")

1. Vælg **Gem**.

1. Vælg **Næste**.

### <a name="set-schedule-and-review-configuration"></a>Angive konfiguration for planlægning og evaluering

1. Angiv en hyppighed for at omskole modellen. Denne indstilling er vigtig, hvis du vil opdatere nøjagtigheden af forudsigelser, efterhånden som nye data importeres til Customer Insights. De fleste virksomheder kan omskole én gang om måneden og opnå en god præcision af deres forudsigelse.

1. Vælg **Næste**.

1. Gennemgå konfigurationen. Du kan gå tilbage til en hvilken som helst del af forudsigelseskonfigurationen ved at vælge **Rediger** under den viste værdi. Du kan også vælge et konfigurationstrin i statusindikatoren.

1. Hvis alle værdier er konfigureret korrekt, skal du vælge **Gem og kør** for at starte forudsigelsesprocessen. Du kan se statussen for dine forudsigelser under fanen **Mine forudsigelser**. Det kan tage flere timer, før processen er fuldført, afhængigt af mængden af data, der bruges i forudsigelsen.

## <a name="review-a-prediction-status-and-results"></a>Gennemgå en forudsigelses status og resultater

1. Gå til fanen **Mine forudsigelser** i **Intelligens** > **forudsigelser**.
   > [!div class="mx-imgBorder"]
   > ![Visning af siden Mine forudsigelser](media/product-recommendation-mypredictions.PNG "Visning af siden Mine forudsigelser")

1. Vælg den forudsigelse, du vil gennemse.
   - **Forudsigelsesnavn:** Navnet på forudsigelsen, der blev angivet under oprettelsen.
   - **Forudsigelsestype:** Den type model, der bruges til forudsigelsen
   - **Outputobjekt:** Navnet på det objekt, som outputtet af forudsigelsen skal gemmes i. Du kan finde et objekt med dette navn på **Data** > **Objekter**.
   - **Forventet felt:** Dette felt udfyldes kun i forbindelse med visse typer forudsigelser og bruges ikke i afgang af forudsigelse.
   - **Status:** Den aktuelle status for forudsigelsens kørsel.
        - **Sat i kø:** Forudsigelsen venter i øjeblikket på, at andre processer skal køre.
        - **Opdaterer:** Forudsigelse kører i øjeblikket "score"-fasen i behandlingen af de resultater, der vil blive overført til outputenheden.
        - **Mislykkedes:** Forudsigelsen mislykkedes. Vælg **Logge** for at få flere oplysninger.
        - **Lykkedes:** Forudsigelsen blev fuldført. Vælg **Vis** under de lodrette ellipser for at gennemgå forudsigelse.
   - **Redigeret:** Den dato, hvor konfigurationen af forudsigelse blev ændret.
   - **Sidst opdateret:** Den dato, hvor forudsigelsen opdaterede resultater i outputenheden.

1. Vælg de lodrette ellipser ud for den forudsigelse, du vil gennemgå resultaterne for, og vælg **Vis**.
   > [!div class="mx-imgBorder"]
   > ![Visning af indstillinger i menuen med lodrette ellipser for en forudsigelse, herunder redigering, opdatering, visning, logfiler og sletning](media/product-recommendation-verticalellipses.PNG "Visning af indstillinger i menuen med lodrette ellipser for en forudsigelse, herunder redigering, opdatering, visning, logfiler og sletning")

1. Der findes tre primære sektioner med data på resultatsiden:
    1. **Træningsmodellens ydeevne:** A, B eller C er mulige scorer. Denne score ydeevnen af forudsigelsen og kan hjælpe dig med at træffe beslutningen om at bruge de resultater, der er gemt i outputobjektet.
        - Scorer bestemmes ud fra følgende regler:
            - **A** Modellen betragtes som **A**-kvalitet, hvis målingen "Succes @ K" er mindst 10 % mere end basislinjen. 
            - **B** Modellen betragtes som **B**-kvalitet, hvis målingen "Succes @ K" er 0 - 10 % mere end basislinjen.
            - **C** Modellen betragtes som **C**-kvalitet, hvis målingen "Succes @ K" er mindre end basislinjen.
               
               > [!div class="mx-imgBorder"]
               > ![Visning af modellens ydeevneresultat](media/product-recommendation-modelperformance.PNG "Visning af modellens ydeevneresultat")
            - **Basislinje**: Modellen tager de mest anbefalede produkter ved køb på tværs af alle kunder, og den bruger lærde regler, der identificeres af modellen, til at oprette et sæt anbefalinger til kunderne. Forudsigelserne sammenlignes derefter med de øverste produkter som beregnet ud fra antallet af kunder, der har købt produktet. Hvis en kunde har mindst ét produkt i sine anbefalede produkter, der også blev set i de mest købte produkter, betragtes de som en del af udgangspunktet. Hvis der var 10 af disse kunder, hvor der var købt et anbefalet produkt ud af 100 samlede kunder, ville udgangsværdien være 10 %.
            - **Succes @ K**: Ved hjælp af et valideringssæt med transaktioner oprettes der anbefalinger for alle kunder og sammenlignes med valideringssættet for transaktioner. I en periode på 12 måneder kan der f.eks. blive afsat 12 måneder som et valideringssæt af data. Hvis modellen bygger på mindst én ting, du ville købe i måned 12 på baggrund af det, den har lært af de foregående 11 måneder, vil kunden øge målingen "Succes @ K".
    
    1. **De fleste forslag til produkter (med stemmer):** De fem vigtigste produkter, der blev foretrukne for dine kunder.
       > [!div class="mx-imgBorder"]
       > ![Graf, der viser de fem mest anbefalede produkter](media/product-recommendation-topproducts.PNG "Graf, der viser de fem mest anbefalede produkter")
    
    1. **Produktanbefalinger med høj sikkerhed:** Et eksempel på anbefalinger, der kommer til dine kunder, og som efter modellens mening sandsynligvis vil blive købt af kunden.
       > [!div class="mx-imgBorder"]
       > ![Liste med forslag med stor sikkerhed til udvalgte individuelle kunder](media/product-recommendation-highconfidence.PNG "Liste med forslag med stor sikkerhed til udvalgte individuelle kunder")

## <a name="fix-a-failed-prediction"></a>Rette en mislykket forudsigelse

1. Gå til fanen **Mine forudsigelser** i **Intelligens** > **forudsigelser**.

1. Vælg den forudsigelse, som du vil have vist fejllogfiler for, og vælg **Logge**.

1. Gennemgå alle fejlene. Der er flere typer fejl, der kan opstå, og som beskriver, hvilken betingelse der forårsagede fejlen. En fejlmeddelelse om, at der ikke er nok data til præcist at forudsige noget, løses typisk ved at indlæse yderligere data i Customer Insights.

## <a name="refresh-a-prediction"></a>Opdatere en forudsigelse

Forudsigelser opdateres automatisk efter samme [tidsplan, som dataene opdateres](system.md#schedule-tab), som konfigureret i indstillingerne.

1. Gå til fanen **Mine forudsigelser** i **Intelligens** > **forudsigelser**.

1. Vælg de lodrette ellipser ud for den forudsigelse,, du vil opdatere.

1. Vælg **Opdater**.

## <a name="delete-a-prediction"></a>Slette en forudsigelse

Hvis du sletter en forudsigelse, fjernes outputobjektet også.

1. Gå til fanen **Mine forudsigelser** i **Intelligens** > **forudsigelser**.

1. Vælg de lodrette ellipser ud for den forudsigelse, du vil slette.

1. Vælg **Slet**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]