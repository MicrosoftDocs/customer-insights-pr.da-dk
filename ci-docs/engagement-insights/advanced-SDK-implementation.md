---
title: Avancerede web-SDK-scenarier
description: Der skal overvejes avancerede scenarier, når du bruger SDK til at instrumentere dit websted.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036321"
---
# <a name="advanced-web-sdk-instrumentation"></a>Avanceret web-SDK-instrumentation

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

I denne artikel gennemgås avancerede scenarier, du skal overveje, når du [udstyrer dit websted](instrument-website.md) med en Dynamics 365 Customer Insights engagementsindsigt med SDK.

## <a name="setting-user-details-for-your-event"></a>Angivelse af brugeroplysninger for begivenheden

I SDK kan du definere brugeroplysninger, der kan sendes til alle hændelser. Du kan angive brugeroplysningerne i en egenskab, der kaldes `user` (de forventede data for denne egenskab er objektet `IUser`), i stil med `src`, `name` og `cfg` i kodestykke-konfigurationen.

Objektet `IUser` indeholder følgende strengegenskaber:

- **localId**: Brugerens lokale id.
- **authId**: Det godkendte bruger-id.
- **authType**: Den godkendelsestype, der bruges til at hente det godkendte bruger-id.
- **navn**: Brugerens navn.
- **e-mail**: Brugers e-mailadresse.
    
I følgende eksempel vises en kode, kodestykke der sender brugeroplysninger. Hvor du kan se Funktioner angivet af *, skal du erstatte dem med implementeringen for at kalde disse værdier:  

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
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Du kan også angive brugeroplysninger ved at kalde `setUser(user: IUser)` API'en i SDK'en. Telemetri, der sendes efter kald af `setUser API`, indeholder brugeroplysningerne.

## <a name="adding-custom-properties-for-each-event"></a>Tilføjelse af brugerdefinerede egenskaber for hver hændelse

I SDK kan du definere brugerdefinerede egenskaber, der kan sendes til alle hændelser. Du kan angive de brugerdefinerede egenskaber som et objekt, der indeholder nøgleværdipar (værdien kan være af typen `string | number | boolean`). Objektet kan tilføjes i en egenskab, der kaldes `props`, i stil med `src`, `name` og `cfg` i kodestykkekonfiguration. 

I følgende eksempel vises en kode, kodestykke der sender brugerdefinerede egenskaber.

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
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Du kan også angive brugerdefinerede egenskaber enkeltvis ved at kalde `setProperty(name: string, value: string | number | boolean)` API i SDK'en.

## <a name="sending-custom-events"></a>Sende brugerdefinerede hændelser

Du kan bruge SDK til at sende brugerdefinerede hændelser. Du skal angive et navn for den hændelse og de egenskaber, der skal sendes sammen med hændelsen.

I følgende eksempel vises en kode, kodestykke der sporer brugerdefineret hændelse. "NAVN" er værdien i nøglen `name` i kodestykkekonfiguration. Det er også variabelnavnet i det vinduesobjekt, hvor SDK'en indlæses.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]