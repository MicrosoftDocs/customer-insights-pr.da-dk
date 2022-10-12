---
title: Forudsige kundens levetidsværdi (CLV)
description: Indtægtskilde for aktive kunder i fremtiden.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610367"
---
# <a name="predict-customer-lifetime-value-clv"></a>Forudsige kundens levetidsværdi (CLV)

Potentiel værdi (omsætning), som de enkelte aktive kunder henter ind i virksomheden via en defineret fremtidig tidsperiode. Denne forudsigelse hjælper dig med at:

- Identificere kunder af høj værdi, og bearbejde denne indsigt.
- Oprette strategiske kundesegmenter baseret på deres potentielle værdi for at køre tilpassede kampagner med målrettede salgs-, marketing- og supportindsatser.
- Vejlede i produktudvikling ved at fokusere på funktioner, der øger kundeværdien.
- Optimere salgs- eller marketingstrategien og tildeling af budget mere nøjagtigt til kundekontakt.
- Genkende og belønne kunder med høj værdi via loyalitets- eller præmieprogrammer.

Find ud af, hvad CLV betyder for virksomheden. Vi understøtter transaktionsbaseret CLV-forudsigelse. En kundes samlede værdi er baseret på oversigten over forretningstransaktioner. Overvej at oprette flere modeller med forskellige inputindstillinger og sammenligne modelresultater for at se, hvilket modelscenarie der passer bedst til dine forretningsbehov.

> [!TIP]
> Prøv CLV-forudsigelse ved hjælp af eksempeldata: [Vejledning til eksempel på forudsigelse af kundens levetidsværdi (CLV)](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Forudsætninger

- Mindst [Bidragyder](permissions.md)-tilladelser
- Mindst 100 unikke kunder, helst mere end 10.000 kunder
- Kunde-id: et entydigt id, der skal svare til transaktioner med en enkelt kunde
- Mindst et års transaktionshistorik, helst to til tre år. Ideelt set mindst to til tre transaktioner pr. kunde-id, helst på tværs af flere datoer. Transaktionshistorikken skal omfatte:
  - **Transaktions-id**: Entydigt id for hver transaktion
  - **Transaktionsdato**: Dato eller tidsstempel for hver transaktion
  - **Transaktionsbeløb**: Pengeværdi (f.eks. omsætning eller avance) for hver transaktion
  - **Etiket, der er tildelt til returneringer**: Boolesk sand/falsk-værdi, der angiver, om transaktionen er en returvare
  - **Produkt-id**: Produkt-id for det produkt, der er involveret i transaktionen
- Data om kundeaktiviteter:
  - **Primær nøgle**: Entydigt id for en aktivitet
  - **Tidsstempel**: Dato og klokkeslæt for hændelsen, der identificeres af den primære nøgle
  - **Hændelse (aktivitetsnavn):** Navnet på den hændelse, du vil bruge
  - **Detaljer (beløb eller værdi)**: Detaljer om kundeaktiviteten
- Yderligere data, f.eks.:
  - Webaktiviteter: Oversigt over besøg på websted eller mailoversigt
  - Loyalitetsaktiviteter: Akkumulerede loyalitetspoint og oversigt over loyalitetspræmier
  - Kundeservice oversigt over logfiler: Serviceopkald, klager eller returneringer
  - Kundeprofil-id
- Mindre end 20 % manglende værdier i obligatoriske felter

> [!NOTE]
> Der kan kun konfigureres ét transaktionsoversigtsobjekt. Hvis der er flere købs- eller transaktionsobjekter, kan du samle dem i Power Query, før dataindtagelse går i gang.

## <a name="create-a-customer-lifetime-value-prediction"></a>Oprette kundens levetidsværdi (CLV) forudsigelse

Du kan når som helst vælge **Gem kladde** for at gemme forudsigelsen som en kladde. Kladdeforudsigelsen vises under fanen **Mine forudsigelser**.

1. Gå til **Intelligens** > **Forudsigelser**.

1. Gå til fanen **Opret**, og vælg **Brug model** i feltet **Kundens levetidsværdi**.

1. Vælg **Start her**.

1. **Navngive denne model** og **navnet på outputobjektet** for at skelne mellem dem fra andre modeller eller objekter.

1. Vælg **Næste**.

### <a name="define-model-preferences"></a>Definere modelindstillinger

1. Angiv en **Forudsigelsesperiode** for at definere, hvor langt i fremtiden CLV skal være. Enheden angives som standard som måneder.

   > [!TIP]
   > Hvis du vil forudsige CLV nøjagtigt for den angivne tidsperiode, skal der angives en sammenligningsperiode med historiske data. Hvis du f.eks. vil forudsige CLV for de næste 12 måneder, skal du have mindst 18-24 måneders historiske data.

1. Angiv den tidsramme, hvor en kunde skal have haft mindst én transaktion, for at blive fundet aktiv. Modellen forudsiger kun CLV for **Aktive kunder**.
   - **Lad model beregne købsinterval (anbefales)**: I modellen analyseres dataene, og en tidsperiode bestemmes på baggrund af historiske køb.
   - **Angiv intervallet manuelt**: Tidsperiode for din definition af en aktiv kunde.

1. Definer percentilen for **Kunde med høj værdi**.
    - **Modelberegning (anbefales)**: Modellen bruger en 80/20-regel. Den procentdel af kunderne, der har givet en samlet omsætning på 80 % for virksomheden i den historiske periode, betragtes som kunder af høj værdi. Mindre end 30-40 procent af kunderne bidrager som regel til en samlet omsætning på procent. Dette antal kan dog variere, afhængigt af virksomhed og branche.
    - **Procent af aktive kunder i top**: Specifik percentil for en kunde af høj værdi. Du kan f.eks. angive **25** for at definere kunder af høj værdi som de øverste 25 % af de fremtidige betalende kunder.

    Hvis virksomheden definerer kunder af høj værdi på en anden måde, skal du [fortælle os det, som vi gerne vil høre](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Vælg **Næste**.

### <a name="add-required-data"></a>Tilføj påkrævede data

1. Vælg **Tilføj data** for **Kundetransaktionshistorik**.

1. Vælg den semantiske aktivitetstype, **SalesOrder** eller **SalesOrderLine**, der indeholder transaktionshistorikken. Hvis aktiviteten ikke er blevet konfigureret, skal du vælge **her** og oprette den.

1. Hvis aktivitetsattributterne blev semantically tilknyttet under **Aktiviteter**, da aktiviteten blev oprettet, skal du vælge de specifikke attributter eller det objekt, beregningen skal fokusere på. Hvis der ikke blev udført en semantisk tilknytning, skal du vælge **Rediger** og tilknytte dataene.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Tilføje påkrævede data for CLV-modellen":::

1. Vælg **Næste**, og gennemse de attributter, der kræves til denne model.

1. Vælg **Gem**.

1. Tilføj flere aktiviteter, eller vælg **Næste**.

### <a name="add-optional-activity-data"></a>Tilføj ekstra aktivitetsdata

Data, der afspejler vigtige kundeinteraktioner (f.eks. web-, kundeservice- og hændelseslogfiler), føjer kontekst til transaktionsposter. Flere mønstre, der findes i kundeaktivitetsdataene, kan gøre forudsigelserne mere nøjagtige.

1. Vælg **Tilføj data** under **Gør modelindsigten stærkere med yderligere aktivitetsdata**.

1. Vælg en aktivitetstype, der svarer til den type kundeaktivitet, du tilføjer. Hvis aktiviteten ikke er blevet konfigureret, skal du vælge **her** og oprette den.

1. Hvis aktivitetsattributterne blev tilknyttet under **Aktiviteter**, da aktiviteten blev oprettet, skal du vælge de specifikke attributter eller det objekt, beregningen skal fokusere på. Hvis der ikke blev udført en tilknytning, skal du vælge **Rediger** og tilknytte dataene.

1. Vælg **Næste**, og gennemse de attributter, der kræves til denne model.

1. Vælg **Gem**.

1. Vælg **Næste**.

1. [Tilføj valgfrie kundedata](#add-optional-customer-data), eller vælg **Næste**, og gå til [Indstille opdateringsplan](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Tilføje yderligere data (valgfrit)

Vælg mellem 18 almindeligt anvendte kundeprofilattributter, der skal inkluderes som input til modellen. Disse attributter kan føre til mere personlige, relevante og brugbare modelresultater for dine sager i forbindelse med forretningsbrug.

Contoso Coffee ønsker f.eks., at kundernes levetidsværdi skal nå ud til kunder med høj værdi med et personligt tilbud, der relaterer sig til lanceringen af deres nye maskiner. Contoso bruger CLV-modellen og tilføjer alle 18 kundeprofilattributter for at se, hvilke faktorer der påvirker deres kunder med den højeste værdi. Kundernes placering er den mest effektive faktor for disse kunder.
Med disse oplysninger organiserer de en lokal begivenhed for lanceringen af maskinerne og er partner med lokale leverandører for at få tilpassede tilbud og en særlig oplevelse ved arrangementet. Uden disse oplysninger har Contoso måske kun sendt generiske marketingmails og ikke fået mulighed for at tilpasse til dette lokale segment af deres kunder af høj værdi.

1. Vælg **Tilføj data** under **Gør modelindsigten stærkere med yderligere kundedata**.

1. For **Objekt** skal du vælge **Kunde: CustomerInsights** for at vælge den samlede kundeprofil, der knyttes til kundeattributdata. Vælg **System.Customer.CustomerId** for **Kunde-id**.

1. Tilknyt flere felter, hvis dataene er tilgængelige i dine ensartede kundeprofiler.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Eksempel på tilknyttede felter til kundeprofildata.":::

1. Vælg **Gem**.

1. Vælg **Næste**.

### <a name="set-update-schedule"></a>Indstil opdateringsplan

1. Vælg, hvor ofte modellen skal gentrænes på baggrund af de nyeste data. Denne indstilling er vigtig, hvis du vil opdatere nøjagtigheden af forudsigelser, efterhånden som nye data indtages til Customer Insights. De fleste virksomheder kan omskole én gang om måneden og opnå en god præcision af deres forudsigelse.

1. Vælg **Næste**.

### <a name="review-and-run-the-model-configuration"></a>Gennemse og kør modelkonfigurationen

I trinnet **Gennemse og kør** vises en oversigt over konfigurationen, og her kan du foretage ændringer, før du opretter forudsigelsen.

1. Vælg **Rediger** på et af trinnene for at gennemse og foretage ændringer.

1. Hvis du er tilfreds med dine valg, skal du vælge **Gem og kør** for at starte kørsel af modellen. Vælg **Udført**. Fanen **Mine forudsigelser** vises, mens forudsigelse oprettes. Det kan tage flere timer, før processen er fuldført, afhængigt af mængden af data, der bruges i forudsigelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Få vist forudsigelsesresultater

1. Gå til **Intelligens** > **Forudsigelser**.

1. Under fanen **Mine forudsigelser** skal du vælge den forudsigelse, du vil have vist.

Der findes tre primære sektioner med data på resultatsiden.

- **Ydeevne for træning af model**: Klassificeringerne A, B eller C angiver resultatet af forudsigelsen og kan hjælpe dig med at træffe beslutning om at bruge de resultater, der er gemt i outputobjektet.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Billede af feltet med oplysninger om modelpoint med vurderingen A.":::

  Customer Insights vurderer, hvordan AI-modellen præsterede under forudsigelse af kunder af høj værdi i forhold til den oprindelige model.

  Vurderingerne bestemmes ud fra følgende regler:
  - **A** når modellen nøjagtigt har forudsagt mindst 5 % flere kunder med høj værdi i forhold til den oprindelige model.
  - **B** når modellen nøjagtigt har forudsagt 0-5 % flere kunder med høj værdi i forhold til den oprindelige model.
  - **C** når modellen nøjagtigt har forudsagt færre kunder med høj værdi i forhold til den oprindelige model.
  
  Vælg [**Få mere at vide om denne score**](#learn-about-the-score) for at åbne ruden **Modelbedømmelse**, som viser flere detaljer om AI-modelydeevnen og den grundlæggende model. Det hjælper dig med at forstå de underliggende målepunkter for modelresultater, og hvordan klassificeringen af det endelige modelresultat blev afledt. I den grundlæggende model bruges en ikke-AI-baseret metode til at beregne kundens levetidsværdi, primært på baggrund af historiske indkøb foretaget af kunder.

- **Værdi af kunder efter percentil**: Kunder med lav værdi og høj værdi vises i et diagram. Hold musen hen over søjlerne i histogrammet for at se antallet af kunder i de enkelte grupper og den gennemsnitlige CLV for den pågældende gruppe. Du kan også [oprette kundesegmenter](prediction-based-segment.md) baseret på deres CLV-forudsigelser.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Værdi af kunder efter percentil for CLV-model":::

- **De fleste faktorer, der påvirker indflydelsen**: Der tages forskellige faktorer i betragtning, når du opretter forudsigelse CLV baseret på de inputdata, der leveres til AI-modellen. Hver af faktorerne får beregnet deres betydning for de samlede forudsigelser, som en model opretter. Brug disse faktorer til at validere dine forudsigelsesresultater. Disse faktorer giver også større indsigt i de faktorer, der gør det muligt at vælge CLV på tværs af alle dine kunder.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Mest indflydelsesrige faktorer for CLV-model":::

### <a name="learn-about-the-score"></a>Få mere at vide om scoren

Den standardformel, der bruges til at beregne CLV efter basismodellen:

 _**CLV for hver kunde** = Gennemsnitlig månedligt køb foretaget af kunden i vinduet med aktive kunder * Antal måneder i CLV-forudsigelsesperioden * Samlet tilbageholdelseshastighed for alle kunder_

AI-modellen sammenlignes med den oprindelige model, der er baseret på to modelydeevnemetrikværdier.
  
- **Succesfrekvens, der spår kunder med stor værdi**

  Se forskellen i, hvordan kunder med høj værdi bruger AI-modellen i forhold til den oprindelige model. En succesrate på 84 procent betyder f.eks., at AI-modellen kunne registrere 84 procent nøjagtigt ud af alle kunder i uddannelsesdataene. Derefter sammenlignes denne succesrate med succesprocenten for den oprindelige model for at rapportere den relative ændring. Denne værdi bruges til at tildele modellen en vurdering.

- **Fejlmetrikværdier**

  Se modellens overordnede ydeevne med hensyn til fejl i forbindelse med forudsigelse af fremtidige værdier. Vi bruger den overordnede måling (Root Mean Squared Error) til at vurdere denne fejl. RMSE er en standardmåde at måle fejlen i en model på, når data, der skal anvendes, anvendes. AI-modellens RMSE sammenlignes med den RMSE i basismodellen, og den relative forskel rapporteres.

AI-modellen prioriterer den nøjagtige rangering af kunder efter den værdi, de tilfører din virksomhed. Så kun succesprocenten for kunder med høj værdi bruges til at opnå den endelige modelkvalitet. RMSE-målingen er følsom over for afvigende værdier. I scenarier, hvor du har en lille procentdel af kunder med utroligt høje indkøbsværdier, giver den overordnede RMSE-måling måske ikke det fulde billede af modelydeevnen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
