---
title: Forbedre kundeprofiler med SFTP brugerdefineret import (forhåndsversion)
description: Generelle oplysninger om SFTP-brugerdefineret importforbedring.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 88fc366ab9478c3b67034af794e237ff4573da7c
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081027"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Forbedre kundeprofiler med SFTP brugerdefineret import (forhåndsversion)

SFTP (Secure File Transfer Protocol) brugerdefineret import giver dig mulighed for at importere data, der ikke er brug for til at gennemgå processen for datasamling. Det er en fleksibel, sikker og nem måde at samle dine data på. SFTP brugerdefineret import kan bruges sammen med [SFTP-eksport](export-sftp.md), der gør det muligt at eksportere de kundeprofildata, der er nødvendige for at opnå en forbedring. Dataene kan derefter behandles og beriges, og brugerdefineret SFTP-import kan bruges til at få de forbedrede data tilbage til Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Forudsætninger

- Filnavn og lokation (sti) for den fil, der skal importeres på SFTP-værten, kendes.

- En *model.json*-fil, der angiver skemaet Common Data Model for de data, der skal importeres, er tilgængeligt. Denne fil skal være i samme mappe som den fil, der skal importeres.

- En [SFTP-forbindelse](connections.md) er [konfigureret](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Eksempel på filskema

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfiguration af forbindelsen til brugerdefineret SFTP-import

Du skal være [administrator](permissions.md#admin) i Customer Insights og have brugerlegitimationsoplysninger, URL-adresse og portnummer til den SFTP-lokation, hvor du vil importere data fra.

1. Vælg **Tilføj forbindelse**, når du konfigurerer en forbedring, eller gå til **Admin** > **Forbindelser**, og vælg **Konkfigurer** i Brugerdefineret importfelt.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Brugerdefineret konfiguration af importforbindelsesside.":::

1. Angiv et navn for forbindelsen.

1. Angiv et gyldigt brugernavn, en gyldig adgangskode og en gyldig værts-URL-adresse til den SFTP-server, som de data, der skal importeres, findes på.

1. Gennemse og giv dit samtykke til [Beskyttelse af personlige oplysninger og overholdelse af data](#data-privacy-and-compliance) ved at vælge **Jeg accepterer**.

1. Vælg **Kontrollér** for at konfigurationen er valideret, og vælg derefter **Gem**.

### <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights til at overføre data til ved hjælp af brugerdefineret import, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personoplysninger. Microsoft kan overføre sådanne data efter dine instruktioner, men du er ansvarlig for at sikre, at data overholder alle forpligtelser i forbindelse med sikkerhed eller beskyttelse af personlige oplysninger. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne forbedring for at afslutte brugen af denne funktionalitet.

## <a name="configure-the-import"></a>Konfigurer import

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Forbedring af data** i feltet **SFTP-brugerdefineret import**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP-brugerdefineret importfelt.":::

1. Gennemse oversigten, og vælg derefter **Næste**.

1. Vælg forbindelsen. Kontakt en administrator, hvis en ikke er tilgængelig.

1. Vælg **Kundedatasæt**, og vælg den profil eller det segment, du vil forbedre. Objektet *Kunde* forbedrer alle dine kundeprofiler, hvorimod et segment kun forbedrer de kundeprofiler, der findes i dette segment.

1. Vælg **Næste**.

1. Angiv **sti** og **filnavn** på den datafil, du vil importere.

1. Vælg **Næste**.

1. Angiv et **Navn** til forbedringen og **outputobjektnavn**.

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

1. Vælg **Kør** for at starte forbedringsprocessen, eller luk for at vende tilbage til siden **Forbedringer**.

## <a name="view-enrichment-results"></a>Vise forbedringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
