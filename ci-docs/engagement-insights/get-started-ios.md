---
title: Introduktion til iOS SDK
description: Få mere at vide om, hvordan du tilpasser og kører iOS SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 879a71175a2e7d44a54d25fd8efb9f12927cea5a
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977516"
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

- Når du har oprettet et arbejdsområde, skal du gå til **Administration** > **Arbejdsområde** og derefter vælge **Installationsvejledning**.

## <a name="configure-the-sdk"></a>Konfigurer SDK

Når du har hentet SDK, kan du arbejde med det i Xcode for at aktivere og definere hændelser. Du kan søge på to måder

### <a name="option-1-using-cocoapods-recommended"></a>Mulighed 1: Brug af CocoaPods (anbefales)
CocoaPods er afhængighedsbestyrer for projekter af samme kvalitet som Swift og Objective-C. Når du bruger programmet, bliver det nemmere at integrere engagementsindsigt SDK til iOS. CocoaPods giver dig også mulighed for at opgradere til den nyeste version af engagementsindsigt SDK. Her kan du se, hvordan du CocoaPods integrerer Engagementsindsigt SDK i dit Xcode-projekt. 

1. Installer CocoaPods. 

1. Opret en ny fil med navnet Podfile i projektets rodmappe, og føj følgende sætninger til den.Erstat YOUR_TARGET_PROJECT_NAME med navnet på Xcode-projektet. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Rodkonfigurationen ovenfor indeholder både fejlfindings- og udgivelsesversionerne af SDK. Vælg, hvilken af dem der er bedst til dit projekt.

1. Installer roden ved at udføre følgende kommando: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Mulighed 2: Brug af overførselslink

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
