---
title: Power BI-connector (prøveversion)
description: Få at vide, hvordan du kan bruge Dynamics 365 Customer Insights-connectoren i Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 72daf6d4ef3b6afb8049c622b57e7ec44762fb21
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051262"
---
# <a name="power-bi-connector-preview"></a>Power BI-connector (prøveversion)

Opret visualiseringer for dine data med Microsoft Power BI Desktop. Generer yderligere indsigt, og opret rapporter med dine samlede kundedata.

## <a name="prerequisites"></a>Forudsætninger

- Du har samlet kundeprofiler.
- Den nyeste version af [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) installeres på din computer. [Få mere at vide om Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurer connectoren til Power BI

1. Vælg **Fil** > **Hent data** i Power BI Desktop.

1. Vælg **Se mere**, og søg efter **Dynamics 365 Customer Insights**

1. Vælg **Opret forbindelse**.

1. **Log på** med den samme organisationskonto, som du bruger til Customer Insights, og vælg **Opret forbindelse**.
   > [!NOTE]
   > Den konto, du angiver i dette trin, bruges til at hente data fra Customer Insights og behøver ikke at være den samme som den, du er logget på i Power BI. Hvis du vil nulstille den konto, der bruges til hentning af data, skal du åbne Power BI og gå til **Fil** > **Muligheder** > **Indstillinger** > **Datakildeindstillinger**. Vælg **Dynamics 365 Customer Insights-logon** på listen over datakilder, og vælg **Ryd tilladelser**.  

1. I dialogboksen **Navigator**. der vises en liste om alle de miljøer, du har adgang til. Udvid et miljø, og åbn en af mapperne (objekter, målpunkter, segmenter, forbedringer). Du kan f.eks. åbne mappen **Objekter** for at få vist alle de objekter, du kan importere.

   ![Power BI Connector Navigator.](media/power-bi-navigator.png "Power BI Connector Navigator")

1. Markér afkrydsningsfelterne ud for de objekter, der skal inkluderes, og vælg **Indlæs**. Du kan vælge flere objekter fra flere miljøer.

1. Der vises en dialogboks for indlæsning, mens objekterne indlæses. Når alle de valgte objekter er indlæst, kan du bruge funktionerne i Power BI til at visualisere dataene.

## <a name="large-data-sets"></a>Store datasæt

Customer Insights-connectoren for Power BI er udviklet til at fungere for datasæt, der indeholder op til 1 million kundeprofiler. Import af større datasæt fungerer muligvis, men tager længere tid. Processen kan derudover køres med en timeout på grund af Power BI-begrænsninger. Du kan finde flere oplysninger i [Power BI: Anbefalinger til store datasæt](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Arbejde med et delsæt af data

Overvej at arbejde med et delsæt af dine data. Du kan f. eks. oprette [segmenter](segments.md) i stedet for at eksportere alle kundeposter til Power BI.

## <a name="troubleshooting"></a>Fejlfinding

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insights-miljøet vises ikke i Power BI

Miljøer, hvor der er defineret mere end en [relation](relationships.md) mellem to identiske objekter i Customer Insights, er ikke tilgængelige i Power BI-connectoren.

Du kan identificere og fjerne de kopierede relationer.

1. Gå til **Data** > **Relationer** i det miljø, du mangler i Power BI.
2. Identificere kopierede Relationer:
   - Kontrollér, om der er defineret mere end én relation mellem de samme to objekter.
   - Kontrollér, om der er oprettet en relation mellem to objekter, som begge er medtaget i samlingsprocessen. Der er defineret en implicit relation mellem alle objekter, der er inkluderet i samlingsprocessen.
3. Fjern eventuelle kopier af identificerede relationer.

Når du har fjernet de kopierede relationer, skal du prøve at konfigurere Power BI-connector igen. Miljøet skulle nu være tilgængeligt.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Fejl i datofelter under indlæsning af objekter i Power BI Desktop

Når du indlæser objekter, som indeholder felter med et datoformat, f.eks. DD/MM/ÅÅÅÅ, kan du støde på fejl på grund af uoverensstemmende landeformater. Denne uoverensstemmelse opstår, når Power BI Desktop-filen angives til en anden landekonto end engelsk (USA), da datofelter i Customer Insights gemmes i amerikansk format.

Filen Power BI Desktop har en enkelt indstilling for landeindstilling, som anvendes, når du henter data. Du kan få vist datofelterne korrekt ved at angive landestandard for .BPI-fil til engelsk (USA). [Flere oplysninger om, hvordan du ændrer landestandard for en Power BI Desktop-fil](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]
