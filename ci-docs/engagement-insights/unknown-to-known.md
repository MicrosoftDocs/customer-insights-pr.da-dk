---
title: Genkend webhændelser fra tidligere godkendte besøgende med ukendt til kendt
description: Den ukendte til kendte funktion giver dig mulighed for at knytte begivenheder på et websted til besøgende, der tidligere er godkendt.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: 75ce776fd5be1c426508ae6f5c239c86bdd3ec39
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230673"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Genkend webhændelser fra tidligere godkendte besøgende

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Den **ukendte til kendte**- funktion i engagementsindsigtsfunktionen gør det muligt at knytte begivenheder på et websted til besøgende, der tidligere har godkendt. Hvis funktionen er deaktiveret, identificeres besøgende, der blev godkendt under et tidligere besøg og derefter til venstre, ikke, hvis de ikke godkendes igen, når de kommer tilbage. 

En person besøgte f.eks. et websted i sidste uge, loggede ind på deres brugerkonto på webstedet og gennemså produktkataloget. Personen vender tilbage den følgende uge for at gennemse flere produkter uden at logge ind på deres konto. Ejeren af webstedet, der bruger den **ukendte til kendte**-funktion, ville vide, at den samme person var vendt tilbage, og hvad de havde gjort på webstedet. Dette giver mulighed for mere præcis rapportering og analyse af webstedsaktiviteter.

## <a name="enable-unknown-to-known"></a>Aktivere ukendt til kendt

Du skal have være [arbejdsområdeadministrator](user-roles.md) for at aktivere denne funktion. 

1. Gå til **Administration** > **arbejdsområde** i engagementsindsigt. 
2. Vælg fanen **Indstillinger**.
3. Angiv til/fra-knappen til **Aktiveret** i sektionen **Ukendt til kendt**.

![Aktivere ukendt til kendt](media/U2Ktoggle.png "Aktivere ukendt til kendt")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Føje JavaScript-kode til webstedets sporingskodestykke

Et websted kan hente **bruger-authId** med følgende JavaScript-eksempel ved hjælp af [engagementsindsigtswebstedet SDK](advanced-SDK-implementation.md). Hvis funktionen **ukendt til kendt** skal fungere, skal du hente authId *og* aktivere userMapping:True i dit JavaScript-kodestykke som i eksemplet nedenfor.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
