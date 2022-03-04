---
title: Synspunktanalyse for kundefeedback
description: Få mere at vide om, hvordan du anvender en synspunktsanalysemodel på kundefeedback i Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: b06613b00a512a31479f9d30d539a010e17d33ba
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231458"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analysér synspunkt i kundefeedback (forhåndsversion)

Kunderne forventer i disse tider produkter, servicer og oplevelser i høj kvalitet. Især kunder, der deler deres feedback. Det er en stor udfordring for organisationer at analysere en stigende mængde data uden at reducere præcisionen og øge arbejdsomkostningerne. Dynamics 365 Customer Insights indeholder en synspunktsanalysemodel til kundefeedback, der gør det muligt for organisationer at analysere deres data mere nøjagtigt og med lavere omkostninger.

Synspunktsanalyse giver dig mulighed for at synkronisere kundernes synspunkt og identificere forretningsaspekter som muligheder for forbedringer. Denne funktion i Customer Insights hjælper dig med at forstå, hvad der fungerer godt, og hvad du har brug for at ændre. Fokuser på de mest relevante og indflydelsesrige områder i virksomheden for at forbedre oplevelsen for dine kunder. I sidste ende kan det hjælpe dig med at udføre forretningshandlinger, der giver oplevelser, som medfører stor kundetilfredshed og loyalitet.

## <a name="overview"></a>Oversigt

Funktionen til synspunktsanalyse genererer to afledte indsigter pr. kunde-id. En synspunktscore (på -5 til 5) og en liste over relevante forretningsaspekter (forretningsområder) hjælper dig med bedre at forstå kundefeedbacken. 

Disse oplysninger kan hjælpe dig med at opnå følgende resultater: 
- Få en oversigt over kundesynspunkter i forhold til et mærke eller en organisation
- Identificere kunder med negative synspunkter, så du kan fokusere på kampagner og engagementer og optimere for at få højere afkast  
- Identificere forretningsaspekter med problemer, som kunderne påpeger  
- Segmentere kunder baseret på deres synspunkt for at køre tilpassede kampagner med målrettede salgs-, marketing- og supportindsatser
- Optimere virksomhedsdriften ved at tage sig af områder med problemer eller salgsmuligheder, som kunderne har nævnt
- Anerkende forretningsaspekter, der klarer sig godt, og belønne tilfredse kunder gennem loyalitets- og kampagneprogrammer

For at sikre, at du kan stole på resultaterne af modellerne, giver vi gennemskuelige oplysninger om, hvordan modellerne træffer beslutninger. Du får en liste over ord, der påvirkede modellens beslutning om at tildele en bestemt synspunktscore eller forretnings aspekt til feedbackkommentarer.  

Vi bruger to **NLP-modeller (Natural Language Processing)**: De første tildeler hver feedbackkommentar en synspunktscore. Den anden model knytter de enkelte feedbacktilmeldinger til alle relevante forretningsaspekter. Modellen er trænet på offentlige data fra kilder på tværs af sociale medier, detail, restauranter, forbrugerprodukter og bilbranchen.    
  
Foruddefinerede forretningsaspekter for modellen, der skal knyttes til feedbackdata, omfatter:
-   Kontoadministration
-   Tjek ud og betaling
-   Kundesupport
-   Afhentning i lager
-   Pakkeforsendelse og hentning
-   Forudbestilling
-   Pris
-   Beskyttelse af personlige oplysninger og sikkerhed
-   Kampagner og belønninger
-   Kvittering og garanti
-   Ombytning og annullering af returvarer
-   Nøjagtighed af opfyldelse
-   Kvalitet af websted/app

> [!NOTE]
> I øjeblikket understøtter vi kun synspunktsanalyse på engelsk kundefeedback. Flere sprog understøttes i fremtiden. Hvis der overføres feedback på andre sprog, returnerer modellen stadig resultater. Disse resultater er dog ikke nøjagtige. 

## <a name="prerequisites"></a>Forudsætninger

Synspunktsanalysen er baseret på tekstfeedbackdata, der har gennemgået [processen til samling af data](data-unification.md). Det anbefales på det kraftigste, at du [konfigurerer dine feedbackdataobjekter som semantiske aktivitetsobjekter](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (feedbacktype) på forhånd. 

Hvis du vil konfigurere en synspunktsanalysemodel, skal du som minimum have [Bidragyder-tilladelser](permissions.md).

Customer Insights kan behandle op til 10 millioner feedbackposter for en enkelt modelkørsel. Modellen kan analysere feedbackkommentarer på op til 128 ord. Hvis en feedbackkommentar er længere, tager modellen kun de første 128 ord med i analysen.

### <a name="data-requirements"></a>Datakrav
  
Følgende dataattributter kræves:
- UCID (Unified Customer ID), der skal sammenholde tekstfeedbackdataposter med de enkelte kunder. Dette id er resultatet af [processen til samling af data](data-unification.md).
- Feedback-id
- Tidsstempel for feedback
- Feedbacktekst   

> [!TIP]
> Synspunktsanalyser kræver kundernes tekstfeedback. Der kan i øjeblikket kun konfigureres ét feedbackobjekt. Hvis der er flere feedbackobjekter, kan du oprette dem sammen i Power Query, før dataindtagelse går i gang.

## <a name="configure-a-sentiment-analysis"></a>Konfigurere en synspunktsanalyse 

1. Gå til **Intelligens** > **Forudsigelser** i Customer Insights.

1. Vælg **Brug model** i feltet **Kundesynspunktsanalyse**.

1. Vælg **Kom i gang** i ruden **Kundesynspunktsanalyse (forhåndsversion)**.

1. Angiv et **navn** til analysen i trinnet **Modelnavn**. 

1. Angiv **Navn på outputobjekt for forretningsaspekt** og **Navn på outputobjekt for synspunktsscore**, og vælg derefter **Næste**.

1. Vælg **Tilføj data** i trinnet **Påkrævede data**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Tilføje dataflow i synspunktsanalysemodellen.":::

1. Vælg den semantiske type **Feedback** på listen i ruden **Tilføj data**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigurationstrin til valg af feedbackaktiviteter til synspunktsanalyse.":::

1. Vælg de aktiviteter, du vil bruge til denne synspunktsanalyse, og vælg derefter **Næste**.
 
1. Knyt attributterne i dataene til modelattributterne. Vælg **Gem** for at anvende dine valg. 

1. Du kan se status for datatilknytning. Vælg **Næste** for at fortsætte. 

1. Valider konfigurationen af synspunktsanalysen i trinnet **Gennemse detaljerne for din model**. Du kan gå tilbage til en hvilken som helst del af konfigurationen af forudsigelse. Vælg **Gem og kør** for at starte analysen. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Gennemse trinnet for synspunktsmodellen, der viser alle konfigurerede elementer.":::

1. Vælg **Udført** for at forlade konfigurationsoplevelsen. Det kan tage flere timer at fuldføre processen, afhængigt af den anvendte mængde data. 

## <a name="review-analysis-status"></a>Gennemse analysestatus

1.  Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**.
2.  Vælg den forudsigelse, du vil gennemse.
- **Forudsigelsesnavn**: Navnet på den forudsigelse, der blev angivet under oprettelsen.
- **Forudsigelsestype**: Den modeltype, der bruges til forudsigelse.
- **Outputobjekt**: Navnet på det objekt, som outputtet af forudsigelsen skal gemmes i. Gå til **Data** > **Objekter** for at finde objektet med dette navn.
- **Forventet felt**: Dette felt udfyldes kun i forbindelse med visse typer forudsigelser og bruges ikke forudsigelse af værdi for kundelevetid.
- **Status**: Status for forudsigelseskørslen
  - **I kø**: Forudsigelse venter på, at andre processer fuldføres.
  - **Opdatering**: Forudsigelse kører i øjeblikket for at producere resultater, der vil blive overført til outputenheden.
  - **Mislykket**: Forudsigelse kunne ikke køres. Du kan finde flere oplysninger i logfilerne.
  - **Lykkedes**: Forudsigelse blev fuldført. Vælg Vis under de lodrette ellipser for at gennemse de forudsigelse resultater.
- **Redigeret**: Den dato, hvor konfigurationen af forudsigelse blev ændret.
- **Senest opdateret**: Den dato, forudsigelsen opdaterede resultater i outputobjektet.

## <a name="manage-sentiment-analysis"></a>Administrere synspunktsanalyse

Du kan optimere, foretage fejlfinding af, opdatere eller slette forudsigelser. Gennemgå en rapport om dataanvendelighed for at finde ud af, hvordan du gør en forudsigelse hurtigere og mere pålidelig. Du kan finde flere oplysninger under [Administrere forudsigelser](manage-predictions.md).

## <a name="review-analysis-results"></a>Gennemse analyseresultater
 
1. Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**. 
1. Vælg navnet på den forudsigelse, du vil gennemse resultater for. I dette tilfælde skal du vælge den synspunktsanalyse, du vil gennemse. 

### <a name="summary-tab"></a>Fanen Oversigt

Der findes fire primære datasektioner på resultatsiden. 

- **Gennemsnitlig synspunktscore**: Hjælper dig med at forstå det overordnede synspunkt på tværs af alle kunder. Synspunktsscorer er grupperet i tre kategorier: 
  1.    Negativ (-5 > 2)
  2.    Neutral (-1 > 1)
  3.    Positiv (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Visuel repræsentation af det overordnede kundesynspunkt.":::

- **Distribution af kunder efter synspunktscore**: Kunder kategoriseres i negative, neutrale og positive grupper baseret på deres synspunktscore. Hold musen hen over søjlerne i histogrammet for at se antallet af kunder og den gennemsnitlige synspunktscore i hver gruppe. Disse data kan hjælpe dig med at [oprette kundesegmenter](segments.md) baseret på synspunktsscorer.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Søjlediagram, der viser kundesynspunkt på tværs af de tre synspunktsgrupper.":::

- **Gennemsnitlig synspunktscore over tid**: Kunders synspunkt kan ændre sig med tiden. Vi leverer tendenser i dine kunders synspunkt i tidsintervallet for dine data. Denne visning kan hjælpe dig med at måle effekten af sæsonbetonede kampagner, produktlanceringer eller andre tidsbaserede kampagner, der påvirker kundernes synspunkt. Se grafen ved at vælge interesseåret i rullemenuen. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Historikdiagram med synspunktscore over tid repræsenteret som en kurve.":::
 
- **Synspunkt på tværs af forretningsaspekter**: Denne tabel indeholder det gennemsnitlige synspunkt på tværs af forretningsaspekter. Den kan hjælpe dig med at måle, hvilke aspekter af virksomheden der allerede tilfredsstiller kunder, eller aspekter, der kræver større opmærksomhed. Feedbackposter, der ikke passer ind under nogen af de understøttede forretningsaspekter, kategoriseres under **Andet**. Tabellen sorteres som standard alfabetisk. Du kan ændre sorteringen ved at vælge en tabeloverskrift.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Liste over forretningsaspekter med den tilknyttede synspunktsværdi og antallet af kunder, der omtaler den.":::
 
  Vælg navnet på et forretningsaspekt for at få vist flere oplysninger om, hvordan et forretningsaspekt identificeres af modellen. Der findes to dele i denne rude: 

  - **Ord, der giver indflydelse**: Viser de ord, der har størst indflydelse på AI-modellens identifikation af forretningsaspektet i kundefeedback. 
    **Vis stødende ord**: Giver dig mulighed for at inkludere stødende ord på listen fra oprindelige kundefeedbackdata. Det er som standard deaktiveret.  Maskering af stødende ord styres af en AI-model og registrerer muligvis ikke alle stødende ord. Vi fortsætter med at gentage og uddanne klassificeringen for at opnå optimal ydeevne. Hvis du registrerer et stødende ord, der ikke filtreres som forventet, skal du give os besked. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Liste over ord, der giver indflydelse, med mulighed for at få vist eller skjule stødende ord.":::
 
  - **Feedbackprøver**: Viser faktiske feedbackposter i dine data. Ord kodes med farve, afhængigt af deres indflydelse på identifikationen af et forretningsaspekt. 


### <a name="influential-words-analysis-tab"></a>Fanen Analyse af ord, der giver indflydelse

Der findes tre sektioner med yderligere oplysninger, der forklarer, hvordan synspunktsmodellen fungerer.
  
1. **Vigtigste ord, der bidrager til positivt synspunkt**: Viser de ord, der har størst indflydelse på AI-modellens identifikation af positivt synspunkt i kundefeedback.  
2. **Vigtigste ord, der bidrager til negativt synspunkt**: Viser de ord, der har størst indflydelse på AI-modellens identifikation af negativt synspunkt i kundefeedback.  
3. **Feedbackprøver**: Viser faktiske feedbackposter, én med et negativt synspunkt og én med et positivt synspunkt. Ord i feedbackposterne fremhæves afhængigt af deres bidrag til den tildelte synspunktscore. Ord, der bidrager til en positiv synspunktscore, fremhæves med grønt. Ord, der bidrager til et negativt resultat, fremhæves med rødt.
   Vælg **Se mere** for at indlæse flere feedbackprøver, der giver flere oplysninger om og konteksten for, hvordan synspunktsmodellen fungerer.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Eksempler på synspunktsanalyse på kundefeedback.":::
 
**Vis stødende ord**: Giver dig mulighed for at inkludere stødende ord på listen fra oprindelige kundefeedbackdata. Det er som standard deaktiveret.  Maskering af stødende ord styres af en AI-model og registrerer muligvis ikke alle stødende ord. Vi fortsætter med at gentage og uddanne klassificeringen for at opnå optimal ydeevne. Hvis du registrerer et stødende ord, der ikke filtreres som forventet, skal du give os besked. 

## <a name="act-on-analysis-results"></a>Handle på analyseresultater

Du kan nemt komme i gang med at oprette nye kundesegmenter på resultatsiden for synspunktsanalyser ved at vælge **Opret segmenter** øverst på siden med modelresultater.

:::image type="content" source="media/create-segment-model.png" alt-text="Kommandolinje med indstillinger for forudsigelsesmodeller.":::
 
## <a name="potential-bias"></a>Potentiel skævhed

Som med alle funktioner, der bruger kunstig intelligens, skal du være opmærksom på potentielle skævheder i de data, du bruger til at forudsige kundesynspunkt. Hvis du for eksempel kun indsamler feedback digitalt, kan du gå glip af feedback fra kunder, der primært handler med dig personligt, hvilket kan påvirke funktionens output.

Da denne funktion bruger automatiserede metoder til at evaluere data og foretage forudsigelser på baggrund af disse data, kan den derfor bruges som profileringsmetode, da denne betegnelse er defineret i den generelle databeskyttelsesforordning ("GDPR"). Din brug af denne funktion til at behandle data kan være underlagt GDPR eller andre love eller bestemmelser. Du er ansvarlig for at sikre, at din brug af Dynamics 365 Customer Insights, herunder synspunktsanalyser, er i overensstemmelse med alle gældende love og regler, herunder love vedrørende beskyttelse af personlige oplysninger, personlige data, biometriske data, databeskyttelse og fortrolighed i forbindelse med kommunikation.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

