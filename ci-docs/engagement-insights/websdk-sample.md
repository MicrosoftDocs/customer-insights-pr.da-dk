---
title: Køre et eksempel på en web-SDK
description: Få mere at vide om, hvordan du tilpasser og kører et eksempel på en web-SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606195"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Køre eksempel på web-SDK for at få Dynamics 365 Customer Insights engagementsindsigt

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Web SDK-biblioteket med engagementsindsigt er et JavaScript-bibliotek med eksempelkode, du kan bruge på dit websted.

## <a name="prerequisites"></a>Forudsætninger

- Installer [Visual Studio-kode](https://code.visualstudio.com/).
- [Installer liveserverudvidelsen](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) i Visual Studio-kode, og bliv fortrolig med, hvordan du kører Live Server.
- Du skal have et [arbejdsområde med engagementsindsigt](create-workspace.md).

## <a name="run-sample"></a>Kør eksempel

1. [Download eksempel på web-SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Pak den komprimerede fil ud `ei_websdk_sample.zip`.

1. Åbn den udpakkede mappe i Visual Studio-kode.

1. Gå til engagementsindsigtsportalen for dit arbejdsområde. Vælg **Administration** > **Arbejdsområde** og derefter **Installationsvejledning**. Følg den første indstilling, og vælg **Kopiér kode** for at kopiere JavaScript-kodestykket.

1. Indsæt det kodestykke, du lige har kopieret, i filen `ei_websdk_sample.html` under denne linje:

   - <-- INDSÆT JAVASCRIPT-KODESTYKKE FRA ENGAGMENTSINDSIGTSPORTALEN HER UNDER DENNE LINJE -->

1. Åbn filen `ei_websdk_sample.html` ved hjælp af Live Server i Visual Studio-kode ved at vælge **Go Live** på statuslinjen.

1. Når siden åbnes, skal der automatisk sendes en visningshændelse. Hvis du klikker på en af knapperne på siden, sendes der handlingshændelser. Knappen **Spor hændelser** sender også brugerdefinerede hændelser. Hvis du vælger knappen **Gå til Bing**, sendes en handlingshændelse, før du navigerer til Bing-webstedet.

1. Se på de hændelser, der flyder, når du navigerer til arbejdsområdet. Dette arbejdsområde er knyttet til den nøgle til indtagelse, der er angivet i trin 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
