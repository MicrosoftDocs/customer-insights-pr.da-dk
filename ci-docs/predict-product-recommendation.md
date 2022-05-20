---
title: Forudsige produktanbefalinger
description: Forudsige de produkter, en kunde køber eller kommunikerer med.
ms.date: 05/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 9b3e60c49d294d031f43ef0594cb69707bb64019
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762725"
---
# <a name="product-recommendation-prediction"></a>Forudsige produktanbefalinger

Produktanbefalingsmodellen opretter produktanbefalinger for forudsigelse. Anbefalinger er baseret på tidligere købsmåder og kunder med lignende købsmønstre. Du kan oprette forudsigelser om nye produktanbefalinger siden **Intelligens** > **Forudsigelse**. Vælg **Mine forudsigelser** for at få vist andre forudsigelser, du har oprettet.

Produktanbefalinger kan være underlagt lokale love og regler og kundernes forventninger, som modellen ikke er udviklet til specifikt at tage højde for.  Som bruger af denne gode funktion **skal du gennemgå anbefalingerne, inden de leveres til dine kunder**, for at sikre, at du overholder alle gældende love eller regler samt kundernes forventninger til det, du kan anbefale.

Derudover vil outputtet fra denne model give dig anbefalinger baseret på produkt-id. Leveringsmekanismen skal knytte de oversatte produkt-id'er til det relevante indhold, som dine kunder skal tage højde for lokalisering, billedindhold og andet forretningsspecifikt indhold eller adfærd.

## <a name="sample-guide"></a>Eksempelvejledning

Hvis du er interesseret i at prøve denne funktion, men ikke har data, der opfylder kravene nedenfor, kan du [oprette et eksempel på en implementering](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Forudsætninger

- Mindst [bidragydertilladelser](permissions.md) i Customer Insights.

- Forretningsviden om at forstå forskellige typer produkter i virksomheden, og hvordan kunderne kommunikerer med dem. Vi anbefaler produkter, der tidligere er købt af dine kunder, eller anbefalinger til nye produkter.

- Dit miljø skal konfigureres for de **enkelte forbrugeres** primære målgruppe.

- Data om dine transaktioner, køb og deres oversigt:
  - Transaktions-id'er for at skelne mellem køb og transaktioner.
  - Kunde-id'er til tilknytning af transaktioner til dine kunder.
  - Datoer for posteringshændelser, som definerer de datoer, transaktionen forekom i.
  - Oplysninger om produkt-id for transaktionen.
  - (Valgfrit) Et produktkatalogdataobjekt til brug af et produktfilter.
  - (Valgfrit) Hvis en transaktion er en returnering eller ej.
  - Semantisk dataskema kræver følgende oplysninger:
    - **Transaktions-id:** Et entydigt id for et køb eller en transaktion.
    - **Transaktionsdato:** Købs- eller transaktionsdato.
    - **Værdi for transaktion:** Den numeriske værdi for købet eller transaktionen.
    - **Entydigt produkt-id:** Id for det produkt eller den tjeneste, du har købt, hvis dataene befinder sig på linjeelementniveau.
    - (Valgfrit) **Køb eller returnering:** Et boolesk felt, hvor værdien *sand* identificerer, at en transaktion var en returnering. Hvis dataene for Køb eller Retur ikke leveres som model, og **værdien af transaktionen** er negativ, bruger vi også disse oplysninger til at udlede en returnering.
- Forslåede datakarakteristika:
  - Tilstrækkelige historiske data: Mindst et år med transaktionsdata, helst to til tre år for at medtage en vis grad af sårbarhed.
  - Flere køb pr. kunde: Tre eller flere transaktioner pr. kunde-id
  - Antal kunder: Mindst 100 kunder, helst mere end 10.000 kunder. Modellen kan ikke bruges af færre end 100 kunder.

> [!NOTE]
>
> - Modellen kræver kundernes transaktionsoversigt. Definitionen af en transaktion er ret fleksibel. Alle data, der beskriver en brugerproduktinteraktion, kan fungere som et input. Det kan f.eks. være at købe et produkt, tage en klasse eller deltage i et arrangement.
> - Der kan i øjeblikket kun konfigureres ét transaktionsoversigtsobjekt. Hvis der er flere købsobjekter, kan du oprette dem sammen i Power Query, før dataindtagelse går i gang.
> - Hvis ordren og ordredetaljer er forskellige objekter, kan du samle dem, før du bruger den i modellen. Modellen fungerer ikke kun med et ordre-id eller et kvitterings-id i et objekt.

## <a name="create-a-product-recommendation-prediction"></a>Oprette forudsigelse om produktanbefalinger

1. Gå til **Intelligens** > **Forudsigelser** i Customer Insights.

1. Vælg feltet **Model til produktanbefalinger**, og vælg **Brug denne model**.
   > [!div class="mx-imgBorder"]
   > ![Produktanbefalingsmodel med knappen Brug denne model.](media/product-recommendation-usethismodel.PNG "Produktanbefalingsmodel med knappen Brug denne model")

1. Gennemse oplysningerne om modelkravene. Hvis du har de påkrævede data, skal du vælge **Start her**.

### <a name="name-model"></a>Navngiv model

1. Angiv et navn til modellen for at adskille den fra andre modeller.

1. Angiv kun et navn på outputobjektet med bogstaver og tal uden mellemrum. Det er det navn, som modelobjektet skal bruge. Vælg derefter **Næste**.

### <a name="define-product-recommendation-configuration"></a>Konfiguration af produktanbefaling

1. Angiv det **antal produkter**, der skal anbefales til en kunde. Værdien afhænger af, hvordan leveringsmetoden udfylder data. Hvis du kan anbefale tre produkter, skal du angive denne værdi i overensstemmelse hermed.

   >[!TIP]
   > Du kan når som helst vælge **Gem kladde** for at gemme forudsigelsen som en kladde. Du kan se forudsigelse under fanen **Mine forudsigelser**.

1. Vælg, om du vil medtage produkter, som kunderne for nylig har købt, i feltet **Gentag køb forventet**.

1. Angiv **Tilbagebliksvindue**. Denne indstilling angiver den tidsramme, modellen overvejer, før den anbefaler produktet til brugeren igen. Angiv f.eks., at en kunde køber en bærbar computer hvert andet år. I dette vindue kigges der på købsoversigten for de seneste to år, og hvis de finder et element, filtreres elementet efter anbefalingerne.

1. Vælg **Næste**

### <a name="add-required-data"></a>Tilføj påkrævede data

1. Vælg **Tilføj data**, og vælg aktivitetstypen den siderude, der indeholder de påkrævede oplysninger om transaktionen eller købsoversigten.

1. Under **Vælg aktiviteterne** skal du vælge de specifikke aktiviteter fra den valgte aktivitet, som beregningen skal fokusere på.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Sideruden viser, hvordan du vælger bestemte aktiviteter under den semantiske type.":::

1. Hvis du endnu ikke har knyttet aktiviteten til en semantisk type, skal du vælge **Rediger** for at gøre det. Den styrede oplevelse til tilknytning af semantiske aktiviteter åbnes. Knyt nu dine data til relaterede felter i den valgte aktivitetstype.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Aktivitetstype for sideindstilling.":::

1. Når du har knytte aktiviteten til den tilsvarende semantiske type, skal du vælge **Næste** for at fortsætte.

1. Knyt de semantiske attributter til de felter, der kræves for at køre modellen.

1. Vælg **Gem**.

1. Vælg **Næste**.

### <a name="configure-product-filters"></a>Konfigurere produktfiltre

Undertiden er det kun visse produkter, der er gode eller passende for den type forudsigelse du bygger. Produktfiltre gør det muligt at identificere en delmængde af produkter med bestemte egenskaber, som kan anbefales til dine kunder. I modellen bruges alle tilgængelige produkter til at lære mønstre, men kun bruge de produkter, der svarer til produktfilteret i outputtet.

1. Tilføj produktkataloget med oplysninger om hvert produkt i trinnet **Tilføj produktoplysninger**. Tilknyt de nødvendige oplysninger i vælg **Næste**.

1. Vælg mellem følgende indstillinger i trinnet **Produktfiltre**.

   - **Ingen filtre**: Brug alle produkter i produktanbefalingens forudsigelse.

   - **Definer specifikke produktfiltre**: Brug bestemte produkter i produktanbefalingernes forudsigelse.

1. Vælg **Næste**.

1. Hvis du vælger at definere et produktfilter, skal du definere det nu. Vælg de attributter fra objektet **Produktkatalog**, som du vil inkludere i filteret, i ruden *Produktkatalogattributter*.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Sideruden, der viser, hvordan produktkatalogobjektet skal vælges til produktfiltre.":::

1. Vælg, om produktfilteret skal bruge **og** eller **eller** connectors skal kombinere det valgte udvalg af attributter fra produktkataloget på en logisk måde.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Eksempelkonfiguration af produktfiltre kombineret med logiske AND-connectors.":::

1. Vælg **Næste**.

### <a name="set-update-schedule-and-review-configuration"></a>Angive tidsplan for opdatering og gennemgang af konfigurationen

1. Angiv en hyppighed for at omskole modellen. Denne indstilling er vigtig, hvis du vil opdatere nøjagtigheden af forudsigelser, efterhånden som nye data importeres til Customer Insights. De fleste virksomheder kan omskole én gang om måneden og opnå en god præcision af deres forudsigelse.

1. Vælg **Næste**.

1. Gennemgå konfigurationen. Du kan gå tilbage til en hvilken som helst del af forudsigelseskonfigurationen ved at vælge **Rediger** under den viste værdi. Du kan også vælge et konfigurationstrin i statusindikatoren.

1. Hvis alle værdier er konfigureret korrekt, skal du vælge **Gem og kør** for at starte forudsigelsesprocessen. Du kan se statussen for dine forudsigelser under fanen **Mine forudsigelser**. Det kan tage flere timer, før processen er fuldført, afhængigt af mængden af data, der bruges i forudsigelsen.

## <a name="review-a-prediction-status-and-results"></a>Gennemgå en forudsigelses status og resultater

1. Gå til fanen **Mine forudsigelser** i **Intelligens** > **forudsigelser**.
   > [!div class="mx-imgBorder"]
   > ![Visning af siden Mine forudsigelser.](media/product-recommendation-mypredictions.PNG "Visning af siden Mine forudsigelser")

1. Vælg den forudsigelse, du vil gennemse.
   - **Forudsigelsesnavn:** Navnet på forudsigelsen, der blev angivet under oprettelsen.
   - **Forudsigelsestype:** Den type model, der bruges til forudsigelsen
   - **Outputobjekt:** Navnet på det objekt, som outputtet af forudsigelsen skal gemmes i. Du kan finde et objekt med dette navn på **Data** > **Objekter**.
      *Score* i outputobjektet er et mål for anbefalingen. Modellen anbefaler produkter med en højere score i forhold til produkter med en lavere score.
   - **Forudsagt felt**: Dette felt udfyldes kun for visse typer forudsigelser og bruges ikke i produktanbefalingsforudsigelse.
   - **Status:** Den aktuelle status for forudsigelsens kørsel.
        - **Sat i kø:** Forudsigelsen venter i øjeblikket på, at andre processer skal køre.
        - **Opdaterer:** Forudsigelse kører i øjeblikket "score"-fasen i behandlingen af de resultater, der vil blive overført til outputenheden.
        - **Mislykkedes:** Forudsigelsen mislykkedes. Vælg **Logge** for at få flere oplysninger.
        - **Lykkedes:** Forudsigelsen blev fuldført. Vælg **Vis** under de lodrette ellipser for at gennemgå forudsigelse.
   - **Redigeret:** Den dato, hvor konfigurationen af forudsigelse blev ændret.
   - **Sidst opdateret:** Den dato, hvor forudsigelsen opdaterede resultater i outputenheden.

1. Vælg de lodrette ellipser ud for den forudsigelse, du vil gennemgå resultaterne for, og vælg **Vis**.
   > [!div class="mx-imgBorder"]
   > ![Visning af indstillinger i menuen med lodrette ellipser for en forudsigelse, herunder redigering, opdatering, visning, logfiler og sletning.](media/product-recommendation-verticalellipses.PNG "Visning af indstillinger i menuen med lodrette ellipser for en forudsigelse, herunder redigering, opdatering, visning, logfiler og sletning")

1. Der findes fem primære dataafsnit på resultatsiden:
    1. **Træningsmodellens ydeevne:** A, B eller C er mulige scorer. Denne score ydeevnen af forudsigelsen og kan hjælpe dig med at træffe beslutningen om at bruge de resultater, der er gemt i outputobjektet.
        - Scorer bestemmes ud fra følgende regler:
            - **A** Modellen betragtes som **A**-kvalitet, hvis målingen "Succes @ K" er mindst 10 % mere end basislinjen. 
            - **B** Modellen betragtes som **B**-kvalitet, hvis målingen "Succes @ K" er 0 - 10 % mere end basislinjen.
            - **C** Modellen betragtes som **C**-kvalitet, hvis målingen "Succes @ K" er mindre end basislinjen.

               > [!div class="mx-imgBorder"]
               > ![Visning af modellens ydeevneresultat.](media/product-recommendation-modelperformance.PNG "Visning af modellens ydeevneresultat")
            - **Basislinje**: Modellen tager de mest anbefalede produkter ved køb på tværs af alle kunder, og den bruger lærde regler, der identificeres af modellen, til at oprette et sæt anbefalinger til kunderne. Forudsigelserne sammenlignes derefter med de øverste produkter som beregnet ud fra antallet af kunder, der har købt produktet. Hvis en kunde har mindst ét produkt i sine anbefalede produkter, der også blev set i de mest købte produkter, betragtes de som en del af udgangspunktet. Hvis der var 10 af disse kunder, hvor der var købt et anbefalet produkt ud af 100 samlede kunder, ville udgangsværdien være 10 %.
            - **Succes @ K**: Ved hjælp af et valideringssæt med transaktioner oprettes der anbefalinger for alle kunder og sammenlignes med valideringssættet for transaktioner. I en periode på 12 måneder kan der f.eks. blive afsat 12 måneder som et valideringssæt af data. Hvis modellen bygger på mindst én ting, du ville købe i måned 12 på baggrund af det, den har lært af de foregående 11 måneder, vil kunden øge målingen "Succes @ K".

    1. **De fleste forslag til produkter (med sammentælling):** De fem vigtigste produkter, der blev foretrukket for dine kunder.
       > [!div class="mx-imgBorder"]
       > ![Graf, der viser de 5 mest anbefalede produkter.](media/product-recommendation-topproducts.PNG "Graf, der viser de 5 mest anbefalede produkter")

    1. **Vigtige anbefalingsfaktorer:** Modellen bruger kundernes transaktionsoversigt til at komme med produktanbefalinger. Den lærer mønstre på baggrund af tidligere køb, og der findes ligheder mellem kunder og produkter. Disse ligheder bruges derefter til at oprette produktanbefalinger.
    Følgende faktorer kan påvirke en produktanbefaling genereret af modellen.
        - **Tidligere transaktioner**: Tidligere indkøbsmønstre blev brugt af modellen til at oprette produktanbefalinger. Modellen kan f.eks. anbefale en *Surface Arc Mouse*, hvis en person for nylig har købt en *Surface Book 3* og en *Surface Pen*. Modellen har lært, at mange kunder historisk har købt en *Surface Arc Mouse*, efter at de har købt en *Surface Book 3* og en *Surface Pen*.
        - **Kundelighed**: Et anbefalet produkt er historisk købt af andre kunder, der har et lignende købsmønstre. John blev f.eks. anbefalet *Surface Headphones 2* fordi Jennifer og Brad for nylig har købt *Surface Headphones 2*. Modellen mener, at John ligner Jennifer og Brad, fordi de historisk har haft lignende købsmønstre.
        - **Produktlighed**: Et anbefalet produkt svarer til andre produkter, som kunden tidligere har købt. Modellen anser to produkter for at være ens, hvis de ligner hinanden eller af lignende kunder. En person får f.eks. en anbefaling af et *USB-lagerdrev*, fordi de tidligere har købt et *USB-C til USB-adapter*, og modellen antager, at *USB Storage Drive* svarer til *USB-C til USB-adapter* baseret på historiske købsmønstre.

        Enhver produktanbefaling anbefales af en eller flere af disse faktorer. Procentdelen af anbefalinger, hvor hver enkelt faktor spillede en rolle, vises i et diagram. I følgende eksempel var 100 % af anbefalingerne baseret på tidligere transaktioner, 60 % efter kundelighed og 22 % efter produktlighed. Hold musen hen over søjlerne i diagrammet for at se den nøjagtige procentdel, hvor de faktorer, der virkede som faktorer, har indflydelse.

        > [!div class="mx-imgBorder"]
        > ![Nøgleanbefalingsfaktorer.](media/product-recommendation-keyrecommendationfactors.png "Vigtige anbefalingsfaktorer, der læres af modellen for at generere produktanbefalinger")

   1. **Datastatistik**: Leverer en oversigt over antallet af transaktioner, kunder og produkter den pågældende model. Den er baseret på de inputdata, der blev brugt til at lære mønstre og generere produktanbefalinger.

      > [!div class="mx-imgBorder"]
      > ![Datastatistik.](media/product-recommendation-datastatistics.png "Datastatistik angående inout-data, der bruges af modellen til at lære mønstre")

      I dette afsnit vises statistikker over de datapunkter, der blev brugt af modellen for at lære mønstre og generere produktanbefalinger. Filtrering som konfigureret i modelkonfigurationen anvendes på det output, der genereres af modellen. Men i modellen bruges alle tilgængelige data til at lære mønstre. Hvis du bruger produktfiltrering i modelkonfigurationen, vises det samlede antal produkter, som modellen analyseres for at lære mønstre, som kan adskille sig fra antallet af produkter, der opfylder de definerede filtreringskriterier.

   1. **Produktanbefalinger med høj sikkerhed:** Et eksempel på anbefalinger, der kommer til dine kunder, og som efter modellens mening sandsynligvis vil blive købt af kunden.    
      Hvis der tilføjes et produktkatalog, erstattes produkt-id'er med produktnavne. Produktnavne giver mere handlingsbare og intuitive oplysninger om forudsigelserne.
       > [!div class="mx-imgBorder"]
       > ![Liste med forslag med stor sikkerhed til udvalgte individuelle kunder.](media/product-recommendation-highconfidence.PNG "Liste med forslag med stor sikkerhed til udvalgte individuelle kunder")

## <a name="manage-predictions"></a>Administrere forudsigelser

Det er muligt at optimere, foretage fejlfinding, opdatere eller slette forudsigelser. Gennemgå en rapport om dataanvendelighed for at finde ud af, hvordan du gør en forudsigelse hurtigere og mere pålidelig. Du kan finde flere oplysninger under [Administrere forudsigelser](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
