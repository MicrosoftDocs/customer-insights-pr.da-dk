---
title: Nye og kommende funktioner
description: Oplysninger om nye funktioner, forbedringer og rettelser i forbindelse med fejl.
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/30/2020
ms.locfileid: "4649997"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Nyheder i målgruppen Insights-funktioner i Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Vi er glade for at kunne fortælle om vores nyeste opdateringer! Denne artikel indeholder en oversigt over funktionerne i offentlig prøveversion, forbedring af generel tilgængelighed og funktionsopdateringer. Hvis du vil have vist de langsigtede funktionsplaner, skal du kigge i [frigivelsesplanerne for Dynamics 365 og Power Platform](https://docs.microsoft.com/dynamics365/release-plans/).

Du kan også se følgende video for at få mere at vide om de funktioner, der er planlagt for de sidste seks måneder.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Vi udruller opdateringerne område for område. Så visse geografiske områder kan se funktioner før andre. Medmindre andet er angivet, behøver du ikke at foretage dig noget, og vi opdaterer automatisk appen uden nedetid.

> [!TIP]
> Hvis du vil sende og stemme på populære ønsker og produktforslag, skal du gå til [Dynamics 365-portalen for programideer](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2020-updates"></a>Opdatering fra november 2020

Opdateringerne i november 2020 indeholder flere funktioner, opgraderinger af ydeevnen og fejlrettelser.

### <a name="new-and-updated-features-in-november-2020"></a>Nye og opdaterede funktioner i november 2020

#### <a name="data-enrichment"></a>Dataforbedring

- **Anbring dine egne tilsætningsdata via SFTP (Secure File Transfer Protocol)-brugerdefineret import**
  
  SFTP (Secure File Transfer Protocol) brugerdefineret import giver dig mulighed for at importere forbedret data, der ikke er brug for til at gennemgå processen for datasamling. Få mere at vide om SFTP-brugerdefineret import

  Du kan finde flere oplysninger under [Forbedring af kundeprofiler med brugerdefinerede data (prøveversion)](enrichment-SFTP-custom-import.md).
 
- **Forbedring af dine kundedata med placeringsdata fra HERE Technologies**

  Med dataforbedringstjenester i HERE Technologies kan du oprette en mere præcis placering for dine kunder med normalisering af adresser, bredde- og længdegrader og meget mere. Få mere at vide om forbedring af data med HERE Technologies.

  Du kan finde flere oplysninger under [Forbedring af kundeprofiler med HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Datasamling

- **Fleksibilitet til at aktivere dataprofilering for bestemte objekter og felter fra lagerkontoen**

  Du kan angive, hvilke dataobjekter og felter fra en almindelig datamodelmappe i din Azure Data Lake-lagerkonto du vil aktivere dataprofilering for som en del af processen for dataindsættelse.

  Du kan finde flere oplysninger under [Oprettelse af forbindelse til en fælles datamodelmappe](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Udvidelse

- **Aktivér dine segmenter via Google Ads**

  Eksportér segmenter fra Google Ads-målgruppelister, og brug dem til at annoncere på Google Search, Google Display Network, YouTube og Gmail. Få mere at vide om, hvordan du aktiverer dine segmenter via Google Ads.

  Du kan finde flere oplysninger i [Connector til Google Ads](export-google-ads.md).

- **Aktivér dine segmenter via Marketo**

  Eksportér segmenter til Marketo-målgrupper, og brug disse målgrupper til marketingautomatisering. Få mere at vide om, hvordan du aktiverer dine segmenter via Marketo. 

  Du kan finde flere oplysninger i [Connector til Marketo](export-marketo.md).

- **Aktivér dine segmenter via DotDigital**

  Eksportér segmenter til DotDigital, og brug dem til marketingformål. Få mere at vide om, hvordan du aktiverer dine segmenter via DotDigital. 

  Du kan finde flere oplysninger i [Connector til DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Forudsigelser

- **Transaktionsrelateret forudsigelse af afgang**

  Funktionen transaktionsrelateret forudsigelse af afgang gør det muligt for dig at forudsige, at en kunde ikke længere har adgang til at standse køb af produkter eller tjenester, uden at du kan få hjælp af en datatekniker.  Ved hjælp af forudsigelsesresultatet kan du kombinere andre oplysninger om dine kunder, f. eks. kundeværdi, til at oprette segmenter med stor risiko for afgang eller kunder med høj værdi. Brug dette segment til at målrette kunder direkte gennem marketingaktiviteter, kundesupport og andre scenarier for at reducere risikoen for afgang.
 
  Konfigurer definitionen af afgang som et tidsbaseret vindue, der er specifikt for virksomheden, og definer, hvornår kunderne anses for at være tabt. En butik kan f. eks. tage vurdere, at en kunde er tabt, hvis der ikke er købt noget i løbet af de seneste 30 dage.
 
  Når du fortsætter med at oprette forudsigelsen, hjælper vi med at finde de data, du skal bruge, og du får mulighed for at tilknytte data om virksomheden til felter, der er nødvendige for at forudsige dine kunders afgang. Du kan også angive en plan for at genbruge modellen på baggrund af nye oplysninger i systemet, så den tilpasses i forhold til ændringer i forretningssituationer.
 
  Du kan finde flere oplysninger i [Transaktionsrelateret forudsigelse om afgang (prøveversion)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Systemadministration

- **Nulstil miljø**

  Nulstil alt i et miljø for en valgt forekomst, for at starte forfra.

  Du kan få flere oplysninger under [Nulstil et eksisterende miljø](manage-environments.md#reset-an-existing-environment).


- **Opret forbindelse til din Azure Data Lake-lagerkonto ved hjælp af en tjenestekonto**

  Skriv dataoutput til og læse data fra din lagerkonto ved hjælp af en Azure-tjenestekonto. Eksisterende lagerkontoforbindelser kan fortsætte med at bruge kontonøglen. De indeholder også en opgraderingsindstilling, der kan bruges til at bruge den tjenestekonto, der flytter videre. Nye forbindelser er baseret på tjenestens hovedgodkendelsesmetode for lagerkontoen.

  Der er flere oplysninger i [Opret forbindelse til en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto til målgruppen Insights](connect-service-principal.md).

## <a name="october-2020-updates"></a>Opdateringer fra oktober 2020

Opdateringerne i oktober 2020 indeholder flere funktioner, opgraderinger af ydeevnen og fejlrettelser.

### <a name="new-and-updated-features-in-october-2020"></a>Nye og opdaterede funktioner i oktober 2020

#### <a name="extensibility"></a>Udvidelse

- **Eksport til Mailchimp**

Eksportér segmenter til eksisterende målgruppelister i Mailchimp for at oprette en personlig e-mailoplevelse for dine kunder.

Du kan finde flere oplysninger i [Connector til Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Dataforbedring

- **Deduplikering af kildeposterne i et objekt, der matcher**

Angiv regler for fjernelse af dubletter for objekter, der bruges i overensstemmelses processen, til at identificere dubletposter. Flet dem til én post, og sammenkæd alle kildeposterne med denne flettede post. Denne deduplikerede post anvendes derefter i processen med match af krydsobjekt.

Du kan finde flere oplysninger i [Definition af deduplikering for et match-objekt](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Systemadministration

- **Organisering: Ny opdateringsindstilling i Fletning**

Indtil i dag kører systemet alle de downstream-processer, der er afhængige af flettede og efterfølgende processer, når du kører fletteprocessen. Du kan nu kontrollere fletteprocessens output (det samlede kundeobjekt), før du bruger det i downstream-behandling, f. eks. segmenter eller målpunkter.
På flettesiden kan du nu vælge kun at køre flettetrinnet og kun køre denne proces. Hvis du f. eks. vil opdatere alle downstream-processer, kan du vælge at køre flette- og downstream-processer. 

## <a name="september-2020-updates"></a>Opdateringer fra september 2020

Opdateringerne fra september 2020 indeholder flere funktioner, ydeevneopgraderinger og fejlrettelser.

### <a name="new-and-updated-features-in-september-2020"></a>Nye og opdaterede funktioner i september 2020

#### <a name="activities"></a>Aktiviteter

- **Intelligent forudsigelse af attributsemantik**

Denne nye funktion bruges til at forudsige de semantiske typer af inputattributter, der overføres til datasamlingsprocessen. Den bruger modeller til maskinel indlæring, der forbedrer præcisionen og sparer tid.

#### <a name="enrichments"></a>Forbedringer

- **Demografiske forbedringer fra Experian**

Den demografiske forbedring fra Experian er nu tilgængelig som prøveversion. Experian er en global leder i forbruger- og virksomhedskreditrapportering og marketingservice. Med [Experians dataforbedringstjenester](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) kan du få en dybere forståelse af dine kunder ved at udvide dine kundeprofiler med demografiske data, f.eks. husstandens størrelse og indkomst og meget mere.

Hvis du vil bruge denne funktion, skal du have et aktivt Experian-abonnement.

Du kan finde flere oplysninger under [Forbedre kundeprofiler med demografi fra Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Systemadministration

- **Ruden Opgavedetaljer**

Ruden med opgavedetaljer giver dig mulighed for at se detaljer om de opgaver, systemet kører. Det er en praktisk måde at identificere problemer i forbindelse med konfiguration og søgning efter løsninger.
Gennemse fejlmeddelelserne, og få mere at vide om, hvordan du løser potentielle problemer.
 
- **Behandling af oplysninger, der er tilføjet på flere sider**

Denne forbedring tilføjer oplysninger om status for objekterne på siderne **Objekter** og **Kunder**.
 
Derudover kan du finde detaljer om forløbet af processer samt detaljer om opgaven på begge sider.

- **Forbedringer af systemstatussiden**

Vi har forbedret strukturen af den tabel med statusdetaljer om **System** > **status**, der vises, når du gennemgår dataeksport.
 
Fejl i kolonnen **Detaljer** er nu desuden mere detaljeret og brugbar. 
 
- **Annuller tilbagefører job til forrige tilstand**

Når du annullerer en opgave f.eks. i matchningsprocessen, gendannes den i den nyeste tilstand. Hvis matchningsprocessen f.eks. blev fuldført i går, og du annullerer den i dag, vender den tilbage til tilstanden fra i går.


## <a name="august-2020-updates"></a>Opdateringer fra august 2020

Opdateringerne fra august 2020 indeholder flere funktioner, ydeevneopgraderinger og fejlrettelser.

### <a name="new-and-updated-features-in-august-2020"></a>Nye og opdaterede funktioner i august 2020

#### <a name="data-unification"></a>Datasamling

- **Forbedret oplevelse af kortfasen under datasamlingen**

  Oplevelsen af kortfasen i datasamlingsprocessen giver dig mulighed for at vælge objekter, attributter og definere semantik på en mere problemfri måde.

  Ændringer omfatter:
  
  - Der kræves færre interaktioner for at tilføje objekter og felter
  - Forbedrede søgefunktioner på kortsiden
  - Visuel og let identifikation af den foreslåede felttype

#### <a name="enrichment"></a>Forbedring

- **Forbedring af interessetilhørsforhold gøres tilgængelig på flere markeder**

  Vi er ved at udvide tilgængeligheden af de forbedrede interessetilhørsforhold ud over USA til fem ekstra markeder: Canada, Australien, Storbritannien, Frankrig og Tyskland. Med denne udvidelse kan du forbedre dine kundedata med yderligere interesser, der gælder for disse markeder. Vi har også forbedret de kundeprofiler, der er placeret på disse markeder, ved hjælp af lokale, beskyttede data fra Microsoft Graph.
  Du kan finde flere oplysninger i [Forbedre kundeprofiler med mærketilhørsforhold og interesser](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Opdateringer i juli 2020

Opdateringerne fra juli 2020 indeholder flere funktioner, opgraderinger af ydeevnen og fejlrettelser.

### <a name="new-and-updated-features-in-july-2020"></a>Nye og opdaterede funktioner i juli 2020

#### <a name="extensibility"></a>Mulighed for udvidelse

- **Power Automate-udløser for fuldført samlingsproces**

  Vi har udvidet udløserne for Power Automate og givet dig mulighed for at oprette en besked eller handling, når en opdatering af samlingsprocessen (tilknytning, match, fletning) er fuldført.    
  Du kan finde flere oplysninger under [Power Automate-connector](export-power-automate.md)

#### <a name="enrichment"></a>Forbedring

- **Forbedring af mærketilhørsforhold er tilgængelig på flere markeder**

  Vi er ved at udvide tilgængeligheden af forbedringen af mærketilhørsforhold ud over USA til fem supplerende markeder: Canada, Australien, Storbritannien, Frankrig og Tyskland. Med denne udvidelse kan du forbedre dine kundedata med lokale mærker på disse markeder. Vi har også forbedret de kundeprofiler, der er placeret på disse markeder, ved hjælp af lokale, beskyttede data fra Microsoft Graph.
  Du kan finde flere oplysninger i [Forbedre kundeprofiler med mærketilhørsforhold og interesser](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Opdateringringer i juni 2020

Opdateringerne fra juni 2020 indeholder flere funktioner, opgraderinger af ydeevnen og fejlrettelser.

### <a name="new-and-updated-features-in-june-2020"></a>Nye og opdaterede funktioner i juni 2020

#### <a name="enrichment"></a>Forbedring

- **Forbedring med virksomhedsdata fra Leadspace**
  
  Definer de felter i samlede kundeprofiler, der bruges til at søge efter relaterede firmadata i Leadspace. Når du har kørt forbedringen, er B2B-profiler udvidet med ekstra attributter, herunder virksomheds størrelse, placering, branche og meget mere.    
  Dette samarbejde gør det muligt forbedre kvaliteten af dine data med input fra tredjepartstjenester. Hvis du vil bruge denne forbedring, skal du have en licens fra Leadspace for at få adgang til sine B2B-virksomhedsdata. Systemet bruger den pågældende licens til løbende at holde dine data beskrivende.    
  Du kan finde flere oplysninger under [Forbedring af virksomhedsprofiler med Leadspace](enrichment-leadspace.md).

- **Hubside for forbedring**

  Alle tilgængelige dataforbedringer fra første og tredjepartsleverandører af forbedringer konfigureres samme sted. Konfiguration af dataforbedring er en problemfri funktion, der administreres fra et fælles sted.    
  Du kan finde flere oplysninger under [Forbedring af kundeprofiler](enrichment-hub.md).

- **Separat forbedring med mærketilhørsforhold og interesser**

  Mærketilhørsforhold og interesser er nu tilgængelige som to uafhængige forbedringer. Adskilte forbedringer gør konfigurationen og administrationen fleksibel, så de kan tilpasses virksomhedens krav eller behov.    
  Du kan finde flere oplysninger i [Forbedre kundeprofiler med mærketilhørsforhold og interesser](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Mulighed for udvidelse

- **Klikbare URL-adresser til samlede aktiviteter i tilføjelsesprogrammet for Dynamics 365-kundekort**

  De samlede aktiviteter i tilføjelsesprogrammet kundekort vises nu med URL-adresserne, hvis der er defineret sådanne URL-adresser under konfigurationen af aktiviteter.    
  Du kan finde flere oplysninger under [Tilføjelsesprogrammet Kundekort](customer-card-add-in.md).

- **Mærketilhørsforhold og interesser, der er tilgængelige i tilføjelsesprogrammet for Dynamics 365-kundekort**

  Du kan bruge et nyt kontrolelement i tilføjelsesprogrammet for Dynamics 365-kundekort kan du se forbedringer af mærker og interesser for dine kontaktpersoner i Customer Engagements-apps i Dynamics 365.    
  Du kan finde flere oplysninger under [Tilføjelsesprogrammet Kundekort](customer-card-add-in.md).

- **Flere Power Automate-udløsere**

  Vi har udvidet udløserne for Power Automate og tilføjet følgende udløsere:
  - Få en besked eller udfør en handling, når en automatisk fuld opdatering (datakilder, samling, målgrupper, målinger, eksporter) er fuldført
  - Definer en tærskel for en forretningsmæssig måling. Du kan f.eks. oprette en besked, der sendes, når den definerede tærskel overskrides. Derudover henter udløseren oplysninger, som gør det muligt at opbygge mere komplekse arbejdsprocesser i Power Automate.    
  Du kan finde flere oplysninger under [Power Automate-connector](export-power-automate.md)

- **Eksportere til Facebook Annonceadministrator**
  
  Denne egenskab giver dig mulighed for at eksportere segmenter til Facebook Ads Manager. Segmenter eksporteres som brugerdefinerede målgrupper for at bruge samlede kundeprofiler i Facebook-marketingkampagner og -reklamer. De brugerdefinerede målgrupper kan også bruges til at oprette kampagner på Instagram via Facebook Annonceadministator.    
  Du kan finde flere oplysninger under [Connector til Facebook Annonceadministrator](export-facebook.md).

#### <a name="predictions"></a>Forudsigelser

- **Forudsigelse af abonnementsafgang**

  Følg en styret oplevelse for at oprette forudsigelse af afgang for abonnementsområder som f.eks. cloudtjenester, kundemedlemskab og andre sektorer. 

  Med funktionen til forudsigelse af abonnementsafgang kan du forudsige sandsynligheden for, at en kunde stopper med at bruge abonnementsbaserede produkter eller servicer, uden at du behøver inddrage en dataekspert. Med forudsigelsesscoren kan du kombinere andre oplysninger om dine kunder for at definere målgrupper med høj afgangsrisiko. Ved hjælp af dette segment kan du direkte målrette kunderne mod marketing, kundesupport og andre scenarier for at reducere risikoen for tab af bestemte kunder for at øge omsætningen og reducere omkostningerne.

  I løbet af oplevelsen, kan du konfigurere definitionen af afgang som et tidsbaseret vindue, der er specifikt for din virksomhed. En videostreamingvirksomhed med en månedsbaseret abonnementsproces kan f.eks. betragte en kunde som mistet efter 15 dage efter udløbet af kundens abonnement.

  Når du fortsætter med forudsigelsen, vil vi føre dig gennem, hvilke data du skal bruge, så du kan knytte data om din virksomhed til felter, der er nødvendige for at forudsige afgang blandt dine kunder. Når forretningsoplysninger ændres, kan du også angive en tidsplan for, hvordan nye oplysninger i systemet skal justeres, så de afspejler ændringerne i virksomhedens forhold.    
  Du kan finde flere oplysninger under [Forudsigelse af abonnementsafgang (eksempel)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmenter

- **Find lignende kunder**
  
  Find lignende kunder i kundebasen ved hjælp af kunstig intelligens. En binær klassificeringsmodel baseret på maskinel indlæring tildeler en lighedsscore til kunder i den udvidede målgruppe. Scoren er baseret på lighed med kunderne i kildesegmentet. Afhængigt af lighedsscoren føjes kundeprofiler til en nyoprettet målgruppe.

  Dette kaldes nogle gange lookalike-modellering inden for digital marketing, idet der anvendes en AI-model til at finde de kunder, som svarer til en anden målgruppe af kunder, ved at indregne flere attributter. Det gør det ikke kun muligt at vælge attributterne, men du kan også angive det maksimale antal kunder, der skal indgå i den nye målgruppe. AI-modellen beregner derefter lighedsscoren for hver enkelt kunde ud fra de valgte attributter og søger efter kunder med den højeste gennemsnitlige lighedsscore. Den resulterende målgruppe indeholder de kunder, der ligner kunden i det oprindelige segment.    
  Se [Lignende kunder](find-similar-customer-segments.md) for at få flere oplysninger.

- **Overlapning og differentiering af målgrupper**

  Gennem målgruppers overlapning kan du se, hvor mange og hvilke kunder der er fælles for to eller flere målgrupper. F.eks. hvordan målgruppen for kunder med stort forbrug overlapper en målgruppe af kunder med stor tilfredshed, eller hvordan en målgruppe for mistede kunder overlapper en målgruppe med lav tilfredshed. Derudover kan du analysere, hvordan overlapningen ændrer sig ud fra de attributter, du vælger.

  Differentiering af målgrupper afslører, hvad der adskiller én målgruppe fra de øvrige kunder eller en anden målgruppe. Det eneste, du skal gøre, er at identificere en målgruppe, så vil systemet identificere de profilattributter og målinger, der kendetegner målgruppen, i form af en sorteret liste over differentieringer – fra den mest markante differentiator til den mindst markante.    
  Du kan finde flere oplysninger under [Indsigt i målgrupper (eksempel)](segment-insights.md).

- **Levetid for målgruppe**
  
  Definer en tidsplan for aktivering eller deaktivering af en målgruppe.    
  Du kan finde flere oplysninger under [Administrere eksisterende målgrupper](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Opdateringer i maj 2020

Opdateringerne fra maj 2020 indeholder flere funktioner, ydeevneopgraderinger og fejlrettelser.

### <a name="new-and-updated-features-in-may-2020"></a>Nye og opdaterede funktioner i maj 2020

#### <a name="data-ingestion"></a>Dataindtagelse

- **Dataindtagelse i realtid: historikvisninger**

  Når du bruger vores API til at indtage opdateringer i realtid, kan du se op til 30 dages aggregeret historik for disse opdateringer. Du har adgang til aggregeringer af alle vellykkede eller mislykkede API-kald, herunder udfald, kildesystem og andre nyttige metadata.    
  Du kan finde flere oplysninger under [Dataindtagelse i realtid](real-time-data-ingestion.md).

- **Dataindtagelse i realtid: profilopdateringer**

  Med denne udvidelse af dataindtagelse i realtid kan du i løbet af få sekunder se, om der er ændringer i bestemte brugerprofilfelter.    
  Ud over realtidsfunktionaliteten af aktiviteter understøtter systemet opdateringer af lav latenstid til profilfelter. Realtidsopdateringer til profilfelter har en udløbstid og er derfor ikke en erstatning for planlagte opdateringer.    
  Du kan finde flere oplysninger under [Dataindtagelse i realtid](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Mulighed for udvidelse

- **Opdateret tidslinje og sideinddeling på tilføjelsesprogrammet Kundekort**

  Tidslinjen for tilføjelsesprogram løsningen for kundekort stemmer overens med tidslinjen for aktiviteten. Sideinddelingen af tidslinjen er forbedret og viser op til 50 aktiviteter på én gang. Den gør det også muligt at indlæse flere aktiviteter på tidslinjen.    
  Du kan finde flere oplysninger under [Tilføjelsesprogrammet Kundekort](customer-card-add-in.md).

- **Power Automate-udløser for segmentændringer**

  Udløsere til Power Automate for at definere, hvad du kan oprette et flow fra. Med den netop tilføjede udløser kan definere en tærskel for et segment. Du kan f.eks. oprette en besked, der sendes, når den definerede tærskel overskrides.    
  Du kan finde flere oplysninger i [Power Automate-connector](export-power-automate.md).

- **Understøttelse af multiprofil for brugerdefinerede modeller**

  Konfigurer arbejdsprocesser for brugerdefinerede modeller med en webtjeneste i en anden Azure Machine Learning-lejer. Du kan logge på Azure Machine Learning-lejeren, når du opretter en ny arbejdsproces for brugerdefinerede modeller. Denne funktion er en tilføjelse til den eksisterende mulighed for at integrere med din egen brugerdefinerede Azure Machine Learning-webtjeneste.    
  Du kan finde flere oplysninger i [Tilpasse modeller til maskinel indlæring](custom-models.md).

#### <a name="segments"></a>Segmenter

- **Automatisering af objektsti**

  Når du opretter et segment, skal brugerne definere stien til objektet. Denne funktion er det første trin til at automatisere definitionen af objektstien, så du kan fokusere på de ønskede segmenteringskriterier.    
  Hvis det objekt, som du vil segmentere dine kunder til, er direkte relateret til det samlede kundeobjekt, behøver du ikke længere at definere objektstien. Men hvis der er mere end én mulig sti for et objekt, skal du stadig definere den manuelt.

- **Handlinger på flere segmenter**
  
  Brugerne kan vælge flere segmenter og udføre handlinger på dem, f.eks. opdatere segmenterne med et enkelt klik.    

- **Opdatere segmenter**

  Brugerne kan opdatere et enkelt segment eller kun vælge de segmenter, de vil opdatere.    

  
- **Forbedringer af sammensatte segmenter**

  Brugerne kan oprette, redigere og slette segmenter, der er baseret på andre segmenter. F.eks. et segment, der er oprettet på et andet segment, som blev bygget på et tredje segment.    

- **Side med segmentliste**

  I det nye design af siden med segmenter bruges der et listeformat, hvor du kan se flere segmenter på én gang. Der er tilføjet et søgefelt for hurtigt at finde segmenter. Brugerne kan nu anvende handlinger, f.eks. download eller sletning af flere segmenter på én gang. Der introduceres en ny tendensoplevelse, som hurtigt kan identificere betydelige ændringer af segmenter.    
  Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).

#### <a name="system-administration"></a>Systemadministration

- **Customer Insights tilgængelig i Microsoft Dynamics 365 Online Government**

  Med flere og flere kanaler til interaktioner, spredes borgernes data hen over at væld af systemer, hvilket fører til silodata og en fragmenteret visning af oplysninger om borgernes interaktioner. Uden en komplet visning af de enkelte borgeres interaktioner på tværs af kanaler er det umuligt for offentlige myndigheder at modernisere i stort omfang. Microsoft arbejder målrettet for at støtte de teknologiske behov hos offentlige myndigheder for at holde trit med borgernes forventninger til konsekvente og funktionelle oplevelser.    
  Med frigivelsesbølge 1, 2020 vil Dynamics 365 Customer Insights være tilgængelig for Government Community Cloud (GCC), et miljø, der er bygget til at opfylde de større behov for overholdelse af angivne standarder hos de offentlige amerikanske myndigheder. Agenturerne opnår en samlet visning af borgerne og bruger en forudbygget AI til at få den indsigt, der forbedrer interaktioner, styrker medarbejdere og transformerer samfund, samtidig med at det reducerer IT-kompleksiteten og overholder de amerikanske og sikkerhedsmæssige standardkrav. Dynamics 365 Government lever op til de krævende behov i USA's Federal Risk and Authorization Management Program (FedRAMP),så de føderale regeringskontorer i USA kan drage fordel af omkostningsbesparelserne og den strenge sikkerhed i Microsoft Cloud.

## <a name="april-2020-updates"></a>Opdateringer i april 2020

Opdateringerne fra april 2020 indeholder flere funktioner, ydeevneopgraderinger og fejlrettelser.

### <a name="new-and-updated-features-in-april-2020"></a>Nye og opdaterede funktioner i april 2020

#### <a name="activities"></a>Aktiviteter

- **Knyt aktivitetsobjekt til standardaktivitetstype**
  
  Aktivitetskonfiguration og lager er i øjeblikket baseret på et statisk design for at få dem vist på en tidslinje. Den semantiske betydning af aktiviteterne, som har mulighed for flere brugsmønstre i AI-modeller, bruges ikke fuldt ud i øjeblikket. Vi planlægger at gøre aktivitetstidslinjen mere dynamisk baseret på aktivitetstypen og mere semantisk forståelse for aktiviteterne. Denne funktion er med til at identificere den aktivitetstype, som er defineret i Common Data Model for enhver indtaget aktivitet.
  Du kan finde flere oplysninger under [Kundeaktiviteter](activities.md).

#### <a name="data-ingestion"></a>Dataindtagelse

- **Dataindtagelse i realtid: aktiviteter**
  
  Realtidsfunktionen med indsættelse af data leverer data med det samme til forbrug, indtil den efterfølgende planlagte opdatering henter disse data fra datakilden.    
  Du kan finde flere oplysninger under [Dataindtagelse i realtid](real-time-data-ingestion.md).

- **Forbedringer af dataforberedelse**
  
  Få mere at vide om dataindtagelse i et objekt. Med dataopsummeringen kan du forstå de egenskaber for datakvalitet, der kan hjælpe dig med at udføre de nødvendige handlinger.    
  Du kan finde flere oplysninger under [Undersøge objektdata](entities.md#exploring-a-specific-entitys-data).

- **Indtage analysedata fra Dynamics 365 med Common Data Service**
  
  Common Data Service er tilgængelig som en måde at oprette datakilder på. Eksisterende Dynamics 365-kunder kan indtage analyseobjekter fra Common Data Service til Customer Insights. En enkelt datakilde kan bruge samme Common Data Service-administrerede Data Lake i et Customer Insights-miljø.    
  Du kan finde flere oplysninger under [Oprette forbindelse til data i en Common Data Service-administreret datasø](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Mulighed for udvidelse

- **Eksport til LiveRamp**

  Aktivér dine data i LiveRamp® for at oprette forbindelse til mere end 500 platforme på tværs af digitale, sociale og TV-økosystemer. Udnyt dine data i LiveRamp til målretning, udeladelse og tilpasning af reklamekampagner.    
  Du kan finde flere oplysninger under [LiveRamp&reg;-connector](export-liveramp.md).

- **Tilføjelsesprogrammet Teams til Customer Insights**
  
  Botten leverer opslagsmuligheder for samlede kundeprofiler. Der vises et kort med op til 15 felter fra den oprettede kundeprofil. Flere forekomster returnerer en liste med resultater, hvor du kan vælge en profil.    
  Du kan finde flere oplysninger i [Teams-robot til Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Målinger

- **Listesiden med målinger**
  
  Forbedringer af siden med målinger omfatter understøttelse af handlinger på en enkelt måling og flere målinger på én gang. Du kan også finde et søgefelt for hurtigt at søge efter og spore målinger.    
  Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).

- **Forbedringer af sammensatte målinger**
  
  Brugerne kan oprette, redigere og slette målinger, der er baseret på andre målinger. F.eks. en måling, der er oprettet på en anden måling, som blev bygget på en tredje måling.

#### <a name="segments"></a>Segmenter

- **Ekstra operator**
  
  In-set-operatoren gør det muligt for kunder at segmentere efter flere forskellige strengværdier. Før denne operator blev tilføjet, skulle du oprette sådanne segmenter med flere eller OR-betingelser. In-set-operatoren giver dig mulighed for at gøre det med en enkelt betingelse.    
  Du kan finde flere oplysninger under [Oprette og administrere segmenter](segments.md).

#### <a name="system-administration"></a>Systemadministration

- **Kopiering af konfigurationsindstillinger til et nyt miljø**
  
  Kopier din konfiguration fra et miljø til et andet. Når du opretter et nyt miljø, kan du vælge et eksisterende miljø, som du vil kopiere konfigurationen fra. Vi understøtter i øjeblikket datakilder, datasamling, relationer, målinger og segmenter til kopiering. Datakilders legitimationsoplysninger og faktiske data kopieres ikke.    
  Du kan finde flere oplysninger under [Administrere miljøer](manage-environments.md).
