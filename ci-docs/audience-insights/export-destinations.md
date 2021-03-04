---
title: Eksportdestinationer
description: Eksportér data, og administrer eksportdestinationer.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477126"
---
# <a name="export-destinations-preview-overview"></a>Oversigt over eksportdestinationer (prøveversion)

Siden **Eksportdestinationer** viser alle de placeringer, du har konfigureret til at eksportere data til. Du kan også tilføje nye destinationer til eksport. Derudover vises de eksportindstillinger, der er tilgængelige i øjeblikket. Få en hurtig oversigt og beskrivelse, og find ud af, hvad du kan gøre med de enkelte udvidelsesmuligheder. Eksportér ensartede profiler, målpunkter og segmenter til understøttede apps, som er relevante for din virksomhed.

Gå til **Admin** > **Exportdestinationer** for at finde følgende udvidelsesmuligheder:

- [Dynamics 365 Customer Kundekort](customer-card-add-in.md)
- [Facebook Annonceadministrator-connector](export-facebook.md)
- [Power AutomateConnector](export-power-automate.md)
- [Power AppsConnector](export-power-apps.md)
- [Power BIConnector](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure Blob Storage](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [LiveRamp&reg;-connector](export-liveramp.md)
- [Bot til Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insights API](apis.md)

## <a name="add-a-new-export-destination"></a>Tilføje en ny eksportdestination

Hvis du vil tilføje eksportdestinationer, har du [administratortilladelser](permissions.md). Hvis du eksporterer til Microsoft-tjenester, antages det, at begge servicer er i den samme organisation.

1. Gå til **Adminstration** > **Eksportdestinationer**.

1. Skift til fanen **Mine eksportdestinationer**.

1. Vælg **Tilføj destination** for at oprette en ny eksportdestination.

1. På ruden **Tilføj destination** vælg **Type** for eksportdestination fra rullelisten.

1. Angiv de nødvendige oplysninger, og vælg **Næste** for at oprette eksportdestinationen.

Du kan også vælge **Konfigurer** i et område på fanen **Udforsk**.

## <a name="view-export-destinations"></a>Vise Eksportdestinationer

Når du har oprettet eksportdestinationer, kan du finde dem i en tabel under fanen **Mine eksportdestinationer**. Denne tabel indeholder tre kolonner:

- **Vist navn**: Det navn, du angav under oprettelsen af destinationen.
- **Type**: Den eksportdestinationstype, du angav, da du oprettede destinationen.
- **Oprettet den**: Den dato, hvor du oprettede destinationen.

## <a name="edit-an-export-destination"></a>Rediger en eksportdestination

1. Vælg den lodrette ellipse for den eksportdestination, du vil redigere.

   > [!div class="mx-imgBorder"]
   > ![Lodret ellipse](media/export-destinations-page-ellipsis.png "Lodret ellipse")

1. Vælg **Rediger** på rullelisten.

1. Rediger de værdier, der skal opdateres, og vælg **Gem**.

## <a name="export-data-on-demand"></a>Eksporter data efter behov

Når en connector er konfigureret til en eksportdestination, køres eksporter med alle [planlagte opdateringer](system.md#schedule-tab).

Hvis du vil eksportere data uden at vente på en planlagt opdatering, så gå til fanen **Mine eksportdestinationer** i **Administrator** > **Eksportdestinationer**.

> [!div class="mx-imgBorder"]
> ![Lodret ellipse](media/export-destinations-page-ellipsis.png "Lodret ellipse")

- Vælg **Eksport** over listen for at køre eksporten til alle eksportdestinationer på samme tid.
- Vælg ellipsen (...) efter et listeelement, og vælg derefter indstillingen **Eksport** for at køre eksporten for en enkelt eksportdestination.

## <a name="remove-an-export-destination"></a>Fjerne en eksportdestination

Hvis du vil fjerne en eksportdestination, skal du begynde på siden med primære **Eksportdestinationer**.

1. Vælg den lodrette ellipse for den eksportdestination, du vil fjerne.

   > [!div class="mx-imgBorder"]
   > ![Lodret ellipse](media/export-destinations-page-ellipsis.png "Lodret ellipse")

2. Vælg **Fjern** på rullelisten.

3. Bekræft fjernelsen ved at vælge **Fjern** på bekræftelsesskærmen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]