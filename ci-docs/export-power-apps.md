---
title: Power Apps-connector
description: Forbind Power Apps med Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: e99d7d4f231eb2ade67f27c9e52c61af3a21b99d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646462"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps-connector (prøveversion)

Anbring samlede kundeprofiler i dine personlige apps med Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Opret forbindelse mellem Power Apps og Dynamics 365 Customer Insights

Customer Insights er en af de mange [tilgængelige kilder til data i Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Se Power Apps-dokumentationen for at få mere at vide om, hvordan du [føjer en dataforbindelse til en app](/powerapps/maker/canvas-apps/add-data-connection). Det anbefales, at du også gennemgår, [hvordan Power Apps bruger delegering til at håndtere store datasæt i lærred-apps](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Tilgængelige objekter

Når du har tilføjet Customer Insights som dataforbindelse, kan du vælge følgende objekter i Power Apps:

- **Kunde**: Hvis du vil bruge data fra en [samlet kundeprofil](customer-profiles.md).
- **UnifiedActivity**: Hvis du vil vise [aktivitetstidslinjen](activities.md) i appen.
- **ContactProfile**: Hvis du vil vise en kundes kontakter. Dette objekt er kun tilgængeligt i Customer Insights-miljøer til målgruppeindsigt for forretningskonti.

## <a name="limitations"></a>Begrænsninger

### <a name="retrievable-entities"></a>Objekter, der kan hentes

Du kan kun hente objekterne **Kunde**, **UnifiedActivity**, **Segmenter** og **ContactProfile** via Power Apps-connectoren. ContactProfile er kun tilgængelig i forekomster af Customer Insights for forretningskonti. Andre objekter vises, fordi den underliggende connector understøtter dem gennem udløsere i Power Automate.

Du kan foretage op til 100 opkald pr. 60 sekunder. Du kan kalde API-slutpunkt flere gange ved hjælp af $skip parameteren. [Få mere at vide om $skip parameter](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegering

Delegering fungerer for **Kunde**-objektet og **UnifiedActivity**-objektet. 

- Uddelegering for **Kunde**-objekt: Hvis du vil bruge et uddelegering til dette objekt, skal felterne indekseres i [Søg og filtrér](search-filter-index.md).  
- Delegering for **UnifiedActivity**: Delegering for dette objekt fungerer kun for felterne **ActivityId** og **CustomerId**.  
- Delegering for **ContactProfile**: Delegering for dette objekt fungerer kun for felterne **ContactId** og **CustomerId**. ContactProfile er kun tilgængelig i Customer Insights-miljøer for forretningskonti.

Du kan finde flere oplysninger om delegering i [Power Apps-funktioner og -handlinger, der kan uddelegeres](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Eksempel på gallerikontrolelement

Du kan føje kundeprofiler til et [gallerikontrolelement](/powerapps/maker/canvas-apps/add-gallery).

1. Føj et **galleri**-kontrolelement til en app, du opretter.

    > [!div class="mx-imgBorder"]
    > ![Tilføje et gallerielement.](media/connector-powerapps9.png "Tilføj et gallerielement.")

2. Vælg **Kunde** som datakilde for elementer.

    > [!div class="mx-imgBorder"]
    > ![Vælge en datakilde.](media/choose-datasource-powerapps.png "Vælg en datakilde.")

3. Du kan ændre datapanelet til højre for at vælge, hvilket felt for kundeobjektet, der skal vises i galleriet.

4. Hvis du vil have vist et felt fra den valgte kunde i galleriet, skal du udfylde **Tekst**-egenskaben for et navn ved hjælp af **{Name_of_the_gallery}.Selected.{property_name}**  
    - Eksempel: _Gallery1.Selected.address1_city_

5. Hvis du vil have vist den samlede tidslinje for en kunde, skal du tilføje et gallerielement og tilføje egenskaben **Elementer** ved hjælp af **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Eksempel: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
