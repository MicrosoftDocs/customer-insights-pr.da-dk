---
title: Få vist og opret dimensioner
description: Sådan opretter, redigerer og sletter du dimensioner.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033990"
---
# <a name="view-and-create-dimensions"></a>Få vist og opret dimensioner

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En dimension er en attribut for en hændelse, der kan beskrive, filtrere eller gruppere data. Hvis du kører en markedsføringskampagne på dit websted, kan du bruge dimensioner til at sortere besøgende efter nye og tilbagevendende brugere.  

Engagementsindsigt omfatter køreklare dimensioner for hændelsesegenskaber. Eksempler:

- Browsernavn
- Sidenavn
- Enhedsmodel
- Operativsystem
- Land/område

## <a name="view-dimensions"></a>Vis dimensioner

Dimensioner er baseret på eksisterende hændelsesegenskaber. Når du bruger sporingskoden til engagementsindsigt, oprettes der automatisk systemdimensioner.

1. Vælg **Data** i venstre navigationsrude. 
1. Vælg **Dimensioner** for at få vist en liste over alle dimensioner i arbejdsområdet. 
   > [!NOTE]
   > Systemgenererede dimensioner er skrivebeskyttede. Du kan ikke redigere dem. Du kan kun oprette og redigere brugerdefinerede dimensioner.

## <a name="create-a-dimension"></a>Opret en dimension

Ud over systemgenererede dimensioner kan miljø- og arbejdsområdeadministratorer oprette brugerdefinerede dimensioner. Brugerdefinerede dimensioner er baseret på standardegenskaber for basishændelser, eller de kan bruge [brugerdefinerede egenskaber for en hændelse](advanced-SDK-implementation.md).

1. Vælg **Data** > **Dimensioner**.
1. Vælg **Tilføj en dimension**.

   :::image type="content" source="media/add-dimension.png" alt-text="Føje en dimension til en hændelse.":::

1. Vælg en egenskab, som dimensionen skal baseres på, i ruden **Opret en dimension**. Egenskabslisten viser alle de egenskaber i arbejdsområdet, der ikke er tildelt til en dimension.
1. Angiv et navn i feltet **Vist navn**. Valgfri: Du kan tilføje en beskrivelse.
1. Vælg **Opret** for at gemme dimensionen. Det kan tage op til et minut, før du kan bruge dimensionen i en [brugerdefineret rapport](custom-reports.md) eller et [segment](segments.md). 

## <a name="edit-a-dimension"></a>Rediger en dimension

Du kan ændre navnet på og beskrivelsen af en dimension.

1. Vælg **Data** > **Dimensioner**.
1. Markér den dimension, som du vil slette.
1. Opdater dimensionen i ruden **Rediger dimension**.
1. Vælg **Anvend** for at gemme dine ændringer.

## <a name="delete-a-dimension"></a>Slet en dimensions

Du kan kun slette brugeroprettede dimensioner, men du kan ikke fjerne systemdimensioner.

Sletning af en dimension er permanent. Rapporter og segmenter, der bruger en slettet dimension, fungerer ikke længere. 

1. Vælg **Data** > **Dimensioner**.
1. Markér den dimension, som du vil slette.
1. Vælg **Slet dimension** i ruden **Rediger dimension**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Slette en dimension til en hændelse.":::

1. Angiv **BEKRÆFT SLETNING** (med store bogstaver) for at bekræfte sletningen. 
1. Vælg **Slet**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
