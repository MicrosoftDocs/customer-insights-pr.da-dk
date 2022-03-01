---
title: Køre et eksempel på en web-SDK
description: Få mere at vide om, hvordan du tilpasser og kører et eksempel på en web-SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036596"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Køre eksempel på web-SDK for at få Dynamics 365 Customer Insights engagementsindsigt

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Web SDK-biblioteket med engagementsindsigt er et JavaScript-bibliotek med eksempelkode, du kan bruge på dit websted.

## <a name="prerequisites"></a>Forudsætninger

- Installer [Visual Studio-kode](https://code.visualstudio.com/).
- [Installer liveserverudvidelsen](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) i Visual Studio-kode, og bliv fortrolig med, hvordan du kører Live Server.
- Du skal have [adgangsnøglen](instrument-website.md).

## <a name="run-sample"></a>Kør eksempel

1. [Download eksempel på web-SDK](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Pak den komprimerede fil ud `ei_websdk_sample.zip`.

1. Åbn den udpakkede mappe i Visual Studio-kode.

1. I `ei_websdk_sample.html`-filen skal du erstatte strengen "INGESTION_KEY" med produktnøglen fra portalen med engagementsindsigt og strengen "NAME" med det globale navn, SDK'en skal instantieres i. Sørg for, at du erstatter alle forekomster.

1. Åbn filen `ei_websdk_sample.html` ved hjælp af Live Server i Visual Studio-kode ved at vælge **Go Live** på statuslinjen.

1. Når siden åbnes, skal der automatisk sendes en visningshændelse. Hvis du klikker på en af knapperne på siden, sendes der handlingshændelser. Knappen **Spor hændelser** sender også brugerdefinerede hændelser. Hvis du vælger knappen **Gå til Bing**, sendes en handlingshændelse, før du navigerer til Bing-webstedet.

1. Se på de hændelser, der flyder, når du navigerer til arbejdsområdet. Dette arbejdsområde er knyttet til den nøgle til indtagelse, der er angivet i trin 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]