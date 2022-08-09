---
title: Eksport af segmenter til Dynamics 365 Sales (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195974"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Eksport af segmenter til Dynamics 365 Sales (forhåndsversion)

Brug dine kundedata til at oprette marketinglister, følge op på arbejdsprocesser og udsende kampagner med Dynamics 365 Sales.

## <a name="prerequisites"></a>Forudsætninger

Kontaktposter skal være til stede i Dynamics 365 Sales, før du kan eksportere et segment fra Customer Insights til Sales. Læs mere om, hvordan du indtager kontakter fra [Dynamics 365 Sales ved hjælp af Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Hvis du eksporterer segmenter fra Customer Insights til Sales, oprettes der ikke nye kontaktposter i Sales-forekomsterne. Kontaktpersonposterne fra Sales skal vises i Customer Insights og bruges som en datakilde. De skal også inkluderes i den samlede brugerdefinerede enhed for at knytte kunde-ID'er til kontakt-ID'er, før segmenter kan eksporteres.

## <a name="known-limitations"></a>Kendte begrænsninger

Eksporter til Dynamics 365 Sales er begrænset til 100.000 pr. segment, som kan tage op til 3 timer at fuldføre.

## <a name="set-up-connection-to-sales"></a>Konfigurer forbindelsen til Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Dynamics 365 Sales**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv din organisations URL-adresse for Sales i feltet **Serveradresse**.

1. I sektionen **Serveradministratorkonto** vælg **Log på** og vælg en Dynamics 365 Sales-konto.

1. Knyt et kunde-ID-felt til Dynamics 365-kontakt-id.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Dynamics 365 Sales i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Vælg feltet Kontakt-id i objektet Kunde til Dynamics 365-kontakt-id'et.

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
