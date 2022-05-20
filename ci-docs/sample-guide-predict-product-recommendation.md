---
title: Eksempelvejledning til forudsigelse til produktanbefaling
description: Brug denne eksempelvejledning til at afprøve den indbyggede forudsigelsesmodel til produktanbefaling.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762679"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Eksempelvejledning til forudsigelse til produktanbefaling

Vi gennemgår fra start til slut et eksempel på forudsigelse af produktanbefaling ved hjælp af de eksempeldata, der er angivet nedenfor.

## <a name="scenario"></a>Scenarie

Contoso er et firma, der fremstiller kaffe og kaffemaskiner i høj kvalitet, som de sælger via deres Contoso Coffee-websted. Deres mål er at forstå, hvilke produkter der skal anbefales til tilbagevendende kunder. Hvis du ved, hvilke kunder der er **større sandsynlighed for at købe**, kan du hjælpe dem med at spare marketingindsatsen ved at fokusere på bestemte elementer.

## <a name="prerequisites"></a>Forudsætninger

- Mindst [bidragydertilladelser](permissions.md) i Customer Insights.
- Vi anbefaler, at du implementerer følgende trin [i et nyt miljø](manage-environments.md).

## <a name="task-1---ingest-data"></a>Opgave 1 - Indsættelse af data

Gennemse artiklerne [om dataimport](data-sources.md) og [import af datakilder ved hjælp af Power Query-connectorer](connect-power-query.md). I følgende oplysninger antages det, at du har generelt kendskab til indsættelse af data.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Indsættelse af kundedata fra eCommerce-platform

1. Opret en datakilde med navnet **eCommerce**, vælg importindstilling og **Text/CSV**-connector.

1. Angiv URL-adressen til eCommerce-kontaktpersoner: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/Klokkeslæt/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformere fødselsdato til dato.":::

1. Omdøb datakilde fra **Forespørgsel** til **eCommerceContacts** i feltet 'Navn' i ruden til højre.

1. **Gem** datakilden.

### <a name="ingest-online-purchase-data"></a>Indsættelse af online købsdata

1. Tilføj et andet datasæt til samme **eCommerce**-datakilde. Vælg **Tekst/CSV**-connector igen.

1. Angiv URL-adressen til **Onlinekøb**-data [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **PurchasedOn**: Dato/Klokkeslæt
   - **TotalPrice**: Valuta

1. Omdøb datakilde fra **Forespørgsel** til **eCommercePurchases** i feltet **Navn** i sideruden.

1. **Gem** datakilden.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Indsæt kundedata fra loyalitetsskemaet

1. Opret en datakilde med navnet **LoyaltyScheme**, vælg importindstilling og **Text/CSV**-connector.

1. Angiv URL-adressen til eCommerce-kontaktpersoner [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **DateOfBirth**: Dato
   - **RewardsPoints**: Heltal
   - **CreatedOn**: Dato/Klokkeslæt

1. Omdøb datakilde fra **Forespørgsel** til **loyCustomers** i feltet **Navn** i ruden til højre.

1. **Gem** datakilden.

## <a name="task-2---data-unification"></a>Opgave 2 - Datasamling

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Opgave 3 – Konfigurere forudsigelse af produktanbefaling

Nu, hvor de samlede kundeprofiler er på plads, kan vi køre forudsigelse af produktanbefalingen.

1. Gå til **Intelligens** > **Forudsigelse** vælg **Produktanbefaling**.

1. Vælg **Introduktion**.

1. Navngiv modellen **Forudsigelse til OOB-produktanbefalingsmodel** og outputobjektet **OOBProductRecommendationModelPrediction**.

1. Definer tre betingelser for modellen:

   - **Antal produkter**: Angiv denne værdi til **5**. Denne indstilling definerer, hvor mange produkter du vil anbefale til dine kunder.

   - **Forventede gentagne køb**: Vælg **Ja** for at angive, at du vil medtage produkter i den anbefaling, som dine kunder tidligere har købt.

   - **Kig tilbage-vinduet:** Vælg mindst **365 dage**. Denne indstilling definerer, hvor langt tilbage modellen tjekker en kundens aktivitet som input til deres anbefalinger.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelindstillinger for produktanbefalingsmodellen.":::

1. Vælg **Tilføj data** i trinnet **Tilføj påkrævede data**.

1. Vælg **SalesOrderLine** som objektet til købsoversigten i ruden **Tilføj data**. På nuværende tidspunkt er det sandsynligvis ikke konfigureret endnu. Åbn linket i ruden for at oprette aktiviteten ved hjælp af følgende trin:
   1. Angiv et **Aktivitetsnavn**, og vælg *eCommercePurchases:eCommerce* som objektet **Aktivitet**. Den **primære nøgle** er *PurchaseId*.
   1. Definer og navngive relationen til objektet *eCommerceContacts:eCommerce*, og vælg **ContactId** som den fremmede nøgle.
   1. I forbindelse med en enhed af aktiviteter skal du angive **Hændelsesaktivitet** som *TotalPrice* og tidsstempel til *PurchasedOn*. Du kan angive flere felter som skitseret i [Kundeaktiviteter](activities.md).
   1. Vælg **SalesOrderLine** for *Aktivitetstype*. Tilknyt følgende aktivitetsfelter
      - Ordrelinje-id: PurchaseId
      - Ordre-id: PurchaseId
      - Ordredata: PurchasedOn
      - Produkt-id: ProductId
      - Beløb: TotalPrice
   1. Gennemse og afslut aktiviteten, inden du går tilbage til modelkonfigurationen.

1. Tilbage i trinnet **Vælg aktiviteter** skal du vælge den aktivitet, du netop har oprettet, i sektionen **Aktiviteter**. Vælg **Næste,** og attributtilknytningen er allerede udfyldt. Vælg **Gem**.

1. I denne eksempelvejledning springes **Tilføj produktoplysninger** og **Produktfiltre** over, da der ikke er angivet produktoplysninger.

1. Angiv modelplanen i trinnet **Dataopdateringer**.

   Modellen skal trænes regelmæssigt for at lære nye mønstre, når der er nye data, der indtages. I dette eksempel skal du vælge **Månedlig**.

1. Vælg **Gem og Kør**, når du har gennemgået alle detaljer. Det tager et par minutter at køre modellen første gang.

## <a name="task-4---review-model-results-and-explanations"></a>Opgave 4 - Gennemse modelresultater og forklaringer

Lad modellen fuldføre med at få oplæring og resultaterne af dataene. Du kan nu gennemgå produktanbefalinger til modelforklaringer. Du kan finde flere oplysninger under [Gennemse en forudsigelsesstatus og resultater](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Opgave 5 – Oprettelse af et segment med højt købte produkter

Når produktionsmodellen køres, oprettes der et nyt objekt, som du kan se i **Data** > **Objekter**.

Du kan oprette et nyt segment baseret på det objekt, der er oprettet af modellen.

1. Gå til **Segmenter** Vælg **Ny** og vælg **Opret fra Intelligens**.

   ![Oprettelse af et segment ved hjælp af model-output.](media/segment-intelligence.png)

1. Vælg det **OOBProductRecommendationModelPrediction**-slutpunkt, og definer segmentet:

   - Felt: Produktid
   - Værdi: Vælg de øverste tre produkt-id'er

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Opret et segment ud fra modelresultaterne.":::

Du har nu et segment, der opdateres dynamisk, og som identificerer de kunder, der muligvis er interesseret i at købe de tre mest anbefalede produkter.

Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
