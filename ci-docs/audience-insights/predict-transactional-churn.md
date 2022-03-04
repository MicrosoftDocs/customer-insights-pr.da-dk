---
title: Forudsigelse om transaktionsafgang (indeholder video)
description: Forudsig, om en kunde kan risikere ikke længere at købe virksomhedens produkter eller tjenester.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 9aa208ad94dcb6b1e0f110a3f974c56de00bbd07
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355652"
---
# <a name="transaction-churn-prediction"></a>Forudsigelse af transaktionsafgang

Transaktionsrelateret forudsigelse om afgang er med til at forudsige, om en kunde ikke længere vil købe dine produkter eller tjenester i et bestemt tidsvindue. Du kan oprette nye forudsigelser om afgang på **Intelligens** > **Forudsigelser**. Vælg **Mine forudsigelser** for at få vist andre forudsigelser, du har oprettet. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

I miljøer, der er baseret på forretningskonti, kan vi forudsige transaktionsafgang for en konto og også en kombination af kontooplysninger og et andet oplysningsniveau, f.eks. produktkategori. Hvis du tilføjer en dimension, kan du se, hvor sandsynligt det er, at kontoen "Contoso" holder op med at købe produktkategorien "kontorartikler". I forbindelse med forretningskonti kan vi også bruge AI til at oprette en liste over potentielle årsager til, at et firma sandsynligvis vil afgå i en kategori af oplysninger på sekundært niveau.

> [!TIP]
> Prøv selvstudiet til en forudsigelse af transaktionsafgang med eksempeldata: [Eksempelvejledning til forudsigelse af transaktionsafgang](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Forudsætninger

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

- Mindst [bidragydertilladelser](permissions.md) i Customer Insights.
- Forretningsviden for at forstå, hvad afgang betyder for din virksomhed. Vi understøtter timebaserede definitioner for afgang, hvilket vil sige, at en kunde anses for at have forladt dig efter en periode uden køb.
- Data om dine transaktioner/køb og deres oversigt:
    - Transaktions-id'er for at skelne mellem køb og transaktioner.
    - Kunde-id'er, der stemmer overens med transaktioner til dine kunder.
    - Datoer for posteringshændelser, som definerer de datoer, transaktionen forekom i.
    - Semantisk dataskema for køb/transaktioner kræver følgende oplysninger:
        - **Transaktions-id**: Et entydigt id for et køb eller en transaktion.
        - **Transaktionsdato**: Købs- eller transaktionsdato.
        - **Værdi af transaktionen**: Valutaen/den numeriske værdi af transaktionen/varen.
        - (Valgfrit) **Entydigt produkt-id**: Id for det produkt eller den tjeneste, du har købt, hvis dataene befinder sig på linjeelementniveau.
        - (Valgfrit) **Angiver, om denne transaktion var en returnering**: Et sandt/falsk-felt, der identificerer, om transaktionen var en returvare eller ej. Hvis **Værdi for transaktion** er negativ, bruger vi også disse oplysninger til at udlede et returvare.
- (Valgfri) Data om kundeaktiviteter:
    - Aktivitets-id'er, der skal skelne mellem aktiviteter af samme type.
    - Kunde-id'er, der knytter aktiviteter til dine kunder.
    - Aktivitetsoplysninger, der indeholder navnet på og datoen for aktiviteten.
    - Det semantiske dataskema for kundeaktiviteter omfatter:
        - **Primær nøgle:** Et entydigt id for en aktivitet. F.eks. et webstedbesøg eller en forbrugspost, der viser, at kunden har forsøgt et eksempel af produktet.
        - **Tidsstempel:** Dato og klokkeslæt for hændelsen, der identificeres af den primære nøgle.
        - **Hændelse:** Navnet på den hændelse, du vil bruge. Et felt, der kaldes "UserAction" i en forretning, kan f. eks. være en kupon, der bruges af kunden.
        - **Detaljer:** Detaljerede oplysninger om hændelsen. Et felt, der kaldes "CouponValue" i en forretning, kan f. eks. være valutaværdien af en kupon.

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

- Mindst [bidragydertilladelser](permissions.md) i Customer Insights.
- Forretningsviden for at forstå, hvad afgang betyder for din virksomhed. Vi understøtter timebaserede definitioner for afgang, hvilket vil sige, at en kunde anses for at have forladt dig efter en periode uden køb.
- Data om dine transaktioner/køb og deres oversigt:
    - Transaktions-id'er for at skelne mellem køb og transaktioner.
    - Kunde-id'er, der stemmer overens med transaktioner til dine kunder.
    - Datoer for posteringshændelser, som definerer de datoer, transaktionen forekom i.
    - Semantisk dataskema for køb/transaktioner kræver følgende oplysninger:
        - **Transaktions-id**: Et entydigt id for et køb eller en transaktion.
        - **Transaktionsdato**: Købs- eller transaktionsdato.
        - **Værdi af transaktionen**: Valutaen/den numeriske værdi af transaktionen/varen.
        - (Valgfrit) **Entydigt produkt-id**: Id for det produkt eller den tjeneste, du har købt, hvis dataene befinder sig på linjeelementniveau.
        - (Valgfrit) **Angiver, om denne transaktion var en returnering**: Et sandt/falsk-felt, der identificerer, om transaktionen var en returvare eller ej. Hvis **Værdi for transaktion** er negativ, bruger vi også disse oplysninger til at udlede et returvare.
- (Valgfri) Data om kundeaktiviteter:
    - Aktivitets-id'er, der skal skelne mellem aktiviteter af samme type.
    - Kunde-id'er, der knytter aktiviteter til dine kunder.
    - Aktivitetsoplysninger, der indeholder navnet på og datoen for aktiviteten.
    - Det semantiske dataskema for kundeaktiviteter omfatter:
        - **Primær nøgle:** Et entydigt id for en aktivitet. F.eks. et webstedbesøg eller en forbrugspost, der viser, at kunden har forsøgt et eksempel af produktet.
        - **Tidsstempel:** Dato og klokkeslæt for hændelsen, der identificeres af den primære nøgle.
        - **Hændelse:** Navnet på den hændelse, du vil bruge. Et felt, der kaldes "UserAction" i en forretning, kan f. eks. være en kupon, der bruges af kunden.
        - **Detaljer:** Detaljerede oplysninger om hændelsen. Et felt, der kaldes "CouponValue" i en forretning, kan f. eks. være valutaværdien af en kupon.
- (Valgfrit) Data om dine kunder:
    - Disse data skal justeres i forhold til mere statiske attributter for at sikre, at modellen fungerer bedst.
    - Det semantiske dataskema til kundedata omfatter:
        - **Kunde-id:** Et entydigt id for en kunde.
        - **Oprettelsesdato:** Den dato, hvor kunden oprindeligt blev tilføjet.
        - **Område :** En kundes område eller områdeadresse.
        - **Land:** Kundens land.
        - **Branche:** En kundes branchetype. Et felt, der f.eks. kaldes "Branche" i en kafferister, kan angive, om kunden var detail.
        - **Klassificering:** Kategorisering af en kunde i din virksomhed. Et felt, der f.eks. kaldes "ValueSegment" i en kafferister, kan være kundeniveauet baseret på kundens størrelse.

---

- Forslåede datakarakteristika:
    - Tilstrækkelige historiske data: Transaktionsdata for mindst det dobbelte af det valgte tidsvindue. Helst to til tre års transaktionshistorik. 
    - Flere køb pr. kunde: Ideelt mindst to transaktioner pr. kunde.
    - Antal kunder: Mindst 10 kundeprofiler, helst mere end 1.000 entydige kunder. Modellen kan ikke bruges af færre end 10 kunder og med utilstrækkelige historiske data.
    - Datafuldførelse: Mindre end 20 % af de manglende værdier i datafeltet for det angivne objekt.

> [!NOTE]
> For en virksomhed med mange kunders indkøbshyppighed (med få ugers mellemrum) anbefales det, at du vælger et kortere forudsigelsesvindue og afgangsdefinition. Hvis du har lav indkøbshyppighed (med få måneder mellemrum eller én gang om året), skal du vælge et længere forudsigelsesvindue og afgangsdefinition.

## <a name="create-a-transaction-churn-prediction"></a>Oprette en forudsigelse af transaktionsafgang

1. Gå til **Intelligens** > **Forudsigelser** i Customer Insights.

1. Vælg feltet **Model til kundeafgang**, og vælg **Brug denne model**.

1. Vælg **Transaktion** i ruden **Model for kundeafgang**, og vælg **Start her**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Skærmbillede med valgt transaktionsindstilling i ruden Model for kundeafgang.":::
 
### <a name="name-model"></a>Navngiv model

1. Angiv et navn til modellen for at adskille den fra andre modeller.

1. Angiv et navn til outputenheden udelukkende med bogstaver og tal uden mellemrum. Det er det navn, som modelobjektet skal bruge. 

1. Vælg **Næste**.

### <a name="define-customer-churn"></a>Definer kundeafgang

1. Angiv **Forudsigelsesvindue**. Du kan f. eks. forudsige risikoen for afgang af kunder i løbet af de næste 90 dage for at justere din marketingsindsats. Hvis du forudsiger afgangsrisikoen for en længere eller kortere tidsperiode, kan det være sværere at håndtere faktorerne i din risikoprofil vedrørende afgang, men den afhænger af virksomhedens specifikke behov.
   >[!TIP]
   > Du kan når som helst vælge **Gem kladde** for at gemme forudsigelsen som en kladde. Du kan se kladdeforudsigelsen under fanen **Mine forudsigelser** for at fortsætte.

1. Angiv antallet af dage for at definere afgang i feltet **Definition af kundeafgang**. Hvis kunden f. eks. ikke har foretaget køb inden for de seneste 30 dage, betragtes de muligvis som afgået for virksomheden. 

1. Vælg **Næste** for at fortsætte.

### <a name="add-required-data"></a>Tilføj påkrævede data

1. Vælg **Tilføj data**, og vælg aktivitetstypen den siderude, der indeholder de påkrævede oplysninger om transaktionen eller købsoversigten.

1. Under **Vælg aktiviteter** skal du vælge de specifikke aktiviteter fra den valgte aktivitetstype, som beregningen skal fokusere på.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Sideruden viser, hvordan du vælger bestemte aktiviteter under den semantiske type.":::

   Hvis du endnu ikke har knyttet aktiviteten til en semantisk type, skal du vælge **Rediger** for at gøre det. Den styrede oplevelse til tilknytning af semantiske aktiviteter åbnes. Knyt nu dine data til relaterede felter i den valgte aktivitetstype.

1. Knyt de semantiske attributter til de felter, der kræves for at køre modellen. Hvis nedenstående felter ikke er udfyldt, skal du konfigurere relationen fra dit indkøbsoversigtsobjekt til objektet *Kunde*. Vælg **Gem**.

1. Vælg **Næste** i trinnet **Tilføj påkrævede data** for at fortsætte, hvis du ikke vil tilføje flere aktiviteter.


# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Tilføje yderligere data (valgfrit)

Konfigurer relationen fra kundeaktivitetsobjektet til *Kunde*-objektet.

1. Vælg det felt, der identificerer kunden i objektet kundeaktivitetsoversigt. Det kan relateres direkte til det primære kunde-id for *Kunde*-objektet.

1. Vælg det objekt, der er det primære *Kunde*-objekt.

1. Angiv et navn, der beskriver relationen.

#### <a name="customer-activities"></a>Kundeaktiviteter

1. Du kan også vælge **Tilføj data** til **Kundeaktiviteter**.

1. Vælg den semantiske aktivitetstype, der indeholder de data, du vil bruge, og vælg derefter en eller flere aktiviteter i sektionen **Aktiviteter**.

1. Vælg en aktivitetstype, der svarer til den type kundeaktivitet, du konfigurerer. Vælg **Opret ny**, og vælg en tilgængelig aktivitetstype, eller opret en ny type.

1. Vælg **Næste** og derefter **Gem**.

1. Hvis du har andre kundeaktiviteter, som du vil medtage, skal du gentage trinnene ovenfor.

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

### <a name="select-prediction-level"></a>Vælge forudsigelsesniveau

De fleste forudsigelser oprettes på kundeniveau. I visse situationer er det måske ikke så detaljeret, at det opfylder forretningsbehovene. Du kan f.eks. bruge denne funktion til at forudsige afgang i en forgrening for en kunde i stedet for kunden som en helhed.

1. Hvis du vil oprette en forudsigelse på et mere detaljeret niveau end kunden, skal du vælge **Vælg objekt for et sekundært niveau**. Hvis indstillingen ikke er tilgængelig, skal du kontrollere, at du har fuldført forrige afsnit.

1. Udvid de objekter, du vil vælge det sekundære niveau fra, eller brug søgefilterfeltet til at filtrere de valgte indstillinger.

1. Vælg den attribut, der skal bruges som sekundært niveau, og vælg derefter **Tilføj**.

1. Vælg **Næste**.

> [!NOTE]
> De objekter, der er tilgængelige i dette afsnit, vises, fordi de har en relation til det objekt, du vælger i forrige afsnit. Hvis du ikke kan se det objekt, du vil tilføje, skal du kontrollere, at det har en gyldig relation i **Relationer**. Der er kun én til én- og mange-til-én-relationer, der er gyldige for denne konfiguration.

### <a name="add-additional-data-optional"></a>Tilføje yderligere data (valgfrit)

Konfigurer relationen fra kundeaktivitetsobjektet til *Kunde*-objektet.

1. Vælg det felt, der identificerer kunden i objektet kundeaktivitetsoversigt. Det kan relateres direkte til det primære kunde-id for *Kunde*-objektet.

1. Vælg det objekt, der er det primære *Kunde*-objekt.

1. Angiv et navn, der beskriver relationen.

#### <a name="customer-activities"></a>Kundeaktiviteter

1. Du kan også vælge **Tilføj data** til **Kundeaktiviteter**.

1. Vælg den semantiske aktivitetstype, der indeholder de data, du vil bruge, og vælg derefter en eller flere aktiviteter i sektionen **Aktiviteter**.

1. Vælg en aktivitetstype, der svarer til den type kundeaktivitet, du konfigurerer. Vælg **Opret ny**, og vælg en tilgængelig aktivitetstype, eller opret en ny type.

1. Vælg **Næste** og derefter **Gem**.

1. Hvis du har andre kundeaktiviteter, som du vil medtage, skal du gentage trinnene ovenfor.

#### <a name="customers-data"></a>Kundedata

1. Vælg også **Tilføj data** for **Kundedata**.

1. Knyt de semantiske attributter til felter i dine egne kundedata som identificeret. Dataene i de felter, der bruges, bør ikke ændres ofte for at sikre, at modellen opnår den bedste ydeevne. Hvis du f.eks. vælger et felt til "Klassificering", der er ændret hver måned, bruges den sidste værdi i forudsigelsen, selvom den historisk set måske ikke gælder for kunden, når forudsigelsesmønstrene opbygges.

1. Vælg **Næste**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Angive en valgfri liste over benchmarkkonti

Tilføj en liste over de forretningskunder og konti, du vil bruge som benchmarks. Du får [detaljer om disse benchmarkkonti](#review-a-prediction-status-and-results), herunder deres kundeafgangsscore og de mest betydende funktioner, der har påvirket deres forudsigelse af kundeafgang.

1. Vælg **+ Tilføj kunder**.

1. Vælg de kunder, der fungerer som benchmark.

1. Vælg **Næste** for at fortsætte.

---

### <a name="set-schedule-and-review-configuration"></a>Angive konfiguration for planlægning og evaluering

1. Angiv en hyppighed for at omskole modellen. Denne indstilling er vigtig, hvis du vil opdatere nøjagtigheden af forudsigelserne, efterhånden som nye data indsættes. De fleste virksomheder kan omskole én gang om måneden og opnå en god præcision af deres forudsigelse.

1. Vælg **Næste**.

1. Gennemgå forudsigelsen for konfigurationen. Du kan gå tilbage til tidligere trin ved at vælge **Rediger** under den viste værdi. Du kan også vælge et konfigurationstrin i statusindikatoren.

1. Hvis alle værdier er konfigureret korrekt, skal du vælge **Gem og kør** for at starte forudsigelsesprocessen. Du kan se statussen for dine forudsigelser under fanen **Mine forudsigelser**. Det kan tage flere timer, før processen er fuldført, afhængigt af mængden af data, der bruges i forudsigelsen.

## <a name="review-a-prediction-status-and-results"></a>Gennemgå en forudsigelses status og resultater

1. Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**.

1. Vælg den forudsigelse, du vil gennemse.
   - **Forudsigelsesnavn**: Navnet på den forudsigelse, der blev angivet under oprettelsen.
   - **Forudsigelsestype**: Den modeltype, der bruges til forudsigelse
   - **Outputobjekt**: Navnet på det objekt, som outputtet af forudsigelsen skal gemmes i. Du kan finde et objekt med dette navn på **Data** > **Objekter**.
     I outputobjektet er *ChurnScore* den anslåede sandsynlighed for kundeafgang, og *IsChurn* er en binær etiket baseret på *ChurnScore* med en tærskelværdi på 0,5. Standardgrænsen fungerer muligvis ikke i dit scenarie. [Opret et nyt segment](segments.md#create-a-new-segment) med din foretrukne grænseværdi.
     Ikke alle kunder er nødvendigvis aktive kunder. Nogle af dem har måske ikke haft nogen aktivitet i lang tid og betragtes som allerede som afgåede baseret på din afgangsdefinition. Det er ikke nyttigt at forudsige afgangsrisiko for kunder, der allerede er afgået, da de ikke er den interessante målgruppe.
   - **Forudsagt felt**: Dette felt udfyldes kun i forbindelse med visse typer forudsigelser og bruges ikke i forudsigelse af kundeafgang.
   - **Status**: Status for forudsigelseskørslen
        - **I kø**: Forudsigelse venter på, at andre processer køres.
        - **Opdatering**: Forudsigelse kører i øjeblikket for at producere resultater, der vil blive overført til outputenheden.
        - **Mislykket**: Forudsigelse kunne ikke køres. Du kan finde flere oplysninger i [logfilerne](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Lykkedes**: Forudsigelse blev fuldført. Vælg **Vis** under de lodrette ellipser for at gennemgå forudsigelse.
   - **Redigeret**: Den dato, hvor konfigurationen af forudsigelse blev ændret.
   - **Sidst opdateret**: Den dato, hvor forudsigelsen opdaterede resultater i outputenheden.

1. Vælg de lodrette ellipser ud for den forudsigelse, du vil gennemgå resultaterne for, og vælg **Vis**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Vis kontrol for at se resultater af en forudsigelse.":::

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

1. Der findes tre primære sektioner med data på resultatsiden:
   - **Træningsmodellens ydeevne**: A, B eller C er mulige scorer. Denne score ydeevnen af forudsigelsen og kan hjælpe dig med at træffe beslutningen om at bruge de resultater, der er gemt i outputobjektet. Scorer bestemmes ud fra følgende regler: 
        - **A**, når modellen forventes at forudse mindst 50 % af de samlede forudsigelser, og når procentsatsen for præcise forudsigelser for kunder, der er afgået, er større end den oprindelige sats, med mindst 10 %.
            
        - **B**, når modellen forventes at forudse mindst 50 % af de samlede forudsigelser, og når procentsatsen for præcise forudsigelser for kunder, der er afgået, er op til 10 % større end den oprindelige sats.
            
        - **CB**, når modellen forventes at forudse mindre end 50 % af de samlede forudsigelser, eller når procentsatsen for præcise forudsigelser for kunder, der er afgået, er mindre end den oprindelige sats.
               
        - **Oprindelig plan** tager forudsigelsestidsvinduets input for modellen (f. eks. et år), og modellen opretter forskellige brøkdele af tiden ved at dividere den med 2, indtil den er på en måned eller mindre. Disse brøker bruges til at oprette en forretningsregel for kunder, der ikke har købt i denne tidsramme. Disse kunder betragtes som afgået. Den tidsbaserede forretningsregel med den højeste mulighed for at forudse, hvem der sandsynligvis afgår, vælges som oprindelig plan.
            
    - **Sandsynlighed for afgang (antal kunder)**: Kundegrupper baseret på deres forudsagte risiko for afgang. Du kan senere bruge disse data, hvis du vil oprette et kundesegment med stor risiko for afgang. Sådanne segmenter hjælper dig med at forstå, hvor din grænse skal være for segmentmedlemskab.
       
    - **Mest indflydelsesrige faktorer**: Der er mange faktorer, som tages i betragtning ved oprettelsen af din forudsigelse. Hver af faktorerne er vigtig for de aggregerede forudsigelser, som en model opretter. Du kan bruge disse faktorer til at validere resultaterne af forudsigelse, eller du kan bruge disse oplysninger senere til at [oprette segmenter](segments.md), der kan have indflydelse på kundernes afgangsrisiko.


# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

1. Der findes tre primære sektioner med data på resultatsiden:
   - **Træningsmodellens ydeevne**: A, B eller C er mulige scorer. Denne score ydeevnen af forudsigelsen og kan hjælpe dig med at træffe beslutningen om at bruge de resultater, der er gemt i outputobjektet. Scorer bestemmes ud fra følgende regler: 
        - **A**, når modellen forventes at forudse mindst 50 % af de samlede forudsigelser, og når procentsatsen for præcise forudsigelser for kunder, der er afgået, er større end den oprindelige sats, med mindst 10 %.
            
        - **B**, når modellen forventes at forudse mindst 50 % af de samlede forudsigelser, og når procentsatsen for præcise forudsigelser for kunder, der er afgået, er op til 10 % større end den oprindelige sats.
            
        - **CB**, når modellen forventes at forudse mindre end 50 % af de samlede forudsigelser, eller når procentsatsen for præcise forudsigelser for kunder, der er afgået, er mindre end den oprindelige sats.
               
        - **Oprindelig plan** tager forudsigelsestidsvinduets input for modellen (f. eks. et år), og modellen opretter forskellige brøkdele af tiden ved at dividere den med 2, indtil den er på en måned eller mindre. Disse brøker bruges til at oprette en forretningsregel for kunder, der ikke har købt i denne tidsramme. Disse kunder betragtes som afgået. Den tidsbaserede forretningsregel med den højeste mulighed for at forudse, hvem der sandsynligvis afgår, vælges som oprindelig plan.
            
    - **Sandsynlighed for afgang (antal kunder)**: Kundegrupper baseret på deres forudsagte risiko for afgang. Du kan senere bruge disse data, hvis du vil oprette et kundesegment med stor risiko for afgang. Sådanne segmenter hjælper dig med at forstå, hvor din grænse skal være for segmentmedlemskab.
       
    - **Mest indflydelsesrige faktorer**: Der er mange faktorer, som tages i betragtning ved oprettelsen af din forudsigelse. Hver af faktorerne er vigtig for de aggregerede forudsigelser, som en model opretter. Du kan bruge disse faktorer til at validere resultaterne af forudsigelse, eller du kan bruge disse oplysninger senere til at [oprette segmenter](segments.md), der kan have indflydelse på kundernes afgangsrisiko.


1. For forretningskonti findes der en side med **Analyse af indflydelsesrige funktioner**. Den indeholder fire afsnit af data:

    - Det element, der vælges i ruden til højre, bestemmer indholdet på denne side. Vælg et element fra **Bedste kunder** eller **Benchmarkkunder**. Begge lister sorteres efter faldende værdi af kundeafgangsscore, uanset om scoren kun er for kunden eller en samlet score for kunder og et sekundært niveau som produktkategori.
        
        - **Bedste kunder**: Liste over ti kunder med den højeste risiko for kundeafgang og laveste risiko for kundeafgang baseret på deres kundeafgangsscorer. 
        - **Benchmarkkunder**: Liste over op til ti kunder, der blev valgt under konfigurationen af modellen.
 
    - **Kundeafgangsscore:** Viser kundeafgangsscoren for det valgte element i ruden til højre.
    
    - **Fordeling af risiko for kundeafgang:** Viser fordeling af risiko for kundeafgang på tværs af kunder og den percentil, den valgte kunde er i. 
    
    - **Vigtigste funktioner, der øger og reducerer risikoen for kundeafgang:** For det valgte element i ruden til højre vises de fem vigtigste funktioner, der øgede og reducerede risikoen for kundeafgang. For indflydelsesrig funktion finder du værdien af funktionen for det pågældende element og dens indflydelse på kundeafgangsscoren. Den gennemsnitlige værdi af hver funktion på tværs af lave, mellem og høje kundeafgangssegmenter vises også. Det giver en bedre kontekst af værdierne af de vigtigste funktioner for det valgte element og sammenligner det med lave, mellemstore og høje kundeafgangssegmenter.

       - Lav: konti eller kombinationer af konto og sekundært niveau med en kundeafgangsscore mellem 0 og 0,33
       - Medium: konti eller kombinationer af konti og sekundære niveauer med en kundeafgangsscore mellem 0,33 og 0,66
       - Høj: konti eller kombinationer af konti og sekundære niveauer med en kundeafgangsscore over 0,66
    
       Når du forudsiger kundeafgang på kontoniveau, tages alle konti i betragtning med henblik på at udlede de gennemsnitlige funktionsværdier for kundeafgangssegmenter. I forbindelse med forudsigelser af kundeafgang på sekundært niveau for hver konto afhænger afledningen af kundeafgangssegmenter af det sekundære niveau for det element, der er valgt i sideruden. Hvis et element f.eks. har et sekundært niveau af produktkategorien = kontorartikler, er det kun de elementer, der har kontorartikler som produktkategori, der tages i betragtning, når de gennemsnitlige funktionsværdier for kundeafgangssegmenter afledes. Denne logik anvendes for at sikre en rimelig sammenligning af elementers funktionsværdier med de gennemsnitlige værdier i lave, mellem og høje afgangssegmenter.

       I visse tilfælde er den gennemsnitlige værdi af lave, mellem eller høje afgangssegmenter tom eller ikke tilgængelig, fordi der ikke er elementer, der tilhører de tilsvarende kundeafgangssegmenter, baseret på ovenstående definition.
       
       > [!NOTE]
       > Værdierne under de gennemsnitlige lave, mellemstore og høje kolonner er forskellige for kategoriske funktioner som land eller branche. Da den almindelige funktionsværdi for "gennemsnitlig" ikke gælder for kategoriske funktioner, er værdierne i disse kolonner proportionen mellem kunder i lav-, mellem- eller højskærmssegmenter, der har samme værdi som den kategoriske funktion i forhold til det element, der er valgt i sidepanelet.

---

## <a name="manage-predictions"></a>Administrere forudsigelser

Det er muligt at optimere, foretage fejlfinding, opdatere eller slette forudsigelser. Gennemgå en rapport om dataanvendelighed for at finde ud af, hvordan du gør en forudsigelse hurtigere og mere pålidelig. Du kan finde flere oplysninger i [Administrere forudsigelser](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
