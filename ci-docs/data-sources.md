---
title: Oversigt over datakilder
description: Få mere at vide om, hvordan du importerer eller indtager data fra forskellige kilder.
ms.date: 07/26/2022
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
ms.openlocfilehash: 591353bf1ba2f9ca05ddd137e1cf29dc0b0fba97
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245642"
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

Datakilder kan opdateres automatisk i en automatisk planlægning eller opdateres manuelt efter behov. [Lokale datakilder](connect-power-query.md#add-data-from-on-premises-data-sources) opdaterer efter deres egne planer, som konfigureres under skrivning af data. I forbindelse med tilknyttede datakilder forbruger dataindtag de nyeste data, der er tilgængelige fra datakilde.

Gå til **Administration** > **system** > [**Plan**](schedule-refresh.md) for at konfigurere systemplanlagte opdateringer af de opdaterede datakilder.

Opdater en datakilde efter behov:

1. Gå til **Data** > **Datakilder**.

1. Vælg den datakilde, du vil opdatere, og vælg **Opdater**. Datakilden er nu udløst for at få en manuel opdatering. Hvis du opdaterer en datakilde, opdateres både objektskemaet og dataene for alle de objekter, der er angivet i datakilden.

1. Vælg status for at åbne ruden **Statusdetaljer** og få vist status for opgaverne. Hvis du vil annullere jobbet, skal du vælge **Annuller job** nederst i ruden.

[!INCLUDE [footer-include](includes/footer-banner.md)]
