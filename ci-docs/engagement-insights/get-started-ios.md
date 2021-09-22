---
title: Introduktion til iOS SDK
description: Få mere at vide om, hvordan du tilpasser og kører iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036866"
---
# <a name="get-started-with-the-ios-sdk"></a>Kom i gang med iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Denne vejledning guider dig gennem processen med at instrumentere din iOS-app med Dynamics 365 Customer Insights-engagementsindsigt til SDK. Du kan se arrangementer på din portal om fem minutter eller før.

## <a name="configuration-options"></a>Konfigurationsindstillinger

Følgende konfigurationsindstillinger kan overføres til SDK via den angivne `EIConfig.plist`-fil:

- **ingestionKey**: Indtagelsesnøgle bruges til at sende hændelser til projektet.
- **autocollectAction**: En boolesk værdi til aktivering eller deaktivering af automatisk instrumentation af handlingshændelsen.
- **autocollectView**: En boolesk værdi til aktivering eller deaktivering af automatisk instrumentation af visningshændelsen.
- **endpointUrl**: Det slutpunkts-URL, hvor hændelserne skal omdirigeres til.

## <a name="prerequisites"></a>Forudsætninger

- Xcode version 9+
- iOS version 8.2+
- En indtagelsesnøgle (se instruktionerne nedenfor for at hente)

## <a name="integrate-the-sdk-into-your-application"></a>Integrer SDK i din app

Begynd processen ved at vælge et arbejdsområde, vælge iOS-mobilplatformen og hent SDK.

- Vælg arbejdsområdet ved hjælp af arbejdsområdeskifteren i venstre navigationsrude.

- Hvis du ikke har et eksisterende arbejdsområde, skal du vælge **Nyt arbejdsområde** og følge trinnene til at oprette et [nyt arbejdsområde](create-workspace.md).

## <a name="configure-the-sdk"></a>Konfigurer SDK

Når du har hentet SDK, kan du arbejde med det i Xcode for at aktivere og definere hændelser.

1. Når du har oprettet et arbejdsområde, skal du gå til **Administration** > **Arbejdsområde** og derefter vælge **Installationsvejledning**.

1. Hent [engagementsindsigt iOS SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip), og placer filen `EIObjC.xcframework` i `Frameworks`-mappen.

1. Hvis mappen `Frameworks` ikke findes, skal du oprette én i projektmappen.

## <a name="enable-auto-instrumentation"></a>Aktiver automatisk instrumentation
 
Du kan nemt aktivere automatisk instrumentering uden kodning. Når projektet køres, spores `view`- og `action`-hændelserne automatisk ved hjælp af den konfigurerede indtagelsesnøgle. 

1. Opdater og inkluder den angivne `EIConfig.plist`-fil i mappen Projektmappe for følgende felter:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = JA
    - autocollectAction = JA

2. Føj derefter `EIConfig.plist`-filen til projektet i Xcode. 



Deaktiver automatisk instrumentering, opdater følgende felter i den angivne `EIConfig.plist`-fil i mappen Projektmappe. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementer brugerdefinerede hændelser

1. Åbn dit projekt i Xcode, og naviger til **Generelle** indstillinger. 
1. Føj `EIObjC.xcframework` til projektet under sektionen "Frameworks, Libraries og Embedded Content".

1. Importér rammeoverskriftsfilen i AppDelegate.m med følgende kodestykke:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Initialiser engagement-indsigt SDK fra appen: didFinishLaunchingWithOptions.
1. Kopiér XML-kodestykke fra **installationsvejledningen**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Spor en hændelse:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Angive brugeroplysninger for hændelsen

I SDK kan du definere brugeroplysninger, der kan sendes til alle hændelser. Du kan angive brugeroplysninger ved at kalde `setUser:(nonnull EIUser *)user`-API på SDK.

Hvis du angiver brugerdetaljer på `Analytics`-niveauet, betyder det, at alle telemetrier har disse oplysninger. Men hvis du angiver på hændelsesniveau ved at kalde `setUser:(nonnull EIUser *)user` API'en på EIEvent-objektet, er det kun den pågældende hændelse, der indeholder oplysningerne.

Dataklassen `EIUser` indeholder følgende NSString-egenskaber:

- **localId**: Brugerens lokale id.
- **authId**: Det godkendte bruger-id.
- **authType**: Den godkendelsestype, der bruges til at hente det godkendte bruger-id.
- **navn**: Brugerens navn.
- **e-mail**: Brugers e-mailadresse.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
