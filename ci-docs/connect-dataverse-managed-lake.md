---
title: Oprette forbindelse til data i en Microsoft Dataverse-administreret data lake
description: Importere data fra en Microsoft Dataverse-administreret data lake.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 9ae0b964d8d39835715b7ddadc712e2338b855af
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080987"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Oprette forbindelse til data i en Microsoft Dataverse-administreret data lake

Microsoft Dataverse-brugerne kan hurtigt oprette forbindelse til analytiske objekter i et Microsoft Dataverse-administreret system.

> [!NOTE]
> Du skal være administrator i Dataverse-organisationen for at kunne fortsætte og få vist listen over objekter i det administrerede område.

## <a name="important-considerations"></a>Vigtige overvejelser

1. Data, der gemmes i onlinetjenester, f.eks. Azure Data Lake Storage, gemmes på en anden placering end der, hvor dataene behandles eller gemmes i Dynamics 365 Customer Insights.Ved at importere eller oprette forbindelse til data, der er gemt i onlinetjenester, accepterer du, at data kan overføres til og gemmes sammen med Dynamics 365 Customer Insights. [Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration](https://www.microsoft.com/trust-center).
2. Kun Dataverse-objekter, hvor [ændringssporing](/power-platform/admin/enable-change-tracking-control-data-synchronization) er aktiveret og synlige. Disse objekter kan eksporteres til de administrerede Dataverse-datasø og bruges i Customer Insights. Standardtabellerne har Dataverse-ændringssporing aktiveret som standard. Du skal slå sporing af ændringer til for brugerdefinerede tabeller. Hvis du vil kontrollere, om en Dataverse-tabel er aktiveret til sporing af ændringer, skal du gå til [Power Apps](https://make.powerapps.com) > **Data** > **Tabeller**. Find tabellen med interesse, og vælg den. Gå til **Indstillinger** > **Avancerede indstillinger**, og gennemse indstillingen **Spor ændringer**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Opret forbindelse til Dataverse-administreret sø

1. Gå til **Data** > **Datakilder**.

1. Vælg **Tilføj datakilde**.

1. Vælg **Microsoft Dataverse**.

1. Angiv et **navn** til datakilden og en valgfri **beskrivelse**.

1. Angiv organisationens Dataverse-**serveradresse**, og vælg **log på**.

1. Vælg de tabeller, du vil bruge som objekter i Customer Insights, på den tilgængelige liste.

   > [!NOTE]
   > Hvis nogle tabeller allerede er valgt, kan de bruges af andre Dynamics 365-programmer (f.eks. Dynamics 365 Sales Insights eller Customer Service Insights). Du kan ikke ændre markeringen. Disse tabeller er tilgængelige som objekter, når datakilde oprettes.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogboks, der viser en liste over objekter i Dataverse-miljøet.":::

1. Gem indstillingen for at starte synkroniseringen af de valgte tabeller fra Dataverse. Du kan finde den netop tilføjede forbindelse på siden **-datakilder**. Den sættes i kø til opdatering og viser objektantal som 0, indtil alle de valgte tabeller synkroniseres.

Kun én datakilde af et miljø kan bruge samme Dataverse administrerede Data Lake samtidig.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Redigere en Dataverse-administreret sø-datakilde

Du kan kun redigere objekt-valget, efter du har oprettet datakilden. Hvis du f.eks. har tilføjet yderligere objekter i Dataverse, og du også vil importere dem.
Hvis du vil oprette forbindelse til en anden Dataverse-data lake, [skal du oprette en ny datakilde](#connect-to-a-dataverse-managed-lake).

1. Gå til **Data** > **Datakilder**.

1. Ud for den datakilde, du vil opdatere, og vælg **Rediger**.

1. Vælg yderligere objekter på listen med tilgængelige objekter, og vælg **Gem**.
