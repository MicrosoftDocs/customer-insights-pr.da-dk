---
title: Få vist og opret målepunkter
description: Sådan oprettes, redigeres og slettes målepunkter.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 79600a14bc7e98dfd066270f19c353fd007e1341
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623715"
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
   > Systemgenererede målepunkter er skrivebeskyttede. Du kan ikke redigere eller slette dem. Du kan kun oprette og redigere brugerdefinerede målepunkter.

## <a name="create-a-metric"></a>Opret et målepunkt

Miljø- og arbejdsområdeadministratorer kan oprette målepunkter. Hændelsesegenskaber skal sendes til arbejdsområdet, før du opretter et målepunkt. Du kan oprette målepunkter baseret på hændelsesegenskaber, der er sendt af basishændelser, eller bruge web-SDK'en til at [sende brugerdefinerede hændelsesegenskaber](advanced-SDK-implementation.md).

1. Gå til **Data** > **Målepunkter**.
1. Vælg **Ny metrikværdi** for at åbne dialogboksen **Ressourcebibliotek** og dialogboksen **Ny ikke-navngivet metrikværdi**.

   :::image type="content" source="media/new-metric.png" alt-text="Føje et målepunkt til en hændelse.":::

1. Vælg rullelisten **Formater** i dialogboksen **Ny ikke-navngivet metrikværdi**, og vælg **Heltal** eller **Dobbelt** som datatype. Heltal er et helt tal. Du kan vælge en og tre decimaler for Dobbelt.

   :::image type="content" source="media/create-new-metric.png" alt-text="Opret en ny metrikværdi.":::
   
5. Find den hændelsesegenskab, som metrikværdien skal baseres på, i ruden **Ressourcebibliotek**.
6. Vælg **plustegnet (+)** ud for egenskaben for at bruge det i formlen. Du kan kun oprette en formel, der er baseret på én egenskab. 
7. Vælg en af følgende samlefunktioner. 

   - Sum: den aritmetiske total for alle værdier 
   - Gennemsnit: gennemsnitsværdien for alle værdier
   - Antal: det samlede antal værdier
   - Adskilt antal: det samlede antal adskilte værdier

   Når du har defineret målepunktet, vises et aktivitetseksempel af målepunktet for den sidste time.

1. Vælg **Gem**. 
1. Angiv et navn til målepunktet, og vælg derefter **Gem**.

Det kan tage op til et minut for målepunktet, før du kan bruge det til at [oprette brugerdefinerede rapporter](custom-reports.md).

## <a name="edit-a-metric"></a>Redigere et målepunkt

Du kan kun redigere brugerdefinerede metrikværdier.

1. Gå til **Data** > **Målepunkter**.
1. Vælg målepunktet på listen.
1. Ændring af definitionen af målepunktet
1. Vælg **Gem**.

## <a name="change-the-name-of-a-metric"></a>Ændre navn på et målepunkt

Du kan kun ændre navnet på brugerdefinerede metrikværdier.

1. Gå til **Data** > **Målepunkter**.
1. Vælg **Flere [...]** for et målepunkt, og vælg **Rediger navn**.
1. Angiv et nyt navn. 
1. Vælg **Omdøb**.

## <a name="delete-a-metric"></a>Slette et målepunkt

Du kan kun slette brugerdefinerede metrikværdier.

1. Gå til **Data** > **Målepunkter**.
1. Vælg **Flere [...]** for et målepunkt, og vælg **Slet**.

   :::image type="content" source="media/delete-metric.png" alt-text="Slette et målepunkt til en hændelse.":::

1. Bekræft sletningen ved at vælge **Slet**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
