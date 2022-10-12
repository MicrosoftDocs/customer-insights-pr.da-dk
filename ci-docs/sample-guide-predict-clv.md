---
title: Vejledning til eksempel på forudsigelse af kundens levetidsværdi (CLV)
description: Brug denne eksempelvejledning til at afprøve forudsigelsesmodellen for kundens levetidsværdi.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609631"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Vejledning til eksempel på forudsigelse af kundens levetidsværdi (CLV)

Denne vejledning indeholder et komplet eksempel på CLV-forudsigelse (Customer Lifetime Value) i Customer Insights ved hjælp af eksempeldata. Vi anbefaler, at du udfører denne forudsigelse [i et nyt miljø](manage-environments.md).

## <a name="scenario"></a>Scenarie

Contoso er en virksomhed, der fremstiller kaffe- og kaffemaskiner af høj kvalitet. Produkterne sælges via deres Contoso Coffee-websted. Virksomheden ønsker at forstå den værdi (omsætning), som deres kunder kan generere i de næste 12 måneder. At kende den forventede værdi af deres kunder i de næste 12 måneder vil hjælpe dem med at styre deres marketingindsats på kunder af høj værdi.

## <a name="prerequisites"></a>Forudsætninger

- Mindst [Bidragyder-tilladelser](permissions.md).

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

1. **Gem** datakilden.

### <a name="ingest-online-purchase-data"></a>Indsættelse af online købsdata

1. Tilføj et andet datasæt til samme **eCommerce**-datakilde. Vælg **Tekst/CSV**-connector igen.

1. Angiv URL-adressen til **onlinekøb**-data https://aka.ms/ciadclassonline.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Indsættelse af kundedata fra gennemsyn af websted

1. Opret en datakilde med navnet **Websted**, og vælg **Text/CSV**-connectoren.

1. Angiv URL-adressen til webstedsgennemsyn https://aka.ms/CI-ILT/WebReviews.

1. Når du redigerer dataene, skal du vælge **Transformer** og derefter **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **ReviewRating**: Decimaltal
   - **ReviewDate**: Dato

1. Omdøb din datakilde til **Gennemsyn** i feltet **Navn** i ruden til højre.

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

1. Tilføj endnu en aktivitet, og knyt feltnavnene til de tilsvarende felter:
   - **Objektet Aktivitet**: Anmeldelser:Websted
   - **Primær nøgle**: ReviewId
   - **Tidsstempel**: ReviewDate
   - **Hændelsesaktivitet**: ActivityTypeDisplay
   - **Flere detaljer**: ReviewRating
   - **Aktivitetstype**: Review

1. Kør aktiviteten.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Opgave 4 – Konfigurer værdien for forudsigelse af kundens levetidsværdi

Nu, hvor vi har samlet kundeprofilerne og oprettet en aktivitet, kan vi køre forudsigelsen af kundens levetidsværdi (CLV). Du kan finde flere oplysninger i [Forudsigelse om kundens levetidsværdi](predict-customer-lifetime-value.md).

1. Gå til **Intelligens** > **Forudsigelser**.

1. Gå til fanen **Opret**, og vælg **Brug model** i feltet **Kundens levetidsværdi**.

1. Vælg **Start her**.

1. Navngiv modellen **OOB eCommerce CLV-forudsigelse** og outputobjektet **OOBeCommerceCLVPrediction**.

1. Definere modelindstillinger:
   - **Forudsigelsesperiode**: **12 måneder eller 1 år** for at definere, hvor langt i fremtiden CLV skal forudsiges.
   - **Aktive kunder**: **Lad model beregne købsinterval**, som er den tidsramme, hvor en kunde skal have haft mindst én transaktion for at blive fundet aktiv.
   - **Kunder af høj værdi**: Definer manuelt kunder af høj værdi som **top 30 % af aktive kunder**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Præferencertrin i den guidede oplevelse for CLV-modellen.":::

1. Vælg **Næste**.

1. I trinnet **Obligatoriske data** skal du vælge **Tilføj data** for at angive transaktionshistorikdataene.

    :::image type="content" source="media/clv-model-required.png" alt-text="Tilføj nødvendige datatrin i den guidede oplevelse for CLV-modellen.":::

1. Vælg **SalesOrderLine** og objektet eCommercePurchases, og vælg **Næste**. De påkrævede data indsættes automatisk fra aktiviteten. Vælg **Gem**, og vælg derefter **Næste**.

1. Trinnet **Yderligere data (valgfrit)** giver dig mulighed for at tilføje flere kundeaktivitetsdata for at få større indsigt i kundeinteraktioner. I dette eksempel skal du vælge **Tilføj data** og tilføje webgennemgangsaktiviteten.

1. Vælg **Næste**.

1. Vælg **Månedligt** i trinnet **Dataopdateringer** for modeltidsplanen.

1. Vælg **Næste**.

1. Vælg **Gem og Kør**, når du har gennemgået alle detaljer.

## <a name="task-5---review-model-results-and-explanations"></a>Opgave 5 - Gennemse modelresultater og forklaringer

Lad modellen fuldføre med at få oplæring og resultaterne af dataene. Gennemse [CLV-modelresultaterne og forklaringerne](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Opgave 6 – Opret et segment af kunder af høj værdi

Når du kører modellen, oprettes der et nyt objekt, som vises i **Data** > **Objekter**. Du kan oprette en ny kundesegment baseret på det objekt, der er oprettet af modellen.

1. Vælg **Opret segment** på resultatsiden.

1. Opret en regel ved hjælp af objektet **OOBeCommerceCLVPrediction**, og definer segmentet:
   - **Felt**: CLVScore
   - **Operator**: større end
   - **Værdi**: 1500

1. Vælg **Gem** og **Kør** segmentet.

Du har nu et segment, der identificerer kunder, der forventes at generere mere end $1500 i omsætning inden for de næste 12 måneder. Dette segment opdateres dynamisk, hvis der indtages flere data. Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).

> [!TIP]
> Du kan også oprette et segment for en forudsigelsesmodel fra siden **Segmenter** ved at vælge **Ny** og vælge **Opret fra** > **Intelligens**. Du kan finde flere oplysninger under [Oprette et nyt segment med hurtige segmenter](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
