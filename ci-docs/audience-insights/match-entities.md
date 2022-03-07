---
title: Match objekter til datasamling
description: Sammenlign objekter for at oprette samlede kundeprofiler.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: de53927f7ed1f58176a7ba83f89be7c39064947c
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650311"
---
# <a name="match-entities"></a>Sammenlign objekter

Matchfasen angiver, hvordan du kan kombinere dine datasæt i et samlet kundeprofildatasæt. Når du har fuldført [tilknytningstrinnet](map-entities.md) i processen til samling af data, er du klar til at matche dine objekter. Matchfasen kræver mindst to tilknyttede objekter.

Matchsiden består af tre sektioner: 
- Nøglemålepunkter, der opsummerer antallet af matchede poster
- Matchrækkefølge og regler for matchning på tværs af objekter
- Regler for deduplikering af matchobjekter

## <a name="specify-the-match-order"></a>Angive matchrækkefølgen

Gå til **Data** > **Saml** > **Match**, og vælg **Angiv rækkefølge** for at starte fasen.

Hvert match samler to eller flere objekter i ét samlet konsolideret objekt. Samtidig opbevares de entydige kundeposter. Vi har f.eks. valgt to objekter: **eCommerce:eCommerceContacts** som det primære objekt og **LoyaltyScheme:loyCustomers** som andet objekt. Rækkefølgen af objekterne angiver, i hvilken rækkefølge systemet skal forsøge at matche posterne.

:::image type="content" source="media/match-page.png" alt-text="Skærmbillede af matchsiden i området Saml af datasamlingsprocessen.":::
  
Det primære objekt *eCommerce:eCommerceContacts* matches med det næste objekt *LoyaltyScheme:loyCustomers*. Det datasæt, der er resultatet af første matchtrin, matches med følgende objekt, hvis du har mere end to objekter.

> [!IMPORTANT]
> Det objekt, du vælger som primært objekt, tjener som udgangspunkt for det samlede profildatasæt. Flere objekter, der er valgt under matchfasen, føjes til dette objekt. Det betyder ikke, at det samlede objekt indeholder *alle* de data, der findes i dette objekt.
>
> Der er to overvejelser, der kan hjælpe dig med at vælge hierarkiet for objekterne:
>
> - Vælg det objekt, der har de mest fuldstændige og pålidelige profildata om kunderne, som det primære objekt.
> - Vælg det objekt, der har flere attributter til fælles med andre objekter (f.eks. navn, telefonnummer eller mailadresse) som primært objekt.

Når du har angivet matchrækkefølgen, kan du se de definerede matchpar i afsnittet **Oplysninger om matchede poster** i **Data** > **Saml** > **Match**. Nøglemålepunkterne er tomme, indtil matchprocessen er fuldført.

## <a name="define-rules-for-match-pairs"></a>Definere regler for matchpar

Matchregler angiver den logik, som et bestemt par af objekter skal matches efter.

Advarslen **Behøver regler** ud for et objektnavn indikerer, at der ikke er defineret en matchregel for et matchpar. 

:::image type="content" source="media/match-rule-add.png" alt-text="Skærmbillede af sektionen Oplysninger om matchet post med kontrolelement for at tilføje regler fremhævet.":::

1. Vælg **Tilføj regler** under et objekt i sektionen **Detaljer om matchede poster** for at definere matchregler.

1. Konfigurer betingelserne for reglen i ruden **Opret regel**.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Skærmbillede af en åben matchregel med tilføjede betingelser.":::

   - **Objekt/felt (første række)**: Vælg et relateret objekt og en attribut for at angive en postegenskab, der sandsynligvis er entydig for en kunde. Et eksempel er et telefonnummer eller en mailadresse. Undgå matchning efter aktivitetstypeattributter. Et købs-id vil f.eks. højst sandsynligt ikke findes i andre posttyper.

   - **Objekt/felt (anden række)**: Vælg en attribut, der er relateret til attributten for det objekt, der er angivet i første række.

   - **Normaliser**: Vælg mellem følgende normaliseringsindstillinger for de valgte attributter. 
     - Blanktegn: Fjerner alle mellemrum. *Hej   verden* bliver til *Hejverden*.
     - Symboler: Fjerner alle symboler og specialtegn. *Head&Shoulder* bliver til *HeadShoulder*.
     - Tekst til små bogstaver: Konverterer alle tegn til små bogstaver. *ALL CAPS og Titel, små/store bogstaver* bliver til *all caps og titel, små/store bogstaver*.
     - Unicode til ASCII: Konverter Unicode-format til ASCII-tegn. */u00B2* bliver til *2*.
     - Tal: Konverterer andre talsystemer, f.eks. romertal, til arabertal. *VIII* bliver til *8*.
     - Semantiske typer: Standardiserer navne, titler, telefonnumre, adresser osv. 

   - **Præcision** : Angiv det præcisionsniveau, der skal gælde for denne betingelse. 
     - **Grundlæggende**: Vælg mellem *Lav*, *Mellem*, *Høj* og *Nøjagtig*. Vælg **Nøjagtig** for kun at matche poster, der matcher 100 procent. Vælg et af de andre niveauer for at matche poster, der ikke er 100 procent identiske.
     - **Brugerdefineret** : Angiv en procentdel, som posterne skal matche. Systemet vil kun matche poster, der opfylder denne grænse.

1. Angiv et **Navn** til reglen.

1. [Tilføj flere betingelser](#add-conditions-to-a-rule), eller vælg **Udført** for at færdiggøre reglen.

1. Du kan også [tilføje flere regler](#add-rules-to-a-match-pair).

1. Vælg **Gem** for at anvende dine ændringer.

### <a name="add-conditions-to-a-rule"></a>Tilføje betingelser i en regel

Hvis du kun vil matche objekter, hvis attributterne overholder flere betingelser, skal du føje flere betingelser til en matchregel. Betingelser er knyttet til en logisk AND-operator og køres derfor kun, hvis alle betingelser er opfyldt.

1. Gå til **Data** > **Saml** > **Match**, og vælg **Rediger** på den regel, du vil føje betingelser til.

1. Vælg **Tilføj betingelse** i ruden **Rediger regel**.

1. Vælg **Udført** for at gemme reglen.

### <a name="add-rules-to-a-match-pair"></a>Føje regler til et matchpar

Matchregler repræsenterer sæt af betingelser. Hvis du vil matche objekter efter betingelser ud fra flere attributter, skal du tilføje flere regler

1.  Gå til **Data** > **Saml** > **Match**, og vælg **Tilføj regel** på det objekt, du vil føje regler til.

2. Følg trinnene under [Definer regler for matchpar](#define-rules-for-match-pairs).

> [!NOTE]
> Rækkefølgen af regler er vigtig. Den matchende algoritme forsøger at matche på baggrund af din første regel og fortsætter kun til den anden regel, hvis der ikke blev identificeret nogen match med den første regel.

### <a name="change-the-entity-order-in-match-rules"></a>Ændre objektrækkefølgen i matchregler

Du kan omarrangere objekter for matchregler for at ændre den rækkefølge, de behandles i. Regler, der er i konflikt på grund af en ændret rækkefølge, fjernes. Du skal genoprette fjernede regler med en opdateret konfiguration.

1. Gå til **Data** > **Saml** > **Match**, og vælg **Rediger**.

1. Vælg kontrolelementet **Flyt op/ned** i ruden **Rediger regel**, eller træk og slip objekter for at ændre rækkefølgen.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Indstillinger, som ændrer den rækkefølge, som ordreobjekter behandles i i matchfasen.":::

1. Vælg **Udført** for at gemme reglen.

## <a name="define-deduplication-on-a-match-entity"></a>Definer deduplikering for et match-objekt

Ud over [matchregler på tværs af objekter](#define-rules-for-match-pairs) kan du også angive regler for deduplikering. *Deduplikering* er en anden proces, når poster matches. Den identificerer dubletposter og fletter dem til én post. Kildeposter knyttes til den flettede post med alternative id'er.

Deduplikerede poster anvendes i processen med match af krydsobjektet. Deduplikering sker på individuelle objekter og kan konfigureres for alle objekter, der bruges i matchpar.

Det er ikke obligatorisk at angive regler for fjernelse af dubletter. Hvis der ikke er konfigureret sådanne regler, anvendes de systemdefinerede regler. De kombinerer alle poster i en enkelt post, før de overfører objektdataene til matchning på tværs af objekter med forbedret ydeevne.

### <a name="add-deduplication-rules"></a>Tilføj regler for deduplikering

1. Gå til **Data** > **Saml** > **Match**.

1. Vælg **Angiv objekter** i sektionen **Flettede dubletter**. Hvis der allerede er oprettet regler for deduplikering, skal du vælge **Rediger**.

1. I ruden **Indstillinger for fletninger** skal du vælge de objekter, du vil køre deduplikering på.

1. Angiv, hvordan dubletposterne skal kombineres, og vælg en af de tre indstillinger:
   - **Flest udfyldte**: Identificerer posten med de fleste udfyldte attributfelter som vinderposten. Dette er standardfletteindstillingen.
   - **Nyeste**: Identificerer vinderposten baseret på de nyeste. Kræver en dato eller et numerisk felt for at definere nyeste.
   - **Mindst nyeste**: Identificerer vinderposten baseret på de mindst nyeste. Kræver en dato eller et numerisk felt for at definere nyeste.
 
   > [!div class="mx-imgBorder"]
   > ![Regler for deduplikering trin 1.](media/match-selfconflation.png "Regler for deduplikering trin 1")
 
1. Når objekterne er valgt, og de flettede indstillinger er angivet, skal du vælge **Tilføj regel** for at definere reglerne for deduplikering på et objektniveau.
   - **Vælg felt** lister alle de tilgængelige felter fra objektet. Vælg det felt, du vil kontrollere for dubletter. Vælg felter, der sandsynligvis er entydige for hver enkelt kunde. Det kan f.eks. være en mailadresse eller en kombination af navn, by og telefonnummer.
   - Angiv indstillingerne for normalisering og præcision.
   - Definer flere betingelser ved at vælge **Tilføj betingelse**.
 
   > [!div class="mx-imgBorder"]
   > ![Regler for deduplikering trin 2.](media/match-selfconflation-rules.png "Regler for deduplikering trin 2")

  Du kan oprette flere deduplikeringsregler for et objekt. 

1. Når du kører processen Sammenlign nu, grupperes posterne på baggrund af de betingelser, der er defineret i reglerne for deduplikering. Efter gruppering af posterne anvendes flettepolitikken til at identificere vinderposten.

1. Denne vinderpost overføres derefter til match på tværs af objekter sammen med de poster, der ikke er vindere (f.eks. alternative id'er), for at forbedre matchkvaliteten.

1. Alle brugerdefinerede matchregler, der er defineret, overskriver deduplikeringsregler. Hvis en deduplikeringsregel identificerer matchende poster, og en brugerdefineret matchregel er angivet til aldrig at matche disse poster, kan disse to poster ikke blive matchet.

1. Når du har [kørt matchprocessen](#run-the-match-process), kan du se deduplikeringsstatistikken i felter med nøglemålepunkter.

### <a name="deduplication-output-as-an-entity"></a>Deduplikere output som et objekt

Under duplikeringsprocessen oprettes der et nyt objekt for hvert objekt ud fra matchparrene for at identificere de deduplikerede poster. Disse objekter findes sammen med **ConflationMatchPairs:CustomerInsights** i afsnittet **System** på siden **Objekter** med navnet **Deduplication_DataSource_Entity**.

Et deduplikeret outputobjekt indeholder følgende oplysninger:
- Id'er / nøgler
  - Feltet Primær nøgle og dets alternative id-felt. Det alternative id-felt består af alle de alternative id'er, der er identificeret for en post.
  - Deduplication_GroupId-felt vises den gruppe eller klynge, der er identificeret i et objekt, og som grupperer alle lignende poster på baggrund af de angivne felter med deduplikering. Det bruges til systembehandlingsformål. Hvis der ikke er angivet nogen regler for manuel deduplikering, og der gælder systemdefinerede regler for deduplikering, kan feltet muligvis ikke findes i outputobjektet.
  - Deduplication_WinnerId: Dette felt indeholder vinder-id fra de identificerede grupper eller klynger. Hvis Deduplication_WinnerId er den samme som værdien for den primære nøgle for en post, betyder det, at posten er vinderposten.
- Felter, der bruges til at definere reglerne for deduplikering.
- Felterne Regel og Resultat angiver, hvilke af de duplikeringsregler der blev anvendt, og det antal point, der returneres af den tilsvarende algoritme.
   
## <a name="run-the-match-process"></a>Køre matchprocessen

Med konfigurerede matchregler, herunder regler for matchning og deduplikering på tværs af objekter, kan du køre matchprocessen. 

Gå til **Data** > **Saml** > **Match**, og vælg **Kør** for at starte processen. Det tager tid at fuldføre matchalgoritmen, og du kan ikke ændre konfigurationen, før den er fuldført. Du kan foretage ændringer ved at annullere kørslen. Vælg jobbets status, og vælg **Annuller job** i ruden **Statusdetaljer**.

Du kan se resultatet af en vellykket kørsel, det samlede kundeprofilobjekt, på siden **Objekter**. Dit samlede kundeobjekt kaldes **Kunder** i sektionen **Profiler**. Ved den første vellykkede matchkørsel oprettes det samlede objekt *Kunde*. Enhver efterfølgende match udvider objektet.

> [!TIP]
> Når du har kørt matchprocessen, skal du vælge processtatus for at åbne ruden med **opgaveoplysninger**. Den giver et overblik over behandlingstiden, den sidste behandlingsdato og alle fejl og advarsler, der er knyttet til opgaven. Vælg **Se detaljer** for at se, hvilke objekter der deltog i matchprocessen, hvilke regler der blev anvendt på dem, og om opdateringerne blev udgivet korrekt.  
> Opgaver og processer indeholder [seks typer status](system.md#status-types). De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Nedrulningssti for at få vist procesoplysninger fra linket til opgavestatus.":::

## <a name="review-and-validate-your-matches"></a>Gennemgå og validere dine matches

Gå til **Data** > **Saml** > **Match** for at evaluere kvaliteten af matchparrene og finjustere dem, hvis det er nødvendigt.

Felterne øverst på siden viser nøglemålepunkter og opsummerer antallet af matchede poster og dubletter.

:::image type="content" source="media/match-KPIs.png" alt-text="Beskåret skærmbillede af nøglemålepunkter på siden Match med tal og detaljer.":::

- **Entydige kildeposter** viser antallet af individuelle kildeposter, der blev behandlet i sidste matchkørsel.
- **Matchede og ikke-matchede poster** fremhæver, hvor mange entydige poster der er tilbage efter behandling af matchreglerne.
- **Kun matchede poster** viser kun antallet af matches på tværs af alle dine matchpar.

Du kan vurdere resultaterne af hvert matchpar og dets regler i tabellen **Oplysninger om matchede poster**. Sammenlign antallet af poster, der kommer fra et matchpar, med procentdelen af fuldførte matchede poster.

Gennemgå reglerne for et matchpar for at se procentdelen af fuldførte matchede poster på regelniveau. Vælg ellipsen (...), og vælg derefter **Forhåndsvisning af match** for at få vist alle disse poster på regelniveau. Det anbefales, at du kigger på nogle poster for at kontrollere, at de blev matchet korrekt.

Prøv at bruge forskellige præcisionstærskelværdier på betingelser for at finde den optimale værdi.

  1. Vælg ellipsen (...) for den regel, du vil eksperimentere med, og vælg **Rediger**.

  2. Rediger præcisionsværdierne i de betingelser, du vil revidere.

  3. Vælg **Vis eksempel** for at se antallet af matchede og ikke-matchede poster for den valgte betingelse.

## <a name="manage-match-rules"></a>Administrere matchregler

Du kan omkonfigurere og finjustere de fleste af matchparametrene.

:::image type="content" source="media/match-rules-management.png" alt-text="Skærmbillede af rullemenuen med indstillinger for matchende regler.":::

- **Du kan ændre rækkefølgen af reglerne**, hvis du har defineret flere regler. Du kan omarrangere matchreglerne ved at vælge indstillingerne **Flyt op** og **Flyt ned** eller ved at trække og slippe.

- **Rediger regelbetingelser** ved at vælge **Rediger** og vælge andre felter.

- **Deaktiver en regel** for at bevare en overensstemmelsesregel, samtidig med at den udelukkes fra matchprocessen.

- **Dupliker reglerne**, hvis du har defineret en matchregel og vil oprette en lignende regel med ændringer, ved at vælge **Dupliker**.

- **Slet en regel** ved at vælge symbolet **Slet**.

## <a name="specify-custom-match-conditions"></a>Angive brugerdefinerede matchbetingelser

Du kan angive betingelser, som visse poster altid skal matche eller aldrig skal matche. Disse regler kan overføres for at tilsidesætte standardmatchprocessen. Hvis der f.eks. findes John Doe I og John Doe II i vores poster, kan systemet matche dem som én person. Med brugerdefinerede matchregler kan du angive, at deres profiler refererer til forskellige personer. 

1. Gå til **Data** > **Saml** > **Match**, og vælg **Brugerdefineret match** i sektionen **Oplysninger om matchede poster**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Skærmbillede af sektionen med matchregler og kontrolelement for brugerdefineret match fremhævet.":::

1. Hvis der ikke er angivet brugerdefinerede matchregler, kan du se en ny **Brugerdefineret match**-rude med flere detaljer.

1. Vælg **Udfyld skabelonen** for at hente en skabelonfil, der kan angive, hvilke poster fra hvilke objekter der altid skal matche eller aldrig matche. Du skal separat udfylde posterne af typen "match altid " og "match aldrig " i to forskellige filer.

1. Skabelonen indeholder felter til angivelse af det objekt og de primære nøgleværdier for objektet, der skal bruges i det brugerdefinerede match. Hvis din primære nøgle *12345* fra objektet *Salg* f.eks. altid skal matche den primære nøgle *34567* fra objektet *Kontakt*, skal du udfylde skabelonen:
    - Entity1: Salg
    - Entity1Key: 12345
    - Entity2: Kontakt
    - Entity2Key: 34567

   Den samme skabelonfil kan angive brugerdefinerede matchposter fra flere objekter.
   
   Hvis du vil angive brugerdefineret matchning for deduplikering for et objekt, skal du angive det samme objekt som både Objekt1 og Objekt2 og angive de forskellige værdier for primære nøgler.

1. Gem skabelonfilen, når du har tilføjet alle de tilsidesættelser, du vil anvende.

1. Gå til **Data** > **Datakilder**, og indsæt skabelonfilerne som nye objekter. Når de er indtaget, kan du bruge dem til at angive matchkonfigurationen.

1. Når du har overført filerne, og objekterne er tilgængelige, skal du vælge indstillingen **Brugerdefineret match** igen. Du kan se indstillinger for at angive de objekter, du vil inkludere. Vælg de nødvendige enheder i rullemenuen.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Skærmbillede af dialogboksen til valg af tilsidesættelser for et brugerdefineret matchscenario.":::

1. Vælg de objekter, du vil bruge til **Match altid** og **Match aldrig**, og vælg **Udført**.

1. Vælg **Gem** på siden **Match** for at anvende den brugerdefinerede matchkonfiguration.

1. Vælg **Kør** på siden **Match** for at starte matchprocessen. Andre angivne matchregler tilsidesættes af den brugerdefinerede matchkonfiguration.

> [!TIP]
> Gå til **Data** > **Objekter**, og gennemgå objektet **ConflationMatchPair** for at bekræfte, at tilsidesættelserne er anvendt.

## <a name="next-step"></a>Næste trin

Når du har fuldført matchprocessen for mindst ét matchpar, kan du løse mulige modstridende data ved at gennemgå emnet [**Flet**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
