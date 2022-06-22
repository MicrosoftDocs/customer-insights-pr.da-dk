---
title: Brug datakilder til at indsætte data
description: Få mere at vide om, hvordan du importerer data fra forskellige kilder.
ms.date: 05/31/2022
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
ms.openlocfilehash: e22977107565a0b28b74f41576a1c7ccc74f6dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011742"
---
# <a name="data-sources-overview"></a>Oversigt over datakilder

Dynamics 365 Customer Insights angiver forbindelser til data fra et bredt sæt kilder. Oprettelse af forbindelse til en datakilde kaldes ofte processen for *dataindtagelse*. Når du har slettet dataene, kan du [samle](data-unification.md), generere indsigt og aktivere dataene til udvikling af personlige erfaringer.

## <a name="add-data-sources"></a>Tilføj datakilder

Du kan vedhæfte eller importere datakilder til Customer Insights. Linkene nedenfor indeholder instruktioner i tilføjelse af datakilder.

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

Gå til **Data** > **Datakilder** for at få vist navnet på hver enkelt datakilde, dens status, og sidste gang dataene blev opdateret for den pågældende kilde. Du kan sortere listen over datakilder efter alle kolonner.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Datakilde er tilføjet.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan tage tid at indlæse data. Når opdateringen er gennemført, kan de indtagne data gennemses fra siden **Objekter**. Du kan finde flere oplysninger under [Objekter](entities.md).

## <a name="refresh-data-sources"></a>Opdatér datakilder

Datakilder kan opdateres automatisk i en automatisk planlægning eller opdateres manuelt efter behov. [Lokale datakilder](connect-power-query.md#add-data-from-on-premises-data-sources) opdaterer efter deres egne planer, som konfigureres under skrivning af data. I forbindelse med tilknyttede datakilder forbruger dataindtag de nyeste data, der er tilgængelige fra datakilde.

Gå til **Administration** > **system** > [**Plan**](system.md#schedule-tab) for at konfigurere systemplanlagte opdateringer af de opdaterede datakilder.

Benyt følgende fremgangsmåde for at opdatere en datakilde efter behov:

1. Gå til **Data** > **Datakilder**.

1. Vælg den lodrette ellipse (&vellip;) ud for den datakilde, du vil opdatere, og vælg **Opdater** i rullemenuen. Datakilden er nu udløst for at få en manuel opdatering. Hvis du opdaterer en datakilde, opdateres både objektskemaet og dataene for alle de objekter, der er angivet i datakilden.

1. Vælg **Stop opdatering**, hvis du vil annullere en eksisterende opdatering, og datakilden nulstilles til seneste opdateringsstatus.

## <a name="delete-a-data-source"></a>Slette en datakilde

En datakilde kan kun slettes, hvis dataene ikke bruges i nogen behandling, f.eks. samling, indsigt, aktiveringer eller eksport.

1. Gå til **Data** > **Datakilder**.

2. Vælg den lodrette ellipse (&vellip;) ud for den datakilde, du vil fjerne, og vælg **Slet** i rullemenuen.

3. Bekræft sletningen.


[!INCLUDE [footer-include](includes/footer-banner.md)]
