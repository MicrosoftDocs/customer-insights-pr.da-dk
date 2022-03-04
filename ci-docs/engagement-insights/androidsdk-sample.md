---
title: Android SDK-eksempel
description: Eksempelprojekt, der kan lære mere om Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229911"
---
# <a name="run-the-android-sdk-sample"></a>Kør Android SDK-eksempel

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dette Android-eksempelprojekt hjælper dig med at forstå, hvordan SDK fungerer i en app. Du behøver ikke at skrive kode. Du skal blot tilføje din indtagelsesnøgle, så kan du se hændelser i arbejdsområdet med det samme.

## <a name="prerequisites"></a>Forudsætninger

- [Android Studio](https://developer.android.com/studio)
- [Indtagelsesnøgle](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Download Android SDK-eksemplet

1. [Download engagementsindsigt til Android SDK-eksempel](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Pak den komprimerede fil ud `ei-android-sample.zip`.
1. Åbn den udpakkede mappe i Android Studio.
1. I filen `AndroidManifest.xml` erstattes strengen `"Your-Ingestion-Key"` med indtagelsesnøgle til arbejdsområdet fra engagementsindsigt under **Administration** > **Arbejdsområde** > **Installationsvejledning**. 

   > [!NOTE]
   > Du behøver ikke at erstatte `${applicationId}`-sektionen. Den udfyldes automatisk.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Vælg **Kør** for at starte eksempelprojektet.
1. Få vist hændelserne i arbejdsområdet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
