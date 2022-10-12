---
title: Eksempelvejledning til transaktionsrelateret forudsigelse af afgang
description: Brug denne eksempelvejledning til at afprøve transaktionsrelateret standardafgang i en forudsigelsesmodel.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609677"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Eksempelvejledning til transaktionsrelateret forudsigelse af afgang

Denne vejledning vil gennemgå et eksempel på forudsigelse af transaktionsrelateret afgang ved hjælp af eksempeldata. Vi anbefaler, at du udfører denne forudsigelse [i et nyt miljø](manage-environments.md).

## <a name="scenario"></a>Scenarie

Contoso er en virksomhed, der fremstiller kaffe- og kaffemaskiner af høj kvalitet. Produkterne sælges via deres Contoso Coffee-websted. Deres mål er at vide, hvilke kunder der jævnligt køber deres produkter, men som holder op med at være aktive kunder i de næste 60 dage. Det kan være en god hjælp at vide, hvilke af deres kunder der evt. **afgår**, ved at spare marketingkræfter og fokusere på at holde på dem.

## <a name="prerequisites"></a>Forudsætninger

- Mindst [Bidragyder-tilladelser](permissions.md).

## <a name="task-1---ingest-data"></a>Opgave 1 - Indsættelse af data

Gennemse artiklerne [om dataindtag](data-sources.md) og [oprettelse af forbindelse til en Power Query-datakilde](connect-power-query.md). I følgende oplysninger antages det, at du har generelt kendskab til indtag af data.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Indsættelse af kundedata fra eCommerce-platform

1. Opret en datakilde med navnet **eCommerce**, og vælg **Text/CSV**-connectoren.

1. Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscontacts.

1. Når du redigerer dataene, skal du vælge **Transformer** og derefter **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:

   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/Klokkeslæt/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Omdan DoB til dato.":::

1. Omdøb datakilden til **eCommerceContacts** i feltet **Navn** i ruden til højre

1. Gem datakilden.

### <a name="ingest-online-purchase-data"></a>Indsættelse af online købsdata

1. Tilføj et andet datasæt til samme **eCommerce**-datakilde. Vælg **Tekst/CSV**-connector igen.

1. Angiv URL-adressen til købsdata https://aka.ms/ciadclassonline.

1. Når du redigerer dataene, skal du vælge **Transformer** og derefter **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:

   - **PurchasedOn**: Dato/Klokkeslæt
   - **TotalPrice**: Valuta

1. Omdøb datakilde til **eCommercePurchases** i feltet **Navn** i ruden til højre.

1. Gem datakilden.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Indsæt kundedata fra loyalitetsskemaet

1. Opret en datakilde med navnet **LoyaltyScheme**, og vælg **Text/CSV**-connectoren.

1. Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/ciadclasscustomerloyalty.

1. Når du redigerer dataene, skal du vælge **Transformer** og derefter **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:

   - **DateOfBirth**: Dato
   - **RewardsPoints**: Heltal
   - **CreatedOn**: Dato/Klokkeslæt

1. Omdøb datakilden til **loyCustomers** i feltet **Navn** i ruden til højre.

1. Gem datakilden.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Opgave 4 - Konfiguration af transaktion af forudsigelse af afgang

Nu, hvor de samlede kundeprofiler og en aktivitet er på plads, kan vi køre forudsigelse af transaktionsafgang.

1. Gå til **Intelligens** > **Forudsigelser**.

1. Gå til fanen **Opret**, og vælg **Brug model** under **Model til kundeafgang**.

1. Vælg **Transaktion** for typen af kundeafgang og derefter **Start her**.

1. Navngiv modellen **Forudsigelse af afgang af OOB eCommerce-transaktion** og outputobjektets **OOBeCommerceChurnPrediction**.

1. Vælg **Næste**.

1. Definere modelindstillinger:

   - **Forudsigelsesvindue**: **60** dage for at definere, hvor langt ud i fremtiden du vil forudsige kundeafgang.

   - **Definition af kundeafgang**: **60** dage for at angive varigheden uden køb, hvorefter en kunde anses for at være tabt.

     :::image type="content" source="media/model-levers.PNG" alt-text="Vælg modelindstillingerne Forudsigelsesvindue og Definition af kundeafgang.":::

1. Vælg **Næste**.

1. Vælg **Købshistorik (påkrævet)**, og vælg **Tilføj data** til købshistorik.

1. Vælg **SalesOrderLine** og objektet eCommercePurchases, og vælg **Næste**. De påkrævede data indsættes automatisk fra aktiviteten. Vælg **Gem**, og vælg derefter **Næste**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Forbind eCommerce-objekter.":::

1. Spring trinnet **Flere data (valgfrit)** over.

1. Vælg **Månedligt** i trinnet **Dataopdateringer** for modeltidsplanen.

1. Vælg **Gem og Kør**, når du har gennemgået alle detaljer.

## <a name="task-5---review-model-results-and-explanations"></a>Opgave 5 - Gennemse modelresultater og forklaringer

Lad modellen fuldføre med at få oplæring og resultaterne af dataene. Gennemse forklaringerne på kundeafgangsmodellen. Du kan finde flere oplysninger under [Få vist forudsigelsesresultater](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Opgave 6 - Opret et segment med kunder med risiko for afgang

Når du kører produktionsmodellen, oprettes der et nyt objekt, som vises i **Data** > **Objekter**. Du kan oprette et nyt segment baseret på det objekt, der er oprettet af modellen.

1. Vælg **Opret segment** på resultatsiden.

1. Opret en regel ved hjælp af objektet **OOBeCommerceChurnPrediction**, og definer segmentet:
   - **Felt**: ChurnScore
   - **Operator**: større end
   - **Værdi**: 0,6

1. Vælg **Gem** og **Kør** segmentet.

Du har nu et segment, der opdateres dynamisk, og som identificerer kunder med høj risiko. Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).

> [!TIP]
> Du kan også oprette et segment for en forudsigelsesmodel fra siden **Segmenter** ved at vælge **Ny** og vælge **Opret fra** > **Intelligens**. Du kan finde flere oplysninger under [Oprette et nyt segment med hurtige segmenter](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
