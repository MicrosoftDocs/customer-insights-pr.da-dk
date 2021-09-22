---
title: Kør iOS SDK-eksempel
description: Eksempelprojekt, der kan lære mere om iOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036821"
---
# <a name="run-the-ios-sdk-sample"></a>Kør iOS SDK-eksempel

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dette iOS-eksempelprojekt hjælper dig med at forstå, hvordan SDK fungerer i en app. Du behøver ikke at skrive kode. Du skal blot tilføje din indtagelsesnøgle, så kan du se hændelser i arbejdsområdet med det samme.

## <a name="prerequisites"></a>Forudsætninger

- [Xcode version 9+](https://developer.apple.com/xcode/downloads/)
- [Indtagelsesnøgle](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Download iOS SDK-eksemplet

1. [Download engagementsindsigt til iOS SDK-eksempel](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Pak den komprimerede fil ud `ei-ios-sample.zip`.
1. Åbn eksempelappprojektet i Xcode.
1. I filen `EIConfig.plist` erstattes strengen `“YOUR-INGESTION-KEY”` i feltet `ingestionKey` med indtagelsesnøgle til arbejdsområdet fra engagementsindsigt under **Administration** > **Arbejdsområde** > **Installationsvejledning**.
1. Vælg **Kør** for at starte eksempelprojektet.
1. Få vist hændelserne i arbejdsområdet.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
