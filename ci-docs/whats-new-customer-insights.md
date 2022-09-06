---
title: Nyheder i Dynamics 365 Customer Insights
description: Oplysninger om nye funktioner, forbedringer og rettelser i forbindelse med fejl.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 1e734464cec1f66428c3a2a2e403437a2a9d8500
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387287"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Nyheder i Dynamics 365 Customer Insights

Vi er glade for at kunne fortælle om vores nyeste opdateringer! Denne artikel indeholder en oversigt over funktionerne i offentlig prøveversion, forbedring af generel tilgængelighed og funktionsopdateringer. Hvis du vil have vist de langsigtede funktionsplaner, skal du kigge i [frigivelsesplanerne for Dynamics 365 og Power Platform](/dynamics365/release-plans/).

Vi udruller opdateringerne område for område. Så visse geografiske områder kan se funktioner før andre. Medmindre andet er angivet, behøver du ikke at foretage dig noget, og vi opdaterer automatisk appen uden nedetid.

> [!TIP]
> Hvis du vil sende og stemme på populære ønsker og produktforslag, skal du gå til [Dynamics 365-portalen for programideer](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="august-2022-updates"></a>Opdateringer fra august 2022

Opdateringerne i august 2022 omfatter nye funktioner, opgradering til ydeevne og fejlrettelser.

### <a name="contact-unification-in-b-to-b-environments"></a>Kontaktsamling i B-til-B-miljøer

B-til-B-miljøer i Customer Insights understøtter nu en forbedret oplevelse af datasamling.

Du kan nu samle kontakter i tillæg til firmaer for at få en komplet oversigt over dine forretningskontakter. Samlede kontakter knyttes til samlede firmaer og vises nu på kundekortene. 

Du kan finde flere oplysninger under [Oprette en samlet kontaktprofil](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>Oprette og eksportere segmenter baseret på samlede kontakter

Takket være den nye kontaktsamling kan du oprette kontaktsegmenter ved hjælp af kriterier fra kontakter, firmaer eller begge dele. Disse segmenter kan eksporteres til aktivering i andre tjenester.

Du kan finde flere oplysninger i [Oversigt over eksport](export-destinations.md).

## <a name="july-2022-updates"></a>Opdateringer i juli 2022

Opdateringen i juli 2022 omfatter nye funktioner, opgradering til ydeevne og fejlrettelser.

### <a name="export-to-moengage"></a>Eksportér til MoEngage

Eksportér segmenter med ensartede kundeprofiler til MoEngage, og brug dem til mailmarketing i MoEngage.

Du kan finde flere oplysninger under [Eksporter segmenter til MoEngage](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>SSH-understøttelse af SFTP-baserede eksporter

Vælg, om du vil godkende via SSH eller brugernavn/adgangskode for forbindelser til eksportmål i SFTP.

Du kan finde flere oplysninger i [Eksportere data til SFTP-værter](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Tilpasse erfaringer med data om kendte og ukendte brugere

Det er ikke en ny udfordring at administrere kundedata, men det bliver sværere for brugerne at navigere i de forskellige digitale kanaler. En bruger, der er kendt (godkendt) på én kanal, bliver ukendt (ikke-godkendt) i en anden, hvis den ikke er logget på. Problemet er ofte, at brugere, der ikke er identificeret (ukendt), ikke har et fælles id. Den kan bruges til at tilknytte beskrivende profilattributter og oprette ensartede kundeprofiler. Customer Insights hjælper med at løse dette problem ved at indtage data fra sporingsmetoder på kildesystemerne.

Du kan finde flere oplysninger i [Tilpasse dine erfaringer med data om kendte og ukendte brugere](unknown-to-known.md).

## <a name="june-2022-updates"></a>Opdateringringer i juni 2022

Opdateringen i juni 2022 omfatter nye funktioner, opgradering til ydeevne og fejlrettelser.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Opdateret brugeroplevelse for datakilder og dataindtag

Import af data fra en lang række datakilder er grundlaget for at beskytte dine kundedata i Dynamics 365 Customer Insights. Vi har revideret brugeroplevelsen i forbindelse med import og forbindelse mellem datakilder. Denne opdatering gør det nemmere for dig at få adgang til Customer Insights med data.

Du kan finde flere oplysninger i [Datakildeoversigten](data-sources.md).

### <a name="export-to-inmobi"></a>Eksportér til InMobi

InMobi hjælper virksomheder med at forstå, identificere, engagere sig og lære at arbejde hurtigt. Du kan eksportere segmenter og andre data til InMobi-tjenesten via Azure Blob Storage-konti.

Du kan finde flere oplysninger under [Eksportere segmenter til InMobi (forhåndsversion)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Lockbox-support i Customer Insights

Customer Lockbox indeholder en brugergrænseflade, hvor du kan gennemse og godkende (eller afvise) anmodninger om dataadgang. Disse anmodninger opstår, når der skal bruges dataadgang til kundedata for at afslutte en supportsag.

Du kan se flere oplysninger i [Sikker adgang til kundedata ved hjælp af Customer Lockbox (forhåndsversion)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Oprette forbindelse til dine data ved hjælp af Azure Private Link

Azure Private Link lader dig oprette forbindelse fra Customer Insights til Azure Data Lake Storage-kontoen via en slutpunkt i dit private slutpunkt i dit virtuelle netværk. I forbindelse med data i en lagerkonto, der ikke er tilgængeligt for det offentlige internet, aktiverer Privat link forbindelsen til det pågældende begrænsede netværk.

Du kan finde flere oplysninger under [Brug privat link i Customer Insights](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>Opdateringer i maj 2022

Opdateringen i maj 2022 omfatter nye funktioner, opgradering til ydeevne og fejlrettelser.

### <a name="updated-data-unification-experience"></a>Opdateret oplevelse af datas enhed

 Med data unification kan du samle én gang forskellige datakilder i en enkelt datasæt, der giver en ensartet visning af de pågældende data. Data kan være samlet i et enkelt objekt eller flere objekter. Først skal du [vælge objekter og kildefelter](map-entities.md), [fjerne dubletposter](remove-duplicates.md), angive regler for [matchningsbetingelser](match-entities.md) og definere, hvilke [felter der skal inkluderes i de ensartede kundeprofiler](merge-entities.md).

Du kan finde flere oplysninger i [Datasamlingsoversigten](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Opdateret startside i Customer Insights

På **Startsiden** vises en vejledning i konfigurationsprocessen for nøglefunktioner og giver dig en oversigt over segmenter, mål og forbedringsdata. Vi har opdateret oplevelsen for at give dig mere relevante oplysninger i overblik.

Du kan finde flere oplysninger i [Udforske Customer Insights](home.md).

### <a name="track-usage-of-a-segment"></a>Spore brugen af et segment

Du kan nu [spore brug af et segment](segments.md#track-usage-of-a-segment) i apps, der er baseret på Dataverse-organisationen, der er knyttet til Customer Insights. I forbindelse med [Customer Insights-segmenter, der bruges i kundekampagneforløb i Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), informerer systemet dig om brugen af dette segment.

### <a name="export-to-criteo"></a>Eksportere til Criteo

Criteo er en onlineplatform, der hjælper brugerne med at administrere digitale reklamer. Du kan nu eksportere segmenter af samlede kundeprofiler for at generere kampagner, levere mailmarketing og bruge bestemte kundegrupper med Criteo.

Du kan finde flere oplysninger under [Eksportere segmenter til Criteo (forhåndsversion)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Raffineret struktur for dokumentation af miljøoprettelse

Vi har revideret de hjælpedokumenter, der vedrører oprettelse og administration af miljøer i Customer Insights. Artiklerne er nu grupperet under noden Miljøer i indholdsfortegnelsen. De artikler, der oprettes, giver flere vejledninger til de forskellige måder at konfigurere miljøer på og få en mere klar struktur. Hvis du har feedback, du vil dele, skal du fortælle os det via kontrolelementerne mod slutningen af artiklerne i Hjælp.

Du kan finde flere oplysninger i [Sådan: Oprette et nyt miljø](create-environment.md).

## <a name="april-2022-updates"></a>Opdateringer i april 2022

Opdateringen i april 2022 omfatter nye funktioner, opgradering til ydeevne og fejlrettelser.

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet-forbedring (Forhåndsversion)

Dun & Bradstreet leverer kommercielle data, analyser og indsigt til virksomheder. Den gør det muligt for kunder, der har en samlet kundeprofil for virksomheder, at forbedre deres data. Forbedringer omfatter attributter, herunder DUNS-nummer, virksomhedsstørrelse, adresse, branche og mere.

Du kan finde flere oplysninger under [Forbedring af kundeprofiler med Dun & Bradstreet (Forhåndsversion)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Definere typen af måleenhed ved oprettelse af en ny måleenhed

Du kan nu skelne mellem mål for individuelle profiler og mål på tværs af hele virksomheden. Forretningstiltag vises på startsiden i Customer Insights, men kundetiltag vises i de detaljerede kundevisninger.

Flere oplysninger i [Brug af målgenerator til at oprette mål fra bunden](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Sammenlægning af dokumentationen til Customer Insights

Vi har revideret vores dokumentationsartikler og fjernet omtaler af indsigt i engagement og funktioner til indsigt i målgruppe. Fremover vil vi konsekvent referere til produktnavnet Customer Insights, når vi skriver om programmets kernefunktioner. Denne ændring medfører også, at indholdsfortegnelsen, URL-strukturen og filstierne i det underliggende dokumentationslager ændres betydeligt. Alle bogmærkerne eller de eksisterende links fungerer fortsat, og de omdirigeres til de opdaterede URL-adresser.

Hvis du vil fortælle os, hvordan du opfatter denne ændring eller opdager, at noget ikke virker som forventet, [kan du sende feedback til denne side](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Marts 2022-opdateringer

Opdateringen i marts 2022 omfatter nye funktioner, opgradering til ydeevne og fejlrettelser.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec-forbedring (forhåndsversion)

LiveRamp leverer identitetsløsning til offline og en sammenlægning af kundedata. Du kan knytte personlige id'er i kundedataene til AbiliTec-identitetsgrafen og modtage AbiliTec-id'er. Du kan derefter bruge disse id'er til at opnå en bedre samling af kundedata.

Du kan finde flere oplysninger i [Forbedre kundeprofiler med identitetsdata fra LiveRamp (forhåndsversion)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organisere segmenter og mål med koder og filtre

Hvis din organisation har mange segmenter eller mål, kan det være en udfordring at finde den rette. Med denne nye funktion kan du organisere lister ved hjælp af koder og kolonner. Det hjælper dig med at finde data hurtigt og nemt og tilpasse visningerne.

Du kan finde flere oplysninger under [Arbejde med koder og kolonner](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Aktiver datadeling med Dataverse, når du bruger din egen lagerkonto

Hvis dit miljø bruger Azure Data Lake Storage til at gemme Customer Insights-data, skal datadeling med Microsoft Dataverse bruge ekstra konfiguration.
Tidligere kunne du kun aktivere datadeling med Dataverse, når dine data blev gemt i vores administrerede datasø.

Flere oplysninger i [Aktivere datadeling med Dataverse fra din egen Azure Data Lake Storage (Forhåndsversion)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Nye eksportmål: Iterable og Braze

Vi fortsætter med at udvide vores muligheder for eksportmål med nye forbindelser. Du kan nu eksportere segmenter til Iterable og Braze for at bruge deres aktiveringstjenester.

Du kan finde flere oplysninger i [Eksportere segmenter til Iterable (forhåndsversion)](export-iterable.md) og [eksportere segmenter til Braze (forhåndsversion).](export-braze.md)

### <a name="improvements-to-marketo-and-google-ads-export"></a>Forbedringer af eksporten af Marketo og Google Ads

Ændring af API'er i forbundne tjenester fører til opdateringer, for at connectorer kan køre pålideligt og problemfrit. Vi har udgivet nogle opdateringer til eksporten til Marketo- og Google Ads-tjenesterne:

- Google Ads: Den nye version af Google Ads-eksport-connector forenkler godkendelsesoplevelsen og giver dig nu mulighed for automatisk at oprette nye Google Ads-målgrupper. 
- Marketo: Den nye version af Marketo-eksporttilslutning understøtter Marketo ID, så du kan undgå duplikering af data, opdatere eksisterende poster og oprette nye poster i Marketo. 

## <a name="february-2022-updates"></a>Februar 2022-opdateringer

Opdateringen i februar 2022 omfatter nye funktioner, opgradering til ydeevne og fejlrettelser.

### <a name="general-availability-for-prediction-models"></a>Generel tilgængelighed for forudsigelsesmodeller

Standardmodeller for forudsigelse, herunder **abonnementsafgang**, **transaktionsafgang** og **CLV (Customer Lifetime Value)** bliver generelt tilgængelige som en del af Customer Insights. 

Du kan finde flere oplysninger i [Oversigt over Forudsigelser](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Ny datakilde: Integration med Azure Synapse Analytics (forhåndsversion)

Azure Synapse Analytics er en virksomheds analysetjeneste, der øger den tid, der skal bruges på at få indsigt på tværs af datalager og big data-systemer.

Organisationer, der allerede bruger Azure Synapse Analytics, kan udnytte disse data til Customer Insights. 

Du kan finde flere oplysninger i [Oprette en Azure Synapse-datakilde (forhåndsversion)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp-forbedring (forhåndsversion)

LiveRamp leverer identitetsløsning til offline og en sammenlægning af kundedata. Du kan knytte personlige id'er i kundedataene til AbiliTec-identitetsgrafen og modtage AbiliTec-id'er. Du kan derefter bruge disse id'er til at opnå en bedre samling af kundedata.

Du kan finde flere oplysninger i [Forbedre kundeprofiler med identitetsdata fra LiveRamp (forhåndsversion)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Forbedring til datakilder (forhåndsversion)

Brug data fra kilder som Microsoft og andre partnere til at forbedre dine kundedata før datasamling. Datakilde hjælper dig med at opnå højere datafuldstændighed -kvalitet, der kan være med til at opnå bedre resultater, når du har samlet dataene.

Du kan finde flere oplysninger i [Forbedring til datakilder (forhåndsversion)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Skift miljøejer

Flere brugere kan have administratortilladelser i Customer Insights, men kun én bruger ejer et miljø. En forbedret oplevelse giver dig mulighed for at skifte ejer i et miljø og kræve ejerskab, hvis en tidligere ejer har forladt organisationen. 

Du kan finde flere oplysninger i [Skifte ejer af et miljø](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Dataforberedelsesprocessen indeholder årsagen til årsagen til, at dataforberedelsen er blevet beskadiget

Forberedelse af data viser nu årsagen til, at alle felter med beskadigede data er beskadiget. Oplysningerne gives på de enkelte postniveauer for at lette identifikationen. 

Du kan finde flere oplysninger i [Ødelagte datakilder](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Afslutning af forhåndsversion for rapporteringsfunktioner i funktionen engagementsindsigt

Forhåndsversionen Dynamics 365 Customer Insights af engagementsindsigt afsluttede 15. februar 2022.  
Denne ændring betyder, at prøveversionen af Customer Insights ikke længere omfatter muligheden for at oprette tragte eller andre rapporteringsfunktioner.

Vi inviterer dig til at undersøge og evaluere de mange andre funktioner i [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), Microsoft-kundedataplatformen (CDP).    
 
I en stilstandsperiode har eksisterende eksempel deltagere stadig adgang til visse eksempelfunktioner og funktioner:

- Hent kode til instrument et websted eller en mobilapp 
- Få vist egenskaber for hændelser og hændelser 
- Forbedre ensartede profiler ved hjælp af arrangementer med særlige behov og fordele for alle, så de kan drage fordel af alle kundedataene
  
I løbet af overgangsperioden streames tilfangetaget stadig til den tilknyttede Data Lake. Når denne funktionalitet er slået fra, standses datadelingen, og der sendes ingen nye hændelser til det tilknyttede lager.
Kontakt Microsoft-firmagruppen direkte, hvis du har spørgsmål til slutningen af forhåndsversionen af funktioner. Dit firmateam vil holde dig opdateret om kommende lanceringer. 

## <a name="january-2022-updates"></a>Opdatering fra januar 2022

Opdateringen i januar 2022 omfatter nye funktioner, opgradering til ydeevne og fejlrettelser.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Synspunktanalyse af din kundes feedback

Customer Insights indeholder en ny AI-baseret funktion, der kan sammenfatte kundernes synspunkt og identificere specifikke forretningsaspekter som muligheder for målrettede forbedringer. Ved at analysere den skriftlige feedback fra dine kunder kan du få nøjagtig indsigt med lave omkostninger. Synspunktsanalyser baseret på NLP-modeller (Natural Language Processing), der genererer to afledte indsigter for hvert kunde-id. En synspunktscore (på –5 til 5) og en liste over relevante forretningsaspekter. 

Du kan finde flere oplysninger i [Analysere synspunkt i kundefeedback (forhåndsversion)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]