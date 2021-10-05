---
title: Avancerede web-SDK-scenarier
description: Der skal overvejes avancerede scenarier, når du bruger SDK til at instrumentere dit websted.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 4c6646ecadbb604000d6c95b685cf6e420969a6d
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558694"
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

I følgende eksempel vises en kode, kodestykke der sender brugeroplysninger. De steder, hvor der vises funktioner, der indledes med stjernesymbolet *, skal du erstatte funktionen med den brugerdefinerede implementering:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
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

Du kan også angive brugeroplysninger ved at ringe til `setUser(user: IUser)`-API. Telemetri, der sendes efter kald af `setUser`-API, indeholder brugeroplysningerne.

## <a name="adding-custom-properties-for-each-event"></a>Tilføjelse af brugerdefinerede egenskaber for hver hændelse

I SDK kan du definere brugerdefinerede egenskaber, der kan sendes til alle hændelser. Du kan angive de brugerdefinerede egenskaber som et objekt, der indeholder nøgleværdipar (værdien kan være af typen `string | number | boolean`). Du kan tilføje objektet i en egenskab, der kaldes `props`, i stil med `src`, `name` og `cfg` i kodestykkekonfiguration.

I følgende eksempel vises en kode, kodestykke der sender brugerdefinerede egenskaber.

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
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

Du kan også angive brugerdefinerede egenskaber individuelt ved at ringe til `setProperty(name: string, value: string | number | boolean)`-API.

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
