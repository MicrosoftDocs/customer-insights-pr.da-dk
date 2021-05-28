---
title: Nye og kommende funktioner
description: Oplysninger om nye funktioner, forbedringer og rettelser i forbindelse med fejl.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988913"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Nyheder i målgruppen Insights-funktioner i Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Vi er glade for at kunne fortælle om vores nyeste opdateringer! Denne artikel indeholder en oversigt over funktionerne i offentlig prøveversion, forbedring af generel tilgængelighed og funktionsopdateringer. Hvis du vil have vist de langsigtede funktionsplaner, skal du kigge i [frigivelsesplanerne for Dynamics 365 og Power Platform](/dynamics365/release-plans/).

Vi udruller opdateringerne område for område. Så visse geografiske områder kan se funktioner før andre. Medmindre andet er angivet, behøver du ikke at foretage dig noget, og vi opdaterer automatisk appen uden nedetid.

> [!TIP]
> Hvis du vil sende og stemme på populære ønsker og produktforslag, skal du gå til [Dynamics 365-portalen for programideer](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

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

- **Eksportér segmenter til RollWorks** Vi har udvidet vores eksportdestinationer til at omfatte RollWorks. Du kan nu eksportere segmenter fra Customer Insights til RollWorks-målgrupper og bruge dem som udgangspunkt for B2B-marketing.    
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

  Administratorer kan kopiere miljøkonfigurationer til et nyt miljø i samme organisation. Med denne funktion udvides funktionaliteten for kopimiljøet i de tilfælde, hvor datakilder er baseret på en Common Data Service-datasø, eller en Common Data Model-mappe bruges.

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