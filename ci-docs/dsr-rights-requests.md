---
title: DSR-anmodninger (Data Subject Rights) under GDPR | Microsoft Docs
description: Reagere på DSR-anmodninger for Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: af2583295627f98e980adbca4f216b9c34c3cad8
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808539"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>DSR-anmodninger (Data Subject Rights) under GDPR

EU's generelle databeskyttelsesforordning (2018) har været gældende siden 25. maj 2018. Den giver personer vigtige rettigheder med hensyn til deres data. GDPR handler om beskyttelse af og aktivering af enkeltpersoners ret til beskyttelse af personlige oplysninger. Du kan læse mere om Microsofts engagement i sikkerhed og overholdelse af regler og standarder i [Microsoft Center for sikkerhed og sikkerhed](https://www.microsoft.com/trust-center).

Vi forpligter os til at hjælpe vores kunder med at leve op til deres GDPR-krav. Den omfatter retten til at slette og eksportere data, der omfatter personlige oplysninger, f.eks. bruger-id'er, telefonnumre og e-mail-adresser. Administratorer kan implementere brugeranmodninger om sletning eller eksport af personlige data.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Reagere på GDPR-anmodninger fra den registrerede (DSR) om datasletning for Dynamics 365 Customer Insights

"Retten til at fjerne" personlige data fra en organisations kundedata er en nøglebeskyttelse i generel forordning om databeskyttelse (GDPR). Fjernelse af personlige data omfatter fjernelse af alle personlige data og systemgenererede logge, undtagen oplysninger om overvågningslog.

#### <a name="manage-data-subject-delete-requests"></a>Administrere anmodninger om datasletning fra den registrerede

Customer Insights indeholder følgende funktioner i produktet, hvor du kan slette personlige data for en bestemt kunde eller bruger:

- **Administrere sletteanmodninger om kundedata**: Kundedata i Customer Insights indtages fra oprindelige datakilder uden for Customer Insights. Alle GDPR-sletteanmodninger skal udføres i den oprindelige datakilde.
- **Administrér sletteanmodninger om Customer Insights-brugerdata**: Data til brugere er oprettet af Customer Insights. Alle GDPR-sletteanmodninger skal udføres i Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Administrere sletteanmodninger for kundedata

En Customer Insights-administrator kan følge disse trin for at fjerne de kundedata, der er blevet slettet i datakilden:

1. Log på Dynamics 365 Customer Insights.
2. Gå til **Data** > **Datakilder**
3. For hver datakilde på listen, der indeholder slettede kundedata:
   1. Vælg den lodrette ellipse (&vellip;), og vælg derefter **Opdater**.
   2. Tjek statussen for datakilden under **Status**. En markering betyder, at opdateringen lykkedes. En advarselstrekant betyder, at noget gik galt. Hvis der vises en advarselstrekant, skal du kontakte D365CI@microsoft.com.

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

## <a name="consent-management-preview"></a>Samtykkeadministration (forhåndsversion)

Funktionen til administration af samtykke indsamler ikke brugerdata direkte. Den importerer og behandler kun samtykkedata, der leveres af brugere i andre programmer.

Hvis du vil fjerne samtykkedata om bestemte brugere, skal du fjerne dem i de datakilder, der er tilgængelige for administration af samtykke. Når du har datakilde, slettes de fjernede data også i Samtykkecenter. Programmer, der bruger objektet til samtykke, sletter også data, der er fjernet på kilden efter en [opdatering](system.md#refresh-processes). Vi anbefaler, at du opdaterer datakilder hurtigt efter at have reageret på en forespørgsel om dataanmodning for at fjerne brugerens data fra alle andre processer og programmer.

[!INCLUDE [footer-include](includes/footer-banner.md)]