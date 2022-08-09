---
title: DSR-anmodninger (Data Subject Rights) under GDPR | Microsoft Docs
description: Reagere på DSR-anmodninger for Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146688"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>DSR-anmodninger (Data Subject Rights) under GDPR

EU's generelle databeskyttelsesforordning (2018) har været gældende siden 25. maj 2018. Den giver personer vigtige rettigheder med hensyn til deres data. GDPR handler om beskyttelse af og aktivering af enkeltpersoners ret til beskyttelse af personlige oplysninger. Du kan læse mere om Microsofts engagement i sikkerhed og overholdelse af regler og standarder i [Microsoft Center for sikkerhed og sikkerhed](https://www.microsoft.com/trust-center).

Vi forpligter os til at hjælpe vores kunder med at leve op til deres GDPR-krav. Den omfatter retten til at slette og eksportere data, der omfatter personlige oplysninger, f.eks. bruger-id'er, telefonnumre og e-mail-adresser. Administratorer kan implementere brugeranmodninger om sletning eller eksport af personlige data.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Reagere på GDPR-anmodninger fra den registrerede (DSR) om datasletning for Dynamics 365 Customer Insights

"Retten til at fjerne" personlige data fra en organisations kundedata er en nøglebeskyttelse i generel forordning om databeskyttelse (GDPR). Fjernelse af personlige data omfatter fjernelse af alle personlige data og systemgenererede logge, undtagen oplysninger om overvågningslog.

#### <a name="manage-data-subject-delete-requests"></a>Administrere anmodninger om datasletning fra den registrerede

Customer Insights indeholder følgende funktioner i produktet, hvor du kan slette personlige data for en bestemt kunde eller bruger:

- **Administrere sletteanmodninger om kundedata**: Kundedata i Customer Insights indtages fra oprindelige datakilder uden for Customer Insights. udfør GDPR-sletteanmodninger i den oprindelige datakilde først.
- **Administrér sletteanmodninger om Customer Insights-brugerdata**: Data til brugere er oprettet af Customer Insights. Alle GDPR-sletteanmodninger skal udføres i Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Administrere sletteanmodninger for kundedata

En Customer Insights-administrator kan følge disse trin for at fjerne de kundedata, der er blevet slettet i datakilden. Kontrollér, at sletningsanmodningen blev udført i din datakilde, før du fortsætter med de trin, der er angivet nedenfor. 

1. Log på Dynamics 365 Customer Insights.
1. Gå til **Data** > **Datakilder**
1. For hver datakilde på listen, der indeholder slettede kundedata:
   1. Vælg den lodrette ellipse (&vellip;), og vælg derefter **Opdater**.
   1. Tjek statussen for datakilden under **Status**. En markering betyder, at opdateringen lykkedes. En advarselstrekant betyder, at noget gik galt. Hvis der vises en advarselstrekant, skal du kontakte D365CI@microsoft.com.
1. Efter en vellykket opdatering af datakilder skal du også køre downstreamopdateringen. Især hvis du ikke har planlagt en tilbagevendende fuldstændig opdatering af Customer Insights. 

> [!IMPORTANT]
> Statiske segmenter er ikke inkluderet i en fuldstændig opdatering eller kører downstreamopdateringer efter en anmodning om sletning. Du kan sikre, at kundedata også fjernes fra statiske segmenter, ved at oprette de statiske segmenter igen med de opdaterede kildedata.

> [!div class="mx-imgBorder"]
> ![Håndtere GDPR-sletteanmodninger for kundedata.](media/gdpr-data-sources.png "Håndtere GDPR-sletteanmodninger for kundedata")

##### <a name="manage-delete-requests-for-user-data"></a>Administrér sletteanmodninger for brugerdata

En Customer Insights-administrator kan følge disse trin for at slette Customer Insights-brugerdata:

1. Log på Dynamics 365 Customer Insights.
2. Gå til **Administration** > **Sikkerhed** > **Tilladelser**.
3. Markér afkrydsningsfeltet ud for den bruger, der skal slettes.
4. Vælg **Fjern**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Besvarelse af GDPR-eksportanmodninger vedrørende dataemne

Som en del af vores forpligtelse i egenskab af din partner i forhold til generel forordning om databeskyttelse (GDPR) har vi udviklet dokumentation som hjælp til din besvarelse af anmodninger fra dataemner.

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

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Håndtering af datasletning i Dynamics 365 Customer Insights

1. Data slettes (datapartitioner og data øjebliksbilleder), hvis datapartitioner og databilleder er inaktive i mere end 30 dage, hvilket betyder, at de er erstattet af en ny datapartition og et nyt øjebliksbillede via en opdatering af datakilder.
2. Ikke alle data og øjebliksbilleder slettes. Den nyeste datapartition og det nyeste øjebliksbillede af data er pr. definition aktive, fordi de bruges i Customer Insights. For de nyeste data er det uden betydning, om datakilderne ikke er blevet opdateret inden for de seneste 30 dage.

[!INCLUDE [footer-include](includes/footer-banner.md)]
