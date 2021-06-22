---
title: Eksportér Customer Insights-data til SFTP-værter
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til en SFTP-lokation.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124312"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Eksportere segmenter og andre data til SFTP (forhåndsversion)

Brug dine kundedata i tredjepartsprogrammer ved at eksportere dem til en SFTP (Secure File Transfer Protocol)-lokation.

## <a name="prerequisites-for-connection"></a>Forudsætninger for forbindelse

- Tilgængeligheden af en SFTP-vært og de tilhørende legitimationsoplysninger.

## <a name="known-limitations"></a>Kendte begrænsninger

- Kørslen af en eksport afhænger af systemets ydeevne. Vi anbefaler to CPU-kerner og 1 GB hukommelse som minimal konfiguration af serveren. 
- Det kan tage 90 minutter at eksportere objekter med op til 100 millioner kundeprofiler, når du bruger den anbefalede minimale konfiguration af to CPU-kerner og 1 GB hukommelse. 

## <a name="set-up-connection-to-sftp"></a>Konfigurer forbindelse til SFTP

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **SFTP** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv et **Brugernavn**, **Adgangskode**, **Værtsnavn** og **Eksportmappe** til din SFTP-konto.

1. Vælg **Bekræft** for at teste forbindelsen.

1. Vælg, om du vil eksportere dataene **Gzippet** eller **Pakket ud** og **feltseparator** for de eksporterede filer.

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen SFTP i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Markér de objekter, f.eks. segmenter, du vil eksportere.

   > [!NOTE]
   > Hvert enkelt valgt objekt opdeles i op til fem outputfiler, når de eksporteres. 

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data via SFTP, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at eksportdestinationen overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
