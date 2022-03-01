---
title: Eksportér Customer Insights-data til Dynamics 365 Sales
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643811"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Opret forbindelse til Dynamics 365 Sales (forhåndsvisning)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Brug dine kundedata til at oprette marketinglister, følge op på arbejdsprocesser og udsende kampagner med Dynamics 365 Sales.

## <a name="prerequisite"></a>Forudsætning

Kontaktpersonposter [fra Dynamics 365 Sales, der tilføres ved hjælp af Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-sales"></a>Konfigurer connectoren til Sales

1. Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.

1. Under **Dynamics 365 Sales** vælg **Konfigurer**.

1. Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.

1. Angiv din organisations URL-adresse for Sales i feltet **Serveradresse**.

1. I sektionen **Serveradministratorkonto** vælg **Log på** og vælg en Dynamics 365 Sales-konto.

1. Knyt et kunde-ID-felt til Dynamics 365-kontakt-id.

1. Vælg **Næste**.

1. Vælg en eller flere segmenter.

1. Vælg **Gem**.

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).
