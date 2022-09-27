---
title: Administrere ukendte profiler med Customer Insights
description: Arbejd med ukendte kundeprofiler, der oprettes og administreres i Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556389"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Administrere ukendte profiler med Customer Insights

Internetbrugere er ofte uidentificerede og anonyme online. Hvis de ikke er logget på, fordi de bruger forskellige enheder eller kanaler, gælder det endda for de mest loyale kunder. Da tredjepartscookies sandsynligvis snart forsvinder, er det vigtigt at administrere brugerindstillinger baseret på førstepartsdata for at opnå personligt tilpassede oplevelser. For mange mærker er kendte eller godkendte brugere i mindretal til trods for de stigende kundeforventninger til personlig tilpasning. Det er godt for virksomheder at vide, hvem deres kunder er, på baggrund af pålidelige, detaljerede og ensartede data.

Personlig tilpasning, der er let at huske, afhænger af, om dine kundedata er uddybende og fuldstændige, og Customer Insights hjælper dig med at nå disse mål. Du behøver ikke at begrænse eller stoppe brugen af de data, der er indsamlet i starten af kundekampagneforløbet. Med Customer Insights kan du bruge dine egne data til at oprette en kundeprofil for ukendte brugere. Du kan derefter bruge den pågældende profil til yderligere handlinger, selvom der mangler kontaktoplysninger. Importér førstepartsdata fra kilder, f.eks. web-, mobil- eller CRM-systemer, til Customer Insights for at forbedre kundeprofiler løbende. Efterhånden som du ensretter flere interaktioner, kan du [gøre den *ukendte* kunde til en *kendt* kunde](unknown-to-known.md).

## <a name="sample-scenario"></a>Eksempelscenarie

E-handel har været den hurtigst voksende kanal de seneste ti år. Antag, at en bruger bruger sin mobilenhed til at gennemse e-handelswebstedet. På webstedet tildeles den besøgende "mobile_guest123" som et entydigt id, og du begynder at indsamle adfærdsaktiviteter på baggrund af deres onlineaktivitet. Det kan f.eks. være, hvilke sider de har besøgt, hvor meget tid de har brugt på de pågældende sider, eller hvilke links de har klikket på. Du kender ikke deres navn eller mailadresse, men disse data kan hjælpe dig med at give meningsfyldt indsigt i denne specifikke bruger. Du kan til gengæld bruge denne indsigt, næste gang brugeren besøger webstedet. Forespørg Customer Insights efter "mobile_guest123" for at hente brugerens segmentliste, f.eks. "organisk", "mobilkunder med forudbestilling", "kunder med høj værdi" osv., eller hente profilen for at oprette personlige weboplevelser. Du kan også eksportere dataene til et hvilket som helst aktiveringssystem for at gøre det samme.

## <a name="prerequisites"></a>Forudsætninger

- Indtage førstepartsdata i Customer Insights
- Hvert objekt har et entydigt id, der er angivet som en primær nøgle
- Hvert objekt med en primær nøgle til personlig tilpasning er samlet
- Systemet til indholdsstyring på dit websted kan bruge API'er (til webtilpasning baseret på direkte kommunikation med Customer Insights)

I følgende tabel vises et forenklet eksempel på, hvordan webhændelser med høj værdi kan hentes.

|EventID|HændelsesTidsstempel|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|0|15-09-2022 9:00:00|abc123|CookieID1|Produktvisning|
|2|18-09-2022 10:05:00|abc123|CookieID1|Produktvisning|
|3|18-09-2022 10:10:00|abc123|CookieID1|Føj til indkøbsvogn|
|4|21-09-2022 09:05:00|abc123|CookieID1|Produktvisning|

## <a name="data-ingestion"></a>Dataindtagelse

Du kan finde flere oplysninger om tilgængelige indstillinger til dataindtag under [Oversigt over datakilder](data-sources.md).

## <a name="data-unification"></a>Datasamling

Du kan finde flere oplysninger om, hvordan du gør kundeprofiler ens, i [oversigten over datasamling](data-unification.md).

## <a name="get-insights"></a>Få indsigt

[Forbedre](enrichment-hub.md) dine data, opbygge [mål](measures.md) og oprette [segmenter](segments.md) for at aktivere dem yderligere.

Du kan f.eks. oprette segmenter med ukendte brugere, der har gennemset de samme produktsider, men som aldrig har gennemfør et køb.

## <a name="activation"></a>Aktivering

Med dine data i Customer Insights og din indsigt, der er klar til brug, kan du bruge Customer Insights til personlig tilpasning:

1. Brug [OData API](apis.md) til at hente et segments medlemskab eller kundeprofil. Du kan finde flere eksempler under [Eksempler på OData-forespørgsler til API'er for Customer Insights](odata-examples.md).

1. [Eksportere](export-destinations.md) dataene til aktiveringssystemet.

Eksempel: En ukendt bruger besøger et websted flere gange og besøger produktsider med forskellige modeller af lædersko. Med de data, der er tilgængelige i Customer Insights, kan du inkludere den ukendte bruger i det segment med personer, der er interesseret i lædersko. Brug dette segment til at informere den personlige tilpasning af dit webstedsbuild om besøgende, der vender tilbage. Under det næste besøg genkender webstedet den ukendte bruger og kan tilbyde en rabat på 10 %.

[!INCLUDE [footer-include](includes/footer-banner.md)]
