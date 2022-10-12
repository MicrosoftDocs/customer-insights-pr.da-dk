---
title: Oprette forbindelse til data i en Microsoft Dataverse-administreret data lake
description: Importere data fra en Microsoft Dataverse-administreret data lake.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609788"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Oprette forbindelse til data i en Microsoft Dataverse-administreret data lake

Microsoft Dataverse-brugerne kan hurtigt oprette forbindelse til analytiske objekter i et Microsoft Dataverse-administreret system. Kun én datakilde af et miljø kan bruge samme Dataverse administrerede Data Lake samtidig.

> [!NOTE]
> Du skal være administrator i Dataverse-organisationen for at kunne fortsætte og få vist listen over objekter i det administrerede område.

## <a name="prerequisites"></a>Forudsætninger

- Data, der gemmes i onlinetjenester, f.eks. Azure Data Lake Storage, gemmes på en anden placering end der, hvor dataene behandles eller gemmes i Dynamics 365 Customer Insights.Ved at importere eller oprette forbindelse til data, der er gemt i onlinetjenester, accepterer du, at data kan overføres til og gemmes sammen med Dynamics 365 Customer Insights. [Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration](https://www.microsoft.com/trust-center).

- Kun Dataverse-objekter, hvor [ændringssporing](/power-platform/admin/enable-change-tracking-control-data-synchronization) er aktiveret og synlige. Disse objekter kan eksporteres til de administrerede Dataverse-datasø og bruges i Customer Insights. Standardtabellerne har Dataverse-ændringssporing aktiveret som standard. Du skal slå sporing af ændringer til for brugerdefinerede tabeller. Hvis du vil kontrollere, om en Dataverse-tabel er aktiveret til sporing af ændringer, skal du gå til [Power Apps](https://make.powerapps.com) > **Data** > **Tabeller**. Find tabellen med interesse, og vælg den. Gå til **Indstillinger** > **Avancerede indstillinger**, og gennemse indstillingen **Spor ændringer**.

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

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan tage tid at indlæse data. Når opdateringen er gennemført, kan de indtagne data gennemses fra siden [**Objekter**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Redigere en Dataverse-administreret sø-datakilde

Du kan kun redigere objekt-valget, efter du har oprettet datakilden. Hvis du f.eks. har tilføjet yderligere objekter i Dataverse, og du også vil importere dem.
Hvis du vil oprette forbindelse til en anden Dataverse-data lake, [skal du oprette en ny datakilde](#connect-to-a-dataverse-managed-lake).

1. Gå til **Data** > **Datakilder**.

1. Ud for den datakilde, du vil opdatere, og vælg **Rediger**.

1. Vælg yderligere objekter på listen med tilgængelige objekter.

1. Klik på **Gem** for at anvende ændringerne og vende tilbage til siden **Datakilder**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Almindelige årsager til indtagelsesfejl eller beskadigede data

Følgende kontroller køres på de indtagne data for at få vist beskadigede poster:

- Værdien i et felt stemmer ikke overens med datatypen i kolonnen.
- Felter indeholder tegn, der medfører, at kolonnerne ikke stemmer overens med det forventede skema. Eksempel: forkert formaterede anførselstegn, unescaped anførselstegn eller ny linje-tegn.
- Hvis der er kolonner af typen datetime/date/datetimeoffset, skal formatet angives i modellen, hvis det ikke følger ISO-standardformatet.

### <a name="schema-or-data-type-mismatch"></a>Uoverensstemmelser i skema- eller datatype

Hvis dataene ikke er i overensstemmelse med skemaet, klassificeres posterne som beskadiget. Ret enten kildedataene eller skemaet, og indtag dataene igen.

### <a name="datetime-fields-in-the-wrong-format"></a>Datetime-felter i det forkerte format

Datetime-felterne i objektet er ikke i ISO- eller en-US-formater. Standardformatet for datetime i Customer Insights er en-US-formatet. Alle datetime-felter i et objekt skal have samme format. Customer Insights understøtter andre formater, hvis anmærkninger eller egenskaber er angivet på kilde- eller objektniveau i modellen eller manifest.json. Eksempel: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  I en manifest.json kan datetime-formatet angives på objektniveau eller på attributniveau. På objektniveau skal du bruge "exhibitsTraits" i objektet i *.manifest.cdm.json til at definere datetime-formatet. På attributniveau skal du bruge "appliedTraits" i attributten i entityname.cdm.json.

**Manifest.json på objektniveau**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json på attributniveau**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
