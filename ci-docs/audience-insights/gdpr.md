---
title: DSR-anmodninger (Data Subject Rights) under GDPR | Microsoft Docs
description: Svar på DSR-anmodninger til muligheder i Dynamics 365 Customer Insights-målgruppen Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405439"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>DSR-anmodninger (Data Subject Rights) under GDPR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Svar på GDPR-sletteanmodninger vedrørende muligheder i dataemne i Dynamics 365 Customer Insights-målgruppen Insights.

"Retten til at fjerne" personlige data fra en organisations kundedata er en nøglebeskyttelse i generel forordning om databeskyttelse (GDPR). Fjernelse af personlige data omfatter fjernelse af alle personlige data og systemgenererede logge, undtagen oplysninger om overvågningslog.

### <a name="manage-data-subject-delete-requests"></a>Administrere anmodninger om datasletning fra den registrerede

Målgruppen Insights tilbyder følgende funktioner i produktet, hvor du kan slette personlige data for en bestemt kunde eller bruger:

- **Administrere sletteanmodninger om kundedata**: Kundedata i Customer Insights indtages fra oprindelige datakilder uden for Customer Insights. Alle GDPR-sletteanmodninger skal udføres i den oprindelige datakilde.
- **Administrér sletteanmodninger om Customer Insights-brugerdata**: Data til brugere er oprettet af Customer Insights. Alle GDPR-sletteanmodninger skal udføres i Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Administrere sletteanmodninger for kundedata

En Customer Insights-administrator kan følge disse trin for at fjerne de kundedata, der er blevet slettet i datakilden:

1. Log på Dynamics 365 Customer Insights.
2. Gå til **Data** > **Datakilder** i målgruppen Insights
3. For hver datakilde på listen, der indeholder slettede kundedata:
   1. Vælg (...), og vælg derefter **Opdater**.
   2. Tjek statussen for datakilden under **Status**. En markering betyder, at opdateringen lykkedes. En advarselstrekant betyder, at noget gik galt. Hvis der vises en advarselstrekant, skal du kontakte D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Håndtere GDPR-sletteanmodninger for kundedata](media/gdpr-data-sources.png "Håndtere GDPR-sletteanmodninger for kundedata")

#### <a name="manage-delete-requests-for-user-data"></a>Administrér sletteanmodninger for brugerdata

En Customer Insights-administrator kan følge disse trin for at slette Customer Insights-brugerdata:

1. Log på Dynamics 365 Customer Insights.
2. Gå til **Adm** > **Tilladelser** i målgruppen Insights.
3. Markér afkrydsningsfeltet ud for den bruger, der skal slettes.
4. Vælg **Fjern**.

> [!div class="mx-imgBorder"]
> ![Håndtering af GDPR-sletteanmodninger for brugerdata](media/gdpr-permissions.png "Håndtering af GDPR-sletteanmodninger for brugerdata")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Besvarelse af GDPR-eksportanmodninger vedrørende dataemne

Som en del af vores forpligtelse i egenskab af din partner i forhold til generel forordning om databeskyttelse (GDPR) har vi udviklet dokumentation som hjælp til din forberedelse. I denne dokumentation beskrives de trin, du kan tage i dag for at understøtte GDPR overholdelse, når du bruger målgrupen Insights.

### <a name="manage-export-and-view-requests"></a>Håndtere anmodninger om eksport og visning

Retten til dataportabilitet gør det muligt for registrerede personer at anmode om en kopi af deres personlige data i et elektronisk format (defineret som et "struktureret, almindeligt anvendt, maskinlæsbart og interoperativt format"), der kan overføres til en anden datacontroller.

#### <a name="export-customer-data-tenant-admin"></a>Eksportere kundedata (lejeradministrator)

En lejeradministrator kan følge disse trin for at eksportere data:

1. Send en mail til D365CI@microsoft.com med angivelse af kundens mailadresse i anmodningen. Customer Insights-teamet sender en e-mail til den registrerede lejeradministrators mailadresse og anmoder om bekræftelse på eksport af data.
2. Acceptér bekræftelsen for at eksportere dataene til den ønskede kunde.
3. Modtag de eksporterede data via mailadressen for lejeradministratoren.

#### <a name="export-user-data-tenant-admin"></a>Eksport af brugerdata (lejeradministrator)

1. Send en mail til D365CI@microsoft.com med angivelse af brugerens mailadresse i anmodningen. Customer Insights-teamet sender en e-mail til den registrerede lejeradministrators mailadresse og anmoder om bekræftelse på eksport af data.
2. Acceptér bekræftelsen for at eksportere dataene til den ønskede bruger.
3. Modtag de eksporterede data via mailadressen for lejeradministratoren.
