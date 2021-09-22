---
title: Få vist og opret målepunkter
description: Sådan oprettes, redigeres og slettes målepunkter.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 97189168e0f5586aad8be8089a1f9e27893c2115c7e805ddaab1efc00e11b860
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034262"
---
# <a name="view-and-create-metrics"></a>Få vist og opret målepunkter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Målepunkter hjælper med at forstå dine besøgendes adfærd. De samler begivenhedsegenskaber og måler statistikker og ydeevne for dine webegenskaber.  

Antag, at du kører en markedsføringskampagne på dit websted. Du kan bruge målepunkter til at spore antallet af unikke besøgende eller brugere, der kom til dit websted under kampagnen. Analyse af målepunkter hjælper dig med bedre at forstå dit websteds målgruppe. Hvis du kombinerer målepunkter med [dimensioner](dimensions.md) i en [brugerdefineret rapport](custom-reports.md), kan du måle funktionsmåden for at forstå dine brugere. Du kan f.eks. opdele besøgende i nye og tilbagevendende kategorier for at identificere forskellene i interesse og hensigt mellem grupperne.

## <a name="view-metrics"></a>Vis målepunkter

Engagementsindsigt omfatter almindeligt anvendte sammenlægninger af hændelsesegenskaber som systemmålepunkter: 

- Besøgende
- Besøg
- Sidevisninger
- Klik

Disse systemmålepunkter er baseret på eksisterende hændelsesegenskaber i basishændelser.

1. Vælg **Data** i venstre navigationsrude. 
1. Vælg fanen **Målepunkter** for at få vist en liste over alle målepunkter i arbejdsområdet. 
   > [!NOTE]
   > Systemgenererede målepunkter er skrivebeskyttede. Du kan ikke ændre eller slette dem. Du kan kun oprette og redigere brugerdefinerede målepunkter.

## <a name="create-a-metric"></a>Opret et målepunkt

Miljø- og arbejdsområdeadministratorer kan oprette målepunkter. Hændelsesegenskaber skal sendes til arbejdsområdet, før du opretter et målepunkt. Du kan oprette målepunkter baseret på hændelsesegenskaber, der er sendt af basishændelser, eller bruge web-SDK'en til at [sende brugerdefinerede hændelsesegenskaber](advanced-SDK-implementation.md).

1. Gå til **Data** > **Målepunkter**.
1. Vælg **Nyt målepunkt**.

   :::image type="content" source="media/new-metric.png" alt-text="Føje et målepunkt til en hændelse.":::

1. Vælg datatypen **Heltal** eller **Dobbelt** for format. Heltal er et helt tal. For Dobbelt kan du vælge mellem en og tre decimaler.
1. Find den hændelsesegenskab, som målepunktet skal baseres på, i ruden **Ressourcebibliotek**.
1. Vælg **plustegnet (+)** ud for egenskaben for at bruge det i formlen. Du kan kun oprette en formel, der er baseret på én egenskab. 
1. Vælg en af følgende samlefunktioner. 

   - Sum: den aritmetiske total for alle værdier 
   - Gennemsnit: gennemsnitsværdien for alle værdier
   - Antal: det samlede antal værdier
   - Adskilt antal: det samlede antal adskilte værdier

   Når du har defineret målepunktet, vises et aktivitetseksempel af målepunktet for den sidste time.

1. Vælg **Gem**. 
1. Angiv et navn til målepunktet, og vælg derefter **Gem**.

Det kan tage op til et minut for målepunktet, før du kan bruge det til at [oprette brugerdefinerede rapporter](custom-reports.md).

## <a name="edit-a-metric"></a>Redigere et målepunkt

1. Gå til **Data** > **Målepunkter**.
1. Vælg målepunktet på listen.
1. Ændring af definitionen af målepunktet
1. Vælg **Gem**.

## <a name="change-the-name-of-a-metric"></a>Ændre navn på et målepunkt

1. Gå til **Data** > **Målepunkter**.
1. Vælg **Flere [...]** for et målepunkt, og vælg **Rediger navn**.
1. Angiv et nyt navn. 
1. Vælg **Omdøb**.

## <a name="delete-a-metric"></a>Slette et målepunkt

1. Gå til **Data** > **Målepunkter**.
1. Vælg **Flere [...]** for et målepunkt, og vælg **Slet**.

   :::image type="content" source="media/delete-metric.png" alt-text="Slette et målepunkt til en hændelse.":::

1. Bekræft sletningen ved at vælge **Slet**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
