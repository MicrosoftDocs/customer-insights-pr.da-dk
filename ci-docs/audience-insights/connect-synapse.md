---
title: Indtag data fra Azure Synapse Analytics
description: Brug en database i Azure Synapse som en datakilde i Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356017"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Tilslut en Azure Synapse-datakilde (forhåndsversion)

Azure Synapse Analytics er en virksomheds analysetjeneste, der øger den tid, der skal bruges på at få indsigt på tværs af datalager og big data-systemer. Azure Synapse Analytics samler det bedste af DE SQL-teknologier, der bruges i virksomhedens lager, Spark teknologier, der bruges til big data, Data Explorer til analyse af log- og tidsserier, pipelines til dataintegration og ETL/ELT og omfattende integration med andre Azure-tjenester som f.eks. Power BI, Cosmos DB og AzureML.

Du kan finde flere oplysninger under [Oversigt over Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Forudsætninger

Følgende forudsætninger skal være opfyldt for at konfigurere forbindelsen fra Customer Insights til Azure Synapse.

> [!IMPORTANT]
> Sørg for at angive alle **rolletildelinger** som beskrevet.  

## <a name="prerequisites-in-customer-insights"></a>Forudsætninger i Customer Insights

* Du har **administrator** rolle i Customer Insights. Få mere at vide om [brugertilladelser i målgruppeindsigt](permissions.md#assign-roles-and-permissions).

I Azure: 

- Et aktivt Azure-abonnement.

- Hvis du bruger en ny Azure Data Lake Storage Gen2-konto, skal *tjenesteprincipal for målgruppeindsigt* have **Bidragyder til Storage Blob-data**-tilladelser. Få mere at vide om, hvordan du [opretter forbindelse til en Azure Data Lake Storage med en servicechef for målgruppeindsigt](connect-service-principal.md). Data Lake Storage Gen2 **skal have** [hierarkisk navneområde](/azure/storage/blobs/data-lake-storage-namespace) aktiveret.

- I ressourcegruppen er Azure Synapse-arbejdsområdet placeret, *tjenesteprincipalen* og *brugeren til målgruppeindsigt* skal tildeles mindst **Læser-** tilladelser. Du kan finde flere oplysninger under [Tildele Azure-roller ved hjælp af Azure-portalen](/azure/role-based-access-control/role-assignments-portal).

- *Brugeren* skal have **Bidragyder til Storage Blob-data**-tilladelser til den Azure Data Lake Storage Gen2-konto, hvor dataene er placeret og sammenkædet med Azure Synapse-arbejdsområdet. Få mere at vide om at [bruge Azure-portalen til at tildele en Azure-rolle for at få adgang til BLOB- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [Bidragyder til Storage Blob-data-tilladelser](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Den *[Azure Synapse-arbejdsområdestyrede identitet](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* skal have **Bidragyder til Storage Blob-data**-tilladelser til den Azure Data Lake Storage Gen2-konto, hvor dataene er placeret og sammenkædet med Azure Synapse-arbejdsområdet. Få mere at vide om at [bruge Azure-portalen til at tildele en Azure-rolle for at få adgang til BLOB- og kødata](/azure/storage/common/storage-auth-aad-rbac-portal) og [Bidragyder til Storage Blob-data-tilladelser](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- I Azure Synapse-arbejdsområdet skal *tjenesteprincipal for målgruppeindsigt* have tildelt en **Synapse-administrator**-rolle. Du kan finde flere oplysninger i [Sådan konfigurerer du adgangskontrol til dit Synapse-arbejdsområde](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Opret forbindelse til data lake-databaser i Azure Synapse Analytics

1. Gå til **Data** > **Datakilder**.

1. Vælg **Tilføj datakilde**.

1. Vælg metoden **Azure Synapse Analytics (forhåndsversion)**.

1. Angiv et **Navn** til datakilde, og vælg **Næste** for at oprette datakilden. 

1. Vælg en [tilgængelig forbindelse](connections.md) til Azure Synapse Analytics eller oprette en ny.

1. Vælg **Lake Database** fra det arbejdsområde, der er forbundet i den valgte Azure Synapse Analytics-forbindelse, og vælg **Næste**.

1. Vælg de objekter, der skal oprettes i den forbundne database. 

1. Du kan også vælge dataobjekterne for at tillade dataprofilering. 

1. Vælg **Gem** for at anvende det valgte, og start indtaget af data fra den nyoprettede datakilde, der er knyttet til databasetabellerne i Azure Synapse Analytics.
