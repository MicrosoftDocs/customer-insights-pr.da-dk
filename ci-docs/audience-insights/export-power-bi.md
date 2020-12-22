---
title: Power BI-connector
description: Få at vide, hvordan du kan bruge Dynamics 365 Customer Insights-connectoren i Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405413"
---
# <a name="connector-for-power-bi-preview"></a>Connector til Power BI (prøve)

Opret visualiseringer for dataene ved hjælp af Power BI Desktop. Generer yderligere indsigt, og opret rapporter med dine samlede kundedata.

## <a name="prerequisites"></a>Forudsætninger

- Du har samlet kundeprofiler.
- Den nyeste version af [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) er installeret på computeren. [Få mere at vide om Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurer connectoren til Power BI

1. Vælg **Fil** > **Hent data** i Power BI Desktop.

1. Vælg **Se mere**, og søg efter **Dynamics 365 Customer Insights**

1. Vælg resultatet, og vælg **Opret forbindelse**.

1. **Log på** med den samme organisationskonto, som du bruger til Customer Insights, og vælg **Opret forbindelse**.
   > [!NOTE]
   > Den konto, du angiver i dette trin, bruges til at hente data fra Customer Insights og behøver ikke at være den samme som den, du er logget på i Power BI. Hvis du vil nulstille den konto, der bruges til hentning af data, skal du åbne Power BI og gå til **Fil** > **Muligheder** > **Indstillinger** > **Datakildeindstillinger**. Vælg **Dynamics 365 Customer Insights-logon** på listen over datakilder, og vælg **Ryd tilladelser**.  

1. I dialogboksen **Navigator**. der vises en liste om alle de miljøer, du har adgang til. Udvid et miljø, og åbn en af mapperne (objekter, målpunkter, segmenter, forbedringer). Du kan f.eks. åbne mappen **Objekter** for at få vist alle de objekter, du kan importere.

   ![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")

1. Markér afkrydsningsfelterne ud for de objekter, der skal inkluderes, og vælg **Indlæs**. Du kan vælge flere objekter fra flere miljøer.

1. Der vises en dialogboks for indlæsning, mens objekterne indlæses. Når alle de valgte objekter er indlæst, kan du bruge funktionerne i Power BI til at visualisere dataene.

## <a name="large-data-sets"></a>Store datasæt

Customer Insights-connectoren for Power BI er udviklet til at fungere for datasæt, der indeholder op til 1 million kundeprofiler. Import af større datasæt fungerer muligvis, men tager længere tid. Processen kan derudover køres med en timeout på grund af Power BI-begrænsninger. Du kan finde flere oplysninger i [Power BI: Anbefalinger til store datasæt](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Arbejde med et delsæt af data

Overvej at arbejde med et delsæt af dine data. Du kan f. eks. oprette [segmenter](segments.md) i stedet for at eksportere alle kundeposter til Power BI.
