---
title: Eksporter Customer Insights-data til Salesforce Marketing Cloud
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: aaf5c2607099bbfccf7ed75330267da8c3c5fe1b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646423"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Eksporter segmenter og andre data til Salesforce Marketing Cloud (forhåndsversion)

Brug dine kundedata i Salesforce Marketing Cloud ved at eksportere dem via en SFTP-lokation (Secure File Transfer Protocol).

## <a name="prerequisites-for-connection"></a>Forudsætninger for forbindelse

- Tilgængeligheden af en SFTP-vært og tilsvarende administratorlegitimationsoplysninger. [Sådan konfigureres SFTP-lokationer til Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Konfigurere forbindelsen til Salesforce Marketing Cloud

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Salesforce Marketing Cloud** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv et **Brugernavn**, **Adgangskode**, **Værtsnavn** og **Eksportmappe** til din SFTP-konto.

1. Vælg **Bekræft** for at teste forbindelsen.

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen SFTP i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Vælg, om du vil eksportere dataene **Gzippet** eller **Pakket ud** og **feltseparator** for de eksporterede filer.

1. Markér de objekter, f.eks. segmenter, du vil eksportere.

   > [!NOTE]
   > Hvert enkelt valgt objekt opdeles i op til fem outputfiler, når de eksporteres. 

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importér Customer Insights-data fra SFTP-lokation til Salesforce Marketing Cloud

1. Opret [dataudvidelser i Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) for at importere datafilen Customer Insights fra SFTP-lokationen.

2. [Importér dataene fra SFTP-lokationen](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) til Salesforce Marketing Cloud-dataudvidelsen. 

3. Konfigurer automatiseringen til at importere dataene til dataudvidelserne. Få mere at vide om [automatiseringer af file drop og planlagte automatiseringer](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definer en [automatisering af file drop](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) eller en [planlagt automatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Her er et eksempel på [en automatisering med SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data via SFTP, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at eksportdestinationen overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.

[!INCLUDE [footer-include](includes/footer-banner.md)]