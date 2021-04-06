---
title: Integrere webdata fra engagementsindsigt med målgruppeindsigt
description: Få weboplysninger om kunder fra engagementsindsigt til målgruppeindsigt.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 14ebff30d3ec7fc52dca6f86136309a3f454fa27
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597458"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrere webdata fra engagementsindsigt med målgruppeindsigt

Kunder foretager ofte deres daglige transaktioner online ved hjælp af websteder. Funktionen engagementsindsigt i Dynamics 365 Customer Insights er en praktisk løsning, hvor webdata integreres som en kilde. Ud over transaktions-, demografi- eller adfærdsdata kan vi se aktiviteter på internettet i samlede kundeprofiler. Vi kan bruge denne profil til at få yderligere indsigt, f.eks. segmenter, mål eller forudsigelser for målgruppeaktivering.

I denne artikel beskrives trinnene til at hente dine kunders webaktivitetsdata fra engagementsindsigt ind i dit målgruppeindsigtsmiljø.

I dette eksempel antages det, at der er et miljø, der indeholder samlede kundeprofiler. Profilerne blev samlet med kilder fra undersøgelser, detailsalg og et billetsystem. Den viser også kundernes relaterede aktiviteter. 

Vi vil nu vide, om en kunde besøger vores webegenskaber og forstår deres aktiviteter. Aktiviteter omfatter f.eks. besøgte websteder eller viste produktsider fra et link, der modtages i en e-mail.

## <a name="prerequisites"></a>Forudsætninger

Hvis du vil integrere data fra engagementsindsigt, skal nogle få forudsætninger opfyldes: 

- Integrer SDK med engagementsindsigt med dit websted. Du finder flere oplysninger under [Kom i gang med web-SDK](../engagement-insights/instrument-website.md).
- Eksport af webhændelser fra engagementsindsigt kræver adgang til en ADLS Gen 2-lagerkonto, der bruges til at udnytte de webhændelsesdata, der skal bruges til at målgruppeindsigt. Du kan finde flere oplysninger under [Eksport af hændelser](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Konfigurere hændelser, der hjælper med engagementsindsigt

Når en administrator planlægger et websted med engagementsindsigt-SDK, indsamles *basishændelser*, når en bruger får vist eller klikker på en webside. Basishændelser med mange detaljer. Afhængigt af din use case skal du kun bruge et delsæt af data i en basishændelse. Engagementsindsigt giver dig mulighed for at oprette *raffinerede hændelser*, der kun indeholder egenskaberne for en basishændelse, du vælger.     

Du kan finde flere oplysninger under [Oprette og ændre raffinerede hændelser](../engagement-insights/refined-events.md).

Overvejelser, når arrangementer oprettes: 

- Angiv et navn, der giver mening, til den raffinerede hændelse. Det bruges som et aktivitetsnavn i en målgruppeindsigt.
- Vælg som minimum følgende egenskaber for at oprette en aktivitet i målgruppeindsigt: 
    - Signal.Action.Name – angivelse af aktivitetsdetaljer
    - Signal.User.Id – bruges til tilknytning med kunde-id
    - Signal.View.Uri – bruges som webadresse som udgangspunkt for segmenter eller mål
    - Signal.Export.Id – bruges som primær nøgle til hændelser <!-- system generated, do we need to list?-->
    - Signal.Timestamp – til bestemmelse af dato og klokkeslæt for aktiviteten

Vælg filtrene for at fokusere på de hændelser og sider, der betyder noget for din use case. I dette eksempel bruger vi handlingsnavnet "Kampagne via mail".

## <a name="export-the-refined-web-events"></a>Eksportere de raffinerede webhændelser 

Når du har defineret den raffinerede hændelse, skal du konfigurere eksporten af hændelsesdata til en Azure Data Lake Storage, der kan angives som en datakilde for indtagelse i målgruppeindsigt. Eksporter sker konstant, mens hændelserne strømmer fra webegenskaben.

Du kan finde flere oplysninger under [Eksport af hændelser](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Indtag hændelsesdata til målgruppeindsigt

Nu, hvor du har defineret den raffinerede hændelse og konfigureret eksporten, går vi videre til at indtage data til målgruppeindsigt. Du skal oprette en ny datakilde baseret på mappen Common Data Model. Angiv oplysninger om den lagerkonto, du eksporterer hændelserne til. I filen *default.cdm.json* skal du vælge den hændelse, hvor objektet indtages og oprette objektet målgruppeindsigt.

Du kan finde flere oplysninger i [Oprette forbindelse til en Common Data Model-mappe ved hjælp af en Azure Data Lake-konto](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Relatere hændelsesdata som en aktivitet i en kundeprofil

Når objektet er indtaget, kan du konfigurere aktiviteten for kundeprofilen.

Du kan finde flere oplysninger under [Kundeaktiviteter](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Aktiviteter-siden med udvidet redigeringsaktivitetsrude og udfyldte felter.":::

Konfigurere den nye aktivitet ved hjælp af følgende tilknytning: 

- **Primær nøgle:** Signal.Export.Id, et entydigt id, der er tilgængeligt for alle hændelsesposter i engagementsindsigt. Denne egenskab genereres automatisk.

- **Tidsstempel:** Signal.Timestamp i hændelsesegenskaben.

- **Hændelse:** Signal.Name, det hændelsesnavn, du vil spore.

- **Webadresse:** Signal.View.Uri refererer til uri'en for den side, der oprettede hændelsen.

- **Detaljer:** Signal.Action.Name til at repræsentere de oplysninger, der skal knyttes til hændelsen. Den valgte egenskab i dette tilfælde indikerer, at hændelsen er til e-mailkampagne.

- **Aktivitetstype:** I dette eksempel vælger vi den eksisterende aktivitetstype WebLog. Denne indstilling er en nyttig filterindstilling til kørsel af forudsigelsesmodeller eller oprettelse af segmenter baseret på denne aktivitetstype.

- **Opret relation:** Denne vigtige indstilling gør aktiviteten gældende i forhold til eksisterende kundeprofiler. **Signal.User.Id** er det id, der konfigureres i SDK til indsamling, og som er relateret til bruger-id i andre datakilder, der er konfigureret i målgruppeindsigt. I dette eksempel konfigurerer vi relationen mellem Signal.User.Id og RetailCustomers:CustomerRetailId, som er den primære nøgle, der blev defineret i tilknytningstrinnet i processen til samling af data.


Når du har behandlet aktiviteterne, kan du gennemse kundeposter og åbne et kundekort for at se aktiviteter fra engagementsindsigt på tidslinjen. 

> [!TIP]
> Hvis du vil finde et kunde-id, der har en engagementsindsigtsaktivitet, skal du gå til **Enheder** og gennemse dataene for objektet UnifiedActivity. ActivityTypeDisplay = WebLog indeholder den engagementsindsigtsaktivitet, der er konfigureret i eksemplet ovenfor. Kopiér kunde-id for en af disse poster og for det pågældende id på siden **Kunder**.

## <a name="next-steps"></a>Næste trin

Du kan nu oprette [segmenter](segments.md), [mål](measures.md) og [forudsigelser](predictions.md) for at skabe en meningsfuld forbindelse til kunderne.


[!INCLUDE[footer-include](../includes/footer-banner.md)]