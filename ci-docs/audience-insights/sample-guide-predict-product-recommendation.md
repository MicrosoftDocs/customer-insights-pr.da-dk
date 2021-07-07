---
title: Eksempelvejledning til forudsigelse til produktanbefaling
description: Brug denne eksempelvejledning til at afprøve den indbyggede forudsigelsesmodel til produktanbefaling.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306159"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Eksempelvejledning til forudsigelse til produktanbefaling (prøveversion)

Vi gennemgår fra start til slut et eksempel på forudsigelse af produktanbefaling ved hjælp af de eksempeldata, der er angivet nedenfor.

## <a name="scenario"></a>Scenarie

Contoso er en virksomhed, der producerer kaffemaskiner af høj kvalitet, som de sælger via deres Contoso Coffee-websted. Deres mål er at forstå, hvilke produkter der skal anbefales til tilbagevendende kunder. Hvis du ved, hvilke kunder der er **større sandsynlighed for at købe**, kan du hjælpe dem med at spare marketingindsatsen ved at fokusere på bestemte elementer.

## <a name="prerequisites"></a>Forudsætninger

- Mindst [bidragydertilladelser](permissions.md) i Customer Insights.
- Vi anbefaler, at du implementerer følgende trin [i et nyt miljø](manage-environments.md).

## <a name="task-1---ingest-data"></a>Opgave 1 - Indsættelse af data

Gennemgå artiklerne [om indsættelse af data](data-sources.md) og [import af datakilder ved hjælp af Power Query-connectors](connect-power-query.md) specifikt. I følgende oplysninger antages det, at du har generelt kendskab til indsættelse af data.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Indsættelse af kundedata fra eCommerce-platform

1. Opret en datakilde med navnet **eCommerce**, vælg importindstilling og **Text/CSV**-connector.

1. Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscontacts.

1. Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/Klokkeslæt/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformere fødselsdato til dato.":::

5. Omdøb datakilde fra **Forespørgsel** til **eCommerceContacts** i feltet 'Navn' i ruden til højre.

6. **Gem** datakilden.

### <a name="ingest-online-purchase-data"></a>Indsættelse af online købsdata

1. Tilføj et andet datasæt til samme **eCommerce**-datakilde. Vælg **Tekst/CSV**-connector igen.

1. Angiv URL-adressen til **onlinekøb**-data https://aka.ms/ciadclassonline.

1. Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **PurchasedOn**: Dato/Klokkeslæt
   - **TotalPrice**: Valuta

1. Omdøb datakilde fra **Forespørgsel** til **eCommercePurchases** i feltet **Navn** i sideruden.

1. **Gem** datakilden.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Indsæt kundedata fra loyalitetsskemaet

1. Opret en datakilde med navnet **LoyaltyScheme**, vælg importindstilling og **Text/CSV**-connector.

1. Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscustomerloyalty.

1. Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **DateOfBirth**: Dato
   - **RewardsPoints**: Heltal
   - **CreatedOn**: Dato/Klokkeslæt

1. Omdøb datakilde fra **Forespørgsel** til **loyCustomers** i feltet **Navn** i ruden til højre.

1. **Gem** datakilden.

## <a name="task-2---data-unification"></a>Opgave 2 - Datasamling

Når vi har indtaget dataene, begynder vi nu datasamlingen for at oprette en samlet kundeprofil. Du kan finde flere oplysninger i [Datasamling](data-unification.md).

### <a name="map"></a>Tilknytning

1. Når du har indsat dataene, skal du knytte kontakterne fra eCommerce- og Loyalty-data til almindelige datatyper. Go to **Data** > **Saml** > **Tilknyt**.

2. Vælg de objekter, der repræsenterer kundeprofilen - **eCommerceContacts** og **loyCustomers**.

   ![samle eCommerce- og loyalty-datakilder.](media/unify-ecommerce-loyalty.png)

3. Vælg **ContactId** som primær nøgle for **eCommerceContacts** og **LoyaltyID** som primær nøgle for **loyCustomers**.

   ![Saml LoyaltyId som primær nøgle.](media/unify-loyaltyid.png)

### <a name="match"></a>Resultat

1. Gå til fanen **Match**, og vælg **Angiv rækkefølge**.

2. På rullelisten **Primær** skal du vælge **eCommerceContacts: e-handel** som den primære kilde og inkludere alle poster.

3. På rullelisten **Entity 2** skal du vælge **loyCustomers: LoyaltyScheme** og medtage alle poster.

   ![Saml og match eCommerce og Loyalty.](media/unify-match-order.png)

4. Vælg **Opret en ny regel**

5. Tilføj din første betingelse ved hjælp af FullName.

   - I forbindelse med eCommerceContacts skal du vælge **Fuldt navn** på rullelisten.
   - I forbindelse med loyCustomers skal du vælge **Fuldt navn** på rullelisten.
   - Vælg **Normaliser**-rullelisten, og vælg **Type (telefon, navn, adresse ...)**.
   - Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.

6. Angiv navnet **FullName, e-mail** til den nye regel.

   - Tilføj endnu en betingelse for e-mailadressen ved at vælge **Tilføj betingelse**
   - For enhed eCommerceContacts skal du vælge **E-mail** i rullelisten.
   - For enhed loyCustomers skal du vælge **E-mail** i rullelisten.
   - Lad Normaliser være tom.
   - Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.

   ![Saml og match regel for navn og e-mail.](media/unify-match-rule.png)

7. Vælg **Gem** og **Kør**.

### <a name="merge"></a>Fletning

1. Gå til fanen **Flet**.

1. I **ContactId** for **loyCustomers** skal du ændre visningsnavn til **ContactIdLOYALTY** for at skelne mellem dem og andre id'er, der indsættes.

   ![omdøb contactid fra loyalty-id.](media/unify-merge-contactid.png)

1. Vælg **Gem** og **Kør** for at starte fletningsprocessen.

## <a name="task-3---configure-product-recommendation-prediction"></a>Opgave 3 – Konfigurere forudsigelse af produktanbefaling

Når du har samlet kundeprofiler på plads, kan vi nu køre forudsigelse af abonnementsafgang.

1. Gå til **Intelligens** > **Forudsigelse** vælg **Produktanbefaling**.

1. Vælg **Introduktion**.

1. Navngiv modellen **Forudsigelse til OOB-produktanbefalingsmodel** og outputobjektet **OOBProductRecommendationModelPrediction**.

1. Definer tre betingelser for modellen:

   - **Antal produkter**: Angiv denne værdi til **5**. Denne indstilling definerer, hvor mange produkter du vil anbefale til dine kunder.

   - **Forventede gentagne køb**: Vælg **Ja** for at angive, at du vil medtage produkter i den anbefaling, som dine kunder tidligere har købt.

   - **Kig tilbage-vinduet:** Vælg mindst **365 dage**. Denne indstilling definerer, hvor langt tilbage modellen tjekker en kundens aktivitet som input til deres anbefalinger.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelindstillinger for produktanbefalingsmodellen":::.

1. Vælg **Påkrævede data**, og vælg **Tilføj data** til købshistorik.

1. Tilføj **eCommercePurchases: eCommerce**-objektet, og tilknyt felterne fra eCommerce til de tilsvarende felter, der kræves af modellen.

1. Deltag i objektet **eCommercePurchases: eCommerce** med **eCommerceContacts: eCommerce**.

   ![Forbind eCommerce-objekter.](media/model-purchase-join.png)

1. Vælg **Næste** for at angive modelplanen.

   Modellen skal trænes regelmæssigt for at lære nye mønstre, når der er nye data, der indtages. I dette eksempel skal du vælge **Månedlig**.

1. Vælg **Gem og Kør**, når du har gennemgået alle detaljer.


## <a name="task-4---review-model-results-and-explanations"></a>Opgave 4 - Gennemse modelresultater og forklaringer

Lad modellen fuldføre med at få oplæring og resultaterne af dataene. Du kan nu gennemgå produktanbefalinger til modelforklaringer. Du kan finde flere oplysninger under [Gennemse en forudsigelsesstatus og resultater](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Opgave 5 – Oprettelse af et segment med højt købte produkter

Når produktionsmodellen køres, oprettes der et nyt objekt, som du kan se i **Data** > **Objekter**.

Du kan oprette et nyt segment baseret på det objekt, der er oprettet af modellen.

1. Gå til **Segmenter** Vælg **Ny**, og vælg **Opret fra** > **Intelligens**.

   ![Oprettelse af et segment ved hjælp af model-output.](media/segment-intelligence.png)

1. Vælg det **OOBProductRecommendationModelPrediction**-slutpunkt, og definer segmentet:

   - Felt: Produktid
   - Operator: Værdi
   - Værdi: Vælg de øverste tre produkt-id'er

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Opret et segment ud fra modelresultaterne.":::

Du har nu et segment, der opdateres dynamisk, og som identificerer de kunder, der er mere villige til at købe de tre mest anbefalede produkter 

Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
