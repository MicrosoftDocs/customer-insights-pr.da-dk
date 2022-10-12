---
title: Forudsige produktanbefalinger
description: Forudsige de produkter, en kunde køber eller kommunikerer med.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610275"
---
# <a name="predict-product-recommendations"></a>Forudsige produktanbefalinger

Produktanbefalingsmodellen opretter produktanbefalinger for forudsigelse. Anbefalinger er baseret på tidligere købsmåder og kunder med lignende købsmønstre. Denne model er til individuel brug (B-to-C).

Du skal have forretningsviden om de forskellige typer produkter i virksomheden, og hvordan kunderne kommunikerer med dem. Vi anbefaler produkter, der tidligere er købt af dine kunder, eller anbefalinger til nye produkter.

Produktanbefalinger kan være underlagt lokale love og regler og kundernes forventninger, som modellen ikke er udviklet til specifikt at tage højde for. Du skal derfor **gennemgå anbefalingerne, inden de leveres til dine kunder**, for at sikre, at du overholder alle gældende love eller regler samt kundernes forventninger til det, du kan anbefale.

Outputtet fra denne model giver dig anbefalinger baseret på produkt-id. Leveringsmekanismen skal knytte de forudsagte produkt-id'er til det relevante indhold, så dine kunder kan tage højde for lokalisering, billedindhold og andet forretningsspecifikt indhold eller funktionsmåde.

> [!TIP]
> Prøv forudsigelsen af produktanbefalinger ved hjælp af eksempeldata: [Eksempelvejledning til forudsigelse af produktanbefalinger](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Forudsætninger

- Mindst [Bidragyder-tilladelser](permissions.md)
- Mindst 100 kunder, helst mere end 10.000 kunder.
- Kunde-id: et entydigt id, der skal svare til transaktioner med en enkelt kunde
- Mindst et år med transaktionsdata, helst to til tre år for at medtage en vis grad af kontinuitet. Ideelt set mindst tre eller flere transaktioner pr. kunde-id. Transaktionshistorikken skal omfatte:
  - **Transaktions-id**: Entydigt id for et køb eller en transaktion.
  - **Transaktionsdato**: Købs- eller transaktionsdato.
  - **Værdi for transaktion:** Numerisk værdi for købet eller transaktionen.
  - **Entydigt produkt-id**: Id for det produkt eller den tjeneste, du har købt, hvis dataene befinder sig på linjeelementniveau.
  - **Køb eller returnering**: En boolesk sand/falsk-værdi, hvor *sand* identificerer, at en transaktion var en returnering. Hvis dataene for Køb eller Retur ikke leveres i modellen, og **værdien af transaktionen** er negativ, udleder vi en returnering.
- Et produktkatalogdataobjekt til brug som et produktfilter.

> [!NOTE]
> - Modellen kræver kundernes transaktionsoversigt, hvor transaktion er data, der beskriver en interaktion mellem bruger og produkt. Det kan f.eks. være at købe et produkt, tage en klasse eller deltage i et arrangement.
> - Der kan kun konfigureres ét transaktionsoversigtsobjekt. Hvis der er flere købsobjekter, kan du samle sammen i Power Query, før dataindtagelse går i gang.
> - Hvis ordren og ordredetaljer er forskellige objekter, kan du samle dem, før du bruger den i modellen. Modellen fungerer ikke kun med et ordre-id eller et kvitterings-id i et objekt.

## <a name="create-a-product-recommendation-prediction"></a>Oprette forudsigelse om produktanbefalinger

Du kan når som helst vælge **Gem kladde** for at gemme forudsigelsen som en kladde. Kladdeforudsigelsen vises under fanen **Mine forudsigelser**.

1. Gå til **Intelligens** > **Forudsigelser**.

1. Under fanen **Opret** skal du vælge **Brug model** i feltet **Produktanbefalinger (forhåndsversion)**.

1. Vælg **Start her**.

1. **Navngive denne model** og **navnet på outputobjektet** for at skelne mellem dem fra andre modeller eller objekter.

1. Vælg **Næste**.

### <a name="define-product-recommendation-preferences"></a>Definere indstillinger for produktanbefalinger

1. Angiv det **antal produkter**, der skal anbefales til en kunde. Værdien afhænger af, hvordan leveringsmetoden udfylder data.

1. Vælg, om du vil medtage produkter, som kunderne tidligere har købt, i feltet **Gentag køb forventet**.

1. Angiv **Tilbagebliksvindue** med den tidsramme, som modellen overvejer, før produktet anbefales til brugeren igen. Angiv f.eks., at en kunde køber en bærbar computer hvert andet år. I denne model kigges der på købsoversigten for de seneste to år, og hvis den finder et vare, filtreres varen efter anbefalingerne.

1. Vælg **Næste**

### <a name="add-purchase-history"></a>Tilføj købshistorik

1. Vælg **Tilføj data** for **Kundetransaktionshistorik**.

1. Vælg den semantiske aktivitetstype **SalesOrderLine**, der indeholder de nødvendige oplysninger om transaktions- eller købshistorikken. Hvis aktiviteten ikke er blevet konfigureret, skal du vælge **her** og oprette den.

1. Hvis aktivitetsattributterne blev semantically tilknyttet under **Aktiviteter**, da aktiviteten blev oprettet, skal du vælge de specifikke attributter eller det objekt, beregningen skal fokusere på. Hvis der ikke blev udført en semantisk tilknytning, skal du vælge **Rediger** og tilknytte dataene.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Sideruden viser, hvordan du vælger bestemte aktiviteter under den semantiske type.":::

1. Vælg **Næste**, og gennemse de attributter, der kræves til denne model.

1. Vælg **Gem**.

1. Vælg **Næste**.

### <a name="add-product-information-and-filters"></a>Tilføje produktoplysninger og filtre

Undertiden er det kun visse produkter, der er gode eller passende for den type forudsigelse du bygger. Brug produktfiltre til at identificere en delmængde af produkter med bestemte egenskaber, som kan anbefales til dine kunder. I modellen bruges alle tilgængelige produkter til at lære mønstre, men kun bruge de produkter, der svarer til produktfilteret i outputtet.

1. Tilføj det produktkatalogobjekt, der indeholder oplysninger om de enkelte produkter. Tilknyt de nødvendige oplysninger, og vælg **Gem**.

1. Vælg **Næste**.

1. Vælg **Produktfiltre**:

   - **Ingen filtre**: Brug alle produkter i produktanbefalingens forudsigelse.

   - **Definer specifikke produktfiltre**: Brug bestemte produkter i produktanbefalingernes forudsigelse. Vælg de attributter fra produktkatalogobjektet, som du vil inkludere i filteret, i ruden **Produktkatalogattributter**.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Sideruden, der viser, hvordan produktkatalogobjektet skal vælges til produktfiltre.":::

1. Vælg, om produktfilteret skal bruge **og** eller **eller** for at udføre en logisk kombination af dine valgte attributter fra produktkataloget.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Eksempelkonfiguration af produktfiltre kombineret med logiske AND-connectors.":::

1. Vælg **Næste**.

### <a name="set-update-schedule"></a>Indstil opdateringsplan

1. Vælg en hyppighed for gentræning af modellen. Denne indstilling er vigtig, hvis du vil opdatere nøjagtigheden af forudsigelser, efterhånden som nye data indtages til Customer Insights. De fleste virksomheder kan omskole én gang om måneden og opnå en god præcision af deres forudsigelse.

1. Vælg **Næste**.

### <a name="review-and-run-the-model-configuration"></a>Gennemse og kør modelkonfigurationen

I trinnet **Gennemse og kør** vises en oversigt over konfigurationen, og her kan du foretage ændringer, før du opretter forudsigelsen.

1. Vælg **Rediger** på et af trinnene for at gennemse og foretage ændringer.

1. Hvis du er tilfreds med dine valg, skal du vælge **Gem og kør** for at starte kørsel af modellen. Vælg **Udført**. Fanen **Mine forudsigelser** vises, mens forudsigelse oprettes. Det kan tage flere timer, før processen er fuldført, afhængigt af mængden af data, der bruges i forudsigelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Få vist forudsigelsesresultater

1. Gå til **Intelligens** > **Forudsigelser**.

1. Under fanen **Mine forudsigelser** skal du vælge den forudsigelse, du vil have vist.

Der findes fem primære dataafsnit på resultatsiden.

- **Modellens ydeevne:** Klassificeringerne A, B eller C angiver resultatet af forudsigelsen og kan hjælpe dig med at træffe beslutning om at bruge de resultater, der er gemt i outputobjektet.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Billede af modellens ydeevneresultat med klassifikationen A.":::

  Vurderingerne bestemmes ud fra følgende regler:
  - **A**, når metrikværdien "Success @ K" er mindst 10 % mere end den oprindelige værdi.
  - **B**, når metrikværdien "Success @ K" er 0 % til 10 % mere end den oprindelige værdi.
  - **C**, når metrikværdien "Success @ K" er mindre end den oprindelige værdi.
  - **Basislinje**: Antallet af de mest anbefalede produkter efter køb på tværs af alle kunder + lærte regler, der identificeres af modellen = et sæt anbefalinger til kunderne. Forudsigelserne sammenlignes derefter med de øverste produkter som beregnet ud fra antallet af kunder, der har købt produktet. Hvis en kunde har mindst ét produkt i sine anbefalede produkter, der også blev set i de mest købte produkter, betragtes de som en del af udgangspunktet. Hvis f.eks. 10 af disse kunder havde købt et anbefalet produkt ud af 100 kunder i alt, ville udgangsværdien være 10 %.
  - **Success @ K**: Anbefalinger oprettes for alle kunder og sammenlignes med valideringssættet for tidsperioden for transaktioner. I en periode på 12 måneder kan der f.eks. afsættes 12 måneder som et valideringssæt af data. Hvis modellen bygger på mindst én ting, du ville købe i måned 12 på baggrund af det, den har lært af de foregående 11 måneder, vil kunden øge målingen "Succes @ K".

- **De fleste forslag til produkter (med sammentælling):** De fem vigtigste produkter, der blev foretrukket for dine kunder.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Graf, der viser de 5 mest anbefalede produkter.":::

- **Vigtige anbefalingsfaktorer:** Modellen bruger kundernes transaktionsoversigt til at komme med produktanbefalinger. Den lærer mønstre på baggrund af tidligere køb, og der findes ligheder mellem kunder og produkter. Disse ligheder bruges derefter til at oprette produktanbefalinger.
  Følgende faktorer kan påvirke en produktanbefaling, der genereres af modellen.
  - **Tidligere transaktioner**: Et anbefalet produkt var baseret på tidligere købsmønstre. Modellen kan f.eks. anbefale en *Surface Arc Mouse*, hvis en person for nylig har købt en *Surface Book 3* og en *Surface Pen*. Modellen har lært, at mange kunder historisk har købt en *Surface Arc Mouse*, efter at de har købt en *Surface Book 3* og en *Surface Pen*.
  - **Kundelighed**: Et anbefalet produkt er historisk købt af andre kunder, der har et lignende købsmønstre. John blev f.eks. anbefalet *Surface Headphones 2* fordi Jennifer og Brad for nylig har købt *Surface Headphones 2*. Modellen mener, at John ligner Jennifer og Brad, fordi de historisk har haft lignende købsmønstre.
  - **Produktlighed**: Et anbefalet produkt svarer til andre produkter, som kunden tidligere har købt. Modellen anser to produkter for at være ens, hvis de ligner hinanden eller af lignende kunder. En person får f.eks. en anbefaling af et *USB-lagerdrev*, fordi de tidligere har købt et *USB-C til USB-adapter*, og modellen antager, at *USB Storage Drive* svarer til *USB-C til USB-adapter* baseret på historiske købsmønstre.

  Enhver produktanbefaling anbefales af en eller flere af disse faktorer. Procentdelen af anbefalinger, hvor hver enkelt faktor spillede en rolle, vises i et diagram. I følgende eksempel var 100 % af anbefalingerne baseret på tidligere transaktioner, 60 % efter kundelighed og 22 % efter produktlighed. Hold musen hen over søjlerne i diagrammet for at se den nøjagtige procentdel, hvor de faktorer, der virkede som faktorer, har indflydelse.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Vigtige anbefalingsfaktorer, der læres af modellen for at generere produktanbefalinger.":::

- **Datastatistik**: En oversigt over antallet af transaktioner, kunder og produkter, som modellen tager med i betragtning. Den er baseret på de inputdata, der blev brugt til at lære mønstre og generere produktanbefalinger.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Datastatistik angående inputdata, der bruges af modellen til at lære mønstre.":::
  
  Modellen bruger alle tilgængelige data til at lære mønstre. Hvis du bruger produktfiltrering i modelkonfigurationen, vises det samlede antal produkter, som modellen analyserer for at lære mønstre, hvilket muligvis ikke er det samme som antallet af produkter, der opfylder de definerede filtreringskriterier. Filtrering anvendes på det output, som modellen genererer.

- **Eksempel på produktanbefalinger:** Et eksempel på anbefalinger, som efter modellens mening sandsynligvis vil blive købt af kunden. Hvis der tilføjes et produktkatalog, erstattes produkt-id'erne med produktnavne.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Liste med forslag med stor sikkerhed til udvalgte individuelle kunder.":::

> [!NOTE]
> I outputobjektet for denne model viser *Score* den kvantitative måling for anbefalingen. Modellen anbefaler produkter med en højere score i forhold til produkter med en lavere score. Hvis du vil have vist scoren, skal du gå til **Data** > **Objekter** og se datafanen for det outputobjekt, du har defineret for denne model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
