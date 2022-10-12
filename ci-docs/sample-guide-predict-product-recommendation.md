---
title: Eksempelvejledning til forudsigelse til produktanbefaling
description: Brug denne eksempelvejledning til at afprøve den indbyggede forudsigelsesmodel til produktanbefaling.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610137"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Eksempelvejledning til forudsigelse til produktanbefaling

I denne vejledning gennemgår vi fra start til slut et eksempel på forudsigelse af produktanbefaling ved hjælp af eksempeldata. Vi anbefaler, at du udfører denne forudsigelse [i et nyt miljø](manage-environments.md).

## <a name="scenario"></a>Scenarie

Contoso er en virksomhed, der fremstiller kaffe- og kaffemaskiner af høj kvalitet. Produkterne sælges via deres Contoso Coffee-websted. Deres mål er at forstå, hvilke produkter der skal anbefales til tilbagevendende kunder. Hvis du ved, hvilke kunder der er **større sandsynlighed for at købe**, kan du hjælpe dem med at spare marketingindsatsen ved at fokusere på bestemte elementer.

## <a name="prerequisites"></a>Forudsætninger

- Mindst [bidragydertilladelser](permissions.md) i Customer Insights.

## <a name="task-1---ingest-data"></a>Opgave 1 - Indsættelse af data

Gennemse artiklerne [om dataindtag](data-sources.md) og [oprettelse af forbindelse til en Power Query-datakilde](connect-power-query.md). I følgende oplysninger antages det, at du har generelt kendskab til indtag af data.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Indsættelse af kundedata fra eCommerce-platform

1. Opret en Power Query-datakilde med navnet **eCommerce**, og vælg **Text/CSV**-connectoren.

1. Angiv URL-adressen til eCommerce-kontakter: https://aka.ms/ciadclasscontacts.

1. Når du redigerer dataene, skal du vælge **Transformer** og derefter **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/Klokkeslæt/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformere fødselsdato til dato.":::

1. Omdøb datakilden til **eCommerceContacts** i feltet **Navn** i ruden til højre.

1. **Gem** datakilden.

### <a name="ingest-online-purchase-data"></a>Indsættelse af online købsdata

1. Tilføj et andet datasæt til samme **eCommerce**-datakilde. Vælg **Tekst/CSV**-connector igen.

1. Angiv URL-adressen til købsdata https://aka.ms/ciadclassonline.

1. Når du redigerer dataene, skal du vælge **Transformer** og derefter **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **PurchasedOn**: Dato/Klokkeslæt
   - **TotalPrice**: Valuta

1. Omdøb datakilden til **eCommercePurchases** i feltet **Navn** i sideruden.

1. **Gem** datakilden.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Indsæt kundedata fra loyalitetsskemaet

1. Opret en datakilde med navnet **LoyaltyScheme**, og vælg **Text/CSV**-connectoren.

1. Angiv URL-adressen til loyale kunder https://aka.ms/ciadclasscustomerloyalty.

1. Når du redigerer dataene, skal du vælge **Transformer** og derefter **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **DateOfBirth**: Dato
   - **RewardsPoints**: Heltal
   - **CreatedOn**: Dato/Klokkeslæt

1. Omdøb datakilden til **loyCustomers** i feltet **Navn** i ruden til højre.

1. **Gem** datakilden.

## <a name="task-2---data-unification"></a>Opgave 2 - Datasamling

Gennemse artiklen [om datasamling](data-unification.md). I følgende oplysninger antages det, at du har generelt kendskab til datasamling.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Opgave 3 – Opret transaktionshistorikaktivitet

Gennemse artiklen [om kundeaktiviteter](activities.md). I følgende oplysninger antages det, at du har generelt kendskab til oprettelse af aktiviteter.

1. Opret en aktivitet, der kaldes **eCommercePurchases** med objektet *eCommercePurchases:eCommerce* og den primære nøgle **PurchaseId**.

1. Opret en relation mellem *eCommercePurchases:eCommerce* og *eCommerceContacts:eCommerce* med **ContactID** som den fremmede nøgle for at oprette forbindelse til de to objekter.

1. Vælg **TotalPrice** for **EventActivity** og **PurchasedOn** for **TimeStamp**.

1. Vælg **SalesOrderLine** for **Aktivitetstype**, og tilknyt aktivitetsdataene semantisk.

1. Kør aktiviteten.

## <a name="task-4---configure-product-recommendation-prediction"></a>Opgave 4 – Konfigurere forudsigelse af produktanbefaling

Nu, hvor de samlede kundeprofiler er på plads, og der er oprettet en aktivitet, kan vi køre forudsigelse af produktanbefalingen.

1. Gå til **Intelligens** > **Forudsigelser**.

1. Under fanen **Opret** skal du vælge **Brug model** i feltet **Produktanbefalinger (forhåndsversion)**.

1. Vælg **Start her**.

1. Navngiv modellen **Forudsigelse til OOB-produktanbefalingsmodel** og outputobjektet **OOBProductRecommendationModelPrediction**.

1. Vælg **Næste**.

1. Definere modelindstillinger:
   - **Antal produkter**: **5** for at definere, hvor mange produkter du vil anbefale til dine kunder.
   - **Gentaget køb forventet**: **Ja** for at inkludere tidligere købte produkter i anbefalingen.
   - **Tilbagebliksvindue:** **365 dage** for at definere, hvor langt tilbage modellen vil se, før der anbefales et produkt igen.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelindstillinger for produktanbefalingsmodellen.":::

1. Vælg **Næste**.

1. Vælg **Tilføj data** i trinnet **Tilføj købshistorik**.

1. Vælg **SalesOrderLine** og objektet eCommercePurchases, og vælg **Næste**. De påkrævede data indsættes automatisk fra aktiviteten. Vælg **Gem**, og vælg derefter **Næste**.

1. Spring trinnene **Tilføj produktoplysninger** og **Produktfiltre** over, da vi ikke har produktoplysninger.

1. Vælg **Månedligt** i trinnet **Dataopdateringer** for modeltidsplanen.

1. Vælg **Næste**.

1. Vælg **Gem og Kør**, når du har gennemgået alle detaljer.

## <a name="task-5---review-model-results-and-explanations"></a>Opgave 5 - Gennemse modelresultater og forklaringer

Lad modellen fuldføre med at få oplæring og resultaterne af dataene. Gennemse [produktanbefalingerne til modelforklaringer](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Opgave 6 – Oprettelse af et segment med højt købte produkter

Når du kører modellen, oprettes der et nyt objekt, som vises i **Data** > **Objekter**. Du kan oprette et nyt segment baseret på det objekt, der er oprettet af modellen.

1. Vælg **Opret segment** på resultatsiden.

1. Opret en regel ved hjælp af objektet **OOBProductRecommendationModelPrediction**, og definer segmentet:
   - **Felt**: ProductID
   - **Værdi**: Vælg de øverste tre produkt-id'er

1. Vælg **Gem** og **Kør** segmentet.

Du har nu et segment, der opdateres dynamisk, og som identificerer de kunder, der muligvis er interesseret i at købe de fem mest anbefalede produkter. Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).

> [!TIP]
> Du kan også oprette et segment for en forudsigelsesmodel fra siden **Segmenter** ved at vælge **Ny** og vælge **Opret fra** > **Intelligens**. Du kan finde flere oplysninger under [Oprette et nyt segment med hurtige segmenter](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
