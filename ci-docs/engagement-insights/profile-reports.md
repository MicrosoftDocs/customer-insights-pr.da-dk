---
title: Aktivere de indbyggede profilrapporter
description: Sådan oprettes de indbyggede profilrapporter grupperet efter område, alder og område.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486113"
---
# <a name="out-of-box-profile-reports"></a>Indbyggede profilrapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En rapport er en samling datavisualiseringer, der hjælper dig med at forstå brugerfunktionsmåder. Hvis du opretter forbindelse til Customer Insights og målgruppeindsigt, kan engagementsindsigt vise en rapport med oplysninger om ensartede kundeprofiler. Rapporten indeholder antallet af profiler, du har grupperet efter placering, alder og geografisk placering.

## <a name="prerequisites"></a>Forudsætninger

I målgruppeindsigt-miljøet skal der lagres data i et kundebaseret Azure Data Lake Storage-firma.

Hvis du bruger en prøveversion af målgruppeindsigt eller et miljø i et Customer Insights-administreret Data Lake, kan du [kontakte os](https://go.microsoft.com/fwlink/?linkid=2145734) for at få hjælp.  


## <a name="enable-the-customer-profile-report"></a>Aktivere kundeprofilrapporten

En miljøadministrator skal [sammenkæde engagementsindsigt og målgruppeindsigt](integrate-audience-insights-engagement-insights.md).

Når du har angivet forbindelsesoplysningerne, kan administratoren give andre personer i organisationen adgang til at se rapporten. Den miljøadministrator, der konfigurerer forbindelsen, har automatisk adgang til rapporten. 

Når forbindelsen er fuldført, er funktionen **Profiler** tilgængelig i venstre navigationsrude. 

- Gå til **Opdag** > **Profiler** for at se rapporten.

Rapporten **Profiler** indeholder visualiseringer om de tilknyttede kundeprofilers placering, alder og geografiske placering.

:::image type="content" source="media/customer-profiles.png" alt-text="Kundeprofilrapport.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]