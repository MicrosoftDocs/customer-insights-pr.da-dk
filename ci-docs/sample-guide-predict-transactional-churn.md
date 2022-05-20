---
title: Eksempelvejledning til transaktionsrelateret forudsigelse af afgang
description: Brug denne eksempelvejledning til at afprøve transaktionsrelateret standardafgang i en forudsigelsesmodel.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741312"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Eksempelvejledning til transaktionsrelateret forudsigelse af afgang

Denne vejledning vil gennemgå et eksempel på forudsigelse af transaktionsrelateret afgang i Customer Insights fra start til slut ved hjælp af de data, der er angivet nedenfor. Alle de data, der bruges i denne vejledning, er ikke virkelige kundedata og er en del af det Contoso-datasæt, der findes i *Demo*-miljøet i Customer Insights-abonnementet.

## <a name="scenario"></a>Scenarie

Contoso er et firma, der fremstiller kaffe og kaffemaskiner i høj kvalitet, som de sælger via deres Contoso Coffee-websted. Deres mål er at vide, hvilke kunder der jævnligt køber deres produkter, men som holder op med at være aktive kunder i de næste 60 dage. Det kan være en god hjælp at vide, hvilke af deres kunder der evt. **afgår**, ved at spare marketingkræfter og fokusere på at holde på dem.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Omdan DoB til dato.":::

1. Omdøb datakilde fra **Forespørgsel** til **eCommerceContactsQuery** i feltet **Navn** i ruden til højre

1. Gem datakilden.

### <a name="ingest-online-purchase-data"></a>Indsættelse af online købsdata

1. Tilføj et andet datasæt til samme **eCommerce**-datakilde. Vælg **Tekst/CSV**-connector igen.

1. Angiv URL-adressen til **onlinekøb**-data https://aka.ms/ciadclassonline.

1. Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:

   - **PurchasedOn**: Dato/Klokkeslæt
   - **TotalPrice**: Valuta
   
1. Omdøb datakilde fra **Forespørgsel** til **eCommercePurchases** i feltet **Navn** i ruden til højre.

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

## <a name="task-2---data-unification"></a>Opgave 2 - Datasamling

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Opgave 3 - Konfiguration af transaktion af forudsigelse af afgang

Nu, hvor de samlede kundeprofiler er på plads, kan vi køre forudsigelse af transaktionsafgang. Du kan finde flere oplysninger i artiklen om [Forudsigelse af transaktionsafgang](predict-transactional-churn.md). 

1. Gå til **Intelligens** > **Find**, og vælg at bruge **Model for kundeafgang**.

1. Vælg indstillingen **Transaktionsrelateret**, og vælg **Start her**.

1. Navngiv modellen **Forudsigelse af afgang af OOB eCommerce-transaktion** og outputobjektets **OOBeCommerceChurnPrediction**.

1. Definer to betingelser for afgangsmodellen:

   * **Forudsigelsesvindue**: **mindst 60** dage. Brug denne indstilling til at definere, hvor langt ud i fremtiden du vil forudsige kundeafgang.

   * **Definition af afgang**: **mindst 60** dage. Varigheden uden køb, hvorefter en kunde anses for at være tabt.

     :::image type="content" source="media/model-levers.PNG" alt-text="Vælg den model, der udnytter et forudsigelsesvindue og definition af afgang.":::

1. Vælg **Købshistorik (påkrævet)**, og vælg **Tilføj data** til købshistorik.

1. Tilføj **eCommercePurchases: eCommerce**-objektet, og tilknyt felterne fra eCommerce til de tilsvarende felter, der kræves af modellen.

1. Deltag i objektet **eCommercePurchases: eCommerce** med **eCommerceContacts: eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Forbind eCommerce-objekter.":::

1. Vælg **Næste** for at angive modelplanen.

   Modellen skal trænes regelmæssigt for at lære nye mønstre, når der er nye data, der indtages. I dette eksempel skal du vælge **Månedlig**.

1. Vælg **Gem og Kør**, når du har gennemgået alle detaljer.

## <a name="task-4---review-model-results-and-explanations"></a>Opgave 4 - Gennemse modelresultater og forklaringer

Lad modellen fuldføre med at få oplæring og resultaterne af dataene. Du kan nu gennemse den forklaringer på kundeafgangsmodellen. Du kan finde flere oplysninger under [Gennemse en forudsigelsesstatus og resultater](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Opgave 5 - Opret et segment med kunder med risiko for afgang

Når produktionsmodellen køres, oprettes der et nyt objekt, som du kan se i **Data** > **Objekter**.   

Du kan oprette et nyt segment baseret på det objekt, der er oprettet af modellen.

1.  Gå til **Segmenter** Vælg **Ny**, og vælg **Opret fra** > **Intelligens**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Oprettelse af et segment ved hjælp af model-output.":::

1. Vælg **OOBeCommerceChurnPrediction**-slutpunkt, og definer segmentet: 
   - Felt: ChurnScore
   - Operatør: større end
   - Værdi: 0,6

Du har nu et segment, der opdateres dynamisk, og som identificerer kunder med høj risiko.

Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
