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
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033945"
---
# <a name="out-of-box-profile-reports"></a>Indbyggede profilrapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En rapport er en samling datavisualiseringer, der hjælper dig med at forstå brugerfunktionsmåder. Hvis du opretter forbindelse til Customer Insights og målgruppeindsigt, kan engagementsindsigt vise en rapport med oplysninger om ensartede kundeprofiler. Rapporten indeholder antallet af profiler, du har grupperet efter placering, alder og geografisk placering.

## <a name="prerequisites"></a>Forudsætninger

I målgruppeindsigt-miljøet skal der lagres data i et kundebaseret Azure Data Lake Storage-firma.

Hvis du bruger en prøveversion af målgruppeindsigt eller et miljø i et Customer Insights-administreret Data Lake, kan du [kontakte os](https://go.microsoft.com/fwlink/?linkid=2145734) for at få hjælp.  


## <a name="enable-the-customer-profile-report"></a>Aktivere kundeprofilrapporten

En miljøadministrator skal [oprette forbindelse til målgruppeindsigt](configure-connections.md).

Når du har angivet forbindelsesoplysningerne, kan administratoren give andre personer i organisationen adgang til at se rapporten. Den miljøadministrator, der konfigurerer forbindelsen, har automatisk adgang til rapporten. 

Når forbindelsen er fuldført, er funktionen **Profiler** tilgængelig i venstre navigationsrude. 

- Gå til **Opdag** > **Profiler** for at se rapporten.

Rapporten **Profiler** indeholder visualiseringer om de tilknyttede kundeprofilers placering, alder og geografiske placering.

:::image type="content" source="media/customer-profiles.png" alt-text="Kundeprofilrapport.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]