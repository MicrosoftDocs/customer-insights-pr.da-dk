---
title: Forudsigelse af kundens levetidsværdi (CLV)
description: Indtægtskilde for aktive kunder i fremtiden.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
ms.openlocfilehash: e2f92a64d01a443bcf3c1605621abe045b93ee5e
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095503"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Kundens levetidsværdi (CLV) forudsigelse (prøveversion)

Potentiel værdi (omsætning), som de enkelte aktive kunder henter ind i virksomheden via en defineret fremtidig tidsperiode. Du kan bruge denne funktion til at nå forskellige mål: 
- Identificere kunder af høj værdi, og bearbejde denne indsigt
- Oprette strategiske kundesegmenter baseret på deres potentielle værdi til at køre tilpassede kampagner med målrettede salgs-, marketing- og supportindsatser
- Vejlede i produktudvikling ved at fokusere på funktioner, der øger kundeværdien
- Optimere salgs- eller marketingstrategien og tildeling af budget mere nøjagtigt til kundekontakt
- Genkende og belønne kunder med høj værdi via loyalitets- eller præmierprogrammer 

## <a name="prerequisites"></a>Forudsætninger

Før du går i gang, skal du overveje, hvad CLV betyder for din virksomhed. I øjeblikket understøtter vi transaktionsbaseret CLV-forudsigelse. En kundes samlede værdi er baseret på oversigten over forretningstransaktioner. Hvis du vil forudsigelse, skal du som minimum have [Bidragyder](permissions.md)-tilladelser.

Da det ikke tager lang tid at konfigurere og køre en CLV-model, kan du overveje at oprette flere modeller med forskellige inputindstillinger og sammenligne modelresultater for at se, hvilket modelscenarie der passer bedst til dine forretningsbehov.

###  <a name="data-requirements"></a>Datakrav

Følgende data kræves, og hvor de er markeret valgfri, anbefales det, hvis modelydeevnen skal øges. Jo flere data modellen kan behandle, jo mere nøjagtige forudsigelse bliver. Vi opfordrer dig derfor til at bruge flere kundeaktivitetsdata, hvis de bliver tilgængelige.

- Kunde-id: Entydigt id, der skal svare til transaktioner med en enkelt kunde

- Transaktionshistorik: Historisk transaktionslog med nedenstående semantiske dataskema
    - **Transaktions-id**: Entydigt id for hver transaktion
    - **Transaktionsdato**: Dato og helst et tidsstempel for hver transaktion
    - **Transaktionsbeløb**: Pengeværdi (f.eks. omsætning eller avance) for hver transaktion
    - **Etiket, der er tildelt til returneringer** (valgfrit): Boolesk værdi, der angiver, om transaktionen er en returvare 
    - **Produkt-id** (valgfrit): Produkt-id for det produkt, der er involveret i transaktionen

- Yderligere data (valgfrit), f.eks.
    - Webaktiviteter: oversigt over besøg på websted, e-mail-oversigt
    - Loyalitetsaktiviteter: akkumulerede loyalitetspoint og oversigt over loyalitetspræmier
    - Kundeservice oversigt over logfiler, serviceopkald, klager eller returneringer
- Data om kundeaktiviteter (valgfri):
    - Aktivitets-id'er, der skal skelne mellem aktiviteter af samme type
    - Kunde-id'er, der knytter aktiviteter til dine kunder
    - Aktivitetsoplysninger, der indeholder navnet på og datoen for aktiviteten
    - Det semantiske dataskema for aktiviteter omfatter: 
        - **Primær nøgle**: Et entydigt id for en aktivitet
        - **Tidsstempel**: Dato og klokkeslæt for hændelsen, der identificeres af den primære nøgle
        - **Hændelse (aktivitetsnavn)**: Navnet på den hændelse, du vil bruge
        - **Detaljer (beløb eller værdi)**: Detaljer om kundeaktiviteten

- Forslåede datakarakteristika:
    - Tilstrækkelige historiske data: Mindst et års transaktionsdata. Helst to til tre års transaktionsdata for at forudsige CLV i et år.
    - Flere køb pr. kunde: Ideelt set mindst to til tre transaktioner pr. kunde-id, helst på tværs af flere datoer.
    - Antal kunder: Mindst 100 forskellige kunder, helst mere end 10.000 kunder. Modellen kan ikke bruges af færre end 100 kunder og med utilstrækkelige historiske data
    - Datafuldstændighed: Mindre end 20 % manglende værdier i obligatoriske felter i inputdataene   

> [!NOTE]
> - Modellen kræver kundernes transaktionsoversigt. Der kan i øjeblikket kun konfigureres ét transaktionsoversigtsobjekt. Hvis der er flere købs-/transaktionsobjekter, kan du samle dem i Power Query inden dataindtagelse.
> - Hvis du vil have flere kundeaktivitetsdata (valgfrit), kan du dog tilføje lige så mange kundeaktivitetsobjekter, som du ønsker, til overvejelse af modellen.

## <a name="create-a-customer-lifetime-value-prediction"></a>Oprette kundens levetidsværdi (CLV) forudsigelse

1. Gå til **Intelligens** > **Forudsigelser** i målgruppen insights.

1. Vælg feltet **Kundens levetidsværdi**, og vælg **Brug model**. 

1. Vælg **Start her** i ruden **Kundens levetidsværdi (prøveversion)**.

1. **Navngive denne model** og **navnet på outputobjektet** for at skelne mellem dem fra andre modeller eller objekter.

1. Vælg **Næste**.

### <a name="define-model-preferences"></a>Definere modelindstillinger

1. Angiv en **Forudsigelsesperiode** for at definere, hvor langt i fremtiden CLV skal være.    
   Enheden angives som standard som måneder. Du kan ændre det til år, så du kommer længere ud i fremtiden.

   > [!TIP]
   > Hvis du vil sammenligne CLV nøjagtigt for den tidsperiode, du angiver, skal du have en tilsvarende periode med historiske data. Hvis du f.eks. vil forudsige CLV for de næste 12 måneder, anbefales det, at du har mindst 18-24 måneders historiske data.

1. Angiv, hvad **Aktive kunder** betyder for virksomheden. Angiv den tidsramme, hvor en kunde skal have haft mindst én transaktion, for at blive fundet aktiv. Modellen ønsker kun at bruge CLV til aktive kunder. 
   - **Lad model beregne købsinterval (anbefales)**: I modellen analyseres dataene, og en tidsperiode bestemmes på baggrund af historiske køb.
   - **Angiv intervallet manuelt**: Hvis du har en bestemt forretningsdefinition for en aktiv kunde, skal du vælge denne indstilling og angive tidsperiode efter behov.

1. Definer percentil for **Kunder af høj værdi** for at aktivere modellen til at levere resultater, der svarer til virksomhedens definition.
    - **Modelberegning (anbefales)**: I modellen analyseres dine data, og det bestemmes, hvad en kunde med høj værdi kan have for virksomheden på baggrund af kundernes transaktionsoversigt. I modellen bruges en heuristikregel (der er inspireret af reglen 80/20 eller pareto-princippet) til at finde proportionen med kunder af høj værdi. Den procentdel af kunderne, der har givet en samlet omsætning på 80 % for virksomheden i den historiske periode, betragtes som kunder af høj værdi. Mindre end 30-40 procent af kunderne bidrager som regel til en samlet omsætning på procent. Dette antal kan dog variere, afhængigt af virksomhed og branche.    
    - **Procent af aktive kunder i top**: Definer kunder af høj værdi for virksomheden som en percentil af de mest aktive betalende kunder. Du kan f.eks. bruge denne indstilling til at definere kunder af høj værdi som de øverste 20 % af de fremtidige betalende kunder.

    Hvis virksomheden definerer kunder af høj værdi på en anden måde, skal du [fortælle os det, som vi gerne vil høre](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Vælg **Næste** for at fortsætte til næste trin.

### <a name="add-required-data"></a>Tilføj påkrævede data

1. I trinnet **Påkrævede data** skal du vælge **Tilføj data** for **Kundetransaktionshistorik** vælge, hvilket objekt der indeholder de transaktionshistorikoplysninger, der beskrives i [forudsætninger](#prerequisites).

1. Tilknyt de semantiske felter til attributter i objektet indkøbsoversigt, og vælg **Næste**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Billede af konfigurationstrinnet til tilknytning af dataattributter for de påkrævede data.":::
 
1. Hvis nedenstående felter ikke er udfyldt, skal du konfigurere relationen fra dit indkøbsoversigtsobjekt til objektet *Kunde* og vælge **Gem**.
    1. Vælg transaktionshistorikobjekt.
    1. Vælg det felt, der identificerer en kunde i objektet indkøbsoversigt. Det skal relateres til kundeobjektets primære kunde-id.
    1. Vælg objektet, der svarer til det primære kundeobjekt.
    1. Angiv et navn, der beskriver relationen.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Billede af konfigurationstrinnet for at definere relationen til kundeobjektet.":::

1. Vælg **Næste**.

### <a name="add-optional-data"></a>Tilføj valgfrie data

Data, der afspejler vigtige kundeinteraktioner (f.eks. web-, kundeservice- og hændelseslogfiler), føjer kontekst til transaktionsposter. Flere mønstre, der findes i kundeaktivitetsdataene, kan gøre forudsigelserne mere nøjagtige. 

1. Vælg **Tilføj data** i trinnet **Flere data (valgfrit)**. Vælg det kundeaktivitetsobjekt, der indeholder oplysninger om kundeaktiviteten, som beskrevet i [forudsætninger](#prerequisites).

1. Tilknyt de semantiske felter til attributter i objektet kundeaktivitet, og vælg **Næste**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Billede af konfigurationstrinnet til tilknytning af felter for yderligere data.":::

1. Vælg en aktivitetstype, der svarer til den type kundeaktivitet, du tilføjer. Vælg mellem eksisterende aktivitetstyper, eller tilføj en ny aktivitetstype.

1. Konfigurer relationen fra kundeaktivitetsobjektet til *Kunde*-objektet.
    
    1. Vælg det felt, der identificerer kunden i objektet kundeaktivitetsoversigt. Det kan relateres direkte til det primære kunde-id for *Kunde*-objektet.
    1. Vælg det *Kundeobjekt*, der stemmer overens med dit primære *Kundeobjekt*.
    1. Angiv et navn, der beskriver relationen.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Billede af trinnet i konfigurationsforløbet for at tilføje flere data og konfigurere aktiviteten med udfyldte eksempler.":::

1. Vælg **Gem**.    
    Tilføj flere data, hvis du vil medtage andre kundeaktiviteter.

1. Vælg **Næste**.

### <a name="set-update-schedule"></a>Indstil opdateringsplan

1. I trinnet til **planlægning af dataopdatering** skal du vælge, hvor ofte modellen skal omformere sig på baggrund af de nyeste data. Denne indstilling er vigtig, hvis du vil opdatere nøjagtigheden af forudsigelserne, efterhånden som nye data indsættes i målgruppen Insights. De fleste virksomheder kan omskole én gang om måneden og opnå en god præcision af deres forudsigelse.

1. Vælg **Næste**.

### <a name="review-and-run-the-model-configuration"></a>Gennemse og kør modelkonfigurationen

1. I trinnet **Gennemse modeldetaljer** skal du validere konfigurationen forudsigelse. Du kan gå tilbage til en hvilken som helst del af forudsigelseskonfigurationen ved at vælge **Rediger** under den viste værdi. Du kan også vælge et konfigurationstrin fra statusindikatoren.

1. Hvis alle værdier er konfigureret korrekt, skal du vælge **Gem og kør** for at starte kørsel af modellen. Under fanen **Mine forudsigelser** kan du se status for den forudsigelsesproces. Det kan tage flere timer, før processen er fuldført, afhængigt af mængden af data, der bruges i forudsigelsen.

## <a name="review-prediction-status-and-results"></a>Gennemse forudsigelsesstatus og resultater

### <a name="review-prediction-status"></a>Gennemse forudsigelsesstatus

1.  Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**.
2.  Vælg den forudsigelse, du vil gennemse.

- **Forudsigelsesnavn**: Navnet på den forudsigelse, der blev angivet under oprettelsen.
- **Forudsigelsestype**: Den modeltype, der bruges til forudsigelse
- **Outputobjekt**: Navnet på det objekt, som outputtet af forudsigelsen skal gemmes i. Gå til **Data** > **Objekter** for at finde objektet med dette navn.
- **Forventet felt**: Dette felt udfyldes kun i forbindelse med visse typer forudsigelser og bruges ikke forudsigelse af værdi for kundelevetid.
- **Status**: Status for forudsigelseskørslen
    - **I kø**: Forudsigelse venter på, at andre processer fuldføres.
    - **Opdatering**: Forudsigelse kører i øjeblikket for at producere resultater, der vil blive overført til outputenheden.
    - **Mislykket**: Forudsigelse kunne ikke køres. Du kan finde flere oplysninger i [logfilerne](manage-predictions.md#troubleshoot-a-failed-prediction).
    - **Lykkedes**: Forudsigelse blev fuldført. Vælg **Vis** under de lodrette ellipser for at gennemse de forudsigelse resultater.
- **Redigeret**: Den dato, hvor konfigurationen af forudsigelse blev ændret.
- **Sidst opdateret**: Den dato, hvor forudsigelsen opdaterede resultater i outputenheden.

### <a name="review-prediction-results"></a>Gennemse forudsigelsesresultater

1. Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**.

1. Vælg den forudsigelse du vil gennemse resultaterne for.

Der findes tre primære sektioner med data på resultatsiden.

- **Præstation i uddannelsesmodellen**: A, B eller C er mulige grader. Denne grad angiver resultaterne for objektet forudsigelse kan hjælpe dig med at træffe beslutning om at bruge de resultater, der er gemt i outputobjektet. Vælg **Få mere at vide om denne score** for bedre at forstå de underliggende målepunkter for modelresultater, og hvordan den endelige modelresultatkvalitet blev afledt.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Billede af feltet med oplysninger om modelpoint med vurderingen A.":::

  Ved hjælp af definitionen af kunder med høj værdi, der blev leveret, mens forudsigelse konfigureres, vurderer systemet, hvordan AI-modellen præsterede i forhold til en basismodel.    

  Vurderingerne bestemmes ud fra følgende regler:
  - **A** når modellen nøjagtigt har forudsagt mindst 5 % flere kunder med høj værdi i forhold til den oprindelige model.
  - **B** når modellen nøjagtigt har forudsagt 0-5 % flere kunder med høj værdi i forhold til den oprindelige model.
  - **C** når modellen nøjagtigt har forudsagt færre kunder med høj værdi i forhold til den oprindelige model.

  I ruden **Bedømmelse** vises flere detaljer om AI-modelydeevnen og den grundlæggende model. I den grundlæggende model bruges en ikke-AI-baseret metode til at beregne kundens levetidsværdi, primært på baggrund af historiske indkøb foretaget af kunder.     
  Den standardformel, der bruges til at beregne CLV efter basismodellen:    

  _**CLV for hver kunde** = Gennemsnitlig månedligt køb foretaget af kunden i vinduet med aktive kunder *Antal måneder i CLV-forudsigelse perioden* Samlet tilbageholdelseshastighed for alle kunder*_

  AI-modellen sammenlignes med den oprindelige model, der er baseret på to modelydeevnemetrikværdier.
  
  - **Succesfrekvens, der spår kunder med stor værdi**

    Se forskellen i, hvordan kunder med høj værdi bruger AI-modellen i forhold til den oprindelige model. En succesrate på 84 procent betyder f.eks., at AI-modellen kunne registrere 84 procent nøjagtigt ud af alle kunder i uddannelsesdataene. Derefter sammenlignes denne succesrate med succesprocenten for den oprindelige model for at rapportere den relative ændring. Denne værdi bruges til at tildele modellen en vurdering.

  - **Fejlmetrikværdier**
    
    En anden metrikværdi giver dig mulighed for at gennemgå modellens overordnede ydeevne med hensyn til fejl i forbindelse med fremtidigt arbejde. Vi bruger den overordnede måling (Root Mean Squared Error) til at vurdere denne fejl. RMSE er en standardmåde at måle fejlen i en model på, når data, der skal anvendes, anvendes. AI-modellens RMSE sammenlignes med den RMSE i basismodellen, og den relative forskel rapporteres.

  AI-modellen prioriterer den nøjagtige rangering af kunder efter den værdi, de tilfører din virksomhed. Så kun succesprocenten for kunder med høj værdi bruges til at opnå den endelige modelkvalitet. RMSE-målingen er følsom over for afvigende værdier. I scenarier, hvor du har en lille procentdel af kunder med utroligt høje indkøbsværdier, giver den overordnede RMSE-måling måske ikke det fulde billede af modelydeevnen.   

- **Kundeværdi efter percentil**: Ved hjælp af din definition af kunder med høj værdi grupperes kunderne i lave værdier og høj værdi baseret på deres CLV-forudsigelser og vises i et diagram. Hvis du holder musen hen over søjlerne i hist hover, kan du se antallet af kunder i de enkelte grupper og den gennemsnitlige CLV for den pågældende gruppe. Disse data kan være en hjælp, hvis du [vil oprette kundesegmenter](segments.md) baseret på deres CLV-forudsigelser.

- **De fleste faktorer, der påvirker indflydelsen**: Der tages forskellige faktorer i betragtning, når du opretter forudsigelse CLV baseret på de inputdata, der leveres til AI-modellen. Hver af faktorerne får beregnet deres betydning for de samlede forudsigelser, som en model opretter. Du kan bruge disse faktorer til at validere dine forudsigelsesresultater. Disse faktorer giver også større indsigt i de faktorer, der gør det muligt at vælge CLV på tværs af alle dine kunder.

## <a name="manage-predictions"></a>Administrere forudsigelser

Det er muligt at optimere, foretage fejlfinding, opdatere eller slette forudsigelser. Gennemgå en rapport om dataanvendelighed for at finde ud af, hvordan du gør en forudsigelse hurtigere og mere pålidelig. Du kan finde flere oplysninger under [Administrere forudsigelser](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
