---
title: Transaktionsrelateret forudsigelse om afgang
description: Forudsig, om en kunde kan risikere ikke længere at købe virksomhedens produkter eller tjenester.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f0d56fc6595fcbb226897fcb52148924d00306b6d75b617fc8cafbcc0aab0641
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034903"
---
# <a name="transactional-churn-prediction-preview"></a>Transaktionsrelateret forudsigelse om afgang

Transaktionsrelateret forudsigelse om afgang er med til at forudsige, om en kunde ikke længere vil købe dine produkter eller tjenester i et bestemt tidsvindue. Du kan oprette nye forudsigelser om afgang på **Intelligens** > **Forudsigelser**. Vælg **Mine forudsigelser** for at få vist andre forudsigelser, du har oprettet.

> [!TIP]
> Prøv selvstudiet for at få en transaktionsrelateret forudsigelse om afgang ved at bruge eksempeldata: [Transaktionsrelateret forudsigelse om afgang (prøveversion) eksempelvejledning](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Forudsætninger

- Mindst [bidragydertilladelser](permissions.md) i Customer Insights.
- Forretningsviden for at forstå, hvad afgang betyder for din virksomhed. Vi understøtter timebaserede definitioner for afgang, hvilket vil sige, at en kunde anses for at have forladt dig efter en periode uden køb.
- Data om dine transaktioner/køb og deres oversigt:
    - Transaktions-id'er for at skelne mellem køb og transaktioner.
    - Kunde-id'er, der stemmer overens med transaktioner til dine kunder.
    - Datoer for posteringshændelser, som definerer de datoer, transaktionen forekom i.
    - Semantisk dataskema for køb/transaktioner kræver følgende oplysninger:
        - **Transaktions-id:** Et entydigt id for et køb eller en transaktion.
        - **Posteringsdato:** Fakturadatoen eller transaktionens købsdato.
        - **Værdi for posteringen:** Valutaen/den numeriske værdi i posteringen/elementet.
        - (Valgfrit) **Entydigt produkt-id:** Id for det produkt eller den tjeneste, du har købt, hvis dataene befinder sig på linjeelementniveau.
        - (Valgfrit) **Angiver, om denne transaktion var returneret:** Et sandt/falsk-felt, der identificerer, om posteringen var en returvare eller ej. Hvis **Værdi for transaktion** er negativ, bruger vi også disse oplysninger til at udlede et returvare.
- (Valgfri) Data om kundeaktiviteter:
    - Aktivitets-id'er, der skal skelne mellem aktiviteter af samme type.
    - Kunde-id'er, der knytter aktiviteter til dine kunder.
    - Aktivitetsoplysninger, der indeholder navnet på og datoen for aktiviteten.
    - Det semantiske dataskema for kundeaktiviteter omfatter:
        - **Primær nøgle:** Et entydigt id for en aktivitet. F.eks. et webstedbesøg eller en forbrugspost, der viser, at kunden har forsøgt et eksempel af produktet.
        - **Tidsstempel:** Dato og klokkeslæt for hændelsen, der identificeres af den primære nøgle.
        - **Hændelse:** Navnet på den hændelse, du vil bruge. Et felt, der kaldes "UserAction" i en forretning, kan f. eks. være en kupon, der bruges af kunden.
        - **Detaljer:** Detaljerede oplysninger om hændelsen. Et felt, der kaldes "CouponValue" i en forretning, kan f. eks. være valutaværdien af en kupon.
- Forslåede datakarakteristika:
    - Tilstrækkelige historiske data: Transaktionsdata for mindst det dobbelte af det valgte tidsvindue. Helst to til tre års transaktionshistorik. 
    - Flere køb pr. kunde: Ideelt mindst to transaktioner pr. kunde.
    - Antal kunder: Mindst 10 kundeprofiler, helst mere end 1.000 entydige kunder. Modellen kan ikke bruges af færre end 10 kunder og med utilstrækkelige historiske data.
    - Datafuldførelse: Mindre end 20 % af de manglende værdier i datafeltet for det angivne objekt.

> [!NOTE]
> For en virksomhed med mange kunders indkøbshyppighed (med få ugers mellemrum) anbefales det, at du vælger et kortere forudsigelsesvindue og afgangsdefinition. Hvis du har lav indkøbshyppighed (med få måneder mellemrum eller én gang om året), skal du vælge et længere forudsigelsesvindue og afgangsdefinition.

## <a name="create-a-transactional-churn-prediction"></a>Opret transaktionsrelateret forudsigelse om afgang

1. Gå til **Intelligens** > **Forudsigelser** i Customer Insights.

1. Vælg visningen **Afgangsmodel for kunde (prøveversion)**, og vælg **Brug denne model**.
   
1. Vælg **Transaktionsrelateret** i ruden **Afgangsmodel for kunde**, og vælg **Start her**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Skærmbillede med valgt transaktionsrelateret indstilling i ruden Afgangsmodel for kunde.":::

### <a name="name-model"></a>Navngiv model

1. Angiv et navn til modellen for at adskille den fra andre modeller.

1. Angiv et navn til outputenheden udelukkende med bogstaver og tal uden mellemrum. Det er det navn, som modelobjektet skal bruge. 

1. Vælg **Næste**.

### <a name="define-customer-churn"></a>Definer kundeafgang

1. Angiv et vindue med dage til forudsigelse af afgang i feltet **identificere kunder, der kan afgå i næste**. Du kan f. eks. forudsige risikoen for afgang af kunder i løbet af de næste 90 dage for at justere din marketingsindsats. Hvis du forudsiger afgangsrisikoen for en længere eller kortere tidsperiode, kan det være sværere at håndtere faktorerne i din risikoprofil vedrørende afgang, men den afhænger af virksomhedens specifikke behov. 
   >[!TIP]
   > Du kan til enhver tid vælge **Gem og Luk** for at gemme forudsigelsen som en kladde. Du kan se kladdeforudsigelsen under fanen **Mine forudsigelser** for at fortsætte.

1. Angiv det antal dage, afgang skal defineres i feltet **En kunde er afgået, hvis der ikke er foretaget køb i:**. Hvis kunden f. eks. ikke har foretaget køb inden for de seneste 30 dage, betragtes de muligvis som afgået for virksomheden. 

1. Vælge **Næste** for at fortsætte

### <a name="add-required-data"></a>Tilføj påkrævede data

1. Vælg **Tilføj data** til **Indkøbshistorik**, og vælg det objekt, der indeholder oplysninger om transaktionen/indkøbshistorikken, som beskrevet i [forudsætningerne](#prerequisites).

1. Tilknyt de semantiske felter til attributter i objektet indkøbsoversigt, og vælg **Næste**. Du kan finde beskrivelser af felterne under [forudsætningerne](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Tilknyt semantiske felter for indkøbsobjektet.":::

1. Hvis nedenstående felter ikke er udfyldt, skal du konfigurere relationen fra dit indkøbsoversigtsobjekt til kundeobjektet.
    1. Vælg **Indkøbsoversigtsobjekt**.
    1. Vælg det **Felt**, der identificerer kunden i objektet indkøbsoversigt. Det skal relateres til kundeobjektets primære kunde-id.
    1. Vælg det **Kundeobjekt**, der stemmer overens med dit primære kundeobjekt.
    1. Angiv et navn, der beskriver relationen.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Siden Indkøbsoversigt, der viser oprettelsen af en relation til kunde.":::
   
1. Vælg **Næste**.

1. Du kan også vælge **Tilføj data** til **Kundeaktiviteter**. Vælg det objekt, der indeholder oplysninger om kundeaktiviteten, som beskrevet i forudsætningerne.

1. Tilknyt de semantiske felter til attributter i objektet kundeaktivitet, og vælg **Næste**. Du kan finde beskrivelser af felterne under [forudsætningerne](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Tilknyt kundefelter til transaktionsdata.":::

1. Vælg en aktivitetstype, der svarer til den type kundeaktivitet, du konfigurerer. Vælg **Opret ny**, og vælg en tilgængelig aktivitetstype, eller opret en ny type.

1. Du skal konfigurere relationen fra kundeaktivitetsobjektet til kundeobjektet.
    1. Vælg det felt, der identificerer kunden i objektet kundeaktivitetsoversigt. Det kan relateres direkte til det primære kunde-id for kundeobjektet.
    1. Vælg det kundeobjekt, der stemmer overens med dit primære kundeobjekt.
    1. Angiv et navn, der beskriver relationen.

1. Vælg **Gem**.

1. Hvis du har andre kundeaktiviteter, som du vil medtage, skal du gentage trinnene ovenfor.

1. Vælg **Næste**.

### <a name="set-schedule-and-review-configuration"></a>Angive konfiguration for planlægning og evaluering

1. Angiv en hyppighed for at omskole modellen. Denne indstilling er vigtig, hvis du vil opdatere nøjagtigheden af forudsigelserne, efterhånden som nye data indsættes. De fleste virksomheder kan omskole én gang om måneden og opnå en god præcision af deres forudsigelse.

1. Vælg **Næste**.

1. Gennemgå forudsigelsen for konfigurationen. Du kan gå tilbage til tidligere trin ved at vælge **Rediger** under den viste værdi. Du kan også vælge et konfigurationstrin i statusindikatoren.

1. Hvis alle værdier er konfigureret korrekt, skal du vælge **Gem og kør** for at starte forudsigelsesprocessen. Du kan se statussen for dine forudsigelser under fanen **Mine forudsigelser**. Det kan tage flere timer, før processen er fuldført, afhængigt af mængden af data, der bruges i forudsigelsen.

## <a name="review-a-prediction-status-and-results"></a>Gennemgå en forudsigelses status og resultater

1. Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**.

1. Vælg den forudsigelse, du vil gennemse.
   - **Forudsigelsesnavn:** Navnet på den forudsigelse, der blev angivet under oprettelsen.
   - **Forudsigelsestype:** Den modeltype, der bruges til forudsigelse
   - **Outputobjekt:** Navnet på det objekt, som outputtet af forudsigelsen skal gemmes i. Du kan finde et objekt med dette navn på **Data** > **Objekter**.    
     I outputobjektet er *ChurnScore* den anslåede sandsynlighed for kundeafgang, og *IsChurn* er en binær etiket baseret på *ChurnScore* med en tærskelværdi på 0,5. Standardgrænsen fungerer muligvis ikke i dit scenarie. [Opret et nyt segment](segments.md#create-a-new-segment) med din foretrukne grænseværdi.
     Ikke alle kunder er nødvendigvis aktive kunder. Nogle af dem har måske ikke haft nogen aktivitet i lang tid og betragtes som allerede som afgåede baseret på din afgangsdefinition. Det er ikke brugbart at forudsige risikoen for kundeafgang for kunder, der allerede er afgået, fordi de ikke er en relevant målgruppe.
   - **Forventet felt:** Dette felt udfyldes kun i forbindelse med visse typer forudsigelser og bruges ikke i afgang af forudsigelse.
   - **Status:** Status for forudsigelseskørslen
        - **I kø:** Forudsigelse venter på, at andre processer køres.
        - **Opdatering:** Forudsigelse kører i øjeblikket for at producere resultater, der vil blive overført til outputenheden.
        - **Mislykket:** Forudsigelse kunne ikke køres. Du kan finde flere oplysninger i [logfilerne](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Lykkedes:** Forudsigelse blev fuldført. Vælg **Vis** under de lodrette ellipser for at gennemgå forudsigelse.
   - **Redigeret:** Den dato, hvor konfigurationen af forudsigelse blev ændret.
   - **Sidst opdateret:** Den dato, hvor forudsigelsen opdaterede resultater i outputenheden.

1. Vælg de lodrette ellipser ud for den forudsigelse, du vil gennemgå resultaterne for, og vælg **Vis**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Vis kontrol for at se resultater af en forudsigelse.":::   

1. Der findes tre primære sektioner med data på resultatsiden:
    1. **Træningsmodellens ydeevne:** A, B eller C er mulige scorer. Denne score ydeevnen af forudsigelsen og kan hjælpe dig med at træffe beslutningen om at bruge de resultater, der er gemt i outputobjektet. Scorer bestemmes ud fra følgende regler:
         
         - **A**, når modellen forventes at forudse mindst 50 % af de samlede forudsigelser, og når procentsatsen for præcise forudsigelser for kunder, der er afgået, er større end den oprindelige sats, med mindst 10 %.
            
         - **B**, når modellen forventes at forudse mindst 50 % af de samlede forudsigelser, og når procentsatsen for præcise forudsigelser for kunder, der er afgået, er op til 10 % større end den oprindelige sats.
            
         - **CB**, når modellen forventes at forudse mindre end 50 % af de samlede forudsigelser, eller når procentsatsen for præcise forudsigelser for kunder, der er afgået, er mindre end den oprindelige sats.
               
         - **Oprindelig plan** tager forudsigelsestidsvinduets input for modellen (f. eks. et år), og modellen opretter forskellige brøkdele af tiden ved at dividere den med 2, indtil den er på en måned eller mindre. Disse brøker bruges til at oprette en forretningsregel for kunder, der ikke har købt i denne tidsramme. Disse kunder betragtes som afgået. Den tidsbaserede forretningsregel med den højeste mulighed for at forudse, hvem der sandsynligvis afgår, vælges som oprindelig plan.
            
    1. **Sandsynlighed for afgang (antal kunder):** Kundegrupper baseret på deres forudsagte risiko for afgang. Du kan senere bruge disse data, hvis du vil oprette et kundesegment med stor risiko for afgang. Sådanne segmenter hjælper dig med at forstå, hvor din grænse skal være for segmentmedlemskab.
       
    1. **Mest indflydelsesrige faktorer:** Der er mange faktorer, som tages i betragtning ved oprettelsen af din forudsigelse. Hver af faktorerne er vigtig for de aggregerede forudsigelser, som en model opretter. Du kan bruge disse faktorer til at validere dine forudsigelsesresultater. Du kan også bruge oplysningerne senere til at [oprette segmenter](segments.md), der kan være med til at påvirke afgangsrisikoen for kunderne.

## <a name="manage-predictions"></a>Administrere forudsigelser

Det er muligt at optimere, foretage fejlfinding, opdatere eller slette forudsigelser. Gennemgå en rapport om dataanvendelighed for at finde ud af, hvordan du gør en forudsigelse hurtigere og mere pålidelig. Du kan finde flere oplysninger under [Administrere forudsigelser](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
