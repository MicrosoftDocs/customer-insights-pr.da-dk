---
title: Tilføjelsesprogrammet Kundekort til Dynamics 365-apps (forhåndsversion) (indeholder video)
description: Vis kundeprofildata fra Customer Insights i Dynamics 365-apps med dette tilføjelsesprogram.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8b3b6a0d54b80d7df454e9dc925f14cc3c39684c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194916"
---
# <a name="customer-card-add-in-for-dynamics-365-apps-preview"></a>Tilføjelsesprogram til kundekort for Dynamics 365-apps (forhåndsversion)

Få en 360-grads visning af dine kunder direkte i Dynamics 365-apps. Når tilføjelsesprogrammet Kundekort er installeret i en understøttet Dynamics 365-app, kan du vælge at få vist kundeprofilfelter, indsigt og aktivitetstidslinje. Tilføjelsesprogrammet henter data fra Customer Insights, uden at det påvirker dataene i den tilknyttede Dynamics 365-app.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Forudsætninger

- Dynamics 365-modelbaserede apps, f.eks. Sales eller Customer Service, version 9.0 og nyere.
- Hvis dine Dynamics 365-data skal knyttes til Customer Insights-kundeprofilers, anbefaler vi, at de [indtages fra Dynamics 365-appen ved hjælp af Microsoft Dataverse-connectoren](connect-power-query.md). Hvis du bruger en anden metode til at indtage Dynamics 365-kontakter (eller firmaer), skal du kontrollere, at feltet `contactid` (eller `accountid`) er angivet som den [primære nøgle for den pågældende datakilde i tilknytningstrinnene i processen til samling af data](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Alle Dynamics 365-brugere af Kundekort-tilføjelsesprogrammet skal [tilføjes som brugere](permissions.md) i Customer Insights for at se dataene.
- [Konfigurerede søge- og filtreringsfunktioner](search-filter-index.md) i Customer Insights.
- Hvert tilføjelsesprograms kontrolelement afhænger af specifikke data i Customer Insights. Nogle data og kontrolelementer er kun tilgængelige i miljøer af bestemte typer. Du får besked i konfigurationen af tilføjelsesprogrammet, hvis et kontrolelement ikke er tilgængeligt på grund af den valgte miljøtype. Få mere at vide om [miljøanvendelser](work-with-business-accounts.md).
  - **Kontrolelementet Måling**: kræver [konfigurerede kundeattributmålinger](measures.md).
  - **Intelligenskontrol**: kræver data genereret ved hjælp af [forudsigelser eller brugerdefinerede modeller](predictions-overview.md).
  - **Kontrolelementet Kundeoplysninger**: viser alle felter fra profilen er tilgængelige i den samlede kundeprofil.
  - **Kontrolelementet Forbedring**: kræver aktive [forbedringer](enrichment-hub.md), der anvendes på kundeprofiler. Korttillægget understøtter disse forbedringer. [Mærker](enrichment-microsoft.md), der er leveret af Microsoft, [Interesser](enrichment-microsoft.md), der leveres af Microsoft, og [Office-engagementdata](enrichment-office.md), der leveres af Microsoft.
  - **Kontrolelementet Kontakter**: kræveren kontakt af semantisk objekttype.
  - **Kontrolelementet Tidslinje**: kræver [konfigurerede aktiviteter](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installere tilføjelsesprogrammet Kundekort

Tilføjelsesprogrammet Kundekort er en løsning til Customer Engagement-apps i Dynamics 365. Installere løsningen:

1. Gå til AppSource, og søg efter **Dynamics Customer Card**.

1. Vælg [Tilføjelsesprogrammet Kundekort i AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview), og vælg **Hent det nu**.

Det kan være nødvendigt at logge på med dine administrator-legitimationsoplysninger, når Dynamics 365-appen skal installere løsningen. Det kan tage et stykke tid, før løsningen er installeret i dit miljø.

## <a name="configure-the-customer-card-add-in"></a>Konfigurere tilføjelsesprogrammet Kundekort

1. Som administrator kan du gå til sektionen **Indstillinger** i Dynamics 365 og vælge **Løsninger**.

1. Vælg linket **Vist navn** til løsningen **tilføjelsesprogrammet Kundekort til Dynamics 365 Customer Insights (eksempel)**.

   > [!div class="mx-imgBorder"]
   > ![Vælge vist navn.](media/select-display-name.png "Vælg vist navn.")

1. Vælg **Log på**, og angiv legitimationsoplysningerne for den administratorkonto, du bruger til at konfigurere Customer Insights.

   > [!NOTE]
   > Kontrollér, at browserens blokering af pop op-vinduer ikke blokerer for godkendelsesvinduet, når du vælger knappen **Log på**.

1. Vælg det Customer Insights-miljø, du vil hente data fra.

1. Definer felttilknytningen til poster i Dynamics 365-appen. Afhængigt af dine data i Customer Insights kan du vælge at tilknytte følgende muligheder:
   - Hvis du vil tilknytte en kontaktperson, skal du vælge det felt i kundeobjektet, der stemmer overens med id for dit kontaktpersonsobjekt.
   - Hvis du vil tilknytte en konto, skal du vælge det felt i kundeobjektet, der stemmer overens med id for dit kontoobjekt.

   > [!div class="mx-imgBorder"]
   > ![Feltet Kontakt-id.](media/contact-id-field.png "Feltet Kontakt-id.")

1. Vælg **Gem konfiguration** for at gemme indstillingerne.

1. Derefter skal du tildele sikkerhedsroller i Dynamics 365, så brugerne kan tilpasse og få vist kundekortet. I Dynamics 365 skal du gå til **Indstillinger** > **Sikkerhed** > **Brugere**. Vælg de brugere, hvis brugerroller der skal redigeres, og vælg **Administrer roller**.

1. Tildel rollen **Customer Insights-korttilpasser** til brugere, der skal tilpasse det indhold, der vises på kortet, for hele organisationen.

## <a name="add-customer-card-controls-to-forms"></a>Tilføj Kundekort-kontrolelementer til formularer

Afhængigt af scenariet kan du vælge at føje kontrolelementer til enten formularen **Kontakt** eller formularen **Firma**. Hvis dit miljø for Customer Insights er til forretningskonti, anbefales det, at du føjer kontrolelementerne til formularen Firma. I det tilfælde skal du erstatte "kontakt" i nedenstående trin med "firma".

1. Hvis du vil føje Kundekort-kontrolelementer til formularen Kontakt, skal du gå til **Indstillinger** > **Tilpasninger** i Dynamics 365.

1. Vælg **Tilpas systemet**.

1. Gå til objektet **Kontakt**, udvid det, og vælg **Formularer**.

1. Vælg den kontaktformular, hvor du vil tilføje kontrolelementerne for Kundekort.

    > [!div class="mx-imgBorder"]
    > ![Vælge formularen Kontakt.](media/contact-active-forms.png "Vælg formularen Kontakt.")

1. Hvis du vil tilføje et kontrolelement, skal du i formulareditoren trække et hvilket som helst felt fra **Feltoversigt** til det sted, hvor du vil placere kontrolelementet.

1. Vælg feltet i den formular, du lige har tilføjet, og vælg **Skift egenskaber**.

1. Gå til fanen **Kontrolelementer**, og vælg **Tilføj kontrolelement**. Vælg et af de tilgængelige brugerdefinerede kontrolelementer, og vælg **Tilføj**.

1. Fjern markeringen i afkrydsningsfeltet **Vis etiket på formularen**, i dialogboksen **Feltegenskaber**.

1. Vælg indstillingen **Internet** for kontrolelementet. Vælg den type forbedring, du vil have vist, ved at konfigurere feltet **Forbedring**. Tilføj et særskilt forbedringskontrolelement for hver forbedringstype.

1. Vælg **Gem** og **Publicer** for at publicere den opdaterede kontaktpersonformular.

1. Gå til den publicerede kontaktformular. Du kan se det netop tilføjede kontrolelement. Det kan være nødvendigt at logge på, første gang du bruger det.

1. Hvis du vil tilpasse det, du vil have vist på det brugerdefinerede kontrolelement, skal du vælge knappen Rediger i øverste højre hjørne.

## <a name="upgrade-customer-card-add-in"></a>Opgradere tilføjelsesprogrammet Kundekort

Tilføjelsesprogrammet Kundekort opgraderes ikke automatisk. Hvis du vil opgradere til den nyeste version, skal du følge disse trin i Dynamics 365-appen, hvor tilføjelsesprogrammet er installeret.

1. Gå til **Indstillinger** > **Tilpasning** og vælg **Løsninger** i Dynamics 365-appen.

1. I tabellen over tilføjelsesprogrammer skal du kigge efter **CustomerInsightsCustomerCard** og markere rækken.

1. Vælg **Anvend løsningsopgradering** på handlingslinjen.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Opgradere løsningen i området Tilpasning i Dynamics 365-apps.":::

1. Når du har startet opgraderingsprocessen, kan du se en indlæsningsindikator, indtil opgraderingen er fuldført. Hvis der ikke findes en nyere version, vises der en fejlmeddelelse i opgraderingen.

## <a name="troubleshooting"></a>Fejlfinding

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Kontrolelementer fra tilføjelsesprogrammet Kundekort kan ikke finde data

**Problem:**

Selv med korrekt konfigurerede id-felter kan kontrolelementerne ikke finde data til kunder.  

**Løsning:**

1. Kontrollér, at du har konfigureret tilføjelsesprogrammet Kort i henhold til instruktionerne: [Konfiguration af kundekort-tilføjelsesprogrammet](#configure-the-customer-card-add-in)

1. Gennemse konfigurationen af dataindtagelse. Rediger datakilde til Dynamics 365-systemet, som indeholder kontakt-id'et GUID. Hvis der vises et GUID for kontakt-id'et med store bogstaver i Power Query-editoren, skal du prøve følgende trin:
    1. Rediger datakilde for at åbne datakilde i Power Query-editor.
    1. Vælg kolonnen for kontakt-id.
    1. Vælg **Transformér** i overskriftslinjen for at få vist tilgængelige handlinger.
    1. Vælg **små bogstaver**. Kontrollér, om GUID'er i tabellen nu er med små bogstaver.
    1. Gem datakilden.
    1. Kør dataindtagelse, samling og downstream-processer for at overføre ændringerne til GUID'et.

Når systemet har fuldført hele opdateringen, skal kontrolelementerne til tilføjelsesprogrammet Til kundekort vise de forventede data.

[!INCLUDE [footer-include](includes/footer-banner.md)]
