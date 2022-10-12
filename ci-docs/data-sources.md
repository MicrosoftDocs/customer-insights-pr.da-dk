---
title: Oversigt over datakilder
description: Få mere at vide om, hvordan du importerer eller indtager data fra forskellige kilder.
ms.date: 09/29/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610045"
---
# <a name="data-sources-overview"></a>Oversigt over datakilder

Dynamics 365 Customer Insights angiver forbindelser til data fra et bredt sæt kilder. Oprettelse af forbindelse til en datakilde kaldes ofte processen for *dataindtagelse*. Når du har slettet dataene, kan du [samle](data-unification.md), generere indsigt og aktivere dataene til udvikling af personlige erfaringer.

## <a name="add-or-edit-data-sources"></a>Tilføj eller rediger datakilder

Du kan vedhæfte eller importere datakilder til Customer Insights. Linkene nedenfor indeholder instruktioner i tilføjelse og redigering af datakilder.

**Vedhæft en datakilde**

Hvis du har udarbejdet data i en af Microsofts Azure-datatjenester, kan Customer Insights nemt oprette forbindelse til datakilde uden at skulle bruge dataene igen. Vælg en af følgende indstillinger:
- [Azure Data Lake Storage (csv- eller parquet-filer i mappen Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics (Lake-databaser)](connect-synapse.md)
- [Microsoft Dataverse-datasø](connect-dataverse-managed-lake.md)

**Importere og transformere**

Hvis du bruger lokale datakilder, Microsoft eller tredjepartsdata, skal du importere og transformere dataene ved hjælp af Power Query-forbindelser.
- [Power Query-connectorer](connect-power-query.md)

## <a name="review-data-sources"></a>Gennemse datakilder

Hvis dit miljø er konfigureret til at bruge Customer Insights-lager, og du bruger lokale datakilder, skal du bruge Power Platform-dataflow. Med Power Platform-dataflow kan du få vist delte datakilder og datakilder, der administreres af andre. På siden **Datakilder** vises datakilderne i tre sektioner:
- **Delt**: Datakilder, der kan administreres af alle Customer Insights-administratorer. Power Platform-dataflows, din egen lagerkonto og din vedhæftede fil til en Dataverse-administreret datasø er eksempler på delte datakilder.
- **Administreres af mig**: Power Platform-dataflow, der er oprettet og kun kan administreres af dig. Andre Customer Insights-administratorer kan kun få vist disse dataflows, men de kan ikke redigere, opdatere eller slette dem.
- **Administreret af andre**: Power Platform-dataflows, der er oprettet af andre administratorer. Du kan kun se dem. Ejeren af det dataflow, der skal kontaktes, vises for at få hjælp.
> [!NOTE]
> Alle objekter kan ses og bruges af andre brugere. Datakilder ejes af den bruger, der har oprettet dem, men de objekter, der oprettes fra datatilsigtet, kan bruges af alle brugere af Customer Insights.

Hvis der ikke bruges Power Platform-dataflows i miljøet, indeholder siden **Datakilder** kun en liste over alle datakilder. Igen sektioner at vise.

## <a name="manage-existing-data-sources"></a>Administrere eksisterende datakilder

Gå til **Data** > **Datakilder** for at få vist navnet på hver enkelt datakilde, dens status, og sidste gang dataene blev opdateret for den pågældende kilde. Du kan sortere listen over datakilder efter en hvilken som helst kolonne eller bruge søgefeltet til at søge efter de datakilder, der skal håndteres.

Vælg en datakilde for at få vist tilgængelige handlinger.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Datakilde er tilføjet.":::

- [**Rediger**](#add-or-edit-data-sources) datakilden for at ændre dets egenskaber.
- [**Opdater**](#refresh-data-sources) datakilden, så den indeholder de seneste data.
- [**Forbedre**](data-sources-enrichment.md) datakilden før samling.
- **Slet** datakilden. En datakilde kan kun slettes, hvis dataene ikke bruges i nogen behandling, f.eks. samling, indsigt, aktiveringer eller eksport.

## <a name="refresh-data-sources"></a>Opdatér datakilder

Datakilder kan opdateres automatisk i en automatisk planlægning eller opdateres manuelt efter behov. [Lokale datakilder](connect-power-query.md#add-data-from-on-premises-data-sources) opdaterer efter deres egne planer, som konfigureres under skrivning af data. Du kan finde tip til fejlfinding i [Fejlfinding af problemer med opdatering af PPDF Power Query-baserede datakilder](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

I forbindelse med tilknyttede datakilder forbruger dataindtag de nyeste data, der er tilgængelige fra datakilde.

Gå til **Administration** > **system** > [**Plan**](schedule-refresh.md) for at konfigurere systemplanlagte opdateringer af de opdaterede datakilder.

Opdater en datakilde efter behov:

1. Gå til **Data** > **Datakilder**.

1. Vælg den datakilde, du vil opdatere, og vælg **Opdater**. Datakilden er nu udløst for at få en manuel opdatering. Hvis du opdaterer en datakilde, opdateres både objektskemaet og dataene for alle de objekter, der er angivet i datakilden.

1. Vælg status for at åbne ruden **Statusdetaljer** og få vist status for opgaverne. Hvis du vil annullere jobbet, skal du vælge **Annuller job** nederst i ruden.

## <a name="corrupt-data-sources"></a>Beskadigede datakilder

Data, der indtages, kan have beskadigede poster, som kan forårsage, at dataindtagelsesprocessen fuldføres med fejl eller advarsler.

> [!NOTE]
> Hvis dataindtagelse fuldføres med fejl, springes efterfølgende behandling (f.eks. oprettelse af en enhed eller aktivitet), der udnytter denne datakilde, over. Hvis indtagelse fuldføres med advarsler, fortsætter den efterfølgende behandling, men nogle af posterne medtages muligvis ikke.

Disse fejl kan ses i opgavedetaljerne.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Opgavedetaljer, der viser beskadigede data.":::

Beskadigede poster vises i systemoprettede objekter.

### <a name="fix-corrupt-data"></a>Reparere beskadigede data

1. Du kan få vist beskadigede data ved at gå til **Data** > **Objekter** og søge efter de beskadigede objekter i sektionen **System**. Navngivningsskemaet for beskadigede objekter: 'DataSourceName_EntityName_corrupt'.

1. Vælg et beskadiget objekt og derefter fanen **Data**.

1. Identificer de beskadigede felter i en post og årsagen.

   :::image type="content" source="media/corruption-reason.png" alt-text="Årsag til beskadigelse." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Data** > **Objekter** viser kun en del af de beskadigede poster. Hvis du vil have vist alle de beskadigede poster, skal du eksportere filerne til en objektbeholder på lagerkontoen ved hjælp af [eksportprocessen i Customer Insights](export-destinations.md). Hvis du har brugt din egen lagerkonto, kan du også kigge på Customer Insights-mappen i lagerkontoen.

1. Reparer de beskadigede data. For Azure Data Lake-datakilder kan du f.eks. [reparere dataene i Data Lake Storage eller opdatere datatyperne i manifest-/model.json-filen](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). I forbindelse med Power Query-datakilder skal du reparere dataene i kildefilen og [rette datatypen i transformeringstrinnet](connect-power-query.md#data-type-does-not-match-data) på siden **Power Query – Rediger forespørgsler**.

Efter den næste opdatering af datakilde overføres de korrigerede poster til Customer Insights og overføres til downstreamprocesser.

Datatypen er f.eks. angivet som 'dato' i kolonnen 'fødselsdag'. En kundepost har fødselsdag angivet som '01/01/1977'. Denne post markeres som beskadiget af systemet. Skift fødselsdagen i kildesystemet til '1977'. Efter en automatiseret opdatering af datakilder har feltet nu et gyldigt format, og posten fjernes fra det beskadigede objekt.

[!INCLUDE [footer-include](includes/footer-banner.md)]
