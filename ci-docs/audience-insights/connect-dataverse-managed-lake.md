---
title: Opret forbindelse til tabeller i Microsoft Dataverse
description: Importere data fra en Microsoft Dataverse-administreret data lake.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
---

# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Oprette forbindelse til data i en Microsoft Dataverse-administreret data lake



Denne artikel indeholder oplysninger om, hvordan Dataverse-brugere hurtigt kan oprette forbindelse til analytiske objekter i et Microsoft Dataverse-administreret område. 

> [!NOTE]
> Du skal være administrator i Dataverse-organisationen for at kunne fortsætte og få vist listen over objekter i det administrerede område.

## <a name="important-considerations"></a>Vigtige overvejelser

Data, der gemmes i onlinetjenester, f.eks. Azure Data Lake Storage, gemmes på en anden placering end der, hvor dataene behandles eller gemmes i Dynamics 365 Customer Insights.Ved at importere eller oprette forbindelse til data, der er gemt i onlinetjenester, accepterer du, at data kan overføres til og gemmes sammen med Dynamics 365 Customer Insights. [Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-dataverse-managed-lake"></a>Opret forbindelse til Dataverse-administreret sø

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

2. Vælg **Tilføj datakilde**.

3. Vælg **Microsoft Dataverse**, og vælg **Næste**.

4. Angiv et **Navn** til datakilden, og vælg derefter **Næste**. 

5. Angiv organisationens Dataverse-**serveradresse**, og vælg **log på**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Skærmbillede i datatrin, hvor en bruger kan angive Dataverse URL-adressen til miljøet.":::

6. Vælg de tabeller, du vil bruge som objekter, for publikum få indblik på den tilgængelige liste.    

   > [!NOTE]
   > Hvis nogle tabeller allerede er valgt, kan de bruges af andre Dynamics 365-programmer (f.eks. Dynamics 365 Sales Insights eller Customer Service Insights). Du kan ikke ændre markeringen. Disse tabeller er tilgængelige som objekter, når datakilde oprettes.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogboks, der viser en liste over objekter i Dataverse-miljøet.":::

7. Gem indstillingen for at starte synkroniseringen af de valgte tabeller fra Dataverse. Du kan finde den netop tilføjede forbindelse på siden **-datakilder**. Den sættes i kø til opdatering og viser objektantal som 0, indtil alle de valgte tabeller synkroniseres.

Kun én datakilde af et miljø kan bruge samme Dataverse administrerede Data Lake samtidig.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Redigere en Dataverse-administreret sø-datakilde

Du kan kun redigere objekt-valget, efter du har oprettet datakilden. Hvis du f.eks. har tilføjet yderligere objekter i Dataverse, og du også vil importere dem.    
Hvis du vil oprette forbindelse til en anden Dataverse-data lake, [skal du oprette en ny datakilde](#connect-to-a-dataverse-managed-lake).

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

2. Vælg ellipsen ud for den datakilde, du vil opdatere.

3. Vælg indstillingen **Rediger** på listen.

4. Vælg yderligere objekter på listen med tilgængelige objekter, og vælg **Gem**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
