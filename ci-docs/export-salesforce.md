---
title: Eksportere data til Salesforce Marketing Cloud (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197031"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Eksportere data til Salesforce Marketing Cloud (forhåndsversion)

Brug dine kundedata i Salesforce Marketing Cloud ved at eksportere dem via en SFTP-lokation (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Forudsætninger

- En [SFTP-vært for Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) og tilhørende administratorlegitimationsoplysninger.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Konfigurere forbindelsen til Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Salesforce Marketing Cloud**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv et **Brugernavn**, **Adgangskode**, **Værtsnavn** og **Eksportmappe** til din SFTP-konto.

1. Vælg **Bekræft** for at teste forbindelsen.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen SFTP i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Vælg, om du vil eksportere dataene **Gzippet** eller **Pakket ud** og **feltseparator** for de eksporterede filer.

1. Markér de objekter, f.eks. segmenter, du vil eksportere.

   > [!NOTE]
   > Hvert enkelt valgt objekt opdeles i op til maks. fem outputfiler, når de eksporteres.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importér Customer Insights-data fra SFTP-lokation til Salesforce Marketing Cloud

1. Opret [dataudvidelser i Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) for at importere datafilen Customer Insights fra SFTP-lokationen.

2. [Importér dataene fra SFTP-lokationen](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) til Salesforce Marketing Cloud-dataudvidelsen.

3. Konfigurer automatiseringen til at importere dataene til dataudvidelserne. Få mere at vide om [automatiseringer af file drop og planlagte automatiseringer](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Definer en [automatisering af file drop](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) eller en [planlagt automatisering](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Her er et eksempel på [en automatisering med SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
