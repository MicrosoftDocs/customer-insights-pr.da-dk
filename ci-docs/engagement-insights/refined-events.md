---
title: Opret og opdatér begivenheder
description: Sådan opretter og redigerer du hændelser.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606193"
---
# <a name="create-and-modify-events"></a>Opret og opdatér begivenheder

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En hændelse er data, der repræsenterer brugerfunktionsmåden, f.eks. aktivitet på et websted.

- En *basis*-hændelse registrerer, hvornår en bruger får vist en side (få vist en hændelse) eller kommunikerer med indhold (handlingshændelse).
- En *forfinet* hændelse, der kan bruges til arrangementet, er en virtuel visning af en basishændelse. Du kan definere hændelser, der kan hjælpe, ved at fjerne og tilføje egenskaber eller ved at filtrere hændelser baseret på egenskabsværdier.

## <a name="prerequisites"></a>Forudsætninger

For at få hændelser skal du først forbinde dine webstedsdata med engagementsindsigt med et kodestykke. Du kan finde flere oplysninger under [Installere web-SDK'en på et websted](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Opret først forbindelse til dine data.":::

## <a name="create-refined-events"></a>Opret og rediger forbedrede hændelser

Brug hændelseshændelser til at reducere omfanget af en basishændelse i forbindelse med [eksport](export-events.md) eller til at fjerne egenskaber, der ikke er nødvendige for at holde sig tilbage.

> [!NOTE]
> Når du har føjet web-SDK'en til dit websted, kan du få vist dine basishændelser og oprette forbedrede hændelser. 

Sådan får du vist basishændelser:

1. Vælg **Data** i venstre navigationsrude.

1. Vælg **Hændelser** for at se en liste over alle hændelserne i arbejdsområdet.

    :::image type="content" source="media/data-events.png" alt-text="Se hændelser.":::

Sådan opretter du en forbedret hændelse ud fra en basishændelse: 

1. Gå til **Data** > **Hændelser**, og vælg **+ Nye hændelser** øverst på skærmen.

1. Vælg **Opret forbedrede hændelser** i dialogboksen **Nye hændelser**, og vælg derefter **Næste**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Guiden Nye hændelser.":::
     
1. Angiv følgende oplysninger i dialogboksen **Nye hændelser**:

   - Vælg en hændelse på rullelisten **Basishændelser**.
   - Angiv et navn i feltet **Forfinede hændelser, vist navn**.
   - Du kan også opdatere det foreslåede **faktiske navn** uden at bruge mellemrum.

1. Vælg **Opret** for at anvende indstillingerne.

Den forbedrede hændelse vises nu på listen **Hændelser**.

### <a name="edit-event-name"></a>Redigere hændelsesnavn

Du kan ændre navnet på og egenskaberne for en basishændelse eller forbedret hændelse.

1. Gå til **Data** > **Hændelser**. 

1. Vælg **Flere [...]** for en hændelse, og vælg **Rediger navn**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Indstillinger for oprettelse af forfinede hændelser.":::

3. Opdater hændelsesnavnet, og vælg **Omdøb**.

### <a name="view-the-details-of-a-refined-event"></a>Få vist detaljerne om en forbedret hændelse:

1. Vælg basishændelsen eller den forbedrede hændelse på listen **Hændelser**. 

1. Vælg **Tilføj og fjern egenskaber** øverst på skærmen for at åbne ruden **Rediger egenskaber**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Tilføj og fjern egenskaber.":::

1. Brug afkrydsningsfelterne til at markere de egenskaber, du vil have vist, og dem, du vil skjule. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Redigere egenskaber for forfinede hændelser.":::

1. Vælg **Bekræft** for at anvende dit valg, og vælg derefter **Gem**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Redigere valgte egenskaber for en forbedret hændelse

1. Gå til **Data** > **Hændelser**, og vælg forfinede hændelser for at åbne den detaljerede visning.
1. Vælg **Tilføj og fjern egenskaber**. 
1. Redigere markeringen i afkrydsningsfelterne.
1. Vælg **Bekræft**, og **Gem** for at anvende ændringerne.

Du kan finde oplysninger om eksport af hændelser under [Eksport af hændelser](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
