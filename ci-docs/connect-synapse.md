---
title: Tilslut en Azure Synapse-datakilde (forhåndsversion)
description: Brug en database i Azure Synapse som en datakilde i Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c4ae65613a02df38a30f907dae72d413bf1a702f
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052692"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Tilslut en Azure Synapse Analytics-datakilde (forhåndsversion)

Azure Synapse Analytics er en virksomheds analysetjeneste, der øger den tid, der skal bruges på at få indsigt på tværs af datalager og big data-systemer. Azure Synapse Analytics samler det bedste af DE SQL-teknologier, der bruges i virksomhedens lager, Spark teknologier, der bruges til big data, Data Explorer til analyse af log- og tidsserier, pipelines til dataintegration og ETL/ELT og omfattende integration med andre Azure-tjenester som f.eks. Power BI, Cosmos DB og AzureML.

Du kan finde flere oplysninger under [Oversigt over Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Forudsætninger

> [!IMPORTANT]
> Sørg for at angive alle **rolletildelinger** som beskrevet.  

**I Customer Insights**:

* Du har **administrator** rolle i Customer Insights. Få mere at vide om [brugertilladelser i Customer Insights](permissions.md#assign-roles-and-permissions).

**I Azure**:

- Et aktivt Azure-abonnement.

- Hvis du bruger en ny Azure Data Lake Storage Gen2-konto, skal *servicekontoen for Customer Insights* have **Bidragsyder til lager Blob-data**-tilladelser. Få mere at vide om, hvordan du [opretter forbindelse til en Azure Data Lake Storage med en tjenestens hovednavn til Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **skal have** [hierarkisk navneområde](/azure/storage/blobs/data-lake-storage-namespace) aktiveret.

- I ressourcegruppen, hvor du finder Azure Synapse workspace, skal *tjenestens hovednavn* og *brugere med Customer Insights* skal tildeles mindst **Læse**-tilladelse. Du kan finde flere oplysninger under [Tildele Azure-roller ved hjælp af Azure-portalen](/azure/role-based-access-control/role-assignments-portal).

- *Brugeren* skal have **Bidragyder til Storage Blob-data**-tilladelser til den Azure Data Lake Storage Gen2-konto, hvor dataene er placeret og sammenkædet med Azure Synapse-arbejdsområdet. Få mere at vide om at [bruge Azure-portalen til at tildele en Azure-rolle for at få adgang til BLOB- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [Bidragyder til Storage Blob-data-tilladelser](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Den *[Azure Synapse workspace-styrede identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* skal have **Bidragyder til Storage Blob-data**-tilladelser til den Azure Data Lake Storage Gen2-konto, hvor dataene er placeret og sammenkædet med Azure Synapse-arbejdsområdet. Få mere at vide om at [bruge Azure-portalen til at tildele en Azure-rolle for at få adgang til BLOB- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [Bidragyder til Storage Blob-data-tilladelser](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- I Azure Synapse workspace skal *servicekontoen for Customer Insights* bruge **Synapse-administrator**-tildelt rolle. Du kan finde flere oplysninger i [Sådan konfigurerer du adgangskontrol til dit Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Opret forbindelse til data lake-database i Azure Synapse Analytics

1. Gå til **Data** > **Datakilder**.

1. Vælg **Tilføj datakilde**.

1. Vælg metoden **Azure Synapse Analytics (forhåndsversion)**.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialogboks til oprettelse af forbindelse til Synapse Analytics-data":::
  
1. Angiv et **navn** til datakilden og en valgfri **beskrivelse**.

1. Vælg en [tilgængelig forbindelse](connections.md) til Azure Synapse Analytics eller oprette en ny.

1. Vælg en **Database** fra det arbejdsområde, der er forbundet i den valgte Azure Synapse Analytics-forbindelse, og vælg **Næste**. I øjeblikket understøtter vi kun databasetypen *Lake database*.

1. Vælg de objekter, der skal oprettes i den forbundne database og vælg **Næste**.

1. Du kan også vælge dataobjekterne for at tillade dataprofilering.

1. Vælg **Gem** for at anvende det valgte, og start indtaget af data fra den nyoprettede datakilde, der er knyttet til databasetabellerne i Azure Synapse Analytics. Siden **Datakilder** åbnes, der viser de nye datakilde status for **Opdatering**.
