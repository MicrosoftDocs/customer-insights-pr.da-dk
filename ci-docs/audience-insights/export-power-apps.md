---
title: Power Apps-connector
description: Forbind Power Apps med Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031742"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps-connector (prøveversion)

Anbring samlede kundeprofiler i dine personlige apps med Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Opret forbindelse mellem Power Apps og Dynamics 365 Customer Insights

Customer Insights er en af de mange [tilgængelige kilder til data i Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Se Power Apps-dokumentationen for at få mere at vide om, hvordan du [føjer en dataforbindelse til en app](/powerapps/maker/canvas-apps/add-data-connection). Det anbefales, at du også gennemgår, [hvordan Power Apps bruger delegering til at håndtere store datasæt i lærred-apps](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Tilgængelige objekter

Når du har tilføjet Customer Insights som dataforbindelse, kan du vælge følgende objekter i Power Apps:

- Kunde: Hvis du vil bruge data fra en [samlet kundeprofil](customer-profiles.md).
- Samlet aktivitet: Hvis du vil se [aktivitetstidslinje](activities.md) i appen.

## <a name="limitations"></a>Begrænsninger

### <a name="retrievable-entities"></a>Objekter, der kan hentes

Du kan kun hente objekterne **Kunde**, **UnifiedActivity** og **Segmenter** via Power Apps-connectoren. Andre objekter vises, fordi den underliggende connector understøtter dem gennem udløsere i Power Automate.  

### <a name="delegation"></a>Delegering

Delegering fungerer for Kunde-objektet og UnifiedActivity-objektet. 

- Uddelegering for **Kunde**-objekt: Hvis du vil bruge et uddelegering til dette objekt, skal felterne indekseres i [Søg og filtrér](search-filter-index.md).  

- Delegering for **UnifiedActivity**: Delegering for dette objekt fungerer kun for felterne **ActivityId** og **CustomerId**.  

- Du kan finde flere oplysninger om delegering under [Power Apps-funktioner og -handlinger, der kan uddelegeres](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Eksempel på gallerikontrolelement

Du kan f. eks. føje kundeprofiler til et [gallerikontrolelement](/powerapps/maker/canvas-apps/add-gallery).

1. Føj et **Galleri**-kontrolelement til en app, som du opretter.

> [!div class="mx-imgBorder"]
> ![Tilføje et gallerielement.](media/connector-powerapps9.png "Tilføje et gallerielement")

1. Vælg **Kunde** som datakilde for elementer.

    > [!div class="mx-imgBorder"]
    > ![Vælge en datakilde.](media/choose-datasource-powerapps.png "Vælge en datakilde")

1. Du kan ændre datapanelet til højre for at vælge, hvilket felt for kundeobjektet, der skal vises i galleriet.

1. Hvis du vil have vist et felt fra den valgte kunde i galleriet, skal du udfylde tekstegenskaben for et navn: **{Name_of_the_gallery}.Valgt.{property_name}**

    Eksempel: Galleri1.Valgt.adresse1_by

1. Hvis du vil have vist den samlede tidslinje for en kunde, skal du tilføje et gallerielement og tilføje egenskaben Elementer: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Eksempel: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]