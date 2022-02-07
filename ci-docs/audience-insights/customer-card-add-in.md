---
title: Tilføjelsesprogrammet Kundekort til Dynamics 365-apps (indeholder video)
description: Vis data fra målgruppeindsigt i Dynamics 365-apps med dette tilføjelsesprogram.
ms.date: 12/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
---

# <a name="customer-card-add-in-preview"></a>Tilføjelsesprogrammet Kundekort (eksempel)



Få en 360-grads visning af dine kunder direkte i Dynamics 365-apps. Når tilføjelsesprogrammet Kundekort er installeret i en understøttet Dynamics 365-app, kan du vælge at få vist kundeprofilfelter, indsigt og aktivitetstidslinje. Tilføjelsesprogrammet henter data fra Customer Insights, uden at det påvirker dataene i den tilknyttede Dynamics 365-app.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Forudsætninger

- Tilføjelsesprogrammet fungerer kun med Dynamics 365-modelbaserede apps, f.eks. Sales eller Customer Service, version 9.0 og nyere.
- Hvis dine Dynamics 365-data skal knyttes til kundeprofilers målgruppeindsigt, anbefaler vi, at de [indtages fra Dynamics 365-appen ved hjælp af Microsoft Dataverse-connectoren](connect-power-query.md). Hvis du bruger en anden metode til at indtage Dynamics 365-kontakter (eller firmaer), skal du kontrollere, at feltet `contactid` (eller `accountid`) er angivet som den [primære nøgle for den pågældende datakilde i tilknytningstrinnene i processen til samling af data](map-entities.md#select-primary-key-and-semantic-type-for-attributes). 
- Alle Dynamics 365-brugere af Kundekort-tilføjelsesprogrammet skal [tilføjes som brugere](permissions.md) i målgruppeindsigt for at kunne se dataene.
- [Konfigurerede søge- og filterfunktioner](search-filter-index.md) i målgruppeindsigt kræves for at få opslag af data til at fungere.
- Hvert tilføjelsesprograms kontrolelement afhænger af specifikke data i målgruppeindsigt. Nogle data og kontrolelementer er kun tilgængelige i miljøer af bestemte typer. Du får besked i konfigurationen af tilføjelsesprogrammet, hvis et kontrolelement ikke er tilgængeligt på grund af den valgte miljøtype. Få mere at vide om [miljøanvendelser](work-with-business-accounts.md).
  - **Kontrolelementet Måling**: Kræver [konfigurerede målinger](measures.md) af typen kundeattributter.
  - **Intelligenskontrol**: Kræver data genereret ved hjælp af [forudsigelser eller brugerdefinerede modeller](predictions-overview.md).
  - **Kontrolelementet Kundeoplysninger**: Alle felter fra profilen er tilgængelige i den samlede kundeprofil.
  - **Kontrolelementet Forbedring**: Kræver aktive [forbedringer](enrichment-hub.md), der anvendes på kundeprofiler. Korttillægget understøtter disse forbedringer. [Mærker](enrichment-microsoft.md), der er leveret af Microsoft, [Interesser](enrichment-microsoft.md), der leveres af Microsoft, og [Office-engagementdata](enrichment-office.md), der leveres af Microsoft.
  - **Kontrolelementet Kontakter**: Kræver definition af semantisk objekt af typen kontakter.
  - **Kontrolelementet Tidslinje**: Kræver [konfigurerede aktiviteter](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installere tilføjelsesprogrammet Kundekort

Tilføjelsesprogrammet Kundekort er en løsning til Customer Engagement-apps i Dynamics 365. Hvis du vil installere løsningen, skal du gå til AppSource og søge efter **Dynamics-kundekort**. Vælg [Tilføjelsesprogrammet Kundekort i AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview), og vælg **Hent det nu**.

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

Afhængigt af scenariet kan du vælge at føje kontrolelementer til enten formularen **Kontakt** eller formularen **Firma**. Hvis dit miljø for målgruppeindsigt er til forretningskonti, anbefales det, at du føjer kontrolelementerne til formularen Firma. I det tilfælde skal du erstatte "kontakt" i nedenstående trin med "firma".

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
