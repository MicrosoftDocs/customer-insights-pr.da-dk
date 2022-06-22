---
title: Brug kundesamtykke
description: Angiv kundernes præferencer for samtykke i Customer Insights ved at importere data om dit samtykke.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947494"
---
# <a name="use-customer-consent"></a>Brug kundesamtykke

Lovgivning om databeskyttelse og beskyttelse af personlige oplysninger giver enkeltpersoner ret til at styre, hvordan en organisation bruger deres personlige data. Eksempler på sådanne regler er den generelle forordning om databeskyttelse i EU eller California Consumer Privacy Act i USA. Disse regler giver personer mulighed for at framelde sig, at deres personlige data indsamles, behandles af eller deles med tredjepart.  

Kunder kan vælge at trække deres samtykke tilbage eller trække det tilbage til bestemte kontaktformularer. De kan også anmode om, at du framelde sig indsamling, lagring, brug eller salg af deres personlige data. Det er vigtigt, at din organisation hædrer alle kunders samtykke og indstillinger for beskyttelse af personlige oplysninger.  

Dynamics 365 Customer Insights hjælper dig med at imødekomme dine kunders anmodninger ved at importere og lagre deres præferencer som en del af de ensartede kundeprofiler.

Hvis der lagres samtykkedata separat fra dine kundeprofiler, skal du [tilføje dine samtykkedata som en ny datakilde](#import-and-unify-consent-data). Den datakilde, der indeholder samtykkedataene, føjes til processen til datas enhed. En vellykket samling af samtykkedata og kundeprofiler fører derefter til ensartede kundeprofiler, der indeholder oplysningerne om samtykke. For kundeprofiler, der allerede indeholder oplysninger om samtykke, skal du gå direkte til sektionen [brug af data om samtykke](#use-consent-data).

## <a name="prerequisites"></a>Forudsætninger

Følgende oplysninger skal være tilgængelige i kildedataene for at gøre samtykkedataene ens for andre kundeprofiler:

- Alternativ nøgle til at knytte samtykkeoplysningerne til brugerprofiler i Customer Insights. F.eks. et telefonnummer eller en e-mailadresse.
- Samtykkeværdi til bestemmelse af status for kundens samtykke.

Overvej følgende *valgfri* oplysninger:

- Primær nøgle til opdatering af samtykkestatus, hvis en kunde anmoder om en ændring.
- Type af samtykke, hvis der er mere end én måde at behandle kundeoplysninger på.
- Dato for samtykke eller andre typer data, der er relevante i dine samtykkescenarier.

Eksempeltabel over en simpel database med samtykke med flere muligheder for samtykke:

|Samtykke-id (primær nøgle)   |E-mail (alternativ nøgle)  |Indstillingen Samtykke  |Værdi af samtykke  |
|---------|---------|---------|---------|
|0    |  holly@contoso.com       |  Nyhedsbrev       |  False       |
|2    |  holly@contoso.com       |  Produktopdateringer       |  True       |
|3    |  frank@contoso.com       |  Nyhedsbrev       | True        |
|4    |  frank@contoso.com       |  Produktopdateringer       |  False       |

## <a name="import-and-unify-consent-data"></a>Importere og samle samtykkedata

Du kan importere samtykkedata på samme måde, som andre datakilder importeres til Customer Insights. Du kan finde flere oplysninger om understøttede datakilder, og hvordan du importerer dem, i [Oversigt over datakilder](data-sources.md).

Du kan finde flere oplysninger om, hvordan du gør datakilder ens, i [oversigten over datasamling](data-unification.md).

## <a name="use-consent-data"></a>Brug samtykkedata

Når dine samtykkedata er en del af dine ensartede kundeprofiler, kan du bruge dem i Customer Insights. Du kan f.eks. oprette et segment med en regel, der sikrer, at du hædrer dine kunders præferencer med hensyn til beskyttelse af personlige oplysninger og databeskyttelse. Regler, der understøtter indstillinger for samtykke, bruges til at udelukke brugere fra et segment baseret på profilattributter. Tilføjelse af en regel til et segment, der udelukker kundeprofiler, som ikke har givet samtykke til kontakt.

Hvis der henvises til eksempeltabellen ovenfor, kan et segment indeholde denne regel:`Consent option=Newsletter & Consent value=True`. Denne konfiguration resulterer i et segment, der hædrer kontaktpersonindstillinger for at sende et nyhedsbrev.

Du kan finde flere oplysninger om byggesegmenter under [Oprette segmenter](segment-builder.md).

Når segmentet er oprettet, kan du bruge en af de mange [eksportindstillinger](export-destinations.md) til at bruge segmentet i andre programmer.

## <a name="ensure-updated-consent-status"></a>Sikre opdateret status for samtykke

Det er vigtigt at holde dine kunders samtykkestatus opdateret. Den planlagte opdatering i Customer Insights importerer altid den seneste tilstand for datakilderne. Disse oplysninger behandles derefter gennem en samling af data og resulterer i opdaterede kundeprofiler. Disse opdaterede profiler bruges derefter til at opdatere segmenter for at sikre, at du arbejder med de mest opdaterede oplysninger.

Med andre ord: Sørg for, at de kildedata, der importeres til Customer Insights, altid har de nyeste oplysninger.

Du kan finde flere oplysninger i [Opdatere segmenter manuelt](segments.md#refresh-segments) eller konfigurere [en planlagt opdatering](system.md#schedule-tab).
