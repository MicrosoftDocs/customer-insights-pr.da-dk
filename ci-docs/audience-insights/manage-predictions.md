---
title: Delte opgaver til forudsigelsesscenarier
description: Få mere at vide om, hvordan du administrerer, foretager fejlfinding og finjusterer forudsigelser.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 8c5d8b0395452c8da1631f09cffeddfc811e6d29
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230785"
---
# <a name="manage-predictions"></a>Administrere forudsigelser

I denne artikel beskrives nogle opgaver, som de fleste forudsigelsesscenarier deler.

## <a name="troubleshoot-a-failed-prediction"></a>Fejlfinding i forbindelse med mislykkede forudsigelse

1. Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**.

1. Vælg de lodrette ellipser ud for den forudsigelse, du vil have vist fejllogfiler for.

1. Vælg **logfiler**.

1. Gennemgå alle fejlene. Der er flere typer fejl, der kan opstå, og som beskriver, hvilken betingelse der forårsagede fejlen. En fejlmeddelelse om, at der ikke er nok data til præcist at forudsige noget, løses typisk ved at indlæse yderligere data i Customer Insights.

## <a name="input-data-usability-report"></a>Rapport over inputdatas anvendelighed

Rapporten om brugbarhed af inputdata giver en konsolideret visning af de fejl og advarsler, som dine køreklare forudsigelser kan generere. Den giver også anbefalinger til, hvordan man kan forbedre modellens ydeevne.

Rapporten er tilgængelig, når en model har fuldført sin træningsproces. Den oprettes for hver model separat, uanset om det er fuldført.

### <a name="view-the-input-data-usability-report"></a>Vis rapporten over inputdatas anvendelighed

Når en køreklar model har fuldført sine træningstrin, skal du se rapporten:
- Vælg ellipserne ud for modelnavnet, og vælg **Rapport over inputdatas anvendelighed**.
- Vælg status for en model. Vælg **Se rapporten over brugbarhed af inputdata** i sideruden.
- Vælg en af modellerne på listen, og vælg **Rapport over brugbarhed af inputdata** på kommandolinjen.
- Åbn modellens resultatside, og vælg **Rapport over brugbarhed af inputdata** på kommandolinjen.

### <a name="information-in-the-input-data-usability-report"></a>Oplysninger om rapporten over inputdatas anvendelighed

Følgende kolonner i rapporten indeholder nyttige oplysninger til forbedring af dataene for modellen.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Eksempel på en rapport om brugbarhed af inputdata, der viser en tabel med fejl, advarsler og anbefalinger.":::

- **Navn:** Beskrivende navn på fejlen, advarslen eller anbefalingen.
- **Trin:** Modelfase, -træning eller -score, som oplysningerne refererer til.
- **Tilstand:** Oplysningernes alvorlighed (fejl, advarsel, anbefaling).
- **Kolonnenavn:** Kolonne i et objekt, der skal ændres for at forbedre modellens ydeevne.
- **Objektnavn:** Navn på objektet, der skal ændres for at forbedre modellens ydeevne.
- **Detaljer:** Oplysninger om fejlen, advarslen eller anbefalingen.

## <a name="refresh-a-prediction"></a>Opdatere en forudsigelse

Forudsigelser opdateres automatisk efter den samme [tidsplan, som dataene opdateres i](system.md#schedule-tab), som de er konfigureret i indstillinger. Du kan også opdatere dem manuelt.

1. Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**.

1. Vælg de lodrette ellipser ud for den forudsigelse,, du vil opdatere.

1. Vælg **Opdater**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Slette en forudsigelse

Hvis du sletter en forudsigelse, fjernes outputenheden også.

1. Gå til **Intelligens** > **Forudsigelser**, og vælg fanen **Mine forudsigelser**.

1. Vælg de lodrette ellipser ud for den forudsigelse, du vil slette.

1. Vælg **Slet**.
