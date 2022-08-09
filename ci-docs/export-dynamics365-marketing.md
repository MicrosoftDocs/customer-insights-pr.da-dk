---
title: Eksport af segmenter til Dynamics 365 Marketing (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Dynamics 365 Marketing.
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
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196617"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Eksport af segmenter til Dynamics 365 Marketing (forhåndsversion)

Brug [segmenter](segments.md) til at generere kampagner, og kontakt bestemte grupper af kunder sammen med [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Hvis du bruger de nye funktioner i Dynamics 365 Marketing til organisering i realtid af kundekampagneforløb i en Dataverse-organisation, er det ikke nødvendigt at oprette en standardeksport til Dynamics 365 Marketing. Kontakter og segmenter fra Customer Insights er tilgængelige direkte i Dynamics 365 Marketing, når du har forbindelse til marketing og Customer Insights. Før du sletter eksisterende eksporter, skal du gennemgå dokumentationen for, [hvordan du opretter forbindelse mellem Customer Insights og orkestrering af Dynamics 365 Marketing-kundekampagneforløb](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Forudsætning

Kontaktposter skal være til stede i Dynamics 365 Marketing, før du kan eksportere et segment fra Customer Insights til Marketing. Læs mere om, hvordan du kontakter i [Dynamics 365 Marketing ved hjælp af Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Hvis du eksporterer segmenter fra Customer Insights til Marketing, oprettes der ikke nye kontaktposter i Marketing-forekomsterne. Kontaktpersonposterne fra Marketing skal vises i Customer Insights og bruges som en datakilde. De skal også inkluderes i den samlede brugerdefinerede enhed for at knytte kunde-ID'er til kontakt-ID'er, før segmenter kan eksporteres.

## <a name="set-up-connection-to-marketing"></a>Konfigurer forbindelsen til Marketing.

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Dynamics 365 Marketing**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv din organisationens URL-adresse for marketing i feltet **Serveradresse**.

1. I sektionen **Serveradministratorkonto** vælg **Log på** og vælg en Dynamics 365 Marketing-konto.

1. Knyt feltet Kontakt-id i objektet Kunde til Dynamics 365-kontakt-id'et.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Dynamics 365 Marketing i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Vælg feltet Kontakt-id i objektet Kunde til Dynamics 365-kontakt-id'et.

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
