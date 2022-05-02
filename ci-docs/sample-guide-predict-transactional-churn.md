---
title: Eksempelvejledning til transaktionsrelateret forudsigelse af afgang
description: Brug denne eksempelvejledning til at afprøve transaktionsrelateret standardafgang i en forudsigelsesmodel.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 05c221c634b8e0f582a6c6d3f4d90e971aa9707e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646362"
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

Når dataene er indsat, skal du nu starte **Tilknyt, Match, Flet**-processen for at oprette en samlet kundeprofil. Du kan finde flere oplysninger i [Datasamling](data-unification.md).

### <a name="map"></a>Tilknytning

1. Når du har indsat dataene, skal du knytte kontakterne fra eCommerce- og Loyalty-data til almindelige datatyper. Go to **Data** > **Saml** > **Tilknyt**.

1. Vælg de objekter, der repræsenterer kundeprofilen - **eCommerceContacts** og **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="samle eCommerce- og loyalty-datakilder.":::

1. Vælg **ContactId** som primær nøgle for **eCommerceContacts** og **LoyaltyID** som primær nøgle for **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Saml LoyaltyId som primær nøgle.":::

### <a name="match"></a>Resultat

1. Gå til fanen **Match**, og vælg **Angiv rækkefølge**.

1. På rullelisten **Primær** skal du vælge **eCommerceContacts: e-handel** som den primære kilde og inkludere alle poster.

1. På rullelisten **Entity 2** skal du vælge **loyCustomers: LoyaltyScheme** og medtage alle poster.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Saml og match eCommerce og Loyalty.":::

1. Vælg **Opret en ny regel**

1. Tilføj din første betingelse ved hjælp af FullName.

   * I forbindelse med eCommerceContacts skal du vælge **Fuldt navn** på rullelisten.
   * I forbindelse med loyCustomers skal du vælge **Fuldt navn** på rullelisten.
   * Vælg **Normaliser**-rullelisten, og vælg **Type (telefon, navn, adresse ...)**.
   * Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.

1. Angiv navnet **FullName, e-mail** til den nye regel.

   * Tilføj endnu en betingelse for e-mailadressen ved at vælge **Tilføj betingelse**
   * For enhed eCommerceContacts skal du vælge **E-mail** i rullelisten.
   * For enhed loyCustomers skal du vælge **E-mail** i rullelisten. 
   * Lad Normaliser være tom. 
   * Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Saml og match regel for navn og e-mail.":::

7. Vælg **Gem** og **Kør**.

### <a name="merge"></a>Fletning

1. Gå til fanen **Flet**.

1. I **ContactId** for **loyCustomers** skal du ændre visningsnavn til **ContactIdLOYALTY** for at skelne mellem dem og andre id'er, der indsættes.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="omdøb contactid fra loyalty-id.":::

1. Vælg **Gem** og **Kør** for at starte fletningsprocessen.



## <a name="task-3---configure-transaction-churn-prediction"></a>Opgave 3 - Konfiguration af transaktion af forudsigelse af afgang

Når du har samlet kundeprofiler på plads, kan vi nu køre forudsigelse af abonnementsafgang. Du kan finde flere oplysninger i artiklen om [Forudsigelse af opsigelse af abonnement](predict-subscription-churn.md). 

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
