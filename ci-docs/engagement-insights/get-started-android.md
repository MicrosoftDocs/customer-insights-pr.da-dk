---
title: Introduktion til Android SDK
description: Få mere at vide om, hvordan du tilpasser og kører Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a060ac60db71a7b0fb8c0d7a3b0e266004fbee6a
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494268"
---
# <a name="get-started-with-the-android-sdk"></a>Kom i gang med Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Denne vejledning guider dig gennem processen med at instrumentere din Android-app med Dynamics 365 Customer Insights engagementsindsigt stil SDK. Du kan se arrangementer på din portal om fem minutter eller før.

## <a name="configuration-options"></a>Konfigurationsindstillinger
Følgende konfigurationsindstillinger kan overføres til SDK:

- **indtagelsesnøgle**: Indtagelsesnøgle bruges til at sende hændelser til arbejdsområdet.

## <a name="prerequisites"></a>Forudsætninger

- Android Studio

- Minimum Android API-niveau: 16 (Jelly Bean)

- En indtagelsesnøgle (se nedenfor for at få instruktioner i, hvordan du henter)

## <a name="integrate-the-sdk-into-your-application"></a>Integrer SDK i din app
Begynd processen ved at vælge et arbejdsområde, vælge Android-mobilplatformen og hent Android SDK.

- Vælg arbejdsområdet ved hjælp af arbejdsområdeskifteren i venstre navigationsrude.

- Hvis du ikke har et eksisterende arbejdsområde, skal du vælge **Nyt arbejdsområde** og følge trinnene til at oprette et [nyt arbejdsområde](create-workspace.md).

- Når du har oprettet et arbejdsområde, skal du gå til **Administration** > **Arbejdsområde** og derefter vælge **Installationsvejledning**. 

## <a name="configure-the-sdk"></a>Konfigurer SDK

Når du har hentet SDK, kan du arbejde med det i Android Studio for at aktivere og definere hændelser. Du kan søge på to måder:
### <a name="option-1-using-jitpack-recommended"></a>Mulighed 1: Brug af JitPack (anbefales)
1. Føj JitPack-lageret til `build.gradle`-roden:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Tilføj afhængigheden:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-using-download-link"></a>Mulighed 2: Brug af overførselslink
1. Hent [engagementsindsigt Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip), og placer filen `eiandroidsdk-debug.aar` i `libs`-mappen.

1. Åbn filen `build.gradle` på projektniveau, og tilføj følgende kodestykker.
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Tilføj tilladelse til netværk og internet i `AndroidManifest.xml`-filen, der findes under `manifests`-mappen. 
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```
    
1. Konfigurer SDK-konfigurationen med engagementsindsigt via `AndroidManifest.xml`-filen. 

## <a name="enable-auto-instrumentation"></a>Aktiver automatisk instrumentation
1. Kopiér XML-kodestykke fra **installationsvejledningen**. `Your-Ingestion-Key` bør udfyldes automatisk.

   > [!NOTE]
   > Du behøver ikke at erstatte `${applicationId}`-sektionen. Den udfyldes automatisk.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Aktivér eller deaktiver automatisk registrering af `View`-hændelser ved at indstille ovenstående `autoCapture`-felt til `true` eller `false`. `Action`-hændelser skal tilføjes manuelt i øjeblikket.

1. (Valgfrit) Andre konfigurationer omfatter angivelse slutpunkt URL-slutpunkt. De kan tilføjes under indtagelsen af nøglemetadata i `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="implement-custom-events"></a>Implementer brugerdefinerede hændelser

Når du har initialiseret SDK, kan du arbejde med hændelserne og deres egenskaber i `MainActivity`-miljøet.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Angiv egenskab for alle hændelser (valgfrit)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Følgende typer understøttes for egenskaber for konteksthændelser:
- String
- Dato
- Dobbelt
- Long
- Boolean
- UUID

### <a name="track-an-event"></a>Spor en hændelse

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Angive brugeroplysninger for hændelsen (valgfrit)

I SDK kan du definere brugeroplysninger, der kan sendes til alle hændelser. Du kan angive brugeroplysninger ved at kalde `setUser(user: User)`-API på `Analytics`-niveauet.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Dataklassen `User` indeholder følgende strengegenskaber:

- **localId**: Brugerens lokale id.
- **authId**: Det godkendte bruger-id.
- **authType**: Den godkendelsestype, der bruges til at hente godkendt bruger-id.
- **navn**: Brugerens navn.
- **e-mail**: Brugers e-mailadresse.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
