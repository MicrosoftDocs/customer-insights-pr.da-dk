---
title: Forbedre kundeprofiler med data fra Microsoft Office 365
description: Brug beskyttede data fra Microsoft Office for at forbedre dine kundeprofiler med engagementsdata.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a30e09b5ed491c8d36019b5f0d35e0a2f7a0199c
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/03/2021
ms.locfileid: "7889748"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Forbedre kundeprofiler med engagementsdata (prøveversion)

Brug data fra Microsoft Office 365 til at forbedre dine kundekontoprofiler med indsigt i engagementer via Office 365-apps. Engagementsdataene består af mail- og mødeaktivitet, der aggregeres på kontoniveau. F.eks. antallet af mails fra et forretningskonto eller antallet af møder med kontoen. Der er ingen data om de enkelte brugere tilgængelige. 

Denne forbedring er kun tilgængelig i følgende områder: Storbritannien, Europa, Nordamerika.

## <a name="prerequisites"></a>Forudsætninger

Hvis du vil konfigurere forbedringen, skal følgende forudsætninger være opfyldt:

- Du har en aktiv Office 365-skylicens.
- Du har [samlet kundeprofiler](customer-profiles.md) baseret på [forretningskonti](work-with-business-accounts.md)..
- Dit Customer Insights-miljø skal have en [Microsoft Dataverse-organisation tilknyttet](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Du har [administrator](permissions.md#administrator)-tilladelser.
- Du har eller kan få dit samtykke fra din Office 365-lejeradministrator at bruge Office 365-data til at give **indblik for organisationen** i Dynamics 365-programmer.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring** i målgruppeindsigt.

1. Gå til fanen **Opdag**, og vælg **Gør mine data bedre** i feltet **Kontoengagement**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Firmaengagement-felt.":::
   
1. Vælg **Næste** i **oversigtstrinnet**, og angiv e-mail-adresser fra din organisation, som Office-data skal aggregeres for. Det er kun data fra de angivne e-mail-adresser, der behandles med henblik på relevant kommunikation. Den bedste fremgangsmåde er at bruge e-mail-grupper, f.eks. *USA-salgsteam*, som let administreres i Office 365. Antallet af e-mailadresser i grupperne løses og vises. Det samlede antal e-mailadresser skal være mindst 2 og må ikke være større end 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-mailadresser for firmaengagement.":::

1. Gennemse erklæringen om samtykke, markér afkrydsningsfeltet **Jeg accepterer**, og vælg **Næste**.

1. Vælg **Næste**, og vælg kundedatasættet.

1. Tilknyt feltet med kontakt-e-mail-adressen, og vælg **Næste**.

1. Gennemse forbedringen af konfigurationen, giv forbedringen et navn og vælg **Gem forbedring** for at gemme forbedringen.

## <a name="office-365-tenant-administrator-consent"></a>Office 365-lejeradministratorsamtykke

Der skal bruges samtykke fra en Office 365-lejeradministrator for at aktivere funktionen. Der sendes en mail til Office 365-lejeradministratorerne, når forbedringen gemmes, og de bliver bedt om at gennemgå og give deres samtykke til, at Dynamics 365-programmer bruger virksomhedens Office 365-data til at give **indsigt til organisationen**. Office 365-lejeadministratoren også acceptere direkte i deres Office 365-administrationskonsol ved at vælge **Indblik for organisationen**.

## <a name="running-the-enrichment-for-the-first-time"></a>Kørsel af forbedring første gang

Når forbedringen startes for første gang, efter at Office 365-lejeadministratoren har givet sit samtykke, starter overførslen af data fra Office 365. Denne proces kan tage noget tid. Den første forbedring kører efter planen med en forsinkelse på seks timer. Du kan se det antal dage, dataene dækker, på siden Oversigt over firmaengagement, når gennemgangen er afsluttet. Med en stor datamængde kan du køre programmet igen efter et par dage. den sikrer, at dataene er fuldført for hele tidsvinduet, som er et år.

Vælg **Kør** på konfigurationssiden for firmaengagement for at starte processen. Derudover kan du gøre det muligt for systemet at køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab). Problemet køres som standard én gang om ugen.

Afhængigt af størrelsen på dine Office-data kan det tage flere timer, før en kørsel af en bruger kan fuldføres.

Når du kører en produktprøve, behandler Microsoft dataene inden for Office 365-grænsen for overholdelse for at oprette samlet indsigt, der derefter føjes til dit Customer Insights-miljø. Ingen data på individuelt niveau (f.eks. brødteksten i en e-mail eller kalenderinvitation) bliver tilgængelige for brugere af Customer Insights. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Forbedringsresultater

Når processen er kørt, kan du gå til **Mine forbedringer** for at gennemgå resultaterne af forbedringerne. Du kan se det samlede antal forbedrede kunder og en oversigt over resultaterne. Det omfatter antallet af behandles mails og møder, antallet af dage, hvor data er blevet aggregeret, og meget mere.

Du kan også finde et diagram med antallet af forbedrede kunder over tid og en forhåndsversion af forbedrede data.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Eksempel på resultater efter kørsel af en forbedringsproces.":::

Alle data aggregeres op til kontoniveauet. Der beregnes et engagementspoint, som varierer fra 0 til 100, for hvert firma. Engagementspointet er et sammensat mål for firmaengagementet på tværs af mails og møder i forhold til dine andre firmaer. Følgende liste indeholder de aggregerede data, som indgår i firmaengagementet:



| Data                                                                              | Kolonnenavn                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Engagementsscore                                                                  |  EngagementScore                         |
| Antal mails til konto                                                       |  NoOfEmails_ToAccount                    |
| Antal mails fra konto                                                     |  NoOfEmails_FromAccount                  | 
| Antal møder, som er iværksat af kunden                                           |  NoOfMeetings_FromAccount                | 
| Antal møder, som er iværksat af din organisation                                 |  NoOfMeetings_ToAccount                  | 
| Antal personer fra organisationen, der deltager i møder med firma                  |  NoOfContactsInvolved_Meetings           | 
| Antal personer fra organisationen, der deltager i e-mailsamtaler med firma       |  NoOfContactsInvolved_Emails             | 
| Antal personer fra firmaet, der deltager i møder med organisationen                  |  NoOfAccountContactsInvolved_Meetings    | 
| Antal personer fra firmaet, der deltager i e-mailsamtaler med din organisation       |  NoOfAccountContactsInvolved_Emails      | 
| Startdato for engagement (første mail eller møde i dataene)                        |  EngagementStartDate                     | 
| Dage siden sidste e-mail                                                             |  DaysSinceLastEmail                      | 
| Dage siden sidste møde                                                           |  DaysSinceLastMeeting                    | 
| Gennemsnitlig varighed af møder                                                      |  AverageDuration_Of_Meetings             | 
| Gennemsnitlig varighed for e-mailsvar fra firma                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Aggregeringsstartdato                                                            |  AggregationStartDate                    | 
| Aggregeringsniveau (år, måned eller uge)                                          |  AggregationLevel                        | 


Gennemse de forbedrede data ved at vælge **Se mere** i forhåndsversionsafsnittet. Objektet *Office* åbnes. Du kan også finde det objekt, der er angivet i gruppen **Forbedring** i **Data** > **Objekter**. Du kan også finde det *Office_UserEntity*, som indeholder Active Directory-ip-adresserne for de e-mail-adresser, du har valgt under konfigurationen af forbedringen 

## <a name="see-enrichment-data-on-the-customer-card"></a>Se forbedringsdata på kundekortet

Firmaengagement kan også ses på de enkelte kundekort. Gå til **Kunder**, og vælg en kundeprofil. I kundekortet kan du se kontoens engagementspoint, det samlede antal mails og det samlede antal møder, der er samlet i løbet af det seneste år. Du kan også finde diagrammer, der viser e-mail- og mødeoversigten.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kundekort med forbedrede data.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Oprettelse af målgrupper og mål baseret på forbedrede data

De forbedrede data kan bruges til at oprette segmenter og mål som beskrevet nedenfor. Et segment, der f.eks. indeholder alle kunder, der har en værdi af mere end 60 *dage siden seneste mail* og *dage siden sidste møde*. Dette segment indeholder gamle firmaer, som du kan prøve at genaktivere. 

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
