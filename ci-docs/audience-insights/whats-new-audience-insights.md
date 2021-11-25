---
title: Nye og kommende funktioner
description: Oplysninger om nye funktioner, forbedringer og rettelser i forbindelse med fejl.
ms.date: 11/04/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: f7e2645e1608ea83b5d3af1073a5d6f6e97eec8f
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753110"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Nyheder i målgruppen Insights-funktioner i Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Vi er glade for at kunne fortælle om vores nyeste opdateringer! Denne artikel indeholder en oversigt over funktionerne i offentlig prøveversion, forbedring af generel tilgængelighed og funktionsopdateringer. Hvis du vil have vist de langsigtede funktionsplaner, skal du kigge i [frigivelsesplanerne for Dynamics 365 og Power Platform](/dynamics365/release-plans/).

Vi udruller opdateringerne område for område. Så visse geografiske områder kan se funktioner før andre. Medmindre andet er angivet, behøver du ikke at foretage dig noget, og vi opdaterer automatisk appen uden nedetid.

> [!TIP]
> Hvis du vil sende og stemme på populære ønsker og produktforslag, skal du gå til [Dynamics 365-portalen for programideer](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="october-2021-updates"></a>Opdateringer fra oktober 2021

Opdateringerne i oktober 2021 indeholder nye funktioner, ydeevneopgraderinger og fejlrettelser.

### <a name="b-to-b"></a>B-til-B

Med start i oktober 2021 kan du arbejde med forretningskonti og deres relaterede kontaktpersoner i Customer Insights. Før var appen stort set skræddersyet til individuelle målgrupper. Flere funktionsområder er blevet opdateret, så de understøtter B-til-B-scenarier oven på en ny miljøtype. Du kan få en oversigt over understøttede B-til-B-funktioner under [Arbejde med forretningskonti målgruppeindsigt](work-with-business-accounts.md).

I følgende afsnit fremhæves nogle af de vigtigste områder, der er tilpasset til at understøtte virksomhedskonti og individuelle behov.

#### <a name="export-segments-based-on-business-accounts"></a>Eksport af segmenter baseret på forretningskonti

Alle segmenteksporter i målgruppeindsigt er tilgængelige i forbindelse med forretningskonti. De fleste eksporter af segmenter kræver, at ekstra konfigurations- og [kontaktoplysninger projekteres](segment-builder.md#create-a-new-segment) i de underliggende segmenter, så de kan anvendes på forretningskonti. Du kan finde flere oplysninger under [Eksportere segmenter](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>Brug af eksporten af LinkedIn Ads til forretningskonti

Eksporten af LinkedIn Ads er nu tilgængelig for kontakt- og virksomhedsmålretning i forbindelse med forretningskonti. Når du vælger virksomhedsmålretning som dit primære fokus i forbindelse med LinkedIn-eksporten, kan du eksportere de segmenter, der er opbygget på forretningskonti, uden at det er nødvendigt at projektkontaktoplysninger. Du kan finde flere oplysninger i dokumentationen om [eksport af LinkedIn-annoncer](export-linkedin-ads.md) og forskellen mellem [at målrette kontakter](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) og [at målrette virksomheden](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Oprette mål på baggrund af forretningskonti og deres hierarki

Med målgeneratoren kan du oprette mål omkring forretningskonti og eventuelt bruge hierarkioplysningerne. Hierarkioplysninger bruges til at akkumuler en måleenhedsberegning på tværs af et firma og alle relaterede underordnede firmaer. Du kan f.eks. oprette mål som den samlede omsætning for hver gruppe af forretningskonti, der identificeres af deres hierarki. Du kan finde flere oplysninger under [Definér, og administrer målpunkter](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Oprette segmenter på baggrund af forretningskonti og deres hierarki

Du kan bruge segmentgeneratoren til at oprette forretningssegmenter, der eventuelt indeholder kontaktoplysninger for hvert firma i et segment. Hvis du har konfigureret firmahierarkiet, kan du bruge oplysninger om firmahierarkier i forbindelse med oprettelse af segmenter. Du kan finde flere oplysninger i [Oprette et nyt segment](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Bevare virksomhedskontiene med omfattende indsigt i virksomhedens kunder

Forudsigelsesmodellen til kundeafgang understøtter nu også forretningskonti. Du kan vurdere risikoen for kundeafgang ikke kun for et firma, men for en kombination af et firma og en produkt- eller servicekategori, de køber af dig. Derudover kan du se, om et firma med større sandsynlighed vil ophøre med at købe af dig generelt eller kun for en bestemt kategori af varer eller servicer. Hvis du yderligere vil bruge denne AI-model, vises der også en liste over årsager til, at et firma sandsynligvis vil blive brugt. Du kan finde flere oplysninger i [Forudsigelse om transaktionsafgang (forhåndsversion)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Få vist kontaktpersoner for et forretningskonto i kundevisningen

Hvis forretningskonti er knyttet til relaterede firmaer, viser appen Customer Insights disse relaterede kontakter som en del af visningen med kundedetaljer. Du kan finde flere oplysninger i [Debitorprofiler](customer-profiles.md).


## <a name="september-2021-updates"></a>Opdateringer fra september 2021

Opdateringerne i september 2021 indeholder nye funktioner, ydeevneopgraderinger og fejlrettelser.

### <a name="activities"></a>Aktiviteter

- **Forbedringer af aktivitetstidslinjen** Vi har udvidet filtrene til aktivitetstidslinjen på kundeprofiler. Derudover kan du bruge den nye filterrude til at filtrere efter aktivitetstype og dato. Datoer kan filtreres ved hjælp af forskellige betingelser. Du kan finde flere oplysninger i [Se aktivitetstidslinjer for kundeprofiler](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Relationer

- **Understøttelse af multi-hop-relation** Brug multi-hop-relationer under konfiguration af aktiviteter og definition af relationer mellem objekter. Multi-hop-relationer bruger et midlertidigt objekt til at forbinde to objekter. Når du konfigurerer en aktivitet, kan du bruge en multi-hop-relation til at knytte aktivitetsobjektet til et midlertidigt objekt og derefter til et kundeobjekt. Du kan kombinere multi-hop-relationer og relationer med flere forbindelser. Du kan finde flere oplysninger under [Multi-hop-relation](relationships.md#multi-hop-relationship).

- **Understøttelse af relation med flere forbindelser** Brug relationer med flere forbindelser under konfiguration af aktiviteter og definition af relationer mellem objekter. Relationer med flere forbindelser relaterer et kildeobjekt til mere end ét objekt. Når du konfigurerer en aktivitet, kan du bruge en relation med flere forbindelser til at knytte aktivitetsobjektet til mere end ét kundeobjekt. Du kan kombinere relationer med flere forbindelser med multi-hop-relationer. Du kan finde flere oplysninger under [Relation med flere forbindelser](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Opdateringer fra august 2021

Opdateringerne i juli og august 2021 indeholder en ny funktion, ydelsesopgradering og fejlrettelser.

### <a name="extensibility"></a>Udvidelse

- **Eksportsegmenter til Klaviyo** Vi har udvidet vores [eksportdestinationer til at omfatte Klaviyo](export-klaviyo.md). Du kan nu eksportere segmenter til at oprette kampagner, gennemføre mailmarketing og bruge bestemte grupper af kunder med Klaviyo. 


## <a name="june-2021-updates"></a>Opdateringringer i juni 2021

Opdateringerne fra juni 2021 indeholder flere funktioner, opgraderinger af ydeevnen og fejlrettelser.

### <a name="data-ingestion"></a>Dataindtagelse

- **Forbedrede statusopdateringer til datasammenføring** Du kan nu få vist mere detaljerede, forbedrede dynamiske statusopdateringer om trinnene til [datasammenføringsprocessen](data-unification.md). Med denne funktion kan du holde styr på de detaljerede fremskridt for at forstå procesflowet og handle, hvis et trin kræver opmærksomhed.

### <a name="extensibility"></a>Udvidelse

- **Eksportér segmenter og andre data til Salesforce Marketing Cloud** Vi har udvidet vores eksportdestinationer til at omfatte [Salesforce Marketing Cloud](export-salesforce.md). Du kan nu eksportere segmenter og andre typer data til Salesforce Marketing Cloud via en brandet SFTP-eksport. Dataimport kan automatiseres fuldt ud i Salesforce og bruges til at oprette mere effektive marketingkampagner.  
 
- **Eksportsegmenter til ActiveCampaign** Vi har udvidet vores eksportdestinationer til at omfatte [Aktiv kampagne](export-active-campaign.md). Du kan nu eksportere segmenter til at generere kampagner, køre mailmarketing og arbejde med bestemte grupper af kunder i ActiveCampaign.
 
- **Eksportsegmenter til Sendinblue** Vi har udvidet vores eksportdestinationer til at omfatte [Sendinblue](export-sendinblue.md). Du kan nu eksportere segmenter til at generere kampagner, køre mailmarketing og arbejde med bestemte grupper af kunder med Sendinblue.
 
### <a name="ux-updates"></a>UX-opdateringer 

- **Ny og forbedret kundeside og side med profildetaljer** Vi har redesignet siden Kunder og profildetaljesiderne for at forbedre brugeroplevelsen og øge ydeevnen. Med disse ændringer kan du få vist, sortere, søge efter og filtrere kunder. Filtre er nu repræsenteret i URL-adressen for at dele søgeresultaterne med andre brugere uden problemer. Søgeresultater kan også gemmes som et segment.    
  Detaljesiden for kundeprofiler grupperer nu data i forskellige underafsnit, f.eks. demografiske data, ID'er og andre profilattributter til øget læsbarhed. Andre afsnit på siden med profiloplysninger er nu mere interaktive. Sektionen med aktiviteter tillader f.eks. filtrering og sortering.


## <a name="may-2021-updates"></a>Opdateringer i maj 2021

Opdateringerne i maj 2021 indeholder flere funktioner, ydelsesopgraderinger og fejlrettelser.

### <a name="data-ingestion"></a>Dataindtagelse

- **Få vist eller rediger metadata eller objektdefinition, når du vedhæfter data fra dit Azure Data Lake Storage** Du kan nu få vist og redigere metadata eller objektdefinition i målgruppeindsigt, når du vedhæfter data fra en Common Data Model-mappe i dit Azure Data Lake Storage. Denne funktion giver feedback i realtid, modelvalidering og fejlkontrol. Det giver dig mulighed for at redigere model.json og manifest.json uden problemer.

### <a name="extensibility"></a>Udvidelse

- **Forbedret segmenteksport, brugerdefineret tidsplan og duplikering** Du kan nu [få vist alle eksporter for et bestemt segment](export-destinations.md#view-exports-and-export-details) på en liste. Denne nye visning hjælper med at administrere, hvordan et bestemt segment bruges, og tilpasse eksisterende eller oprette nye eksporter.    
  Du kan [definere brugerdefinerede opdateringsplaner](export-destinations.md#schedule-and-run-exports) for individuelle eksporter eller flere eksporter på én gang. Indtil nu har al eksport været kørt med hver systemopdatering.    
  I stedet for at oprette en ny eksport fra bunden kan du starte baseret på en eksisterende for at spare lidt tid.

- **Eksporter segmenter til Microsoft Advertising** Vi har udvidet vores eksportdestinationer til at omfatte Microsoft Advertising. Opret målgrupper for kundematch på Microsoft Advertising med dine samlede kundeprofildata, og brug disse målgrupper til dine reklamekampagner. Du kan finde flere oplysninger under [Eksporter segmenter til Microsoft Advertising](export-microsoft-advertising.md).

- **Eksporter segmenter til LinkedIn Ads** Vi har udvidet vores eksportdestinationer til at omfatte LinkedIn Ads og giver dig mulighed for at låse op for målretning af kontakter samt målretning af virksomheder via LinkedIn ved at eksportere dine samlede kundeprofildata. Du kan finde flere oplysninger under [Eksporter segmenter til LinkedIn Ads](export-linkedin-ads.md).


- **Eksporter segmenter til Omnisend** Vi har udvidet vores eksportdestinationer til at omfatte Omnisend. Brug de segmenter, der er oprettet i målgruppeindsigt, til at generere kampagner, levere mailmarketing og bruge bestemte grupper af kunder med Omnisend. Du kan finde flere oplysninger under [Eksporter segmenter til Omnisend](export-omnisend.md)

### <a name="predictions"></a>Forudsigelser

- **Rapport over inputdatas brugbarhed** Rapporten over inputdatas brugbarhed indeholder en konsolideret visning af de fejl og advarsler, som dine køreklare forudsigelser kan generere. Den giver også anbefalinger til, hvordan man kan forbedre modellens ydeevne.    
  Rapporten er tilgængelig, når en model har fuldført sin træningsproces. Den er oprettet for hver model separat, uanset om den er fuldført med succes.
  I øjeblikket er denne funktion kun tilgængelig for Transaction Churn-modellen. Du kan finde flere oplysninger i [Rapport over inputdatas brugbarhed](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relationer

- **Relationsvisualisering** Visningen af relationsvisualisering giver dig mulighed for at få vist alle eksisterende relationer mellem objekter og deres kardinalitet. Relationer er nu organiseret i grupper: brugeroprettet, system og nedarvet relationer. Du kan også eksportere en visning som et billede. Du kan finde flere oplysninger under [Vis relationer](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Opdateringer i april 2021

Opdateringerne i april 2021 indeholder flere funktioner, ydelsesopgraderinger og fejlrettelser.

### <a name="data-unification"></a>Datasamling
 
- **Forbedret fletteoplevelse for datasamling**    
  
   Vi har nu en forbedret brugeroplevelse i flettekonfigurationen af datasamlingsprocessen. Ændringerne omfatter intuitiv sortering af de flettede felter og detaljerede statistikker om kombinerede og singleton-felter.

- **Sortering og konfiguration af alle kildeposter til objektet Kunde**  
      
   Du kan nu omarrangere og fjerne objekter fra en eksisterende sammenblandingsplan i datasamlingsprocessen. Det giver fleksibilitet til at omarrangere enhederne i matchprocessen i henhold til virksomhedens behov. Derudover aktiverer vi medtagelse af alle ikke-matchede poster i det endelige *kundeobjekt*, som giver dem mulighed for at definere deres kundeprofils datasæt.

### <a name="enrichments"></a>Forbedringer

 - **Nye forbedringer: Udvidede adresser**    
  
   Vi er glade for at kunne introducere en ny udvidelse for at forbedre adresserne i dine kundedata. Adresser i dine data kan være ustrukturerede, ufuldstændige eller forkerte. Denne funktion bruger Microsofts modeller til at normalisere og forbedre dine adresser i Common Data Model-formatet for at opnå større nøjagtighed og indsigt.
 
   Du kan finde flere oplysninger under [Udvidelse af kundeprofiler med forbedrede adresser](enrichment-enhanced-addresses.md).

- **Styret konfigurationsoplevelse for forbedringer**    
  
   Vi har revideret konfigurationsoplevelsen, så den giver en enkel, styret oplevelse. Du har nu en klar trinvis proces til oprettelse og redigering af forskellige forbedringer.
 
   Derudover har vi adskilt konfigurationen af forbindelser for tredjeparts forbedringer, så den samme forbindelse kan bruges af flere forbedringer. Det er kun administratorer, der kan konfigurere nye forbindelser, men de oprettede forbindelser er tilgængelige for både administratorer og bidragydere.    

   Du kan finde flere oplysninger i [Oversigt over forbindelser](connections.md).

- **Flere forbedringer af samme type**    
  
   Nu giver vi brugerne mulighed for at oprette og administrere flere forbedringer af den samme type. Du kan f.eks. oprette to separate adressesegmenter for at forbedre to forskellige kundesegmenter. Grænseværdierne gælder for, hvor mange forbedringer af den samme type der kan oprettes, og hvor forskellige de er, afhængigt af forbedringstypen.
  
   Du kan finde flere oplysninger under [Forbedring af kundeprofiler](enrichment-hub.md).

## <a name="march-2021-updates"></a>Marts 2021-opdateringer

Opdateringerne i marts 2021 indeholder flere funktioner, ydelsesopgraderinger og fejlrettelser.

### <a name="activities"></a>Aktiviteter

- **Aktivitetsguide og semantiske typer**

   Vi har forbedret og opdateret vores oplevelse med aktivitetstilknytning, så det bliver nemmere at oprette aktivitetstilknytning. I denne nye oplevelse får brugerne en styret oplevelse, der kan hjælpe dem med at fuldføre hvert trin i processen. På aktivitetstilknytningstrinnet kan brugeren vælge at tilknytte data for *Abonnement* og/eller *SalesOrderLine* til branchestandardskemaer, der kan bruges til downstreamforbrug.   

   Du kan finde flere oplysninger under [Kundeaktiviteter](activities.md).

### <a name="data-ingestion"></a>Dataindtagelse

- **Opret forbindelse til det lokale miljø datakilder ved hjælp af Power Platform-dataflows og gateways** Vi er klar til at annoncere forhåndsversionen af Power Platform-dataflows og de lokale forbindelser ved hjælp af gateways i Customer Insights med et tilknyttet Power Platform- eller Dataverse-miljø. Alle nye datakilder, der oprettes i et Customer Insights-miljø med et tilknyttet Dataverse-miljø, bruger som standard Power Platform-dataflows i forbindelse med de lokale dataforbindelser og mange forbindelsessæt med connectorer og transformeringsfunktioner.

### <a name="extensibility"></a>Udvidelse

- **Eksporter organiseret i forbindelser og eksport** Vi har ændret navnet på siden **Eksportdestinationer** til **Forbindelser** og tilføjet en separat side for **Eksporter**. Som en del af denne opdatering vil vi overflytte eksisterende eksporter til forbindelsespar og til en eksport ved hjælp af den pågældende forbindelse. Administratorer har nu større klarhed over udgående data på siden **Forbindelser**. Alle brugerroller har adgang til siden **Eksporter**, men det er kun administratorer, der kan vælge at give bidragydere tilladelse til at redigere bestemte eksporter med delte forbindelser.     
  Du kan finde flere oplysninger i [Oversigt over forbindelser](connections.md) og [Oversigt over eksporter](export-destinations.md).

- **Eksportér segmenter til Kampagneovervågning** Vi har udvidet vores eksportmål til at omfatte Kampagneovervågning. Du kan nu eksportere målgrupper fra Customer Insights til kampagneovervågningslister og bruge dem som udgangspunkt for marketingkampagner.    
   Du kan finde flere oplysninger i [Eksportere til Kampagneovervågning](export-campaign-monitor.md).

- **Eksportér segmenter til Constant Contact** Vi har udvidet vores eksportdestinationer til at omfatte Constant Contact. Du kan nu eksportere segmenter fra Customer Insights til Constant Contact-lister og bruge dem som udgangspunkt for marketingkampagner.   
   Du kan finde flere oplysninger i [Eksportere til Constant Contact](export-constant-contact.md).

- **Eksportér segmenter til RollWorks** Vi har udvidet vores eksportdestinationer til at omfatte RollWorks. Du kan nu eksportere segmenter fra Customer Insights til RollWorks-målgrupper og bruge dem som udgangspunkt for dine B-til-B-reklamer.    
   Du kan finde flere oplysninger i [Eksportere til RollWorks ](export-rollworks.md).

- **Eksportér segmenter til Snapchat** Vi har udvidet vores eksportdestinationer til at omfatte Snapchat. Du kan nu eksportere segmenter fra Customer Insights til Snapchat-målgrupper og bruge dem som udgangspunkt for marketing.     
   Du kan finde flere oplysninger i [Eksportere til Snapchat](export-snapchat.md).

### <a name="predictions"></a>Forudsigelser

- **Brug produktfiltre i produktanbefalinger til forudsigelse** Vi har tilføjet muligheden for at bruge produktfiltre i vores produktanbefalingsmodel. Du kan nu oprette en forudsigelse, der kun bruger en delmængde af produkterne.    
   Du kan finde flere oplysninger under [Konfiguration af produktfiltre](predict-product-recommendation.md#configure-product-filters).

- **Opret segmenter ud fra modelforudsigelser** Vi har tilføjet en hurtig måde at oprette segmenter på ved hjælp af resultaterne af en forudsigelsesmodel. På siden med modelresultater kan du nemt oprette et nyt segment ved at vælge den nye indstilling **Opret segment**.    
  Du kan finde flere oplysninger i [Oprette et segment baseret på en forudsigelsesmodel](prediction-based-segment.md).

- **Forklaringer til produktanbefalinger** Vi har tilføjet oplysninger, der forklarer de nøglefaktorer, AI-modellen har lært, for at generere produktanbefalinger og i hvor høj grad disse faktorer bidrager til produktanbefalingerne. Disse oplysninger føjes til skærmbilledet med modelresultater.    
   Du kan finde flere oplysninger under [Gennemse en forudsigelsesstatus og resultater](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Februar 2021-opdateringer

Opdateringerne i februar 2021 indeholder flere funktioner, opgraderinger af ydeevnen og fejlrettelser.

#### <a name="extensibility"></a>Udvidelse

- **Eksportere segmenter til AdRoll**

  Vi har udvidet vores eksportdestinationer til at omfatte AdRoll. Du kan nu eksportere segmenter fra Customer Insights til AdRoll-målgrupper og bruge dem som udgangspunkt for dine reklamer. Du kan finde flere oplysninger i [Connector til AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmenter
 
- **Dublere et segment**
  
  Hvis du vil oprette et nyt segment baseret på et eksisterende, kan du nu dublere et segment og redigere det dublerede segment for at forfine det yderligere. 

- **Føje yderligere attributter til et segment**

  Du kan nu inkludere attributter i segmentoutputtet, selvom disse attributter ikke er en del af kundeprofilen. Du kan f.eks. inkludere abonnements-id'er i et segment, selvom det er en del af det abonnementsobjekt, der har en M:1-relation til kundeobjektet. Så længe attributten tilhører et objekt, der er relateret til kundeobjektet, kan du nu medtage disse attributter.  

#### <a name="predictions"></a>Forudsigelser

- **Oprette forudsigelse om produktanbefalinger**

  At forstå, hvad kunderne er interesseret i at købe, er et af de første trin, der skal bruges til at øge omsætning og opbygge kundeloyalitet gennem personlig tilpasning og engagement. Hvis du kommer med anbefalinger til produkter, der ikke er tilpasset kundens interesser, kan du skabe en fornemmelse af manglende forbindelse mellem kunden og din virksomhed og i sidste ende begrænse den samlede potentielle omsætning og oplevelse for en kunde. 

  Med dine egne data kan du nu oprette forudsigelser af, hvilke produkter dine kunder sandsynligvis vil købe i fremtiden. Du kan finde flere oplysninger i [Forudsige produktanbefalinger](predict-product-recommendation.md).

#### <a name="system-administration"></a>Systemadministration

- **Kopiering af miljø understøtter flere typer datakilder**

  Administratorer kan kopiere miljøkonfigurationer til et nyt miljø i samme organisation. Denne funktion udvider kopimiljøfunktionaliteten i tilfælde, hvor der bruges datakilder, der er baseret på en Microsoft Dataverse-administreret datasø eller en fælles datamodelmappe.

## <a name="january-2021-updates"></a>Opdatering fra januar 2021

Opdateringerne fra januar 2021 indeholder flere funktioner, opgraderinger af ydeevnen og fejlrettelser.

#### <a name="extensibility"></a>Udvidelse

- **Udvidet funktionalitet og forbedret ydeevne ved eksport af SFTP** Du kan nu eksportere alle outputobjekter fra Customer Insights til en SFTP-vært. Tidligere var eksport begrænset til segmentobjekter. Ydeevnen af eksporten af SFTP giver desuden mulighed for mere datamængde på mindre tid, afhængigt af SFTP-værtsydeevnen.    
  Du kan finde flere oplysninger i [Connector til SFTP (prøveversion)](export-sftp.md).  

#### <a name="segments"></a>Segmenter

- **Maskinel indlæring foreslåede segmenter for at forbedre målinger** Der er en ny måde at opdage og oprette segmenter på. Systemet bruger en AI-model til at foreslå segmenter, der kan være med til at forbedre et nøgletal (måling), du allerede sporer. Vi viser omfanget af den indflydelse, som attributter, du vælger på en måleenhed eller en anden primær attribut, er. Oplysningerne hjælper dig med at finde potentielle segmenter, der indeholder salgsmuligheder.    
  Du kan finde flere oplysninger i [Foreslåede segmenter (prøveversion)](suggested-segments.md).

#### <a name="data-unification"></a>Datasamling

- **Forbedret matchoplevelse** I området til datasamlinger blev matchoplevelsen opdateret. Det giver dig mulighed for at konfigurere og få vist matchregler, herunder detaljeret statistik for yderligere at forklare, hvordan matchning fungerer. Der er indstillinger, som deaktiverer en matchregel, så den ikke længere er aktiv, samtidig med at konfigurationen, træk og slip-reglerne og meget mere bevares.
  Du kan finde flere oplysninger under [Match objekter](match-entities.md).

- **Deduplikering af output fra overensstemmelsesprocessen er tilgængelig som et objekt** Output fra deduplikeringsprocessen fra matchprocessen skrives nu til et separat objekt, så det kan analyseres yderligere. Dette objekt består af de felter, der bruges i deduplikeringsprocessen, og vinderposten og de tilsvarende alternative poster, der flettes med vinderposten.
  Du kan finde flere oplysninger i [Deduplikering af output som et objekt](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Systemadministration

- **Problemfri deling af data med Microsoft Dataverse** Du kan nu dele Customer Insights-output med Microsoft Dataverse-programmer ved hjælp af Microsoft Dataverse Managed Data Lake. Når du knytter et Dataverse-miljø til Customer Insights, får du mulighed for at aktivere datadeling.
  Du kan finde flere oplysninger under [Administrere miljøer](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]