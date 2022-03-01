---
title: Eksportere Customer Insights-data til Azure Synapse Analytics
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7ee57aa9e86ebf9bd1989d88750642f0b01bd4bf
ms.sourcegitcommit: f18635c29bb25d9e424a3f5825dc2696278450cf
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/30/2021
ms.locfileid: "6327357"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Eksportere data til Azure Synapse Analytics (forhåndsversion)

Azure Synapse er en analysetjeneste, der accelererer tiden til at få indsigt på tværs af data warehouses og big data-systemer. Du kan indtage og bruge dine Customer Insights-data i [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Forudsætninger

Følgende forudsætninger skal være opfyldt for at konfigurere forbindelsen fra Customer Insights til Azure Synapse.

> [!NOTE]
> Sørg for at angive alle **rolletildelinger** som beskrevet.  

## <a name="prerequisites-in-customer-insights"></a>Forudsætninger i Customer Insights

* Du har rollen som **Administrator** i målgruppeindsigt. Få mere at vide om [at angive brugertilladelser i målgruppeindsigt](permissions.md#assign-roles-and-permissions)

I Azure: 

- Et aktivt Azure-abonnement.

- Hvis du bruger en ny Azure Data Lake Storage Gen2-konto, skal *tjenesteprincipal for målgruppeindsigt* have **Bidragyder til Storage Blob-data**-tilladelser. Få mere at vide om [at oprette forbindelse til en Azure Data Lake Storage Gen2-konto med Azure-tjenesteprincipal for målgruppeindsigt](connect-service-principal.md). Data Lake Storage Gen2 **skal have** [hierarkisk navneområde](/azure/storage/blobs/data-lake-storage-namespace) aktiveret.

- I ressourcegruppen er Azure Synapse-arbejdsområdet placeret, *tjenesteprincipalen* og *brugeren til målgruppeindsigt* skal tildeles mindst **Læser-** tilladelser. Du kan finde flere oplysninger under [Tildele Azure-roller ved hjælp af Azure-portalen](/azure/role-based-access-control/role-assignments-portal).

- *Brugeren* skal have **Bidragyder til Storage Blob-data**-tilladelser til den Azure Data Lake Storage Gen2-konto, hvor dataene er placeret og sammenkædet med Azure Synapse-arbejdsområdet. Få mere at vide om at [bruge Azure-portalen til at tildele en Azure-rolle for at få adgang til BLOB- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [Bidragyder til Storage Blob-data-tilladelser](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Den *[Azure Synapse-arbejdsområdestyrede identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* skal have **Bidragyder til Storage Blob-data**-tilladelser til den Azure Data Lake Storage Gen2-konto, hvor dataene er placeret og sammenkædet med Azure Synapse-arbejdsområdet. Få mere at vide om at [bruge Azure-portalen til at tildele en Azure-rolle for at få adgang til BLOB- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [Bidragyder til Storage Blob-data-tilladelser](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- I Azure Synapse-arbejdsområdet skal *tjenesteprincipal for målgruppeindsigt* have tildelt en **Synapse-administrator**-rolle. Du kan finde flere oplysninger i [Sådan konfigurerer du adgangskontrol til dit Synapse-arbejdsområde](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Konfigurere forbindelsen og eksportere til Azure Synapse

### <a name="configure-a-connection"></a>Konfiguration af en forbindelse

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Azure Synapse Analytics**, eller vælg **Konfigurer** i feltet **Azure Synapse Analytics** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet Vist navn. Navnet og forbindelsestypen beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vælg eller søg efter det abonnement, hvor du vil bruge Customer Insights-dataene. Så snart et abonnement er valgt, kan du også vælge **Arbejdsområde**, **Lagerkonto** og **Container**.

1. Vælg **Gem** for at gemme forbindelsen.

### <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Hvis du vil oprette en ny eksport, skal du vælge **Tilføj eksport**.

1. Vælg en forbindelse i feltet **Forbindelse til eksport** i sektionen **Azure Synapse Analytics**. Hvis du ikke kan se dette sektionsnavn, er der ingen [forbindelser](connections.md) af denne type tilgængelige for dig.

1. Angiv et genkendeligt **Vist navn** til eksport og et **Databasenavn**.

1. Vælg, hvilke objekter du vil eksportere til Azure Synapse Analytics.
   > [!NOTE]
   > Datakilder, der er baseret på en [fælles datamodelmappe](connect-common-data-model.md), understøttes ikke.

2. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Opdatere en eksport

1. Gå til **Data** > **Eksport**.

1. Vælg **Rediger** på den eksport, du vil opdatere.

   - **Tilføj** eller **Fjern** objekter fra valget. Hvis objekter fjernes fra markeringen, slettes de ikke fra Synapse Analytics-databasen. Fremtidige dataopdateringer opdaterer dog ikke de fjernede objekter i den pågældende database.

   - **Hvis du ændrer databasenavnet**, oprettes der en ny Synapse Analytics-database. Databasen med det navn, der tidligere er konfigureret, modtager ingen opdateringer fremover.
