---
title: Nye og kommende funktioner
description: Oplysninger om nye funktioner, forbedringer og rettelser i forbindelse med fejl.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547665"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Nyheder i målgruppen Insights-funktioner i Dynamics 365 Customer Insights

Vi er glade for at kunne fortælle om vores nyeste opdateringer! Denne artikel indeholder en oversigt over funktionerne i offentlig forhåndsversion, forbedring af generel tilgængelighed og funktionsopdateringer. Hvis du vil have vist de langsigtede funktionsplaner, skal du kigge i [frigivelsesplanerne for Dynamics 365 og Power Platform](/dynamics365/release-plans/).

Vi udruller opdateringerne område for område. Så visse geografiske områder kan se funktioner før andre. Medmindre andet er angivet, behøver du ikke at foretage dig noget, og vi opdaterer automatisk appen uden nedetid.

> [!TIP]
> Hvis du vil sende og stemme på populære ønsker og produktforslag, skal du gå til [Dynamics 365-portalen for programideer](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


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

Flere oplysninger i [Aktivere datadeling med Dataverse fra din egen Azure Data Lake Storage (Forhåndsversion)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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
  
I løbet af overgangsperioden streames tilfangetaget stadig til den tilknyttede Data Lake. Når denne funktionalitet er slået fra, standses datadelingen mellem engagementsindsigt og publikum, og der sendes ingen nye hændelser til det tilknyttede lager.
Kontakt Microsoft-firmagruppen direkte, hvis du har spørgsmål til slutningen af forhåndsversionen af funktioner. Dit firmateam vil holde dig opdateret om kommende lanceringer. 

## <a name="january-2022-updates"></a>Opdatering fra januar 2022

Opdateringen i januar 2022 omfatter nye funktioner, opgradering til ydeevne og fejlrettelser.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Synspunktanalyse af din kundes feedback

Customer Insights indeholder en ny AI-baseret funktion, der kan sammenfatte kundernes synspunkt og identificere specifikke forretningsaspekter som muligheder for målrettede forbedringer. Ved at analysere den skriftlige feedback fra dine kunder kan du få nøjagtig indsigt med lave omkostninger. Synspunktsanalyser baseret på NLP-modeller (Natural Language Processing), der genererer to afledte indsigter for hvert kunde-id. En synspunktscore (på –5 til 5) og en liste over relevante forretningsaspekter. 

Du kan finde flere oplysninger i [Analysere synspunkt i kundefeedback (forhåndsversion)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]