---
title: Forbedre kundeprofiler med data fra Microsoft Office 365
description: Brug beskyttede data fra Microsoft Office for at forbedre dine kundeprofiler med engagementsdata.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954126"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Forbedre kundeprofiler med engagementsdata (prøveversion)

Brug data fra Microsoft Office 365 til at forbedre dine kundekontoprofiler med indsigt i engagementer via Office 365-apps. Engagementsdataene består af mail- og mødeaktivitet, der aggregeres på kontoniveau. F.eks. antallet af mails fra et forretningskonto eller antallet af møder med kontoen. Der er ingen data om de enkelte brugere tilgængelige.

## <a name="supported-countries-or-regions"></a>Understøttede lande eller områder

Vi understøtter i øjeblikket følgende områder: Storbritannien, Canada, Europa og USA.

## <a name="prerequisites"></a>Forudsætninger

- En aktiv Office 365-skylicens.
- [Samlede kundeprofiler](customer-profiles.md) baseret på [firmaer](work-with-business-accounts.md).
- En [Microsoft Dataverse-organisation tilknyttet](create-environment.md#step-3-connect-to-microsoft-dataverse) i dit Customer Insights-miljø.
- [Administratortilladelser](permissions.md#admin).
- Samtykke fra din Office 365-lejeradministrator til at bruge Office 365-data til at give **Indsigt i organisationen** i Dynamics 365-programmer.

## <a name="configure-the-enrichment"></a>Konfiguration af forbedring

1. Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.

1. Vælg **Forbedring af data** i feltet **Kontoengagement**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Firmaengagement-felt.":::

1. Gennemse oversigten, og vælg derefter **Næste**.

1. Angiv e-mailadresser fra din organisation, som Office-data skal aggregeres for. Det er kun data fra de angivne e-mail-adresser, der behandles med henblik på relevant kommunikation. Den bedste fremgangsmåde er at bruge e-mailgrupper, f.eks. *USA-salgsteam*, som kan administreres i Office 365. Antallet af e-mailadresser i grupperne løses og vises. Det samlede antal e-mailadresser skal være mindst 2 og må ikke være større end 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="E-mailadresser for firmaengagement.":::

1. Gennemse og giv dit samtykke til [Office 365-lejeradministrator](#office-365-tenant-administrator-consent) ved at vælge **Jeg accepterer**.

1. Vælg **Næste**.

1. Vælg **Kontakt datasæt**, og vælg den profil, der skal forbedres. Vælg **Næste**.

1. Tilknyt feltet med kontakt-e-mail-adressen, og vælg **Næste**.

1. Angiv et **Navn** til forbedringen og **outputobjektet**.

1. Vælg **Gem valgmuligheder**, når du har gennemset dine valg.

1. Vælg **Luk** for at vende tilbage til siden **Forbedringer**.

### <a name="office-365-tenant-administrator-consent"></a>Office 365-lejeradministratorsamtykke

Der skal bruges samtykke fra en Office 365-lejeradministrator for at aktivere funktionen. Der sendes en mail til Office 365-lejeradministratorerne, når forbedringen gemmes, og de bliver bedt om at gennemgå og give deres samtykke til, at Dynamics 365-programmer bruger virksomhedens Office 365-data til at give **indsigt til organisationen**. Office 365-lejeadministratoren også acceptere direkte i deres Office 365-administrationskonsol ved at vælge **Indblik for organisationen**.

## <a name="running-the-enrichment-for-the-first-time"></a>Kørsel af forbedring første gang

Når forbedringen startes for første gang, efter at Office 365-lejeadministratoren har givet sit samtykke, starter overførslen af data fra Office 365. Denne proces kan tage noget tid. Den første forbedring kører efter planen med en forsinkelse på seks timer. Du kan se det antal dage, dataene dækker, på siden Oversigt over firmaengagement, når gennemgangen er afsluttet. Med en stor datamængde kan du køre programmet igen efter et par dage. Det sikrer, at dataene er fuldført for hele tidsvinduet, som er et år.

Afhængigt af størrelsen på dine Office-data kan det tage flere timer, før en kørsel af en bruger kan fuldføres.

Når du kører en produktprøve, behandler Microsoft dataene inden for Office 365-grænsen for overholdelse for at oprette samlet indsigt, der derefter føjes til dit Customer Insights-miljø. Ingen data på individuelt niveau (f.eks. brødteksten i en e-mail eller kalenderinvitation) bliver tilgængelige for brugere af Customer Insights.

Vælg **Kør** for at starte forbedringsprocessen.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Forbedringsresultater

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Dette er objektet *Office*. *Office_UserEntity* indeholder Active Directory-ip-adresserne for de e-mail-adresser, du har valgt under konfigurationen af forbedringen.

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

## <a name="see-enrichment-data-on-the-customer-card"></a>Se forbedringsdata på kundekortet

Firmaengagement kan også ses på de enkelte kundekort. Gå til **Kunder**, og vælg en kundeprofil. I kundekortet kan du se kontoens engagementspoint, det samlede antal mails og det samlede antal møder, der er samlet i løbet af det seneste år. Du kan også finde diagrammer, der viser e-mail- og mødeoversigten.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kundekort med forbedrede data.":::

## <a name="next-steps"></a>Næste trin

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Et segment, der f.eks. indeholder alle kunder, der har en værdi af mere end 60 *dage siden seneste mail* og *dage siden sidste møde*. Dette segment indeholder gamle firmaer, som du kan prøve at genaktivere.

[!INCLUDE [footer-include](includes/footer-banner.md)]
