---
title: Forbedring af SFTP-brugerdefineret import
description: Generelle oplysninger om SFTP-brugerdefineret importforbedring.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896274"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Forbedring af kundeprofiler med brugerdefinerede data (prøveversion)

Brugerdefineret import af SFTP (Secure File Transfer Protocol) giver dig mulighed for at importere data, der ikke behøver at gå gennem processen til samling af data. Det er en fleksibel, sikker og nem måde at samle dine data på. SFTP brugerdefineret import kan bruges sammen med [SFTP-eksport](export-sftp.md), der gør det muligt at eksportere de kundeprofildata, der er nødvendige for at opnå en forbedring. Dataene kan derefter behandles og forbedres, og SFTP-brugerdefineret import kan bruges til at få de forbedrede data tilbage til målgruppeindsigt i Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Forudsætninger

Følgende forudsætninger skal være opfyldt, hvis du vil konfigurere SFTP-brugerdefineret import:

- Du har filnavnet og placeringen (stien) til den fil, der skal importeres, på SFTP-værten.
- Der findes en *model.json*-fil, der angiver [skemaet Common Data Model](/common-data-model/) for de data, der skal importeres. Denne fil skal være i samme mappe som den fil, der skal importeres.
- En SFTP-forbindelse er allerede konfigureret af en administrator *eller* du har [administratortilladelser](permissions.md#administrator). Du skal bruge brugerlegitimationsoplysninger, URL-adresse og portnummer til den SFTP-placering, hvor du vil importere data fra.


## <a name="configure-the-import"></a>Konfigurer import

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **SFTP-brugerdefineret importfelt (Secure File Transfer Protocol)**, vælg **Forbedr mine data** og vælg derefter **Start her**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP-brugerdefineret importfelt.":::

1. Vælg en [forbindelse](connections.md) på rullelisten. Kontakt en administrator, hvis der ikke er nogen forbindelse. Hvis du er administrator, kan du oprette en forbindelse ved at vælge **Tilføj forbindelse** og vælge **Brugerdefineret SFTP-import** på rullelisten.

1. Vælg **Opret forbindelse til brugerdefineret import** for at bekræfte den valgte forbindelse.

1.  Vælg **Næste**, og angiv **filnavnet** og **stien** til den datafil, du vil importere.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Skærmbillede, når du angiver datalokation.":::

1. Vælg **Næste**, og angiv et navn, der angiver navnet på outputobjektet. 

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfiguration af forbindelsen til brugerdefineret SFTP-import 

Du skal være en administrator for at konfigurere forbindelser. Vælg **Tilføj forbindelse**, når du konfigurerer en konfiguration, *eller* gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i Brugerdefineret importfelt.

1. Angiv et navn til forbindelsen i feltet **Vis navn**.

1. Angiv et gyldigt brugernavn, en gyldig adgangskode og en gyldig værts-URL-adresse til STFP-server, som dataene skal importeres fra.

1. Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**.

1. Vælg **Kontroller** for at validere konfigurationen.

1. Når verifikationen er fuldført, kan du gemme forbindelsen ved at klikke på **Gem**.

> [!div class="mx-imgBorder"]
   > ![Side til konfiguration af Experian-forbindelse](media/enrichment-SFTP-connection.png "Side til konfiguration af Experian-forbindelse")


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

Byg oven over dine forbedrede kundedata. Opret [segmenter](segments.md), [mål](measures.md), og [eksportér data](export-destinations.md) for at give kunderne personlige erfaringer.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
