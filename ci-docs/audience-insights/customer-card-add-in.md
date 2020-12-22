---
title: Installer og konfigurér tilføjelsesprogrammet Kundekort.
description: Installer og konfigurer tilføjelsesprogrammet Kundekort til Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644036"
---
# <a name="customer-card-add-in-preview"></a>Tilføjelsesprogrammet Kundekort (eksempel)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Få en 360-grads visning af dine kunder direkte i Dynamics 365-apps. Få vist demografiske oplysninger, indsigt og aktivitetstidslinjer med tilføjelsesprogrammet Kundekort.

## <a name="prerequisites"></a>Forudsætninger

- Dynamics 365-app (f.eks. Salgshub eller Kundeservicehub), version 9.0 og nyere med Unified Interface aktiveret.
- Kundeprofiler, [der er overført fra Dynamics 365-appen ved hjælp af Common Data Service](connect-power-query.md).
- Brugere af tilføjelsesprogrammet kundekort skal [tilføjes som brugere](permissions.md) i målgruppeindsigt.
- [Konfigurerede søge- og filtreringsfunktioner](search-filter-index.md).
- Demografisk kontrolelement: Demografiske felter, f. eks. alder eller køn, er tilgængelige i den samlede kundeprofil.
- Forbedringskontrol: Kræver aktive [forbedringer](enrichment-hub.md), der anvendes på kundeprofiler.
- Intelligent kontrol: Kræver data, der er genereret ved hjælp af Azure Machine Learning ([Forudsigelser](predictions.md) eller [Brugerdefinerede modeller](custom-models.md))
- Målingskontrol: Kræver [konfigurerede målinger](measures.md).
- Tidslinjekontrol: Kræver [konfigurerede aktiviteter](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installere tilføjelsesprogrammet Kundekort

Tilføjelsesprogrammet Kundekort er en løsning til Customer Engagement-apps i Dynamics 365. Hvis du vil installere løsningen, skal du gå til AppSource og søge efter **Dynamics-kundekort**. Vælg [Tilføjelsesprogrammet Kundekort i AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview), og vælg **Hent det nu**.

Det kan være nødvendigt at logge på med dine administrator-legitimationsoplysninger, når Dynamics 365-appen skal installere løsningen.

Det kan tage et stykke tid, før løsningen er installeret i dit miljø.

## <a name="configure-the-customer-card-add-in"></a>Konfigurere tilføjelsesprogrammet Kundekort

1. Som administrator kan du gå til sektionen **Indstillinger** i Dynamics 365 og vælge **Løsninger**.

1. Vælg linket **Vist navn** til løsningen **tilføjelsesprogrammet Kundekort til Dynamics 365 Customer Insights (eksempel)**.

   > [!div class="mx-imgBorder"]
   > ![Vælge vist navn](media/select-display-name.png "Vælge vist navn")

1. Vælg **Log på**, og angiv legitimationsoplysningerne for den administratorkonto, du bruger til at konfigurere Customer Insights.

   > [!NOTE]
   > Kontrollér, at browserens blokering af pop op-vinduer ikke blokerer for godkendelsesvinduet, når du vælger knappen **Log på**.

1. Vælg det miljø, du vil hente data fra.

1. Definer, hvilket felt der skal knyttes til poster i appen Dynamics 365.
   - Hvis du vil tilknytte en kontaktperson, skal du vælge det felt i kundeobjektet, der stemmer overens med id for dit kontaktpersonsobjekt.
   - Hvis du vil tilknytte en konto, skal du vælge det felt i kundeobjektet, der stemmer overens med id for dit kontoobjekt.

   > [!div class="mx-imgBorder"]
   > ![Feltet Kontakt-id](media/contact-id-field.png "Feltet Kontakt-id")

1. Vælg **Gem konfiguration** for at gemme indstillingerne.

1. Derefter skal du tildele sikkerhedsroller i Dynamics 365, så brugerne kan tilpasse og få vist kundekortet. I Dynamics 365 skal du gå til **Indstillinger** > **Sikkerhed** > **Brugere**. Vælg de brugere, hvis brugerroller der skal redigeres, og vælg **Administrer roller**.

1. Tildel rollen **Customer Insights-korttilpasser** til brugere, der skal tilpasse det indhold, der vises på kortet, for hele organisationen.

## <a name="add-customer-card-controls-to-forms"></a>Tilføj Kundekort-kontrolelementer til formularer
  
1. Hvis du vil føje Kundekort-kontrolelementer til formularen Kontakt, skal du gå til **Indstillinger** > **Tilpasninger** i Dynamics 365.

1. Vælg **Tilpas systemet**.

1. Gå til objektet **Kontakt**, udvid det, og vælg **Formularer**.

1. Vælg den kontaktformular, hvor du vil tilføje kontrolelementerne for kundekortet.

    > [!div class="mx-imgBorder"]
    > ![Vælge formularen Kontakt](media/contact-active-forms.png "Vælge formularen Kontakt")

1. Hvis du vil tilføje et kontrolelement, skal du i formulareditoren trække et hvilket som helst felt fra **Feltoversigt** til det sted, hvor du vil placere kontrolelementet.

1. Vælg det felt i den formular, du lige har tilføjet, og vælg **Skift egenskaber**.

1. Gå til fanen **Kontrolelementer**, og vælg **Tilføj kontrolelement**. Vælg et af de tilgængelige brugerdefinerede kontrolelementer, og vælg **Tilføj**.

1. Fjern markeringen i afkrydsningsfeltet **Vis etiket på formularen**, i dialogboksen **Feltegenskaber**.

1. Vælg indstillingen **Internet** for kontrolelementet. Vælg den type forbedring, du vil have vist, ved at konfigurere feltet **Forbedring**. Du skal tilføje en separat forbedringskontrol for hver type forbedring.

1. Vælg **Gem** og **Publicer** for at publicere den opdaterede kontaktpersonformular.

1. Gå til den publicerede kontaktformular. Du kan se det netop tilføjede kontrolelement. Det kan være nødvendigt at logge på, første gang du bruger det.

1. Hvis du vil tilpasse det, du vil have vist på det brugerdefinerede kontrolelement, skal du vælge knappen Rediger i øverste højre hjørne.
