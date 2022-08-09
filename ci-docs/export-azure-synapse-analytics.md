---
title: Eksportere data til Azure Synapse Analytics (forhåndsversion)
description: Du kan lære, hvordan du kan konfigurere forbindelsen til Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196387"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Eksportere data til Azure Synapse Analytics (forhåndsversion)

Azure Synapse er en analysetjeneste, der accelererer tiden til at få indsigt på tværs af data warehouses og big data-systemer. Du kan indtage og bruge dine Customer Insights-data i [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Forudsætninger

> [!NOTE]
> Sørg for at angive alle **rolletildelinger** som beskrevet.

- I Customer Insights skal du Azure Active Directory (AD)-brugerkonto have en [Administratorrolle](permissions.md#assign-roles-and-permissions).

I Azure:

- Et aktivt Azure-abonnement.

- Hvis du bruger en ny Azure Data Lake Storage Gen2-konto, skal [servicekontoen for Customer Insights](connect-service-principal.md) have **Bidragsyder til lager Blob-data**-tilladelser. Data Lake Storage Gen2 **skal have** [hierarkisk navneområde](/azure/storage/blobs/data-lake-storage-namespace) aktiveret.

- I ressourcegruppen, hvor du finder Azure Synapse workspace, skal *servicekontoen* og *Azure AD-brugeren med administratortilladelser i Customer Insights* tildeles mindst **Læser** [tilladelser](/azure/role-based-access-control/role-assignments-portal).

- Den *Azure AD-bruger, der har administratortilladelser i Customer Insights*, skal have **Storage Blob-bidragyder**-tilladelser på Azure Data Lake Storage Gen2-kontoen, hvor dataene er placeret og knyttet til Azure Synapse workspace. Få mere at vide om at [bruge Azure-portalen til at tildele en Azure-rolle for at få adgang til BLOB- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [Bidragyder til Storage Blob-data-tilladelser](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Den *[Azure Synapse workspace-styrede identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* skal have **Bidragyder til Storage Blob-data**-tilladelser til den Azure Data Lake Storage Gen2-konto, hvor dataene er placeret og sammenkædet med Azure Synapse-arbejdsområdet. Få mere at vide om at [bruge Azure-portalen til at tildele en Azure-rolle for at få adgang til BLOB- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [Bidragyder til Storage Blob-data-tilladelser](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- I Azure Synapse workspace skal *servicekontoen for Customer Insights* have **Synapse Administrator** [rolletildelt](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Konfigurer forbindelse til Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Azure Synapse Analytics**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Navnet og forbindelsestypen beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vælg eller søg efter det abonnement, hvor du vil bruge Customer Insights-dataene. Så snart et abonnement er valgt, kan du også vælge **Arbejdsområde**, **Lagerkonto** og **Container**.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)] Hvis du vil konfigurere eksporten med en delt forbindelse, skal du som minimum have tilladelser som **Bidragyder** i Customer Insights.

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Azure Synapse Analytics i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et genkendeligt **Vist navn** til eksport og et **Databasenavn**. I eksporten oprettes der en ny [Azure Synapse lake database](/azure/synapse-analytics/database-designer/concepts-lake-database) i det arbejdsområde, der er defineret i forbindelsen.

1. Vælg, hvilke objekter du vil eksportere til Azure Synapse Analytics.
   > [!NOTE]
   > Datakilder, der er baseret på en [fælles datamodelmappe](connect-common-data-model.md), understøttes ikke.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Hvis du vil forespørge om data, der er eksporteret til Synapse Analytics, skal du have adgangstilladelsen **Læser af Blob Data-lager** til destinationslageret i eksportarbejdsområdet.

## <a name="update-an-export"></a>Opdatere en eksport

1. Gå til **Data** > **Eksport**.

1. Vælg **Rediger** på den eksport, du vil opdatere.

   - **Tilføj** eller **Fjern** objekter fra valget. Hvis objekter fjernes fra markeringen, slettes de ikke fra Synapse Analytics-databasen. Fremtidige dataopdateringer opdaterer dog ikke de fjernede objekter i den pågældende database.

   - **Hvis du ændrer databasenavnet**, oprettes der en ny Synapse Analytics-database. Databasen med det navn, der tidligere er konfigureret, modtager ingen opdateringer fremover.

[!INCLUDE [footer-include](includes/footer-banner.md)]
