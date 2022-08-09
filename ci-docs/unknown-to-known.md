---
title: Tilpas dine erfaringer med data om kendte og ukendte brugere
description: Indarbejde oplysningerne om tidligere ukendte brugere, når du kender deres identitet.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: ff99721bef0004bc8cae1ec14ff9df16cbb0682e
ms.sourcegitcommit: ece8ff732490ecd3b3421ab273f331e6fd46a7f7
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/19/2022
ms.locfileid: "9173789"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Tilpas dine erfaringer med data om kendte og ukendte brugere

Det er ikke en ny udfordring at administrere kundedata, men det bliver sværere for brugerne at navigere i de forskellige digitale kanaler. En bruger, der er kendt (godkendt) på én kanal, bliver ukendt (ikke-godkendt) i en anden, hvis den ikke er logget på. Problemet er ofte, at brugere, der ikke er identificeret (ukendt), ikke har et fælles id. Den kan bruges til at tilknytte beskrivende profilattributter og oprette ensartede kundeprofiler. Customer Insights hjælper med at løse dette problem ved at indtage data fra sporingsmetoder på kildesystemerne. Samlede ukendte og kendte profiler giver organisationer et komplet overblik over opdaterede profiler og deres historiske transaktioner, funktionsmåder og demografi. Den går endda et skridt videre ved at levere en identitetsløsning, der giver dig mulighed for at samle kundeaktivitet på tværs af flere kanaler, herunder dit websted, køb i forretningen, loyalitetsprogrammer osv.

## <a name="sample-scenario"></a>Eksempelscenarie

Lad os tænke på en kaffebar, som har en bred kundebase, som køber kaffe og mad i forretninger og bestiller produkter online. Ofte godkendes onlinebesøgende ikke, når de gennemser produkterne, hvilket gør dem til "ukendte brugere". Det er svært for kaffebaren at levere personlige tilbud og oplevelser, hvis brugere ikke er kendte. Kunderne kan til gengæld logge på deres konto og blive "kendte brugere" til firmaet ved at oprette et loyalitetssystem, der igen giver mulighed for mere personlige oplevelser. Customer Insights kan hjælpe kaffen med at få indblik i kendte og tidligere ukendte brugere.

Med Customer Insights kan virksomheden kombinere kundeprofiler med aktivitetsdata fra (ukendt) sessioner, når en bruger logger på og bliver kendt. Kaffekopperen kan samle data fra andre datakilder ved hjælp af indbyggede forbindelser til Customer Insights for at flette identiteter for kunder fra forskellige kanaler.

## <a name="prerequisites"></a>Forudsætninger

- Der indsamles webdata, som indeholder "besøgs-id" for alle besøgende.
- Webdata indeholder "godkendte bruger-id'er" for de besøgende, der er logget på. Disse-id̈́'er er knyttet til loyalitetssystemet.
- Data om hændelser af høj værdi, f.eks. "Produktvisning" og "Checkout", defineres og medtages i kildedataene sammen med tidsstempel for hændelsen og et hændelses-id.

I følgende tabel vises et forenklet eksempel på, hvordan webhændelser med høj værdi kan hentes.

|EventID|HændelsesTidsstempel|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|0|07-23-2022 10:00:00|abc123|--|Produktvisning|
|2|07-23-2022 10:05:00|abc123|707|Loyalitets-Login|
|3|07-23-2022 10:10:00|abc123|707|Tjek ud|
|4|07-23-2022 10:20:00|xyz789|--|Produktvisning|

## <a name="data-ingestion"></a>Dataindtagelse

Data om kunder kan stamme fra dit websted som hændelsesdata, og de kan gemmes i dine egne in-house- eller tredjepartsdataanalysetjenester. Webdataene indeholder kendte og ukendte brugere, hvis webstedet har et godkendelsesforløb, der integreres med en godkendelsestjeneste. Et eCommerce, der kræver, at brugerne angiver alle detaljer for at afslutte en købstransaktion. Eller et loyalitetssystem, der kræver godkendelse for at bekræfte en gyldig modtager af præmierne.

Hændelsesdataene i eksemplet herover indeholder de tydelige profil-ID'er for de kendte og ukendte brugere. I hændelse 1 og 4 er brugerne ukendt, mens den bruger, der har id abc123 i hændelse 2 og 3, tilmelder sig et loyalitetsprogram.

:::image type="content" source="media/website-data-source.png" alt-text="Datakilder, herunder Contoso-webstedet.":::

Du kan finde flere oplysninger om tilgængelige indstillinger til dataindtag under [Oversigt over datakilder](data-sources.md).

## <a name="data-unification"></a>Datasamling

Aktivering af ukendte identiteter med kendte identiteter er med til at aktivere tilpasning baseret på brugerfunktionsmåder, uanset profiltilstand (kendt eller ukendt). Tilpasset indhold til alle brugere hjælper kunder med hurtigt at finde de mest relevante produkter eller tjenester, som de er interesseret i i øjeblikket.

Da nogle af brugerne i vores data er kendte, kan vi bruge Customer Insights til at kombinere disse data med brugerens profil. Du kan finde flere oplysninger om, hvordan du gør kundeprofiler ens, i [oversigten over datasamling](data-unification.md).

1. Vælg kildefelterne fra webdataobjektet. Brug de profildata, der er gemt i dine webdata, og vælg de felter, der repræsenterer Id'er med demografiske data.

   :::image type="content" source="media/website-source-fields.png" alt-text="Kildefelter til webdatakilde.":::

1. Tilføj regler for at flette dublerede poster. Til webdata skal du vælge de mest udfyldte data.

1. Konfigurer matchregler og -betingelser. I dette eksempel sammenholdes hændelsesdataene for webprofiler på internettet med profilerne fra de andre datakilder, der indeholder kundeoplysninger. Opret regler for nøjagtigt match på id'er som separate regler for hvert af de andre profilobjekter, der har en tilsvarende primær nøgle eller et id-match. I eksemplet bruges profildata for webhændelser som det sidste tilsvarende objekt, så andre profildata først kombineres.
   1. Kontrollerer ikke **Inkluder alle poster** opretter ensartede profiler for kendte brugere og inkluderer de tilhørende ukendte bruger-id'er. Det er nyttigt i scenarier, når du er interesseret i at få vist kendte brugeres tidligere adfærdsmæssige aktiviteter, da de stadig var ukendte.
   1. Kontrollerer, at **Medtag alle poster** opretter separate profilposter for ukendte brugere. Ukendte brugere får et entydigt kunde-id. Når der fremover knyttes en kendt profil til profildataene for webhændelser, kan den netop kendte brugers tilknytning også ses og bruges til tilpasning på baggrund af tidligere ukendte adfærdsdata.

:::image type="content" source="media/website-match-rule.png" alt-text="Matchregel for webdatakilde-objekt.":::

## <a name="get-insights"></a>Få indsigt

Hvis der oprettes kundeprofiler for ukendte og kendte brugere, kan dataene for webhændelser med høj værdi bruges som [aktiviteter](activities.md). Disse aktiviteter kan bruges til at skabe større indsigt. Kunder, der f.eks. besøgte en webside for seks måneder siden (da de stadig var ukendt), eller kunder, der ikke har et loyalitets-id, har aldrig afsluttet en checkout.

:::image type="content" source="media/website-known-unknown.png" alt-text="Skærmbillede af kundesiden med kendte og ukendte kunder.":::

[Forbedre](enrichment-hub.md) dine data, opbygge [mål](measures.md) og oprette [segmenter](segments.md) for at aktivere dem yderligere.

Du kan f.eks. oprette segmenter af kendte brugere, som er klar til at købe produkter, men som aldrig er færdige med at betale.

Du kan finde flere oplysninger i [Oversigt over segmenter](segments.md).

## <a name="activate-insights"></a>Aktivere indsigt

Du kan eksportere dine data og handle ud fra den underliggende indsigt på flere måder.

Du kan finde flere oplysninger i [Oversigt over eksport](export-destinations.md).
