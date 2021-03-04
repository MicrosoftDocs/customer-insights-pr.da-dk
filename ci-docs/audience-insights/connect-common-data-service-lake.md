---
title: Opret forbindelse til objekter i den Common Data Service administrerede Data Lake
description: Importere data fra en Common Data Service-administreret datasø.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267806"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Oprette forbindelse til data i en Common Data Service-administreret datasø

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Denne artikel indeholder oplysninger om, hvordan eksisterende Dynamics 365-kunder hurtigt kan oprette forbindelse til deres analyseenheder i den Common Data Service-administrerede sø. Du skal være administrator på Common Data Service-organisationen for at fortsætte og se listen over de objekter, der er tilgængelige i den administrerede sø.

## <a name="important-considerations"></a>Vigtige overvejelser

Data, der gemmes i onlinetjenester, f.eks. Azure Data Lake Storage, gemmes på en anden placering end der, hvor dataene behandles eller gemmes i Dynamics 365 Customer Insights.Ved at importere eller oprette forbindelse til data, der er gemt i onlinetjenester, accepterer du, at data kan overføres til og gemmes sammen med Dynamics 365 Customer Insights.  [Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Opret forbindelse til Common Data Service-administreret sø

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

2. Vælg **Tilføj datakilde**.

3. Vælg **Opret forbindelse til Common Data Service**, og vælg **Næste**.

4. Angiv et **Navn** til datakilden, og vælg derefter **Næste**. Navneretningslinjer: 
   - Start med et bogstav.
   - Brug kun bogstaver og tal. Specialtegn og mellemrum er ikke tilladt.
   - Brug mellem 3 og 64 tegn.

5. Angiv **Serveradressen** for din Common Data Service-organisation, og vælg **Log på**.

   > [!div class="mx-imgBorder"]
   > ![Dialogboksen til angivelse af Common Data Service-serveradresse](media/enter-CDS-org-details.png)

6. Vælg det sæt objekter, som du vil indsætte fra listen med tilgængelige.    

   > [!NOTE]
   > Hvis nogle objekter allerede er valgt, vil de muligvis blive brugt af andre Dynamics 365-programmer (fx Dynamics 365 Sales Insights eller Customer Service Insights). Du kan ikke ændre markeringen. Disse objekter er tilgængelige, når datakilden er oprettet.

   > [!div class="mx-imgBorder"]
   > ![Dialogboks, der viser en liste over objekter i Common Data Service-organisationen](media/select-analytical-entities.png)

7. Gem din markering for at begynde at synkronisere de valgte objekter til den Common Data Service-administrerede sø. Du kan finde den netop tilføjede forbindelse på siden **-datakilder**. Det vil blive sat i kø til opdatering og vise antallet af objekter som 0, indtil alle objekterne er synkroniseret.

Kun én datakilde af et miljø kan bruge samme Common Data Service administrerede Data Lake samtidig.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Redigere en Common Data Service-administreret sø-datakilde

Du kan kun redigere objekt-valget, efter du har oprettet datakilden. Hvis du f.eks. har tilføjet yderligere objekter i Common Data Service, og du også vil importere dem.    
Hvis du vil oprette forbindelse til en anden Common Data Service, [skal du oprette en ny datakilde](#connect-to-a-common-data-service-managed-lake).

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

2. Vælg ellipsen ud for den datakilde, du vil opdatere.

3. Vælg indstillingen **Rediger** på listen.

4. Vælg yderligere objekter på listen med tilgængelige objekter, og vælg **Gem**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]