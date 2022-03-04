---
title: DSR-anmodninger (Data Subject Rights) under GDPR | Microsoft Docs
description: Svar på DSR-anmodninger til muligheder i Dynamics 365 Customer Insights-målgruppen Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350262"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>DSR-anmodninger (Data Subject Rights) under GDPR

EU's generelle databeskyttelsesforordning (2018) har været gældende siden 25. maj 2018. Den giver personer vigtige rettigheder med hensyn til deres data. GDPR handler om beskyttelse af og aktivering af enkeltpersoners ret til beskyttelse af personlige oplysninger. Du kan læse mere om Microsofts engagement i sikkerhed og overholdelse af regler og standarder i [Microsoft Center for sikkerhed og sikkerhed](https://www.microsoft.com/trust-center).

Vi forpligter os til at hjælpe vores kunder med at leve op til deres GDPR-krav. Den omfatter retten til at slette og eksportere data, der omfatter personlige oplysninger, f.eks. bruger-id'er, telefonnumre og e-mail-adresser. Administratorer kan implementere brugeranmodninger om sletning eller eksport af personlige data.

## <a name="audience-insights"></a>Indsigt i målgruppe

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Svar på GDPR-sletteanmodninger vedrørende muligheder i dataemne i Dynamics 365 Customer Insights-målgruppen Insights.

"Retten til at fjerne" personlige data fra en organisations kundedata er en nøglebeskyttelse i generel forordning om databeskyttelse (GDPR). Fjernelse af personlige data omfatter fjernelse af alle personlige data og systemgenererede logge, undtagen oplysninger om overvågningslog.

#### <a name="manage-data-subject-delete-requests"></a>Administrere anmodninger om datasletning fra den registrerede

Målgruppen Insights tilbyder følgende funktioner i produktet, hvor du kan slette personlige data for en bestemt kunde eller bruger:

- **Administrere sletteanmodninger om kundedata**: Kundedata i Customer Insights indtages fra oprindelige datakilder uden for Customer Insights. Alle GDPR-sletteanmodninger skal udføres i den oprindelige datakilde.
- **Administrér sletteanmodninger om Customer Insights-brugerdata**: Data til brugere er oprettet af Customer Insights. Alle GDPR-sletteanmodninger skal udføres i Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Administrere sletteanmodninger for kundedata

En Customer Insights-administrator kan følge disse trin for at fjerne de kundedata, der er blevet slettet i datakilden:

1. Log på Dynamics 365 Customer Insights.
2. Gå til **Data** > **Datakilder** i målgruppen Insights
3. For hver datakilde på listen, der indeholder slettede kundedata:
   1. Vælg (...), og vælg derefter **Opdater**.
   2. Tjek statussen for datakilden under **Status**. En markering betyder, at opdateringen lykkedes. En advarselstrekant betyder, at noget gik galt. Hvis der vises en advarselstrekant, skal du kontakte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Håndtere GDPR-sletteanmodninger for kundedata.](audience-insights/media/gdpr-data-sources.png "Håndtere GDPR-sletteanmodninger for kundedata")

##### <a name="manage-delete-requests-for-user-data"></a>Administrér sletteanmodninger for brugerdata

En Customer Insights-administrator kan følge disse trin for at slette Customer Insights-brugerdata:

1. Log på Dynamics 365 Customer Insights.
2. Gå til **Adm** > **Tilladelser** i målgruppen Insights.
3. Markér afkrydsningsfeltet ud for den bruger, der skal slettes.
4. Vælg **Fjern**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Besvarelse af GDPR-eksportanmodninger vedrørende dataemne

Som en del af vores forpligtelse i egenskab af din partner i forhold til generel forordning om databeskyttelse (GDPR) har vi udviklet dokumentation som hjælp til din forberedelse. I denne dokumentation beskrives de trin, du kan tage i dag for at understøtte GDPR overholdelse, når du bruger målgrupen Insights.

#### <a name="manage-export-and-view-requests"></a>Håndtere anmodninger om eksport og visning

Retten til dataportabilitet gør det muligt for registrerede personer at anmode om en kopi af deres personlige data i et elektronisk format (defineret som et "struktureret, almindeligt anvendt, maskinlæsbart og interoperativt format"), der kan overføres til en anden datacontroller.

##### <a name="export-customer-data-tenant-admin"></a>Eksportere kundedata (lejeradministrator)

En lejeradministrator kan følge disse trin for at eksportere data:

1. Send en mail til D365CI@microsoft.com med angivelse af kundens mailadresse i anmodningen. Customer Insights-teamet sender en e-mail til den registrerede lejeradministrators mailadresse og anmoder om bekræftelse på eksport af data.
2. Acceptér bekræftelsen for at eksportere dataene til den ønskede kunde.
3. Modtag de eksporterede data via mailadressen for lejeradministratoren.

##### <a name="export-user-data-tenant-admin"></a>Eksport af brugerdata (lejeradministrator)

1. Send en mail til D365CI@microsoft.com med angivelse af brugerens mailadresse i anmodningen. Customer Insights-teamet sender en e-mail til den registrerede lejeradministrators mailadresse og anmoder om bekræftelse på eksport af data.
2. Acceptér bekræftelsen for at eksportere dataene til den ønskede bruger.
3. Modtag de eksporterede data via mailadressen for lejeradministratoren.

## <a name="consent-management-preview"></a>Samtykkeadministration (forhåndsversion)

Funktionen til administration af samtykke indsamler ikke brugerdata direkte. Den importerer og behandler kun samtykkedata, der leveres af brugere i andre programmer.

Hvis du vil fjerne samtykkedata om bestemte brugere, skal du fjerne dem i de datakilder, der er tilgængelige for administration af samtykke. Når du har datakilde, slettes de fjernede data også i Samtykkecenter. Programmer, der bruger objektet til samtykke, sletter også data, der er fjernet på kilden efter en [opdatering](audience-insights/system.md#refresh-processes). Vi anbefaler, at du opdaterer datakilder hurtigt efter at have reageret på en forespørgsel om dataanmodning for at fjerne brugerens data fra alle andre processer og programmer.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]