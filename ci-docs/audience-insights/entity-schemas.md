---
title: Skemaer til Customer Insights-objekt i Common Data Model
description: Arbejd med objekter i Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269277"
---
# <a name="entity-schemas-in-common-data-model"></a>Objektskema i Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) er en erklærende specifikation og en definition for standardobjekter, der repræsenterer ofte anvendte koncepter og aktiviteter på tværs af forretnings og produktivitets-applikationer. Denne model også udvidet med observations- og analysedata. Common Data Model giver forretningsobjekter, der er veldefinerede, modulopbyggede og kan udvides, f.eks. Konto, Afdeling, Sag, Kontakt, Kundeemne, Salgsmulighed og Produkt — samt interaktioner med leverandører, arbejdere og kunder — såsom aktiviteter og serviceniveauaftaler. Alle kan bygge videre på og udvide Common Data Model-definitioner for at registrere flere forretningsspecifikke ideer.

Denne delte datamodel gør det muligt for programmer og dataintegratorer at samarbejde mere effektivt ved at levere en samlet definition af data. Common Data Model indeholder et rigt metadatasystem med standardobjekter, relationer, hierarkier, egenskaber og meget mere. Det stammer fra Dynamics 365-apps og er open sourced på GitHub med over 260 standardobjekter. Et stort system af interne og eksterne partnere bidrager med branchespecifikke koncepter til Common Data Model.

Flere systemer og platforme implementerer Common Data Model i dag, herunder Power BI-dataflows og Azure Data Services. Det understøttes allerede i Common Data Service, Dynamics 365, Power Apps, Power BI og kommende Azure Data Services – periodisering af værdier direkte til [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Customer Insights-objektskemaer

Vi har udgivet følgende objektskemaer for at give en 360-graders visning af kunden og levere Customer Insights-modeller i Common Data Model for udvidelse.

| Objekt | Beskrivelse |
|---------|---------|
|[Kundeaktivitet](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | En aktivitet, der udføres af en bruger, som har en observationsværdi for virksomheden. |
|[Kundeprofil](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | En person eller organisation, der enten har udført forretningsaktiviteter eller har potentialet til at gøre det. |
|[Definition af måling](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definition af nøgletal, der er partitioneret af nul eller flere dimensioner (f.eks. månedlige aktive brugere, samlet forbrug pr. kunde, gennemsnitlig kundeanskaffelsesomkostning) |
|[Segment](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Definerer en gruppe af medlemmer med almindelige karakteristika. |
|[Segmentmedlemmer](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Medlemmer, der indgår i et bestemt segment. |

Du kan finde flere oplysninger i dokumentationen til [Customer Insights-objektskemaer i Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Visning af objekter ved hjælp af Entity Navigator til Common Data Model

Du kan få vist objekter i [Common Data Model-objektnavigatør](https://microsoft.github.io/CDM/). Vælg knappen **Indlæs fra GitHub!**, og naviger til **foundationCommon** > **crmCommon** > **løsninger** > **customerInsights**, hvor du kan finde listen over Customer Insights-objekter og definitioner af dem.
> [!div class="mx-imgBorder"]
> ![CDM Entity Navigator, der viser CustomerActivity-objekt](media/CDM-entity-navigator.png "CDM Entity Navigator, der viser CustomerActivity-objekt")


[!INCLUDE[footer-include](../includes/footer-banner.md)]