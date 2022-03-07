---
title: Eksportér Customer Insights-data til Dynamics 365 Sales
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269001"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Opret forbindelse til Dynamics 365 Sales (forhåndsvisning)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Brug dine kundedata til at oprette marketinglister, følge op på arbejdsprocesser og udsende kampagner med Dynamics 365 Sales.

## <a name="prerequisite"></a>Forudsætning

1. Kontaktposter skal være til stede i Dynamics 365 Sales, før du kan eksportere et segment fra Customer Insights til Sales. Læs mere om, hvordan du kontakter i [Dynamics 365 Sales ved hjælp af Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Hvis du eksporterer segmenter fra målgruppeindsigt til Sales, oprettes der ikke nye kontaktposter i Sales-forekomsterne. Kontaktpersonposterne fra Sales skal være direkte målgruppeindsigt og bruges som en datakilde. De skal også inkluderes i den samlede brugerdefinerede enhed for at knytte kunde-ID'er til kontakt-ID'er, før segmenter kan eksporteres.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]