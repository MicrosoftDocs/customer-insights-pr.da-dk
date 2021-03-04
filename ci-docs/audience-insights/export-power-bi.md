---
title: Power BI-connector
description: Få at vide, hvordan du kan bruge Dynamics 365 Customer Insights-connectoren i Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477081"
---
# <a name="connector-for-power-bi-preview"></a>Connector til Power BI (prøve)

Opret visualiseringer for dataene ved hjælp af Power BI Desktop. Generer yderligere indsigt, og opret rapporter med dine samlede kundedata.

## <a name="prerequisites"></a>Forudsætninger

- Du har samlet kundeprofiler.
- Den nyeste version af [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) er installeret på computeren. [Få mere at vide om Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurer connectoren til Power BI

1. Vælg **Fil** > **Hent data** i Power BI Desktop.

1. Vælg **Se mere**, og søg efter **Dynamics 365 Customer Insights**

1. Vælg **Opret forbindelse**.

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

## <a name="troubleshooting"></a>Fejlfinding

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights-miljøet vises ikke i Power BI

Miljøer, hvor der er defineret mere end én [relation](relationships.md) mellem to identiske objekter i målgruppeindsigt, er ikke tilgængelige i Power BI-connector.

Du kan identificere og fjerne de kopierede relationer.

1. I målgruppeindsigt, skal du gå til **Data** > **Relationer** vedrørende det miljø, du mangler i Power BI.
2. Identificere kopierede Relationer:
   - Kontrollér, om der er defineret mere end én relation mellem de samme to objekter.
   - Kontrollér, om der er oprettet en relation mellem to objekter, som begge er medtaget i samlingsprocessen. Der er defineret en implicit relation mellem alle objekter, der er inkluderet i samlingsprocessen.
3. Fjern eventuelle kopier af identificerede relationer.

Når du har fjernet de kopierede relationer, skal du prøve at konfigurere Power BI-connector igen. Miljøet skulle nu være tilgængeligt.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

