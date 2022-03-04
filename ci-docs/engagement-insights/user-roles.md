---
title: Roller og tilladelser
description: Oversigt over tilgængelige roller og tilladelser for medlemmer af arbejdsområdet.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227532"
---
# <a name="roles-and-permissions"></a>Roller og tilladelser

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Et arbejdsområde er det sted, hvor du kan gemme og administrere hændelser og rapporter. Du kan finde flere oplysninger under [Oprette et arbejdsområde og tilføje medlemmer](create-workspace.md). 

Et arbejdsområde kan indeholde følgende roller og tilladelser:

- *Medlemsroller* er brugere, der har adgang til et arbejdsområde. Du kan tildele medlemmer til dit arbejdsområde og definere deres roller og tilladelser. 
- *Administratorroller* administrere arbejdsområder og miljøer og konfigurerer indsigt i engagement for andre brugere. 
- *Bidragyderroller* er rettet mod analytikere, der ikke behøver at konfigurere engagementsindsigt, men som vil oprette deres egne rapporter, tragte eller segmenter.

## <a name="permissions"></a>Tilladelser
  
I følgende tabel identificeres tilladelser for de enkelte roller. 

| Tilladelse | Administrator af miljø | Administrator af arbejdsområde | Bidragyder til miljø | Arbejdsområde til bidragsyder | 
|--|--|--|--|--|
| Opret miljøer (Opretter bliver automatisk miljøadministrator) | X* | X* | X* | X* |  
| Konfigurer miljø (miljømedlemmer, slet miljø) | X |  |  |  |  
| Opret arbejdsområder | X |  |  |  |  
| Konfigurer arbejdsområder (medlemmer i arbejdsområdet, slet arbejdsområde) | X | X |  |  |  
| Konfiguration af hændelser og forfinede hændelser | X | X | |  |  
| Få vist hændelser i arbejdsområdet og forfinede hændelser | X | X | |  |  
| Få vist arbejdsområderessourcer (rapporter, segmenter og metrikværdier)| X | X | X | X |  
| Opret brugerdefinerede rapporter og tragte | X | X | X | X |  
| Oprette basismålepunkter og -mål| X | X |  |  |  
| Oprette segmenter| X | X | X | X |  

*Det er kun muligt at oprette prøveversionsmiljøer i forhåndsversion. 

## <a name="add-members"></a>Tilføj medlemmer

Du kan tilføje og fjerne medlemmer fra arbejdsområder og miljøer. Du kan finde flere oplysninger i [Miljøer og arbejdsområder](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
