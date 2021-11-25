---
title: DSR-anmodninger (Data Subject Rights) under GDPR | Microsoft Docs
description: Svar på DSR-anmodninger til muligheder i Dynamics 365 Customer Insights-målgruppen Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732673"
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


## <a name="engagement-insights-preview"></a>Engagementsindsigt (forhåndsversion)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Sletning og eksport af hændelsesdata, der indeholder oplysninger, der kan identificere slutbrugere

I følgende afsnit beskrives, hvordan du kan slette og eksportere hændelsesdata, der kan indeholde personlige data.

Slette eller eksportere eksportdata:

1. Mærk hændelsesegenskaber, der indeholder data med personlige oplysninger.
2. Slette eller eksportere data, der er knyttet til bestemte værdier (f.eks. et angivet bruger-id).

#### <a name="tag-and-update-event-properties"></a>Mærke og opdatere hændelsesegenskaber

Personlige data er tagget på egenskabsniveau for hændelser. Du skal først mærke de egenskaber, der tages i betragtning til sletning eller eksport.

Hvis du vil markere en hændelsesegenskab som indeholdende personlige oplysninger, skal du følge disse trin:

1. Åbn det arbejdsområde, der indeholder hændelsen.

1. Gå til **Data** > **Hændelser** for at se listen over hændelser i det valgte arbejdsområde.
  
1. Vælg den hændelse, du vil mærke.

1. Vælg **Rediger egenskaber** for at åbne ruden med en liste over alle egenskaber for den valgte hændelse.
     
1. Vælg **...**, og vælg derefter **Rediger** for at åbne dialogboksen **Opdater egenskab**.

   ![Rediger hændelse.](engagement-insights/media/edit-event.png "Rediger hændelse")

1. Vælg **...** i øverste højre hjørne i vinduet **Opdater egenskab**, og vælg derefter feltet **Indeholder EUII**. Vælg **Opdater** for at gemme dine ændringerne.

   ![Gem dine ændringer.](engagement-insights/media/update-property.png "Gem dine ændringer")

   > [!NOTE]
   > Hver gang hændelsesskemaet ændres, eller du opretter en ny hændelse, anbefales det, at du evaluerer de tilknyttede hændelsesegenskaber og mærker eller untag dem som indeholdende personlige data, hvis det er nødvendigt.

#### <a name="delete-or-export-tagged-event-data"></a>Slette eller eksportere mærkede hændelsesdata

Hvis alle hændelsesegenskaber er blevet mærket korrekt som beskrevet i forrige trin, kan en miljøadministrator udstede en sletningsanmodning mod de kodede hændelsesdata.

Sådan administreres sletning eller eksportanmodninger i EUII

1. Gå til **Administration** > **Miljø** > **Indstillinger**.

1. Vælg **Administrer EUII** i sektionen **Administrer oplysninger, der kan identificere slutbrugere (EUII)**.

##### <a name="deletion"></a>Sletning

Til sletning kan du angive en liste over kommaseparerede bruger-id'er i sektionen **Slette de slutbrugere, der kan identificeres (EUII)**. Derefter sammenlignes disse -hændelser med alle mærkede hændelsesegenskaber for alle projekter i det aktuelle miljø via nøjagtig strengtilpasning. 

Hvis en egenskabsværdi svarer til et af de angivne id'er, slettes den tilknyttede hændelse permanent. Da handlingen er uigenkaldelig, skal du bekræfte sletningen, når du har valgt **Slet**.

##### <a name="export"></a>Export

Eksportprocessen er identisk med sletningsprocessen, når det drejer sig om at definere værdier for hændelsesegenskab i afsnittet **Eksportere slutbrugerens identificerbare oplysninger (EUII)**. Derudover skal du angive webadressen til **Azure Blob Storage** for at angive eksportdestinationen. Webadressen til Azure Blob skal omfatte en [SAS (Shared Access Signature)](/azure/storage/common/storage-sas-overview).

Når du har valgt **Eksportér**, eksporteres alle hændelser i det aktuelle team, der indeholder tilsvarende kodede egenskaber, til eksportdestinationen i CSV-format.

### <a name="good-practices"></a>Bedste praksis

* Prøv at undgå at sende hændelser, der indeholder personlige data.
* Hvis du har brug for at sende hændelser, der indeholder EUII-data, skal du begrænse antallet af hændelser og hændelsesegenskaber, der indeholder EUII-data. Ideelt set skal du begrænse dig selv til en sådan hændelse.
* Sørg for, at så få personer som muligt har adgang til de sendte personlige data.
* I forbindelse med hændelser, der indeholder personlige data, skal du sørge for at angive én egenskab til at sende et entydigt id, der nemt kan knyttes til en bestemt bruger (f.eks. et bruger-id). Det gør det nemmere at indsamle data og eksportere eller slette de rette data.
* Tag kun én egenskab pr. hændelse, så den indeholder personlige data. Ideelt set ét, der kun indeholder et entydigt id.
* Du skal ikke mærke egenskaber, der indeholder detaljerede værdier (f.eks. en hel brødtekst i anmodningen). Engagementsindsigtsfunktion bruger nøjagtig strengtilpasning, når det besluttes, hvilke hændelser der skal slettes eller eksporteres.

[!INCLUDE[footer-include](includes/footer-banner.md)]