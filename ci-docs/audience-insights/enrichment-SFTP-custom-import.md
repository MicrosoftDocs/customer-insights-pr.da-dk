---
title: Forbedring af SFTP-brugerdefineret import
description: Generelle oplysninger om SFTP-brugerdefineret importforbedring.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e4b9a65eb50f75e0243fabfc10b501cf7acf4490
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229631"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Forbedring af kundeprofiler med brugerdefinerede data (prøveversion)

SFTP (Secure File Transfer Protocol) brugerdefineret import giver dig mulighed for at importere data, der ikke er brug for til at gennemgå processen for datasamling. Det er en fleksibel, sikker og nem måde at samle dine data på. SFTP brugerdefineret import kan bruges sammen med [SFTP-eksport](export-sftp.md), der gør det muligt at eksportere de kundeprofildata, der er nødvendige for at opnå en forbedring. Dataene kan derefter behandles og beriges, og SFTP-brugerdefineret import kan bruges til at bringe de berigede data tilbage til publikum indsigtsfunktionen i Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Forudsætninger

Følgende forudsætninger skal være opfyldt, hvis du vil konfigurere SFTP-brugerdefineret import:

- Du har filnavnet og placeringen (stien) til den fil, der skal importeres på SFTP-værten.
- Der findes en *model.json*-fil, der angiver [skemaet Common Data Model](/common-data-model/) for de data, der skal importeres. Denne fil skal være i samme mappe som den fil, der skal importeres.
- En SFTP-forbindelse er allerede konfigureret af en administrator *eller* du har [administratortilladelser](permissions.md#administrator). Du skal bruge brugerlegitimationsoplysninger, URL-adresse og portnummer til den SFTP-placering, hvor du vil importere data fra.


## <a name="configure-the-import"></a>Konfigurer import

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **SFTP-brugerdefineret importfelt (Secure File Transfer Protocol)**, vælg **Forbedr mine data** og vælg derefter **Start her**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP-brugerdefineret importfelt.":::

1. Vælg en [værdi](connections.md) på rullelisten. Kontakt en administrator, hvis der ikke er nogen forbindelse. Hvis du er administrator, kan du oprette forbindelse ved at vælge **Tilføj forbindelse** og vælge **SFTP Brugerdefineret import** på rullelisten.

1. Vælg **Opret forbindelse til brugerdefineret import** for at bekræfte den valgte forbindelse.

1.  Vælg **Næste**, og angiv **Sti** og **Filnavn** på den datafil, du vil importere.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Skærmbillede, når du angiver datalokation.":::

1. Vælg **Næste**, og vælg kundedatasættet. Dette kan enten være alle kundeprofiler eller et segment.

1. Vælg **Næste**, og angiv et navn, der angiver navnet på outputobjektet. 

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfiguration af forbindelsen til brugerdefineret SFTP-import 

Du skal være en administrator for at konfigurere forbindelser. Vælg **Tilføj forbindelse**, når du konfigurerer en konfiguration, *eller* gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i Brugerdefineret importfelt.

1. Angiv et navn til forbindelsen i feltet **Vis navn**.

1. Angiv et gyldigt brugernavn, en gyldig adgangskode og en gyldig værts-URL-adresse til den SFTP-server, som de data, der skal importeres, findes på.

1. Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**.

1. Vælg **Kontroller** for at validere konfigurationen.

1. Når bekræftelsen er fuldført, kan forbindelsen gemmes ved at vælge **Gem**.

   > [!div class="mx-imgBorder"]
   > ![Experian forbindelseskonfigurationsside.](media/enrichment-SFTP-connection.png "Experian-forbindelseskonfigurationsside")


## <a name="defining-field-mappings"></a>Definerer felttilknytninger 

Den mappe, der indeholder den fil, der skal importeres på SFTP-serveren, skal også indeholde en *model.json*-fil. Denne fil defineres det skema, der skal bruges til at importere data. Skemaet skal bruge [Common Data Model](/common-data-model/) til at angive felttilknytningen. Et simpelt eksempel på en model.json-fil ser ud på følgende måde:

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

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
