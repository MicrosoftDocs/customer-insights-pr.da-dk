---
title: Forudsigelse om transaktionsafgang (indeholder video)
description: Forudsig, om en kunde kan risikere ikke længere at købe virksomhedens produkter eller tjenester.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610505"
---
# <a name="predict-transaction-churn"></a>Forudsige transaktionsafgang

Transaktionsrelateret forudsigelse om afgang er med til at forudsige, om en kunde ikke længere vil købe dine produkter eller tjenester i et bestemt tidsvindue.

Du skal have forretningsviden for at forstå, hvad afgang betyder for din virksomhed. Vi understøtter timebaserede definitioner for afgang, hvilket vil sige, at en kunde anses for at have forladt dig efter en periode uden køb.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

I miljøer, der er baseret på forretningskonti, kan vi forudsige transaktionsafgang for en konto og også en kombination af kontooplysninger og et andet oplysningsniveau, f.eks. produktkategori. Hvis du f.eks. tilføjer en dimension, kan du se, hvor sandsynligt det er, at kontoen "Contoso" holder op med at købe produktkategorien "kontorartikler". I forbindelse med forretningskonti kan vi også bruge AI til at oprette en liste over potentielle årsager til, at et firma sandsynligvis vil afgå i en kategori af oplysninger på sekundært niveau.

> [!TIP]
> Prøv forudsigelsen af transaktionsafgang med eksempeldata: [Eksempelvejledning til forudsigelse af transaktionsafgang](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Forudsætninger

- Mindst [Bidragyder-tilladelser](permissions.md).
- Mindst 10 kundeprofiler, helst mere end 1.000 entydige kunder.
- Kunde-id'er, et entydigt id, der matcher transaktioner med dine kunder.
- Transaktionsdata for mindst det dobbelte af det valgte tidsvindue, f.eks. to til tre års transaktionshistorik. Ideelt set mindst to transaktioner pr. kunde. Transaktionshistorikken skal omfatte:
  - **Transaktions-id**: Entydigt id for et køb eller en transaktion.
  - **Transaktionsdato**: Købs- eller transaktionsdato.
  - **Værdi af transaktionen**: Valutaen eller den numeriske værdi af transaktionen.
  - **Entydigt produkt-id**: Id for det produkt eller den tjeneste, du har købt, hvis dataene befinder sig på linjeelementniveau.
  - **Angiver, om denne transaktion var en returnering**: Et sandt/falsk-felt, der identificerer, om transaktionen var en returvare eller ej. Hvis **Værdi for transaktion** er negativ, udleder vi en returvare.
- Kundeaktivitetsdata:
  - Kunde-id'er, et entydigt id, der knytter aktiviteter til dine kunder.
  - **Primær nøgle:** Entydigt id for en aktivitet. F.eks. et webstedbesøg eller en forbrugspost, der viser, at kunden har forsøgt et eksempel af produktet.
  - **Tidsstempel:** Dato og klokkeslæt for hændelsen, der identificeres af den primære nøgle.
  - **Hændelse:** Navnet på den hændelse, du vil bruge. Et felt, der kaldes "UserAction" i en forretning, kan f. eks. være en kupon, der bruges af kunden.
  - **Detaljer:** Detaljerede oplysninger om hændelsen. Et felt, der kaldes "CouponValue" i en forretning, kan f. eks. være valutaværdien af en kupon.
- Mindre end 20 % af de manglende værdier i datafeltet for det angivne objekt

I forbindelse med forretningskonti (B-to-B) skal du tilføje kundedata, der er justeret i forhold til mere statiske attributter for at sikre, at modellen fungerer bedst:
- **Kunde-id:** Entydigt id for en kunde.
- **Oprettelsesdato:** Dato, hvor kunden oprindeligt blev tilføjet.
- **Område :** En kundes område eller områdeadresse.
- **Land:** Kundens land.
- **Branche:** En kundes branchetype. Et felt, der f.eks. kaldes "Branche" i en kafferister, kan angive, om kunden var detail.
- **Klassificering:** Kategorisering af en kunde i din virksomhed. Et felt, der f.eks. kaldes "ValueSegment" i en kafferister, kan være kundeniveauet baseret på kundens størrelse.

> [!NOTE]
> For en virksomhed med mange kunders indkøbshyppighed (med få ugers mellemrum) anbefales det, at du vælger et kortere forudsigelsesvindue og afgangsdefinition. Hvis du har lav indkøbshyppighed (med få måneder mellemrum eller én gang om året), skal du vælge et længere forudsigelsesvindue og afgangsdefinition.

## <a name="create-a-transaction-churn-prediction"></a>Oprette en forudsigelse af transaktionsafgang

1. Gå til **Intelligens** > **Forudsigelser**.

1. Gå til fanen **Opret**, og vælg **Brug model** i feltet **Model til kundeafgang**.

1. Vælg **Transaktion** for typen af kundeafgang og derefter **Start her**.

1. **Navngive denne model** og **navnet på outputobjektet** for at skelne mellem dem fra andre modeller eller objekter.

1. Vælg **Næste**.

### <a name="define-customer-churn"></a>Definer kundeafgang

Du kan når som helst vælge **Gem kladde** for at gemme forudsigelsen som en kladde. Kladdeforudsigelsen vises under fanen **Mine forudsigelser**.

1. Angiv **Forudsigelsesvindue**. Du kan f. eks. forudsige risikoen for afgang af kunder i løbet af de næste 90 dage for at justere din marketingsindsats. Hvis du forudsiger afgangsrisikoen for en længere eller kortere tidsperiode, kan det være sværere at håndtere faktorerne i din risikoprofil vedrørende afgang, men den afhænger af virksomhedens specifikke behov.

1. Angiv antallet af dage for at definere afgang i feltet **Definition af kundeafgang**. Hvis kunden f. eks. ikke har foretaget et køb inden for de seneste 30 dage, betragtes de muligvis som afgået for virksomheden.

1. Vælg **Næste**.

### <a name="add-purchase-history"></a>Tilføj købshistorik

1. Vælg **Tilføj data** for **Kundetransaktionshistorik**.

1. Vælg den semantiske aktivitetstype, **SalesOrder** eller **SalesOrderLine**, der indeholder oplysningerne om transaktionshistorikken. Hvis aktiviteten ikke er blevet konfigureret, skal du vælge **her** og oprette den.

1. Hvis aktivitetsattributterne blev semantically tilknyttet under **Aktiviteter**, da aktiviteten blev oprettet, skal du vælge de specifikke attributter eller det objekt, beregningen skal fokusere på. Hvis der ikke blev udført en semantisk tilknytning, skal du vælge **Rediger** og tilknytte dataene.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Sideruden viser, hvordan du vælger bestemte aktiviteter under den semantiske type.":::

1. Vælg **Næste**, og gennemse de attributter, der kræves til denne model.

1. Vælg **Gem**.

1. Tilføj flere aktiviteter, eller vælg **Næste**.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Tilføje yderligere data (valgfrit)

1. Vælg **Tilføj data** for **Kundeaktiviteter**.

1. Vælg den semantiske aktivitetstype, der indeholder de data, som du vil bruge. Hvis aktiviteten ikke er blevet konfigureret, skal du vælge **her** og oprette den.

1. Hvis aktivitetsattributterne blev semantically tilknyttet under **Aktiviteter**, da aktiviteten blev oprettet, skal du vælge de specifikke attributter eller det objekt, beregningen skal fokusere på. Hvis der ikke blev udført en semantisk tilknytning, skal du vælge **Rediger** og tilknytte dataene.

1. Vælg **Næste**, og gennemse de attributter, der kræves til denne model.

1. Vælg **Gem**.

1. Vælg **Næste**

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

### <a name="select-prediction-level"></a>Vælge forudsigelsesniveau

De fleste forudsigelser oprettes på kundeniveau. I visse situationer er det måske ikke så detaljeret, at det opfylder forretningsbehovene. Brug f.eks. denne funktion til at forudsige afgang i en forgrening for en kunde i stedet for kunden som en helhed.

1. Vælg **Vælg objekt til et sekundært niveau**. Hvis indstillingen ikke er tilgængelig, skal du kontrollere, at du har fuldført forrige afsnit.

1. Udvid de objekter, du vil vælge det sekundære niveau fra, eller brug søgefilterfeltet til at filtrere de valgte indstillinger.

1. Vælg den attribut, der skal bruges som sekundært niveau, og vælg derefter **Tilføj**.

1. Vælg **Næste**.

> [!NOTE]
> De objekter, der er tilgængelige i dette afsnit, vises, fordi de har en relation til det objekt, du vælger i forrige afsnit. Hvis du ikke kan se det objekt, du vil tilføje, skal du kontrollere, at det har en gyldig relation i **Relationer**. Der er kun én til én- og mange-til-én-relationer, der er gyldige for denne konfiguration.

### <a name="add-additional-data-optional"></a>Tilføje yderligere data (valgfrit)

1. Vælg **Tilføj data** for **Kundeaktiviteter**.

1. Vælg den semantiske aktivitetstype, der indeholder de data, som du vil bruge. Hvis aktiviteten ikke er blevet konfigureret, skal du vælge **her** og oprette den.

1. Hvis aktivitetsattributterne blev semantically tilknyttet under **Aktiviteter**, da aktiviteten blev oprettet, skal du vælge de specifikke attributter eller det objekt, beregningen skal fokusere på. Hvis der ikke blev udført en semantisk tilknytning, skal du vælge **Rediger** og tilknytte dataene.

1. Vælg **Næste**, og gennemse de attributter, der kræves til denne model.

1. Vælg **Gem**.

1. Vælg **Næste**

1. Vælg også **Tilføj data** for **Kundedata**.

1. Knyt de semantiske attributter til felter i dine egne kundedata som identificeret. Dataene i de felter, der bruges, bør ikke ændres ofte for at sikre, at modellen opnår den bedste ydeevne. Hvis du f.eks. vælger et felt til "Klassificering", der er ændret hver måned, bruges den sidste værdi i forudsigelsen, selvom den historisk set måske ikke gælder for kunden, når forudsigelsesmønstrene opbygges.

1. Vælg **Næste**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Angive en valgfri liste over benchmarkkonti

Tilføj en liste over de forretningskunder og konti, du vil bruge som benchmarks. [Detaljerne om disse benchmarkkonti](#view-prediction-results) indeholder deres kundeafgangsscore og de mest betydende funktioner, der har påvirket deres forudsigelse af kundeafgang.

1. Vælg **+ Tilføj kunder**.

1. Vælg de kunder, der fungerer som benchmark.

1. Vælg **Næste**.

---

### <a name="set-update-schedule"></a>Indstil opdateringsplan

1. I forbindelse med trinnet **Dataopdateringer** skal du vælge en hyppighed for gentræning af modellen. Denne indstilling er vigtig, hvis du vil opdatere nøjagtigheden af forudsigelser, efterhånden som nye data indtages til Customer Insights. De fleste virksomheder kan omskole én gang om måneden og opnå en god præcision af deres forudsigelse.

1. Vælg **Næste**.

### <a name="review-and-run-the-model-configuration"></a>Gennemse og kør modelkonfigurationen

I trinnet **Gennemse og kør** vises en oversigt over konfigurationen, og her kan du foretage ændringer, før du opretter forudsigelsen.

1. Vælg **Rediger** på et af trinnene for at gennemse og foretage ændringer.

1. Hvis du er tilfreds med dine valg, skal du vælge **Gem og kør** for at starte kørsel af modellen. Vælg **Udført**. Fanen **Mine forudsigelser** vises, mens forudsigelse oprettes. Det kan tage flere timer, før processen er fuldført, afhængigt af mængden af data, der bruges i forudsigelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Få vist forudsigelsesresultater

1. Gå til **Intelligens** > **Forudsigelser**.

1. Under fanen **Mine forudsigelser** skal du vælge den forudsigelse, du vil have vist.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

Der findes tre primære sektioner med data på resultatsiden:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

Der findes tre primære sektioner med data på resultatsiden:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Informationssiden **Analyse af indflydelsesrige funktioner** indeholder fire dataafsnit:

- I højre rude skal du vælge et element fra **Bedste kunder** eller **Benchmarkkunder**. Begge lister sorteres efter faldende værdi af kundeafgangsscore, uanset om scoren kun er for kunden eller en samlet score for kunder og et sekundært niveau som produktkategori. Det element, der vælges, bestemmer indholdet på denne side.

  - **Bedste kunder**: Liste over ti kunder med den højeste risiko for kundeafgang og laveste risiko for kundeafgang baseret på deres kundeafgangsscorer.
  - **Benchmarkkunder**: Liste over op til ti kunder, der blev valgt under konfigurationen af modellen.

- **Kundeafgangsscore:** Viser kundeafgangsscoren for det valgte element i ruden til højre.

- **Fordeling af risiko for kundeafgang:** Viser fordeling af risiko for kundeafgang på tværs af kunder og den percentil, den valgte kunde er i.

- **Vigtigste funktioner, der øger og reducerer risikoen for kundeafgang:** Viser de fem vigtigste funktioner, der øgede og reducerede risikoen for kundeafgang for det valgte element i højre rude. Viser værdien af funktionen for det pågældende element og dens indflydelse på kundeafgangsscoren for de enkelte funktioner med indflydelse. Den gennemsnitlige værdi af hver funktion på tværs af lave, mellem og høje kundeafgangssegmenter vises også. Det giver en bedre kontekst af værdierne af de vigtigste funktioner for det valgte element og sammenligner det med lave, mellemstore og høje kundeafgangssegmenter.

  - Lav: konti eller kombinationer af konto og sekundært niveau med en kundeafgangsscore mellem 0 og 0,33.
  - Mellem: konti eller kombinationer af konti og sekundære niveauer med en kundeafgangsscore mellem 0,33 og 0,66.
  - Høj: konti eller kombinationer af konti og sekundære niveauer med en kundeafgangsscore over 0,66.

  Når du forudsiger kundeafgang på kontoniveau, tages alle konti i betragtning med henblik på at udlede de gennemsnitlige funktionsværdier for kundeafgangssegmenter. I forbindelse med forudsigelser af kundeafgang på sekundært niveau for hver konto afhænger afledningen af kundeafgangssegmenter af det sekundære niveau for det element, der er valgt i sideruden. Hvis et element f.eks. har et sekundært niveau af en produktkategori (kontorartikler), er det kun de elementer, der har kontorartikler som produktkategori, der tages i betragtning, når de gennemsnitlige funktionsværdier for kundeafgangssegmenter afledes. Denne logik anvendes for at sikre en rimelig sammenligning af elementers funktionsværdier med de gennemsnitlige værdier i lave, mellem og høje afgangssegmenter.

  I visse tilfælde er den gennemsnitlige værdi af lave, mellem eller høje afgangssegmenter tom eller ikke tilgængelig, fordi der ikke er elementer, der tilhører de tilsvarende kundeafgangssegmenter, baseret på ovenstående definition.

  Værdierne under de gennemsnitlige lave, mellemstore og høje kolonner er forskellige for kategoriske funktioner som land eller branche. Da den almindelige funktionsværdi for "gennemsnitlig" ikke gælder for kategoriske funktioner, er værdierne i disse kolonner proportionen mellem kunder i lav-, mellem- eller højskærmssegmenter, der har samme værdi som den kategoriske funktion i forhold til det element, der er valgt i sidepanelet.

---

 > [!NOTE]
 > I outputobjektet for denne model viser *ChurnScore* den anslåede sandsynlighed for kundeafgang, og *IsChurn* er en binær etiket baseret på *ChurnScore* med en tærskelværdi på 0,5. Hvis denne standardtærskelværdi ikke fungerer for dit scenario, skal du [oprette et nyt segment](segments.md#create-a-segment) med din foretrukne tærskelværdi. Ikke alle kunder er nødvendigvis aktive kunder. Nogle af dem har måske ikke haft nogen aktivitet i lang tid og betragtes som allerede som afgåede baseret på din afgangsdefinition. Det er ikke nyttigt at forudsige afgangsrisiko for kunder, der allerede er afgået, da de ikke er den interessante målgruppe.
>
> Hvis du vil have vist kundeafgangsscoren, skal du gå til **Data** > **Objekter** og se datafanen for det outputobjekt, du har defineret for denne model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
