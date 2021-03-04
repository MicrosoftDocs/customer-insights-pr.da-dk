---
title: Eksportér Customer Insights-data til SFTP-værter
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til en SFTP-vært.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267991"
---
# <a name="connector-for-sftp-preview"></a>Connector til SFTP (prøveversion)

Brug dine kundedata i tredjepartsprogrammer ved at eksportere dem til en SFTP-vært.

## <a name="prerequisites"></a>Forudsætninger

- Tilgængeligheden af en SFTP-vært og de tilhørende legitimationsoplysninger.

## <a name="connect-to-sftp"></a>Opret forbindelse til SFTP

1. Gå til **Adminstration** > **Eksportdestinationer**.

1. Vælg **Konfigurer** under **SFTP**.

1. Giv din destination et genkendeligt navn i feltet **Vist navn**.

1. Angiv et **Brugernavn**, **Adgangskode**, **Værtsnavn** og **Eksportmappe** til din SFTP-konto.

1. Vælg **Bekræft** for at teste forbindelsen.

1. Når verifikationen er fuldført, skal du vælge, om du vil eksportere dataene **Gzipped** eller **Udpakket** , og vælge **feltseparator** for de eksporterede filer.

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Næste** for at begynde at konfigurere eksporten.

## <a name="configure-the-export"></a>konfigurere eksporten

1. Markér de objekter, f.eks. segmenter, du vil eksportere.

   > [!NOTE]
   > Hvert valgt objekt vil være på op til fem outputfiler, når de eksporteres. 

1. Vælg **Gem**.

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).

## <a name="known-limitations"></a>Kendte begrænsninger

- Kørslen af en eksport afhænger af systemets ydeevne. Vi anbefaler to CPU-kerner og 1 GB hukommelse som minimal konfiguration af serveren. 
- Det kan tage 90 minutter at eksportere objekter med op til 100 millioner kundeprofiler, når du bruger den anbefalede minimale konfiguration af to CPU-kerner og 1 GB hukommelse. 

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data via SFTP, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at eksportdestinationen overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]