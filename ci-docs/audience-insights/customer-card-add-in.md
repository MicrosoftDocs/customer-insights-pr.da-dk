---
title: Tilføjelsesprogrammet Kundekort til Dynamics 365-apps
description: Vis data fra målgruppeindsigt i Dynamics 365-apps med dette tilføjelsesprogram.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0f6c922104df229980b308136a4d764938121b35d6d744f41b1530bdb5515e7f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032981"
---
# <a name="customer-card-add-in-preview"></a>Tilføjelsesprogrammet Kundekort (eksempel)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Få en 360-grads visning af dine kunder direkte i Dynamics 365-apps. Når tilføjelsesprogrammet Kundekort er installeret i en understøttet Dynamics 365-app, kan du vælge at få vist demografi, indsigt og aktivitetstidslinjer. Tilføjelsesprogrammet henter data fra Customer Insights, uden at det påvirker dataene i den tilknyttede Dynamics 365-app. 

## <a name="prerequisites"></a>Forudsætninger

- Tilføjelsesprogrammet fungerer kun med Dynamics 365-modelbaserede apps, f.eks. Sales eller Customer Service, version 9.0 og nyere.
- Hvis dine Dynamics 365-data skal knyttes til kundeprofilers målgruppeindsigt, skal de [indtages fra Dynamics 365-appen ved hjælp af Microsoft Dataverse connectoren](connect-power-query.md).
- Alle Dynamics 365-brugere af Kundekort-tilføjelsesprogrammet skal [tilføjes som brugere](permissions.md) i målgruppeindsigt for at kunne se dataene.
- [Konfigurerede søge- og filterfunktioner](search-filter-index.md) i målgruppeindsigt kræves for at få opslag af data til at fungere.
- Hvert tilføjelsesprograms kontrolelement afhænger af specifikke data i målgruppeindsigt:
  - Målingskontrol: Kræver [konfigurerede målinger](measures.md).
  - Intelligenskontrol: Kræver data genereret ved hjælp af [forudsigelser](predictions.md) eller [brugerdefinerede modeller](custom-models.md).
  - Demografisk kontrolelement: Demografiske felter (f.eks. alder eller køn) er tilgængelige i den samlede kundeprofil.
  - Forbedringskontrol: Kræver aktive [forbedringer](enrichment-hub.md), der anvendes på kundeprofiler.
  - Tidslinjekontrol: Kræver [konfigurerede aktiviteter](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installere tilføjelsesprogrammet Kundekort

Tilføjelsesprogrammet Kundekort er en løsning til Customer Engagement-apps i Dynamics 365. Hvis du vil installere løsningen, skal du gå til AppSource og søge efter **Dynamics-kundekort**. Vælg [Tilføjelsesprogrammet Kundekort i AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview), og vælg **Hent det nu**.

Det kan være nødvendigt at logge på med dine administrator-legitimationsoplysninger, når Dynamics 365-appen skal installere løsningen.

Det kan tage et stykke tid, før løsningen er installeret i dit miljø.

## <a name="configure-the-customer-card-add-in"></a>Konfigurere tilføjelsesprogrammet Kundekort

1. Som administrator kan du gå til sektionen **Indstillinger** i Dynamics 365 og vælge **Løsninger**.

1. Vælg linket **Vist navn** til løsningen **tilføjelsesprogrammet Kundekort til Dynamics 365 Customer Insights (eksempel)**.

   > [!div class="mx-imgBorder"]
   > ![Vælge vist navn.](media/select-display-name.png "Vælge vist navn")

1. Vælg **Log på**, og angiv legitimationsoplysningerne for den administratorkonto, du bruger til at konfigurere Customer Insights.

   > [!NOTE]
   > Kontrollér, at browserens blokering af pop op-vinduer ikke blokerer for godkendelsesvinduet, når du vælger knappen **Log på**.

1. Vælg det Customer Insights-miljø, du vil hente data fra.

1. Definer felttilknytningen til poster i Dynamics 365-appen. Afhængigt af dine data i Customer Insights kan du vælge at tilknytte følgende muligheder:
   - Hvis du vil tilknytte en kontaktperson, skal du vælge det felt i kundeobjektet, der stemmer overens med id for dit kontaktpersonsobjekt.
   - Hvis du vil tilknytte en konto, skal du vælge det felt i kundeobjektet, der stemmer overens med id for dit kontoobjekt.

   > [!div class="mx-imgBorder"]
   > ![Feltet Kontakt-id.](media/contact-id-field.png "Feltet Kontakt-id")

1. Vælg **Gem konfiguration** for at gemme indstillingerne.

1. Derefter skal du tildele sikkerhedsroller i Dynamics 365, så brugerne kan tilpasse og få vist kundekortet. I Dynamics 365 skal du gå til **Indstillinger** > **Sikkerhed** > **Brugere**. Vælg de brugere, hvis brugerroller der skal redigeres, og vælg **Administrer roller**.

1. Tildel rollen **Customer Insights-korttilpasser** til brugere, der skal tilpasse det indhold, der vises på kortet, for hele organisationen.

## <a name="add-customer-card-controls-to-forms"></a>Tilføj Kundekort-kontrolelementer til formularer
  
1. Hvis du vil føje Kundekort-kontrolelementer til formularen Kontakt, skal du gå til **Indstillinger** > **Tilpasninger** i Dynamics 365.

1. Vælg **Tilpas systemet**.

1. Gå til objektet **Kontakt**, udvid det, og vælg **Formularer**.

1. Vælg den kontaktformular, hvor du vil tilføje kontrolelementerne for kundekortet.

    > [!div class="mx-imgBorder"]
    > ![Vælge formularen Kontakt.](media/contact-active-forms.png "Vælge formularen Kontakt")

1. Hvis du vil tilføje et kontrolelement, skal du i formulareditoren trække et hvilket som helst felt fra **Feltoversigt** til det sted, hvor du vil placere kontrolelementet.

1. Vælg det felt i den formular, du lige har tilføjet, og vælg **Skift egenskaber**.

1. Gå til fanen **Kontrolelementer**, og vælg **Tilføj kontrolelement**. Vælg et af de tilgængelige brugerdefinerede kontrolelementer, og vælg **Tilføj**.

1. Fjern markeringen i afkrydsningsfeltet **Vis etiket på formularen**, i dialogboksen **Feltegenskaber**.

1. Vælg indstillingen **Internet** for kontrolelementet. Vælg den type forbedring, du vil have vist, ved at konfigurere feltet **Forbedring**. Tilføj et særskilt forbedringskontrolelement for hver forbedringstype.

1. Vælg **Gem** og **Publicer** for at publicere den opdaterede kontaktpersonformular.

1. Gå til den publicerede kontaktformular. Du kan se det netop tilføjede kontrolelement. Det kan være nødvendigt at logge på, første gang du bruger det.

1. Hvis du vil tilpasse det, du vil have vist på det brugerdefinerede kontrolelement, skal du vælge knappen Rediger i øverste højre hjørne.

## <a name="upgrade-customer-card-add-in"></a>Opgradere tilføjelsesprogrammet Kundekort
Tilføjelsesprogrammet Kundekort opgraderes ikke automatisk. Hvis du vil opgradere til den nyeste version, skal du følge denne procedure i den Dynamics 365-app, hvor tilføjelsesprogrammet er installeret.

1. Gå til **Indstillinger** > **Tilpasning** og vælg **Løsninger** i Dynamics 365-appen.

1. I tabellen over tilføjelsesprogrammer skal du kigge efter **CustomerInsightsCustomerCard** og markere rækken.

1. Vælg **Anvend løsningsopgradering** på handlingslinjen.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Opgradere løsningen i området Tilpasning i Dynamics 365-apps.":::

1. Når du har startet opgraderingsprocessen, kan du se en indlæsningsindikator, indtil opgraderingen er fuldført. Hvis der ikke findes en nyere version, vises der en fejlmeddelelse i opgraderingen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
