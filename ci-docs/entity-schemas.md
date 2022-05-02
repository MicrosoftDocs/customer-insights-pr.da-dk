---
title: Skemaer til Customer Insights-objekt i Common Data Model
description: Arbejd med objekter i Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: e155f75ffbc2c1bb228bece1b3e34846df794543
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646186"
---
# <a name="entity-schemas-in-common-data-model"></a>Objektskema i Common Data Model



[Common Data Model](/common-data-model/) er en erklærende specifikation og en definition for standardobjekter, der repræsenterer ofte anvendte koncepter og aktiviteter på tværs af forretnings og produktivitets-applikationer. Denne model også udvidet med observations- og analysedata. Common Data Model giver forretningsobjekter, der er veldefinerede, modulopbyggede og kan udvides, f.eks. Konto, Afdeling, Sag, Kontakt, Kundeemne, Salgsmulighed og Produkt — samt interaktioner med leverandører, arbejdere og kunder — såsom aktiviteter og serviceniveauaftaler. Alle kan bygge videre på og udvide Common Data Model-definitioner for at registrere flere forretningsspecifikke ideer.

Denne delte datamodel gør det muligt for programmer og dataintegratorer at samarbejde mere effektivt ved at levere en samlet definition af data. Common Data Model indeholder et rigt metadatasystem med standardobjekter, relationer, hierarkier, egenskaber og meget mere. Det stammer fra Dynamics 365-apps og er open sourced på GitHub med over 260 standardobjekter. Et stort system af interne og eksterne partnere bidrager med branchespecifikke koncepter til Common Data Model.

Flere systemer og platforme implementerer i dag Common Data Model, herunder Power BI-dataflows og Azure Data Services. Det understøttes allerede i Microsoft Dataverse, Dynamics 365, Power Apps, Power BI og kommende Azure-datatjenester, og det akkumulerer værdien direkte mod [Åbn datainitiativ](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Customer Insights-objektskemaer

Vi har udgivet følgende objektskemaer for at give en 360-graders visning af kunden og levere Customer Insights-modeller i Common Data Model for udvidelse.

| Objekt | Beskrivelse |
|---------|---------|
|[Kundeaktivitet](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | En aktivitet, der udføres af en bruger, som har en observationsværdi for virksomheden. |
|[Kundeprofil](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | En person eller organisation, der enten har udført forretningsaktiviteter eller har potentialet til at gøre det. |
|[Definition af måling](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definition af nøgletal, der er partitioneret af nul eller flere dimensioner (f.eks. månedlige aktive brugere, samlet forbrug pr. kunde, gennemsnitlig kundeanskaffelsesomkostning) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definerer en gruppe af medlemmer med almindelige karakteristika. |
|[Segmentmedlemmer](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Medlemmer, der indgår i et bestemt segment. |

Du kan finde flere oplysninger i dokumentationen til [Customer Insights-objektskemaer i Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Visning af objekter ved hjælp af Entity Navigator til Common Data Model

Du kan få vist objekter i [Common Data Model-objektnavigatør](https://microsoft.github.io/CDM/). Vælg et objekt i sektionen Insights-program for at få listen over Customer Insights-objekter og deres definitioner.
> [!div class="mx-imgBorder"]
> ![CDM Entity Navigator, der viser CustomerActivity-objekt.](media/CDM-entity-navigator.png "CDM Entity Navigator, der viser CustomerActivity-objekt")


[!INCLUDE [footer-include](includes/footer-banner.md)]
