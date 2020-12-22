---
title: Forbedring af SFTP-brugerdefineret import
description: Generelle oplysninger om SFTP-brugerdefineret importforbedring.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568423"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Forbedring af kundeprofiler med brugerdefinerede data (prøveversion)

SFTP (Secure File Transfer Protocol) brugerdefineret import giver dig mulighed for at importere data, der ikke er brug for til at gennemgå processen for datasamling. Det er en fleksibel, sikker og nem måde at samle dine data på. SFTP brugerdefineret import kan bruges sammen med [SFTP-eksport](export-sftp.md), der gør det muligt at eksportere de kundeprofildata, der er nødvendige for at opnå en forbedring. Dataene kan derefter behandles og forbedres, og SFTP-brugerdefineret import kan bruges til at få de forbedrede data tilbage til målgruppeindsigt i Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Forudsætninger

Følgende forudsætninger skal være opfyldt, hvis du vil konfigurere SFTP-brugerdefineret import:

- Du har brugerlegitimationsoplysninger (brugernavn og adgangskode) til den SFTP-placering, hvorfra data skal importeres.
- Du har angivet URL- og portnummer (normalt 22) til STFP-værten.
- Du har filnavnet og placeringen for den fil, der skal importeres, på SFTP-værten.
- Der findes en *model.json*-fil, der angiver skemaet for de data, der skal importeres. Denne fil skal være i samme mappe som den fil, der skal importeres.
- Du har [Administrator](permissions.md#administrator)-tilladelse.

## <a name="configuration"></a>Konfiguration

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. I feltet **SFTP-brugerdefineret import** skal du vælge **Forbedring af mine data**.

   > [!div class="mx-imgBorder"]
   > ![SFTP-brugerdefineret importfelt](media/SFTP_Custom_Import_tile.png "SFTP-brugerdefineret importfelt")

1. Vælg **Start her**, og angiv legitimationsoplysninger og adressen til SFTP-serveren. Det kan f. eks. være sftp://mysftpserver.com: 22.

1. Angiv navnet på den fil, der indeholder data og stien til filen på SFTP-serveren, hvis den ikke findes i rodmappen.

1. Bekræft alle input ved at vælge **Opret forbindelse til brugerdefineret import**.

   > [!div class="mx-imgBorder"]
   > ![Pop op-vinduet SFTP-brugerdefineret importkonfiguration](media/SFTP_Custom_Import_Configuration_flyout.png "Pop op-vinduet SFTP-brugerdefineret importkonfiguration")

## <a name="defining-field-mappings"></a>Definerer felttilknytninger 

Den mappe, der indeholder den fil, der skal importeres på SFTP-serveren, skal også indeholde en *model.json*-fil. Denne fil defineres det skema, der skal bruges til at importere data. Skemaet skal bruge [Common Data Model](https://docs.microsoft.com/common-data-model/) til at angive felttilknytningen. Et simpelt eksempel på en model.json-fil ser ud på følgende måde:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>Forbedringsresultater

Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen. Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab). Behandlingstiden afhænger af størrelsen på de data, der skal importeres, og forbindelsen til SFTP-serveren.

Når forbedringsprocessen er fuldført, kan du gennemse de netop importerede brugerdefinerede forbedringsdata under **Mine forbedringer**. Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.

Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.

## <a name="next-steps"></a>Næste trin

Byg oven over dine forbedrede kundedata. Opret [segmenter](segments.md), [mål](measures.md), og [eksportér data](export-destinations.md) for at give kunderne personlige erfaringer.


