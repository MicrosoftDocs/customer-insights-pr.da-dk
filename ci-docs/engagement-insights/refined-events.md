---
title: Opret og rediger forfinede hændelser
description: Sådan kan du oprette og redigere forfinede hændelser.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034767"
---
# <a name="create-and-modify-refined-events"></a>Opret og rediger forfinede hændelser

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


En hændelse er data, der repræsenterer brugerfunktionsmåden, f.eks. aktivitet på et websted.

- En *basis*-hændelse registrerer, hvornår en bruger får vist en side (få vist en hændelse) eller kommunikerer med indhold (handlingshændelse).
- En *forfinet* hændelse, der kan bruges til arrangementet, er en virtuel visning af en basishændelse. Du kan definere hændelser, der kan hjælpe, ved at fjerne og tilføje egenskaber eller ved at filtrere hændelser baseret på egenskabsværdier.

Brug hændelseshændelser til at reducere omfanget af en basishændelse i forbindelse med [eksport](export-events.md) eller til at fjerne egenskaber, der ikke er nødvendige for at holde sig tilbage.

## <a name="create-refined-events"></a>Opret raffinerede hændelser

Der er tre måder, du kan oprette en hændelse ud fra en basisbegivenhed på. 

1. Gå til **Data**> **Hændelser**, og vælg en af følgende indstillinger:
    - Vælg **Nye hændelser**, og vælg derefter **Opret forfinede hændelser**.
    - Vælg en basishændelse for at åbne en detaljeret visning, og vælg **Opret forfinede hændelser** i den øverste menu.
    - Vælg **Flere [...]** for at åbne genvejsmenuen til en basishændelse. Vælg derefter **Opret forfinede hændelser**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Indstillinger for oprettelse af forfinede hændelser.":::

1. Angiv følgende oplysninger i dialogboksen **Opret forfinede hændelser**:

- Vælg en hændelse på rullelisten **Basishændelser**, hvis du opretter en ny hændelse.
- Angiv et navn i feltet **Forfinede hændelser, vist navn**.
- Du kan også opdatere det foreslåede **faktiske navn** uden at bruge mellemrum.

3. Vælg **Opret** for at anvende indstillingerne.

1. Vælg **Tilføj og fjern egenskaber** i den detaljerede visning af den forfinede hændelse for at åbne ruden **Rediger egenskaber**. 

1. Brug afkrydsningsfelterne til at markere de egenskaber, du vil have vist, og dem, du vil skjule. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Redigere egenskaber for forfinede hændelser.":::

1. Vælg **Bekræft** for at anvende det valgte.

1. Vælg **Gem** for at gemme konfigurationen.

## <a name="edit-refined-events"></a>Redigere forfinede hændelser

Du kan ændre navnet på og egenskaberne for en hændelse, der lige er hændelse.

### <a name="edit-event-name"></a>Redigere hændelsesnavn

1. Gå til **Data** > **Hændelser**. 
1. Vælg **Flere [...]** for en hændelse, og vælg **Rediger navn**.
1. Opdater hændelsesnavnet, og vælg **Omdøb**.

### <a name="edit-selected-properties"></a>Redigere valgte egenskaber

1. Gå til **Data** > **Hændelser**, og vælg forfinede hændelser for at åbne den detaljerede visning.
1. Vælg **Tilføj og fjern egenskaber**. 
1. Redigere markeringen i afkrydsningsfelterne.
1. Vælg **Bekræft**, og **Gem** for at anvende ændringerne.

Du kan finde oplysninger om eksport af hændelser under [Eksport af hændelser](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
