---
title: Analysér synspunkt for kundefeedback (forhåndsversion)
description: Få mere at vide om, hvordan du anvender en synspunktsanalysemodel på kundefeedback i Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610454"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analysér synspunkt i kundefeedback (forhåndsversion)

Synspunktsanalyse giver dig mulighed for at synkronisere kundernes synspunkt og identificere forretningsaspekter som muligheder for forbedringer. Denne funktion i Customer Insights hjælper dig med at forstå, hvad der fungerer godt, og hvad du har brug for at ændre. Det kan hjælpe dig med at udføre forretningshandlinger, der giver oplevelser, som medfører stor kundetilfredshed og loyalitet.

## <a name="overview"></a>Oversigt

Funktionen til synspunktsanalyse genererer to afledte indsigter pr. kunde-id. En synspunktscore (på -5 til 5) og en liste over relevante forretningsaspekter (forretningsområder), der tilsammen hjælper dig med bedre at forstå kundefeedbacken.

Denne analyse hjælper dig med at:
- Få en oversigt over kundesynspunkter i forhold til et mærke eller en organisation
- Identificere kunder med negative synspunkter, så du kan fokusere på kampagner og engagementer og optimere for at få højere afkast  
- Identificere forretningsaspekter med problemer, som kunderne påpeger  
- Segmentere kunder baseret på deres synspunkt for at køre tilpassede kampagner med målrettede salgs-, marketing- og supportindsatser
- Optimere virksomhedsdriften ved at tage sig af områder med problemer eller salgsmuligheder, som kunderne har nævnt
- Anerkende forretningsaspekter, der klarer sig godt, og belønne tilfredse kunder gennem loyalitets- og kampagneprogrammer

Modellen indeholder en liste over ord, der påvirkede modellens beslutning om at tildele en bestemt synspunktscore eller et forretningsaspekt til feedbackkommentarer.  

Vi bruger to **NLP-modeller (Natural Language Processing)**: De første tildeler hver feedbackkommentar en synspunktscore. Den anden model knytter de enkelte feedbacktilmeldinger til alle relevante forretningsaspekter. Modellen er trænet på offentlige data fra kilder på tværs af sociale medier, detail, restauranter, forbrugerprodukter og bilbranchen.
  
Foruddefinerede forretningsaspekter for modellen, der skal knyttes til feedbackdata, omfatter:
- Kontoadministration
- Tjek ud og betaling
- Kundesupport
- Afhentning i lager
- Pakkeforsendelse og hentning
- Forudbestilling
- Pris
- Beskyttelse af personlige oplysninger og sikkerhed
- Kampagner og belønninger
- Kvittering og garanti
- Ombytning og annullering af returvarer
- Nøjagtighed af opfyldelse
- Kvalitet af websted/app

> [!NOTE]
> I øjeblikket understøtter vi kun synspunktsanalyse på engelsk kundefeedback. Flere sprog understøttes i fremtiden. Hvis der overføres feedback på andre sprog, returnerer modellen stadig resultater. Disse resultater er dog ikke nøjagtige.

## <a name="prerequisites"></a>Forudsætninger

- Mindst [Bidragyder-tilladelser](permissions.md)
- Feedbackdata med [samlet](data-unification.md) tekst. Det anbefales på det kraftigste, at du [konfigurerer dine feedbackdataobjekter som semantiske aktivitetsobjekter](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (feedbacktype).
- UCID (Unified Customer ID) fra datasamling, der skal sammenholde tekstfeedbackdataposter med de enkelte kunder.
- Feedback-id
- Tidsstempel for feedback
- Feedbacktekst

Customer Insights kan behandle op til 10 millioner feedbackposter for en enkelt modelkørsel. Modellen kan analysere feedbackkommentarer på op til 128 ord. Hvis en feedbackkommentar er længere, tager modellen kun de første 128 ord med i analysen.

> [!NOTE]
> Der kan kun konfigureres ét feedbackobjekt. Hvis der er flere feedbackobjekter, kan du samle dem i Power Query, før dataindtagelse går i gang.

## <a name="configure-a-sentiment-analysis"></a>Konfigurere en synspunktsanalyse

1. Gå til **Intelligens** > **Forudsigelser**.

1. Under fanen **Opret** skal du vælge **Brug model** i feltet **Kundesynspunktsanalyse (forhåndsversion)**.

1. Vælg **Start her**.

1. Giv analysen et **navn**, og angiv **Navn på outputobjekt for forretningsaspekt** og **Navn på outputobjekt for synspunktsscore**.

1. Vælg **Næste**.

1. Vælg **Tilføj data** for **Kundefeedback**.

1. Vælg den semantiske aktivitetstype **Feedback**, der indeholder feedbackdataene. Hvis aktiviteten ikke er blevet konfigureret, skal du vælge **her** og oprette den.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigurationstrin til valg af feedbackaktiviteter til synspunktsanalyse.":::

1. Vælg de aktiviteter, du vil bruge til denne synspunktsanalyse, og vælg derefter **Næste**.

1. Knyt attributterne i dataene til modelattributterne. 

1. Vælg **Gem**.

1. Vælg **Næste**. I trinnet **Gennemse og kør** vises en oversigt over konfigurationen, og her kan du foretage ændringer, før du opretter analysen.

1. Vælg **Rediger** på et af trinnene for at gennemse og foretage ændringer.

1. Hvis du er tilfreds med dine valg, skal du vælge **Gem og kør** for at starte kørsel af modellen. Vælg **Udført**. Fanen **Mine forudsigelser** vises, mens forudsigelse oprettes. Det kan tage flere timer, før processen er fuldført, afhængigt af mængden af data, der bruges i forudsigelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Få vist analyseresultater

1. Gå til **Intelligens** > **Forudsigelser**.

1. Under fanen **Mine forudsigelser** skal du vælge den forudsigelse, du vil have vist.

Der findes to faner med resultater.

### <a name="sumary-tab"></a>Fanen Oversigt

Der findes fire primære datasektioner på resultatsiden.

- **Gennemsnitlig synspunktscore**: Synspunktscore hjælper dig med at forstå det overordnede synspunkt på tværs af alle kunder.
  - **Negativ** (-5 > 2)
  - **Ved ikke** (-1 > 1)
  - **Positiv** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Visuel repræsentation af det overordnede kundesynspunkt.":::

- **Distribution af kunder efter synspunktscore**: Kunder kategoriseres i negative, neutrale og positive grupper baseret på deres synspunktscore. Hold musen hen over søjlerne i histogrammet for at se antallet af kunder og den gennemsnitlige synspunktscore i hver gruppe. Disse data kan hjælpe dig med at [oprette kundesegmenter](prediction-based-segment.md) baseret på synspunktsscorer.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Søjlediagram, der viser kundesynspunkt på tværs af de tre synspunktsgrupper.":::

- **Gennemsnitlig synspunktscore over tid**: Kunders synspunkt kan ændre sig med tiden. Vi leverer tendenser i dine kunders synspunkt i tidsintervallet for dine data. Denne visning hjælper dig med at måle effekten af sæsonbetonede kampagner, produktlanceringer eller andre tidsbaserede kampagner, der påvirker kundernes synspunkt. Se grafen ved at vælge interesseåret i rullemenuen.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Historikdiagram med synspunktscore over tid repræsenteret som en kurve.":::

- **Synspunkt på tværs af forretningsmæssige aspekter**: Gennemsnitligt synspunkt på tværs af forretningsmæssige aspekter hjælper dig med at måle, hvilke aspekter af virksomheden der allerede opfylder kundernes forventninger eller kræver mere opmærksomhed. Feedbackposter, der ikke passer ind under nogen af de understøttede forretningsaspekter, kategoriseres under **Andet**. Sortér dataene ved at markere en hvilken som helst kolonne.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Liste over forretningsaspekter med den tilknyttede synspunktsværdi og antallet af kunder, der omtaler den.":::

  Vælg navnet på et forretningsaspekt for at se, hvordan et forretningsaspekt identificeres af modellen:

  - **Ord, der giver indflydelse**: De ord, der har størst indflydelse på AI-modellens identifikation af forretningsaspektet i kundefeedback.
    **Vis stødende ord**: Giver dig mulighed for at inkludere stødende ord på listen fra oprindelige kundefeedbackdata. Det er som standard deaktiveret.  Maskering af stødende ord styres af en AI-model og registrerer muligvis ikke alle stødende ord. Hvis du registrerer et stødende ord, der ikke filtreres som forventet, skal du give os besked.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Liste over ord, der giver indflydelse, med mulighed for at få vist eller skjule stødende ord.":::

  - **Feedbackprøver**: Faktiske feedbackposter i dine data. Ord kodes med farve, afhængigt af deres indflydelse på identifikationen af et forretningsaspekt.

### <a name="influential-words-analysis-tab"></a>Fanen Analyse af ord, der giver indflydelse

Der findes tre sektioner med yderligere oplysninger, der forklarer, hvordan synspunktsmodellen fungerer.
  
- **Vigtigste ord, der bidrager til positivt synspunkt**: De ord, der har størst indflydelse på AI-modellens identifikation af positivt synspunkt i kundefeedback.  

- **Vigtigste ord, der bidrager til negativt synspunkt**: De ord, der har størst indflydelse på AI-modellens identifikation af negativt synspunkt i kundefeedback.

- **Feedbackprøver**: Faktiske feedbackposter, én med et negativt synspunkt og én med et positivt synspunkt. Ord i feedbackposterne fremhæves afhængigt af deres bidrag til den tildelte synspunktscore. Ord, der bidrager til en positiv synspunktscore, fremhæves med grønt. Ord, der bidrager til et negativt resultat, fremhæves med rødt.
   Vælg **Se mere** for at indlæse flere feedbackprøver.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Eksempler på synspunktsanalyse på kundefeedback.":::

**Vis stødende ord**: Giver dig mulighed for at inkludere stødende ord på listen fra oprindelige kundefeedbackdata. Det er som standard deaktiveret.  Maskering af stødende ord styres af en AI-model og registrerer muligvis ikke alle stødende ord. Hvis du registrerer et stødende ord, der ikke filtreres som forventet, skal du give os besked.

## <a name="act-on-analysis-results"></a>Handle på analyseresultater

Hvis du vil oprette nye kundesegmenter ud fra resultater for synspunktsanalyser, skal du vælge **Opret segmenter** øverst på siden med modelresultater.

## <a name="potential-bias"></a>Potentiel skævhed

Som med alle funktioner, der bruger kunstig intelligens, kan der være potentielle skævheder i de data, du bruger til at forudsige kundesynspunkt. Hvis du for eksempel kun indsamler feedback digitalt, går du muligvis glip af feedback fra kunder, der primært handler med dig personligt, hvilket påvirker funktionens output.

Da denne funktion bruger automatiserede metoder til at evaluere data og foretage forudsigelser på baggrund af disse data, kan den derfor bruges som profileringsmetode, da denne betegnelse er defineret i den generelle databeskyttelsesforordning ("GDPR"). Din brug af denne funktion til at behandle data kan være underlagt GDPR eller andre love eller bestemmelser. Du er ansvarlig for at sikre, at din brug af Dynamics 365 Customer Insights, herunder synspunktsanalyser, er i overensstemmelse med alle gældende love og regler, herunder love vedrørende beskyttelse af personlige oplysninger, personlige data, biometriske data, databeskyttelse og fortrolighed i forbindelse med kommunikation.

[!INCLUDE [footer-include](includes/footer-banner.md)]

