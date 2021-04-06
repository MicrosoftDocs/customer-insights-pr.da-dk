---
title: Eksportér Customer Insights-data til Dynamics 365 Marketing
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597596"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Opret forbindelse til Dynamics 365 Marketing (forhåndsvisning)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Brug [segmenter](segments.md) til at generere kampagner, og kontakt bestemte grupper af kunder sammen med Dynamics 365 Marketing. Du kan finde flere oplysninger under [Bruge segmenter fra Dynamics 365 Customer Insights sammen med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Forudsætning

- Kontaktposter skal være til stede i Dynamics 365 Marketing, før du kan eksportere et segment fra Customer Insights til Marketing. Læs mere om, hvordan du kontakter i [Dynamics 365 Marketing ved hjælp af Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Hvis du eksporterer målgruppeindsigt til marketing, oprettes der ikke nye kontaktposter i marketingforekomsterne. Kontaktpersonposterne fra Marketing skal være direkte målgruppeindsigt og bruges som en datakilde. De skal også inkluderes i den samlede brugerdefinerede enhed for at knytte kunde-ID'er til kontakt-ID'er, før segmenter kan eksporteres.

## <a name="configure-the-connector-for-marketing"></a>Konfigurer forbindelsen til Marketing

1. Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.

1. Under **Dynamics 365 Marketing** vælg **Konfigurer**.

1. Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.

1. Angiv din organisationens URL-adresse for marketing i feltet **Serveradresse**.

1. I sektionen **Serveradministratorkonto** vælg **Log på** og vælg en Dynamics 365 Marketing-konto.

1. Knyt et kunde-ID-felt til Dynamics 365-kontakt-id.

1. Vælg **Næste**.

1. Vælg en eller flere segmenter.

1. Vælg **Gem**.

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]