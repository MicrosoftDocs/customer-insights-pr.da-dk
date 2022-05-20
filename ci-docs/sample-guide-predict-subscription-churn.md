---
title: Eksempelvejledning til forudsigelse af abonnementsafgang
description: Brug denne eksempelvejledning til at afprøve abonnementet i en forudsigelsesmodel for afgang af standard-abonnement.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741404"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Eksempelvejledning til forudsigelse af abonnementsafgang

Vi gennemgår fra start til slut et eksempel på forudsigelse af abonnementsafgang ved hjælp af de eksempeldata, der er angivet nedenfor. 

## <a name="scenario"></a>Scenarie

Contoso er et firma, der fremstiller kaffe og kaffemaskiner i høj kvalitet, som de sælger via deres Contoso Coffee-websted. De har for nylig startet en abonnementsforretning for kunderne for at få kaffe på normal basis. Deres målsætning er at forstå, hvilke abonnementskunder kan opsige deres abonnement i løbet af de næste par måneder. Det kan være en god hjælp at vide, hvilke af deres kunder der evt. **afgår**, ved at spare marketingkræfter og fokusere på at holde på dem.

## <a name="prerequisites"></a>Forudsætninger

- Mindst [bidragydertilladelser](permissions.md) i Customer Insights.
- Vi anbefaler, at du implementerer følgende trin [i et nyt miljø](manage-environments.md).

## <a name="task-1---ingest-data"></a>Opgave 1 - Indsættelse af data

Gennemse artiklerne [om dataimport](data-sources.md) og [import af datakilder ved hjælp af Power Query-connectorer](connect-power-query.md). I følgende oplysninger antages det, at du har generelt kendskab til indsættelse af data. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Indsættelse af kundedata fra eCommerce-platform

1. Opret en datakilde med navnet **eCommerce**, vælg importindstilling og **Text/CSV**-connector.

1. Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscontacts.

1. Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:

   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/Klokkeslæt/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformere fødselsdato til dato.":::

1. Omdøb datakilde fra **Forespørgsel** til **eCommerceContactsQuery** i feltet **Navn** i ruden til højre

1. Gem datakilden.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Indsæt kundedata fra loyalitetsskemaet

1. Opret en datakilde med navnet **LoyaltyScheme**, vælg importindstilling og **Text/CSV**-connector.

1. Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscustomerloyalty.

1. Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:

   - **DateOfBirth**: Dato
   - **RewardsPoints**: Heltal
   - **CreatedOn**: Dato/Klokkeslæt

1. Omdøb datakilde fra **Forespørgsel** til **loyCustomers** i feltet **Navn** i ruden til højre.

1. Gem datakilden.

### <a name="ingest-subscription-information"></a>Indsæt oplysninger om abonnement

1. Opret en datakilde med navnet **SubscriptionHistory**, vælg importindstilling og **Text/CSV**-connector.

1. Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadchurnsubscriptionhistory.

1. Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:

   - **SubscriptioID**: Heltal
   - **SubscriptionAmount**: Valuta
   - **SubscriptionEndDate** : Dato/klokkeslæt
   - **SubscriptionEndDate** : Dato/Klokkeslæt
   - **TransactionDate**: Dato/Klokkeslæt
   - **IsRecurring**: Sand/Falsk
   - **Is_auto_renew**: Sand/Falsk
   - **RecurringFrequencyInMonths**: Heltal

1. Omdøb datakilde fra **Forespørgsel** til **SubscriptionHistory** i feltet **Navn** i ruden til højre.

1. Gem datakilden.

### <a name="ingest-customer-data-from-website-reviews"></a>Indsættelse af kundedata fra gennemsyn af websted

1. Opret en datakilde med navnet **Website**, vælg importindstilling og **Text/CSV**-connector.

1. Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasswebsite.

1. Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:

   - **ReviewRating**: Heltal
   - **ReviewDate**: Dato

1. Omdøb datakilde fra **Forespørgsel** til **webReviews** i feltet 'Navn' i ruden til højre.

## <a name="task-2---data-unification"></a>Opgave 2 - Datasamling

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Opgave 3 - Konfiguration af forudsigelse af abonnementsafgang

Når du har samlet kundeprofiler på plads, kan vi nu køre forudsigelse af abonnementsafgang. Du kan finde flere oplysninger i artiklen om [Forudsigelse af opsigelse af abonnement](predict-subscription-churn.md). 

1. Gå til **Intelligens** > **Find**, og vælg at bruge **Model for kundeafgang**.

1. Vælg indstillingen **Abonnement**, og vælg **Start her**.

1. Navngiv modellen **Forudsigelse af afgang af OOB-abonnement** og outputobjektets **OOBSubscriptionChurnPrediction**.

1. Definer to betingelser for afgangsmodellen:

   * **Antal dage siden abonnement er afsluttet**: **mindst 60** dage. Hvis en kunde ikke har fornyet sit abonnement inden for dette tidsrum, efter at abonnementet er udløbet, betragtes vedkommende som tabt 

   * **Definition af afgang**: **mindst 93** dage. Den varighed, modellen forudsiger, hvilke kunder der afgår. Jo længere i fremtidsvisningen du er, jo mindre præcis er resultaterne.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Vælg den model, der udnytter et forudsigelsesvindue og definition af afgang.":::

1. Vælg **Tilføj påkrævede data**, og vælg **Tilføj data** til abonnementsoversigt.

1. Tilføj **Abonnementet: SubscriptionHistory**-objektet, og tilknyt felterne fra eCommerce til de tilsvarende felter, der kræves af modellen.

1. Deltag i **Abonnement: SubscriptionHistory**-objekt med **eCommerceContacts: eCommerce**, navngiv relationen **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Forbind eCommerce-objekter.":::

1. Tilføj **webReviews: Websted**-objektet under kundeaktiviteter, og tilknyt felterne fra webReviews til de tilsvarende felter, der kræves af modellen. 
   - Primær nøgle: ReviewId
   - Tidsstempel: ReviewDate
   - Hændelse: ReviewRating

1. Konfigurer en aktivitet til webstedets gennemgang. Vælg aktiviteten **Gennemse**, og deltag i **webReviews: Websted**-objekt med **eCommerceContacts: eCommerce**.

1. Vælg **Næste** for at angive modelplanen.

   Modellen skal trænes regelmæssigt for at lære nye mønstre, når der er nye data, der indtages. I dette eksempel skal du vælge **Månedlig**.

1. Vælg **Gem og Kør**, når du har gennemgået alle detaljer.

## <a name="task-4---review-model-results-and-explanations"></a>Opgave 4 - Gennemse modelresultater og forklaringer

Lad modellen fuldføre med at få oplæring og resultaterne af dataene. Du kan nu gennemgå forklaringer på afgang af abonnementsmodellen. Du kan finde flere oplysninger under [Gennemse en forudsigelsesstatus og resultater](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Opgave 5 - Opret et segment med kunder med risiko for afgang

Når produktionsmodellen køres, oprettes der et nyt objekt, som du kan se i **Data** > **Objekter**.   

Du kan oprette et nyt segment baseret på det objekt, der er oprettet af modellen.

1.  Gå til **Segmenter** Vælg **Ny**, og vælg **Opret fra** > **Intelligens**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Oprettelse af et segment ved hjælp af model-output.":::

1. Vælg den **OOBSubscriptionChurnPrediction**-slutpunkt, og definer segmentet: 
   - Felt: ChurnScore
   - Operatør: større end
   - Værdi: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Opsætning af abonnementsafgang-segment.":::

Du har nu et segment, der opdateres dynamisk, og som identificerer de mange kunder med høj risiko for afgang til denne abonnementsforretning.

Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]