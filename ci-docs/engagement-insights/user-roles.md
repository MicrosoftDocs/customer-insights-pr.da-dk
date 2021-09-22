---
title: Roller og tilladelser
description: Oversigt over tilgængelige roller og tilladelser for medlemmer af arbejdsområdet.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036686"
---
# <a name="roles-and-permissions"></a>Roller og tilladelser

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Et arbejdsområde er, hvor du kan gemme og administrere hændelser og rapporter. Et medlem er en bruger, der har adgang til et arbejdsområde. Du kan tildele medlemmer til dit arbejdsområde og definere deres roller og tilladelser. Administrator administrere arbejdsområder og miljøer og konfigurere indblik i engagement for andre brugere. Rollerne bidragyder rettet mod analytikere, der ikke behøver at konfigurere engagementsindsigt, men som vil oprette deres egne rapporter, tragte eller segmenter.

## <a name="permissions"></a>Tilladelser
  
I følgende diagram identificeres tilladelser for de enkelte roller. 

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
