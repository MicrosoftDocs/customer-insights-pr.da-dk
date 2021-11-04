---
title: Introduktion til forretningskonti som primær målgruppe
description: Få mere at vide om forretningskonti som primær målgruppe i Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ac5ae950a44f7f32e3cb9fdc0ffad05b78fddef0
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673680"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Arbejde med forretningskonti målgruppeindsigt

Med målgruppeindsigtsfunktionaliteten i Dynamics 365 Customer Insights kan du konfigurere miljøet til forskellige primære målgrupper: individuelle forbrugere (B-til-C) og forretningskonti (B-til-B). I B-til-C-scenarier er dataene centreret om enkeltpersoner. I forbindelse med B-til-B er den primære målgruppe konti – organisationer eller virksomheder – og kontakter. I denne artikel kan du få hjælp til at komme i gang med et miljø til forretningskonti. Den indeholder en liste over forskellene for funktionsområder i målgruppeindsigt, afhængigt af dit miljøfokus. Du kan finde flere oplysninger om forskelle ved at gennemse dokumentationen til funktionsområder. 

## <a name="create-an-environment-for-business-accounts"></a>Oprette et miljø til forretningskonti

Administratorer kan [oprette et miljø i en eksisterende organisation](create-environment.md). I et trin i processen til oprettelse af et nyt miljø bliver administratorer bedt om at angive den primære målgruppe for miljøet. Hvis det er den første konfiguration af målgruppeindsigt, når du har købt en licens, hjælper en guidet oplevelse med at oprette det første miljø.

Du kan derefter [indtage data](data-sources.md) for forretningskonti og relaterede kontakter som datakilder fra alle understøttede kilder.

Når dataene er blevet samlet, skal du [angive kontohierarkier](relationships.md#set-up-account-hierarchies) som en del af relationskonfigurationen. Du kan også [konfigurere semantiske tilknytninger](semantic-mappings.md) for at oprette forbindelse mellem kontakt- og kontoobjekter. 

## <a name="switch-between-primary-target-audience"></a>Skifte mellem primær målgruppe

Hvis organisationen vedligeholder miljøer for individuelle kunder og forretningskonti, kan du bruge skifteren i venstre rude til at vælge den primære målgruppe.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Skifter til at ændre den primære målgruppe mellem individuelle kunder og forretningskonti.":::

## <a name="supported-feature-areas"></a>Understøttede funktionsområder

- [Aktiviteter](activities.md): Understøtter konti og relaterede kontakter for at oprette aktiviteter og vise dem på en tidslinje.
- [Relationer](relationships.md): Guiden Aktivitet hjælper med at oprette relationer mellem objekterne, så kontovisningen kan vise alle aktiviteter fra kontakter. Kontakter kan bore op for at vise kontaktvisning, og hierarkier kan bruges til sammenlægning af kontoaktiviteter.
- [Målinger](measures.md): Understøtter målinger, der er oprettet fra målergeneratoren med én beregning. En valgfri indstilling gør det muligt at akkumulere underordnede firmaer under oprettelse af målinger.
- [Segmenter](segments.md): Understøtter segmenter, der er oprettet fra bunden med segmentgeneratoren. Nye operatorer gør det muligt at indarbejde kontohierarki ved opbygning af segmenter.
- [Dataindtagelse](data-sources.md): Alle funktioner i dette område er de samme for forretningskonti og individuelle kunder.
- [Datasamling](data-unification.md): Alle funktioner i dette område er de samme for forretningskonti og individuelle kunder.
- [Forbedring](enrichment-hub.md): Visse forbedringstyper er kun tilgængelige for individuelle kundescenarier, mens andre kun er tilgængelige for forretningskonti.
- [Forudsigelser og indbyggede modeller](predictions-overview.md): Forudsigelse af transaktionsafgang indeholder ekstra trin til forretningskonti. Andre forudsigelser er kun tilgængelige for individuelle kunder.
- [Aktivering og eksport](export-destinations.md): Eksport er tilgængelig for forretningskonti og individuelle kunder. Visse eksporter kræver, at ekstra konfigurations- og kontaktoplysninger projekteres i de underliggende segmenter, så de kan anvendes på forretningskonti.
- [Systemindstillinger](system.md) og [brugeradministration](permissions.md): Alle funktioner i dette område er de samme for forretningskonti og individuelle kunder.

