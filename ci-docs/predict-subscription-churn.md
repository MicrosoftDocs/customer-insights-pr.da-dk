---
title: Forudsige abonnementsafgang (indeholder video)
description: Du kan forudsige, om der er risiko for, at en kunde ikke længere vil bruge dit firmas produkter eller services.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610229"
---
# <a name="predict-subscription-churn"></a>Forudsige abonnementsafgang

Du kan forudsige, om der er risiko for, at en kunde ikke længere vil bruge dit firmas produkter eller services. Abonnementsdata omfatter aktive og inaktive abonnementer for hver kunde, så der er flere poster pr. kunde-id.

Du skal have forretningsviden for at forstå, hvad afgang betyder for din virksomhed. Vi understøtter tidsbaserede afgangsdefinitioner, hvilket vil sige, at en kundes afgang forventes et stykke tid efter, at abonnementet er ophørt.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Prøv forudsigelsen af abonnementsafgang ved hjælp af eksempeldata: [Eksempelvejledning til forudsigelse af abonnementsafgang](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Forudsætninger

- Mindst [Bidragyder-tilladelser](permissions.md).
- Mindst 10 kundeprofiler, helst mere end 1.000 entydige kunder.
- Kunde-id'er, et entydigt id, der matcher abonnementer med dine kunder.
- Abonnementsdata for mindst det dobbelte af det valgte tidsvindue. Helst to til tre års abonnementsdata. Abonnementshistorikken skal omfatte:
  - **Abonnements-id:** Entydigt id for et abonnement.
  - **Abonnementets slutdato:** Den dato, abonnementet udløber for kunden.
  - **Abonnementets startdato:** Den dato, abonnementet starter for kunden.
  - **Transaktionsdato:** Den dato, hvor et abonnement er ændret. F.eks. køber eller opsiger en kunde et abonnement.
  - **Er det et tilbagevendende abonnement:** Boolesk sand/falsk-felt, der bestemmer, om abonnementet fornyes med det samme abonnements-id uden kundens indgriben.
  - **Gentagelseshyppighed (i måneder):** For tilbagevendende abonnementer er det den måned, hvor abonnementet fornyes. Et årsabonnement, der automatisk fornys for en kunde hvert år for endnu et andet, har værdien 12.
  - **Abonnementsbeløb:** Valutabeløb, kunden betaler i forbindelse med fornyelsen af abonnementet. Det kan være med til at identificere mønstre for forskellige niveauer af abonnementer.
- Mindst to aktivitetsposter for 50 % af de kunder, du vil beregne kundeafgang for. Kundeaktiviteter skal omfatte:
  - **Primær nøgle:** Entydigt id for en aktivitet. Et besøg på et websted eller en forbrugspost, der viser, at kunden har set et afsnit af et TV-show.
  - **Tidsstempel:** Dato og klokkeslæt for hændelsen, der identificeres af den primære nøgle.
  - **Hændelse:** Navnet på den hændelse, du vil bruge. Et felt kaldes f.eks. "UserAction" i en videostreamingsservice med værdien "Set".
  - **Detaljer:** Detaljerede oplysninger om hændelsen. Et felt kaldes f.eks. "ShowTitle" i en videostreamingsservice med værdien af en video, som en kunde har set.
- Mindre end 20 % af de manglende værdier i datafeltet for det angivne objekt.

## <a name="create-a-subscription-churn-prediction"></a>Oprette en abonnementsafgang (prøveversion)

Du kan når som helst vælge **Gem kladde** for at gemme forudsigelsen som en kladde. Kladdeforudsigelsen vises under fanen **Mine forudsigelser**.

1. Gå til **Intelligens** > **Forudsigelser**.

1. Gå til fanen **Opret**, og vælg **Brug model** i feltet **Model til kundeafgang**.

1. Vælg **Abonnement** for typen af kundeafgang og derefter **Start her**.

1. **Navngive denne model** og **navnet på outputobjektet** for at skelne mellem dem fra andre modeller eller objekter.

1. Vælg **Næste**.

### <a name="define-customer-churn"></a>Definer kundeafgang

1. Angiv antallet af **Dage, siden abonnement sluttede**, som din virksomhed betragter som en kunde, der ikke længere er kunde. Denne periode er typisk knyttet til forretningsaktiviteter som tilbud eller andre marketingtiltag, der forsøger at forhindre tab af kunden.

1. Angiv et antal under **Antal dage, der skal søges fremad for at forudsige afslutning**. Du kan f. eks. forudsige risikoen for afgang af kunder i løbet af de næste 90 dage for at justere din marketingsindsats. Forudsigelse af afgangsrisiko i kortere eller længere perioder kan gøre det mere problematisk at adressere faktorer i din afgangsrisikoprofil, afhængigt at dine specifikke forretningskrav.

1. Vælg **Næste**.

### <a name="add-required-data"></a>Tilføj påkrævede data

1. Vælg **Tilføj data** for **Abonnementshistorik**.

1. Vælg den semantiske aktivitetstype **Abonnement**, der indeholder de påkrævede oplysninger om abonnementshistorikken. Hvis aktiviteten ikke er blevet konfigureret, skal du vælge **her** og oprette den.

1. Hvis aktivitetsattributterne blev semantically tilknyttet under **Aktiviteter**, da aktiviteten blev oprettet, skal du vælge de specifikke attributter eller det objekt, beregningen skal fokusere på. Hvis der ikke blev udført en semantisk tilknytning, skal du vælge **Rediger** og tilknytte dataene.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Tilføje påkrævede data for modellen til abonnementsafgang":::

1. Vælg **Næste**, og gennemse de attributter, der kræves til denne model.

1. Vælg **Gem**.

1. Vælg **Tilføj data** for **Kundeaktiviteter**.

1. Vælg den semantiske aktivitetstype, der indeholder oplysninger om kundeaktiviteter. Hvis aktiviteten ikke er blevet konfigureret, skal du vælge **her** og oprette den.

1. Hvis aktivitetsattributterne blev semantically tilknyttet under **Aktiviteter**, da aktiviteten blev oprettet, skal du vælge de specifikke attributter eller det objekt, beregningen skal fokusere på. Hvis der ikke blev udført en semantisk tilknytning, skal du vælge **Rediger** og tilknytte dataene.

1. Vælg **Næste**, og gennemse de attributter, der kræves til denne model.

1. Vælg **Gem**.

1. Tilføj flere aktiviteter, eller vælg **Næste**.

### <a name="set-update-schedule"></a>Indstil opdateringsplan

1. Vælg hyppigheden for gentræning af modellen. Denne indstilling er vigtig for at opdatere præcisionen af forudsigelser, når nye data vises i Customer Insights. De fleste virksomheder kan omskole én gang om måneden og opnå en god præcision af deres forudsigelse.

1. Vælg **Næste**.

### <a name="review-and-run-the-model-configuration"></a>Gennemse og kør modelkonfigurationen

I trinnet **Gennemse og kør** vises en oversigt over konfigurationen, og her kan du foretage ændringer, før du opretter forudsigelsen.

1. Vælg **Rediger** på et af trinnene for at gennemse og foretage ændringer.

1. Hvis du er tilfreds med dine valg, skal du vælge **Gem og kør** for at starte kørsel af modellen. Vælg **Udført**. Fanen **Mine forudsigelser** vises, mens forudsigelse oprettes. Det kan tage flere timer, før processen er fuldført, afhængigt af mængden af data, der bruges i forudsigelsen.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Få vist forudsigelsesresultater

1. Gå til **Intelligens** > **Forudsigelser**.

1. Under fanen **Mine forudsigelser** skal du vælge den forudsigelse, du vil have vist.

Der findes tre primære sektioner med data på resultatsiden:

- **Ydeevne for træning af model**: Klassificeringerne A, B eller C angiver resultatet af forudsigelsen og kan hjælpe dig med at træffe beslutning om at bruge de resultater, der er gemt i outputobjektet.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Billede af feltet med oplysninger om modelpoint med vurderingen A.":::

  Vurderingerne bestemmes ud fra følgende regler:
  - **A**, når modellen forventes at forudse mindst 50 % af de samlede forudsigelser, og når procentsatsen for præcise forudsigelser for kunder, der er afgået, er større end den historiske gennemsnitlige afgang med mindst 10 %.
  - **B**, når modellen forventes at forudse mindst 50 % af de samlede forudsigelser, og når procentsatsen for præcise forudsigelser for kunder, der er afgået, er op til 10 % større end den historiske gennemsnitlige afgang.
  - **C** når modellen præcist har forudset mindre end 50 % af det samlede antal forudsigelser, eller når procentsatsen for præcise forudsigelser for kunder, der er mistet, er mindre end den historiske gennemsnitlige afgang.
  
- **Sandsynlighed for afgang (antal kunder)**: Kundegrupper baseret på deres forudsagte risiko for afgang. Du kan også [oprette kundesegmenter](prediction-based-segment.md) med stor risiko for afgang. Sådanne segmenter hjælper dig med at forstå, hvor din grænse skal være for segmentmedlemskab.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Graf, der viser fordelingen af afgangsresultater, opdelt i intervaller fra 0 - 100 %":::

- **Mest indflydelsesrige faktorer:** Der er mange faktorer, som tages i betragtning ved oprettelsen af din forudsigelse. Hver af faktorerne er vigtig for de aggregerede forudsigelser, som en model opretter. Brug disse faktorer til at validere dine forudsigelsesresultater. Eller brug oplysningerne senere til at [oprette segmenter](.//prediction-based-segment.md), der kan være med til at påvirke risikoen for kundeafgang.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Liste, der viser indflydelsesrige faktorer og deres betydning ved forudsigelse af afgangsresultatet.":::

> [!NOTE]
> I outputobjektet for denne model er *ChurnScore* den anslåede sandsynlighed for kundeafgang, og *IsChurn* er en binær etiket baseret på *ChurnScore* med en tærskelværdi på 0,5. Hvis denne standardtærskelværdi ikke fungerer for dit scenario, skal du [oprette et nyt segment](segments.md) med din foretrukne tærskelværdi. Hvis du vil have vist kundeafgangsscoren, skal du gå til **Data** > **Objekter** og se datafanen for det outputobjekt, du har defineret for denne model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
