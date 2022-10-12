---
title: Eksempelvejledning til forudsigelse af abonnementsafgang
description: Brug denne eksempelvejledning til at afprøve abonnementet i en forudsigelsesmodel for afgang af standard-abonnement.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609999"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Eksempelvejledning til forudsigelse af abonnementsafgang

Denne vejledning vil gennemgå et eksempel på forudsigelse af abonnementsafgang ved hjælp af eksempeldata. Vi anbefaler, at du udfører denne forudsigelse [i et nyt miljø](manage-environments.md).

## <a name="scenario"></a>Scenarie

Contoso er en virksomhed, der fremstiller kaffe- og kaffemaskiner af høj kvalitet. Produkterne sælges via deres Contoso Coffee-websted. De har for nylig startet en abonnementsforretning for kunderne for at få kaffe på normal basis. Deres målsætning er at forstå, hvilke abonnementskunder kan opsige deres abonnement i løbet af de næste par måneder. Det kan være en god hjælp at vide, hvilke af deres kunder der evt. **afgår**, ved at spare marketingkræfter og fokusere på at holde på dem.

## <a name="prerequisites"></a>Forudsætninger

- Mindst [bidragydertilladelser](permissions.md) i Customer Insights.

## <a name="task-1---ingest-data"></a>Opgave 1 - Indsættelse af data

Gennemse artiklerne [om dataindtag](data-sources.md) og [oprettelse af forbindelse til en Power Query-datakilde](connect-power-query.md). I følgende oplysninger antages det, at du har generelt kendskab til indtag af data.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Indsættelse af kundedata fra eCommerce-platform

1. Opret en Power Query-datakilde med navnet **eCommerce**, og vælg **Text/CSV**-connectoren.

1. Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscontacts.

1. Når du redigerer dataene, skal du vælge **Transformer** og derefter **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/Klokkeslæt/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformere fødselsdato til dato.":::

1. Omdøb datakilden til **eCommerceContacts** i feltet **Navn** i ruden til højre

1. Gem datakilden.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Indsæt kundedata fra loyalitetsskemaet

1. Opret en datakilde med navnet **LoyaltyScheme**, og vælg **Text/CSV**-connectoren.

1. Angiv URL-adressen til loyale kunder https://aka.ms/ciadclasscustomerloyalty.

1. Når du redigerer dataene, skal du vælge **Transformer** og derefter **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **DateOfBirth**: Dato
   - **RewardsPoints**: Heltal
   - **CreatedOn**: Dato/Klokkeslæt

1. Omdøb datakilden til **loyCustomers** i feltet **Navn** i ruden til højre.

1. Gem datakilden.

### <a name="ingest-subscription-information"></a>Indsæt oplysninger om abonnement

1. Opret en datakilde med navnet **SubscriptionHistory**, og vælg **Text/CSV**-connectoren.

1. Angiv URL-adressen til abonnementer https://aka.ms/ciadchurnsubscriptionhistory.

1. Når du redigerer dataene, skal du vælge **Transformer** og derefter **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **SubscriptioID**: Heltal
   - **SubscriptionAmount**: Valuta
   - **SubscriptionEndDate** : Dato/klokkeslæt
   - **SubscriptionEndDate** : Dato/Klokkeslæt
   - **TransactionDate**: Dato/Klokkeslæt
   - **IsRecurring**: Sand/Falsk
   - **Is_auto_renew**: Sand/Falsk
   - **RecurringFrequencyInMonths**: Heltal

1. Omdøb dine datakilde til **SubscriptionHistory** i feltet **Navn** i højre rude.

1. Gem datakilden.

### <a name="ingest-customer-data-from-website-reviews"></a>Indsættelse af kundedata fra gennemsyn af websted

1. Opret en datakilde med navnet **Websted**, og vælg **Text/CSV**-connectoren.

1. Angiv URL-adressen til webstedsgennemsyn https://aka.ms/ciadclasswebsite.

1. Når du redigerer dataene, skal du vælge **Transformer** og derefter **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **ReviewRating**: Heltal
   - **ReviewDate**: Dato

1. Omdøb din datakilde til **webReviews** i feltet **Navn** i ruden til højre.

## <a name="task-2---data-unification"></a>Opgave 2 - Datasamling

Gennemse artiklen [om datasamling](data-unification.md). I følgende oplysninger antages det, at du har generelt kendskab til datasamling.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Opgave 3 – Opret transaktionshistorikaktivitet

Gennemse artiklen [om kundeaktiviteter](activities.md). I følgende oplysninger antages det, at du har generelt kendskab til oprettelse af aktiviteter.

1. Opret en aktivitet, der kaldes **SubscriptionHistory** med objektet *Subscription* og den primære nøgle **CustomerId**.

1. Opret en relation mellem *SubscriptionKonstory:Subscription* og *eCommerceContacts:eCommerce* med **CustomerID** som den fremmede nøgle for at oprette forbindelse til de to objekter.

1. Vælg **SubscriptionType** for **EventActivity** og **SubscriptionEndDate** for **TimeStamp**.

1. Vælg **Abonnement** for **Aktivitetstype**, og tilknyt aktivitetsdataene semantisk.

1. Kør aktiviteten.

1. Tilføj endnu en aktivitet, og knyt feltnavnene til de tilsvarende felter:
   - Kundeaktivitetsobjekt: Anmeldelser:Websted
   - Primær nøgle: Website.Reviews.ReviewId
   - Tidsstempel: Website.Reviews.ReviewDate
   - Hændelse (aktivitetsnavn): Website.Reviews.ActivityTypeDisplay
   - Detaljer (beløb eller værdi): Website.Reviews.ReviewRating

1. Kør aktiviteten.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Opgave 4 - Konfiguration af forudsigelse af abonnementsafgang

Når du har samlet kundeprofiler og oprettet en aktivitet, skal du køre forudsigelse af abonnementsafgang. Du kan finde flere oplysninger i [Forudsigelse af abonnementsafgang](predict-subscription-churn.md).

1. Gå til **Intelligens** > **Forudsigelser**.

1. Gå til fanen **Opret**, og vælg **Brug model** i feltet **Model til kundeafgang**.

1. Vælg **Abonnement** for typen af kundeafgang og derefter **Start her**.

1. Navngiv modellen **Forudsigelse af afgang af OOB-abonnement** og outputobjektets **OOBSubscriptionChurnPrediction**.

1. Definere modelindstillinger:
   - **Dage siden abonnementet sluttede**: **60** dage for at angive, at en kunde betragtes som afgået, hvis kunden ikke fornyer abonnementet i denne periode, efter at abonnementet er afsluttet.
   - **Antal dage, der skal søges fremad for at forudsige afslutning**: **93** dage, dvs. den varighed, som modellen forudsiger, at kunderne afgår. Jo længere i fremtidsvisningen du er, jo mindre præcis er resultaterne.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Vælg modelindstillingerne og afgangsdefinition.":::

1. Vælg **Næste**.

1. I trinnet **Obligatoriske data** skal du vælge **Tilføj data** for at angive en abonnementshistorik.

1. Vælg **Abonnement** og objektet SubscriptionTory, og vælg **Næste**. De påkrævede data indsættes automatisk fra aktiviteten. Vælg **Gem**.

1. Vælg **Tilføj data** under Kundeaktiviteter.

1. I dette eksempel skal du tilføje webgennemgangsaktiviteten.

1. Vælg **Næste**.

1. Vælg **Månedligt** i trinnet **Dataopdateringer** for modeltidsplanen.

1. Vælg **Gem og Kør**, når du har gennemgået alle detaljer.

## <a name="task-5---review-model-results-and-explanations"></a>Opgave 5 - Gennemse modelresultater og forklaringer

Lad modellen fuldføre med at få oplæring og resultaterne af dataene. Gennemse forklaringerne på abonnementsafgangsmodellen. Du kan finde flere oplysninger under [Få vist forudsigelsesresultater](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Opgave 6 - Opret et segment med kunder med risiko for afgang

Når du kører modellen, oprettes der et nyt objekt, som vises i **Data** > **Objekter**. Du kan oprette et nyt segment baseret på det objekt, der er oprettet af modellen.

1. Vælg **Opret segment** på resultatsiden.

1. Opret en regel ved hjælp af objektet **OOBSubscriptionChurnPrediction**, og definer segmentet:
   - **Felt**: ChurnScore
   - **Operator**: større end
   - **Værdi**: 0,6

1. Vælg **Gem** og **Kør** segmentet.

Du har nu et segment, der opdateres dynamisk, og som identificerer de mange kunder med høj risiko for afgang til denne abonnementsforretning. Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).

> [!TIP]
> Du kan også oprette et segment for en forudsigelsesmodel fra siden **Segmenter** ved at vælge **Ny** og vælge **Opret fra** > **Intelligens**. Du kan finde flere oplysninger under [Oprette et nyt segment med hurtige segmenter](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
