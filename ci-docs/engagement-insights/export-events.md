---
title: Eksportér hændelser, der er til eksport
description: Sådan eksporteres begivenheder og basishændelser.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032378"
---
# <a name="export-events"></a>Eksportér hændelser

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En hændelse repræsenterer brugerfunktionsmåden. Den registrerer, hvornår en bruger får vist en side (få vist en hændelse) eller kommunikerer med indhold (handlingshændelse). Når du kan bestemme, hvilke egenskaber for de data du vil have vist i en rapport, kaldes denne virtuelle visning af dataene en *forfinet hændelse*. 

- Du kan eksportere arrangementer og hændelser, der udføres uden for dit arbejde, til eksternt lager. 
- Eksporten er en datastrømme til videresendelse. Du kan ikke udfylde streamingen. 
- Eksporter har faste skemaer. Hvis du føjer brugerdefinerede egenskaber til en hændelse, medtages de ikke. Du skal oprette en ny eksport.

## <a name="prerequisites"></a>Forudsætninger

Før du konfigurerer en eksport, skal du have adgang til Azure-portalen og et aktivt abonnement. Du skal bruge oplysninger om lagerkontoen under eksportprocessen. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Opret Azure Data Lake Storage Gen 2-konti

1. Log på Azure-portalen, og [opret en ny lagerkonto](/azure/storage/common/storage-account-create). 

1. Kontrollér, at du aktiverer **hierarkisk navneområde** under fanen **Avanceret**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Aktiver hierarkisk navneområde under fanen Avanceret.":::

1. Når den er installeret, skal du gå til den lagerkonto, du netop har oprettet. I navigationsrunden skal du vælge **Indstillinger** > **Adgangsnøgler**. 

1. Kopiér **Firmanavn** og **Nøgle** for at bruge dem, når du opretter en ny eksport.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Adgangsnøgler i en lagerkonto.":::

## <a name="export-events"></a>Eksportér hændelser

Du kan eksportere hændelser på to måder: 
- Gå til **Data** > **Eksporter**, og vælg **Ny eksport**.
- Gå til **Data** > **Hændelser**, vælg **Flere [...]** ud for den hændelse, du vil eksportere, og vælg **Eksportér** i rullemenuen. 

Du får en vejledning i at oprette en eksport:

1. Angiv et **Eksportnavn**.

1. Vælg de basishændelser og hændelser, der skal inkluderes i eksporten, på rullelisten **Hændelser**. 

1. Vælg en cadence under **Filstruktur** for at oprette nye filer i destinationslageret. Arrangementer eksporteres løbende, når de ankommer.

1. Vælg formatet for eksporten. Du kan vælge mellem formatet **Almindelig datamodel**, **CSV** og **JSON**. Hvis du vil bruge eksporten sammen med andre Dynamics 365-programmer, anbefales det, at du bruger formatet Common Data Model.

1. Angiv Gen 2-placeringen i **Vælg destination** i Azure Data Lake Storage.
    1. **Firmanavnet ADLS Gen 2** er navnet på den lagerkonto, du vil gemme eksporten til. 
    1. **Mappesti** definerer, hvor eksporten skal gemmes i filsystemet og mappestrukturen for lagerkontoen.
    1. **Delt nøgle** er tilgængelig fra Azure-portalen for lagerkontoen.

1. Gennemse og bekræft dine markeringer.

## <a name="view-and-manage-exports"></a>Få vist og administrere eksporter

Når du har konfigureret en eksport, skal du gå til **Data** > **Eksport** for at få den vist. Vælg **Flere [...]** for en eksisterende eksport for at redigere eller slette den.


[!INCLUDE[footer-include](../includes/footer-banner.md)]