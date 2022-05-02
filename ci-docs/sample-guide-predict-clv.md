---
title: Vejledning til eksempel på forudsigelse af kundens levetidsværdi
description: Brug denne eksempelvejledning til at afprøve forudsigelsesmodellen for kundens levetidsværdi.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 9f8d1d0f0757d8003ad3859fab75362f3988cd00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646297"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Vejledning til eksempel på forudsigelse af kundens levetidsværdi (CLV)

Denne vejledning indeholder et komplet eksempel på CLV-forudsigelse (Customer Lifetime Value) i Customer Insights ved hjælp af eksempeldata.

## <a name="scenario"></a>Scenarie

Contoso er en virksomhed, der fremstiller kaffe- og kaffemaskiner af høj kvalitet. Produkterne sælges via deres Contoso Coffee-websted. Virksomheden ønsker at forstå den værdi (omsætning), som deres kunder kan generere i de næste 12 måneder. At kende den forventede værdi af deres kunder i de næste 12 måneder vil hjælpe dem med at styre deres marketingindsats på kunder af høj værdi.

## <a name="prerequisites"></a>Forudsætninger

- Mindst [bidragydertilladelser](permissions.md) i Customer Insights.
- Vi anbefaler, at du implementerer følgende trin [i et nyt miljø](manage-environments.md).

## <a name="task-1---ingest-data"></a>Opgave 1 - Indsættelse af data

Gennemse artiklerne [om dataindtag](data-sources.md) og [import af datakilder ved hjælp af Power Query-connectorer](connect-power-query.md). I følgende oplysninger antages det, at du har generelt kendskab til indsættelse af data.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Indsættelse af kundedata fra eCommerce-platform

1. Opret en datakilde med navnet **eCommerce**, vælg importindstilling og **Text/CSV**-connectoren.

1. Angiv URL-adressen til eCommerce-kontakter [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Når du redigerer dataene, skal du vælge **Transformer** og derefter **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:
   - **DateOfBirth**: Dato
   - **CreatedOn**: Dato/Klokkeslæt/Zone

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformere fødselsdato til dato.":::

1. Omdøb datakilde fra **Forespørgsel** til **eCommerceContacts** i feltet 'Navn' i ruden til højre.

1. **Gem** datakilden.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Indsættelse af kundedata fra gennemsyn af websted

1. Opret en datakilde med navnet **Website**, vælg importindstilling og **Text/CSV**-connector.

1. Angiv URL-adressen til eCommerce-kontaktpersoner https://aka.ms/CI-ILT/WebReviews.

1. Når du redigerer dataene, skal du vælge **Transformer** og **Brug første række som overskrifter**.

1. Opdater datatypen for de kolonner, der er angivet nedenfor:

   - **ReviewRating**: Decimaltal
   - **ReviewDate**: Dato

1. Omdøb dine datakilde fra **Forespørgsel** til **Korrektur** i feltet "Navn" i øverste, højre rude.

1. **Gem** datakilden.

## <a name="task-2---data-unification"></a>Opgave 2 - Datasamling

Når vi har indtaget dataene, begynder vi nu datasamlingen for at oprette en samlet kundeprofil. Du kan finde flere oplysninger i [Datasamling](data-unification.md).

### <a name="map"></a>Tilknytning

1. Når du har indsat dataene, skal du knytte kontakterne fra eCommerce- og Loyalty-data til almindelige datatyper. Go to **Data** > **Saml** > **Tilknyt**.

1. Vælg de objekter, der repræsenterer kundeprofilen - **eCommerceContacts** og **loyCustomers**. Vælg derefter **Anvend**.

   ![samle eCommerce- og loyalty-datakilder.](media/unify-ecommerce-loyalty.png)

1. Vælg **ContactId** som primær nøgle for **eCommerceContacts** og **LoyaltyID** som primær nøgle for **loyCustomers**.

   ![Saml LoyaltyId som primær nøgle.](media/unify-loyaltyid.png)

1. Vælg **Gem**.

### <a name="match"></a>Resultat

1. Gå til fanen **Match**, og vælg **Angiv rækkefølge**.

1. På rullelisten **Primær** skal du vælge **eCommerceContacts: e-handel** som den primære kilde og inkludere alle poster.

1. På rullelisten **Entity 2** skal du vælge **loyCustomers: LoyaltyScheme** og medtage alle poster.

   ![Saml og match eCommerce og Loyalty.](media/unify-match-order.png)

1. Vælg **Tilføj regel**

1. Tilføj din første betingelse ved hjælp af FullName.

   - I forbindelse med eCommerceContacts skal du vælge **Fuldt navn** på rullelisten.
   - I forbindelse med loyCustomers skal du vælge **Fuldt navn** på rullelisten.
   - Vælg rullelisten **Normaliser**, og vælg **Type (Telefon, Navn, Adresse, ...)**.
   - Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.

1. Angiv navnet **FullName, e-mail** til den nye regel.

   - Tilføj endnu en betingelse for e-mailadressen ved at vælge **Tilføj betingelse**
   - For enhed eCommerceContacts skal du vælge **E-mail** i rullelisten.
   - For enhed loyCustomers skal du vælge **E-mail** i rullelisten.
   - Lad Normaliser være tom.
   - Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.

   ![Saml og match regel for navn og e-mail.](media/unify-match-rule.png)

1. Vælg **Udført**.

1. Vælg **Gem** og **Kør**.

### <a name="merge"></a>Fletning

1. Gå til fanen **Flet**.

1. I **ContactId** for **loyCustomers** skal du ændre visningsnavn til **ContactIdLOYALTY** for at skelne mellem dem og andre id'er, der indsættes.

   ![omdøb contactid fra loyalty-id.](media/unify-merge-contactid.png)

1. Vælg **Gem** og **Kør flettede og downstream-processer**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Opgave 3 – Konfigurer værdien for forudsigelse af kundens levetidsværdi

Med de samlede kundeprofiler på plads kan vi nu køre forudsigelsen af kundens levetidsværdi. Du kan finde flere oplysninger i [Forudsigelse om kundens levetidsværdi](predict-customer-lifetime-value.md).

1. Gå til **Intelligens**  > **Forudsigelser**, og vælg **Model for kundens levetidsværdi**.

1. Gå gennem oplysningerne i sideruden, og vælg **Introduktion**.

1. Navngiv modellen **OOB eCommerce CLV-forudsigelse** og outputobjektet **OOBeCommerceCLVPrediction**.

1. Definer modelindstillinger for CLV-modellen:
   - **Forudsigelsesperiode**: **12 måneder eller 1 år**. Denne indstilling definerer, hvor langt ind i fremtiden der kundens levetidsværdi skal forudsiges.
   - **Aktive kunder**: Angiv, hvad aktive kunder betyder for din virksomhed. Angiv den historiske tidsramme, hvor en kunde skal have haft mindst én transaktion for at blive betragtet som aktiv. Modellen ønsker kun at bruge CLV til aktive kunder. Vælg mellem at lade modellen beregne tidsperioden baseret på historiske transaktionsdata, eller angiv en bestemt tidsramme. I denne eksempelvejledning lader vi **modellen beregne købsintervallet**, som er standardindstillingen.
   - **Kunder af høj værdi**: Definer kunder af høj værdi som en fraktil af topbetalende kunder. Modellen bruger dette input til at levere resultater, der passer til din virksomhedsdefinition af kunder af høj værdi. Du kan vælge at lade modellen definere kunder med høj værdi. Den bruger en heuristisk regel, der udleder percentilen. Du kan også definere kunder af høj værdi som en percentil af fremtidige topbetalende kunder. I denne eksempelguide definerer vi manuelt kunder af høj værdi som **top 30 % af aktive betalende kunder** og vælger **Næste**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Præferencertrin i den guidede oplevelse for CLV-modellen.":::

1. I trinnet **Obligatoriske data** skal du vælge **Tilføj data** for at angive transaktionshistorikdataene.

1. Tilføj objektet **eCommercePurchases: eCommerce**, og tilknyt de attributter, der kræves af modellen:
   - Transaktions-id: eCommerce.eCommercePurchases.PurchaseId
   - Transaktionsdato: eCommerce.eCommercePurchases.PurchasedOn
   - Transaktionsbeløb: eCommerce.eCommercePurchases.TotalPrice
   - Produkt-id: eCommerce.eCommercePurchases.ProductId

1. Vælg **Næste**.

1. Konfigurer relationen mellem objektet **eCommercePurchases : eCommerce** og **eCommerceContacts : eCommerce**.

1. Trinnet **Yderligere data (valgfrit)** giver dig mulighed for at tilføje flere kundeaktivitetsdata. Disse data kan hjælpe med at få mere indsigt i kundeinteraktioner med din virksomhed, hvilket kan bidrage til CLV. Tilføjelse af vigtige kundeinteraktioner som weblogfiler, kundeservicelogfiler eller belønningsprogramhistorik kan forbedre nøjagtigheden af forudsigelser. Vælg **Tilføj data** for at medtage flere kundeaktivitetsdata.

1. Tilføj kundeaktivitetsobjektet, og knyt feltnavnene til de tilsvarende felter, der kræves af modellen:
   - Kundeaktivitetsobjekt: Anmeldelser:Websted
   - Primær nøgle: Website.Reviews.ReviewId
   - Tidsstempel: Website.Reviews.ReviewDate
   - Hændelse (aktivitetsnavn): Website.Reviews.ActivityTypeDisplay
   - Detaljer (beløb eller værdi): Website.Reviews.ReviewRating

1. Vælg **Næste**, og konfigurer aktiviteten og relationen mellem transaktionsdataene og kundedataene:  
   - Aktivitetstype: Vælg eksisterende
   - Aktivitetsnavn: Anmeldelse
   - Tilsvarende navn: Website.Reviews.UserId
   - Kundeobjekt: eCommerceContacts:eCommerce
   - Relation: WebsiteReviews

1. Vælg **Næste** for at angive modelplanen.

   Modellen skal træne regelmæssigt for at lære nye mønstre, når der er nye data indtaget. I dette eksempel skal du vælge **Månedlig**.

1. Vælg **Gem og Kør**, når du har gennemgået alle detaljer.

## <a name="task-4---review-model-results-and-explanations"></a>Opgave 4 - Gennemse modelresultater og forklaringer

Lad modellen fuldføre med at få oplæring og resultaterne af dataene. Dernæst kan du gennemgå CLV-modellens resultater og forklaringer. Du kan finde flere oplysninger under [Gennemse en forudsigelsesstatus og resultater](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Opgave 5 – Opret et segment af kunder af høj værdi

Når du kører modellen, oprettes der et nyt objekt, som vises i **Data** > **Objekter**. Du kan oprette en ny kundesegment baseret på det objekt, der er oprettet af modellen.

1. Gå til **Segmenter** 

1. Vælg **Ny**, og vælg **Opret fra** > **Intelligens**.

   ![Oprettelse af et segment ved hjælp af model-output.](media/segment-intelligence.png)

1. Vælg enheden **OOBeCommerceCLVPrediction**, og definer segmentet:
  - Felt: CLVScore
  - Operatør: større end
  - Værdi: 1500

1. Vælg **Gennemse** og **Gem** segmentet.

Du har nu et segment, der identificerer kunder, der forventes at generere mere end $1500 i omsætning inden for de næste 12 måneder. Dette segment opdateres dynamisk, hvis der indtages flere data.

Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).
