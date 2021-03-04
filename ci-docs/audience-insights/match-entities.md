---
title: Match objekter til datasamling
description: Sammenlign objekter for at oprette samlede kundeprofiler.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267471"
---
# <a name="match-entities"></a>Sammenlign objekter

Når du har fuldført tilknytningsfasen, er du klar til at matche objekterne. Matchfasen angiver, hvordan du kan kombinere dine datasæt i et samlet kundeprofildatasæt. Matchfasen kræver mindst [to tilknyttede objekter](map-entities.md).

## <a name="specify-the-match-order"></a>Angive matchrækkefølgen

Gå til **Data** > **Saml** > **Match**, og vælg **Angiv rækkefølge** for at starte fasen.

Hvert match samler to eller flere objekter i et enkelt objekt, mens alle entydige kundeposter bevares. I følgende eksempel har vi valgt tre objekter: **ContactCSV: TestData** som det **primære** objekt, **WebAccountCSV: TestData** som **Objekt 2** og **CallRecordSmall: TestData** som **Objekt 3**. Diagrammet over valgene illustrerer, hvordan den matchende rækkefølge udføres.

> [!div class="mx-imgBorder"]
> ![Redigere data i matchrækkefølge](media/configure-data-match-order-edit-page.png "Redigere data i matchrækkefølge")
  
Det **primære** objekt matches med **Objekt 2**. Det datasæt, der er resultatet af det første match, matches med **Objekt 3**.
I dette eksempel har vi kun valgt to matches, men systemet understøtter flere.

> [!IMPORTANT]
> Det objekt, du vælger som **primært** objekt, tjener som udgangspunkt for det samlede masterdatasæt. Flere objekter, der er valgt under matchfasen, føjes til dette objekt. Det betyder samtidig ikke, at det samlede objekt indeholder *alle* de data, der er indeholdt i dette objekt.
>
> Der er to overvejelser, der kan hjælpe dig med at vælge hierarkiet for objekterne:
>
> - Hvilket objekt, mener du har de mest fuldstændige og pålidelige data om kunderne?
> - Indeholder det objekt, du lige har identificeret, attributter, der også deles med andre objekter (f.eks. navn, telefonnummer eller mailadresse)? Hvis det ikke er tilfældet, skal du vælge det næstmest pålidelige objekt.

Vælg **Udført** for at gemme matchrækkefølgen.

## <a name="define-rules-for-your-first-match-pair"></a>Definere regler for dit første matchpar

Når du har angivet matchrækkefølgen, kan du se de definerede matches på siden **Match**. Felterne øverst på skærmen er tomme, indtil du kører matchrækkefølgen.

> [!div class="mx-imgBorder"]
> ![Definere regler](media/configure-data-match-need-rules.png "Definere regler")

Advarslen **Behøver regler** regler antyder, at der ikke er defineret nogen matchregler for et matchpar. Matchregler angiver den logik, som et bestemt par af objekter skal matches efter.

1. Du kan definere den første regel ved at åbne ruden **Regeldefinition** ved at vælge den tilsvarende matchrække i tabellen (1) og derefter vælge **Opret ny regel** (2).

   > [!div class="mx-imgBorder"]
   > ![Oprette ny regel](media/configure-data-match-new-rule2.png "Opret ny regel")

2. Konfigurer betingelserne for den pågældende regel i ruden **Rediger regel**. De enkelte betingelser repræsenteres af to rækker, som indeholder obligatoriske valg.

   > [!div class="mx-imgBorder"]
   > ![Ruden Ny regel](media/configure-data-match-new-rule-condition.png "Ruden Ny regel")

   Objekt/felt (først) - En attribut, der skal bruges til matchning fra det første matchpar-objekt. Af eksempler kan nævnes et telefonnummer eller en mailadresse. Vælg en attribut, der sandsynligvis er entydig for kunden.

   > [!TIP]
   > Undgå at matche på basis af aktivitetstypeattributter. Hvis en attribut f.eks. er en aktivitet, kan det være et dårligt kriterium at matche efter.  

   Objekt/felt (andet) - En attribut, der skal bruges til matchning fra det andet matchpar-objekt.

   Normaliser - **Normaliserings metode**: De forskellige normaliseringsindstillinger er tilgængelige for de valgte attributter. F.eks. fjernelse af tegnsætning eller fjernelse af mellemrum

   I forbindelse med normalisering af organisationsnavn (prøveversion) kan du også vælge **Type (telefon, navn, organisation)**

   > [!div class="mx-imgBorder"]
   > ![Normalisering-B2B](media/match-normalization-b2b.png "Normalisering-B2B")

   Præcisionsniveau – Det præcisionsniveau, der bruges til denne betingelse. Angivelse af et præcisionsniveau for en matchbetingelse kan have to typer **Grundlæggende** og **Brugerdefineret**.  
   - Grundlæggende: Giver dig fire muligheder at vælge mellem: Lav, Mellem, Høj og Nøjagtig. Vælg **Nøjagtig** for kun at matche poster, der matcher 100 procent. Vælg et af de andre niveauer for at matche poster, der ikke er 100 procent identiske.
   - Brugerdefineret: Brug skyderen til at definere den brugerdefinerede procent, som posterne skal matche med, eller angiv en værdi i feltet **Brugerdefineret**. Systemet matcher kun poster, der overtiger denne tærskel, som sammensmeltede matchpar. Værdierne i skyderen ligger mellem 0 og 1. Så 0,64 repræsenterer 64 procent.

3. Vælg **Udført** for at gemme reglen.

### <a name="add-multiple-conditions"></a>Tilføje flere betingelser

Hvis du kun vil matche objekterne, når flere betingelser er opfyldt, kan du tilføje flere betingelser, der er tilknyttet via en OG-operator.

1. Vælg **Tilføj betingelse** i ruden **Rediger regel**. Du kan også slette betingelser ved at vælge knappen Fjern ud for en eksisterende betingelse.

2. Vælg **Udført** for at gemme reglen.

## <a name="add-multiple-rules"></a>Tilføje flere regler

De enkelte betingelser gælder for et enkelt par attributter, mens regler repræsenterer sæt af betingelser. Hvis du vil have objekterne matchet af forskellige sæt attributter, kan du tilføje flere regler.

1. Gå til **Data** > **Saml** > **Match** i målgruppen Insights.

2. Vælg det objekt, du vil opdatere, og vælg **Tilføj regler**.

3. Følg fremgangsmåden i [Definere regler for dit første matchpar](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Regelrækkefølgen spiller en rolle. Matchningsalgoritmen forsøger at matche på basis af den første regel og fortsætter kun til den anden regel, hvis der ikke blev identificeret noget match under den første regel.

## <a name="define-deduplication-on-a-match-entity"></a>Definer deduplikering for et match-objekt

Sammen med angivelse af regler for matchning af krydsobjekter, der beskrives i de ovennævnte afsnit, kan du også angive deduplikeringsregler. *Deduplikering* er en proces. Der identificeres dubletposter, der flettes sammen til én post, og alle kildeposterne sammenkædes med de alternative id'er for den flettede post.

Når en ikke-duplikeret post er identificeret, bruges den pågældende post i den krydsobjekt sammenligningsproces. Deduplikering er implementeret på objektniveau og kan anvendes på alle de objekter, der bruges i overensstemmelsesprocessen.

### <a name="add-deduplication-rules"></a>Tilføj regler for deduplikering

1. Gå til **Data** > **Saml** > **Match** i målgruppen Insights.

1. Vælg **Angiv objekter** i sektionen **Flettede dubletter**.

1. I afsnittet **Indstillinger for fletninger** skal du markere de objekter, du vil anvende deduplikering på.

1. Angiv, hvordan dubletposterne skal flettes, og vælg en af de tre fletteindstillinger:
   - *Flest udfyldte*: Identificerer posten med de fleste udfyldte attributter som vinderposten. Dette er standardfletteindstillingen.
   - *Nyeste*: Identificerer vinderposten baseret på de nyeste. Kræver en dato eller et numerisk felt for at definere nyeste.
   - *Mindst nyeste*: Identificerer vinderposten baseret på de mindst nyeste. Kræver en dato eller et numerisk felt for at definere nyeste.
 
   > [!div class="mx-imgBorder"]
   > ![Regler for deduplikering trin 1](media/match-selfconflation.png "Regler for deduplikering trin 1")
 
1. Når objekterne er valgt, og de flettede indstillinger er angivet, skal du vælge **Opret ny regel** for at definere reglerne for fjernelse på et objektniveau.
   - **Vælg felt** viser alle tilgængelige felter fra det objekt, du vil fjerne duplikerede kildedata til.
   - Angiv normaliserings- og præcisionsindstillingerne på samme måde som angivet i det krydsobjekt, der matcher.
   - Du kan definere yderligere betingelser ved at vælge **Tilføj betingelse**.
 
   > [!div class="mx-imgBorder"]
   > ![Regler for deduplikering trin 2](media/match-selfconflation-rules.png "Regler for deduplikering trin 2")

  Du kan oprette flere deduplikeringsregler for et objekt. 

1. Når du kører processen Sammenlign nu, grupperes posterne på baggrund af de betingelser, der er defineret i reglerne for deduplikering. Efter gruppering af posterne anvendes flettepolitikken til at identificere vinderposten.

1. Denne vinderpost overføres derefter til match på tværs af objekter sammen med de poster, der ikke er vindere (f.eks. alternative id'er), for at forbedre matchkvaliteten.

1. Alle brugerdefinerede matchregler, der er defineret for altid at matche, og som ikke matcher, tilsidesætter deduplikeringsregler. Hvis en deduplikeringsregel identificerer matchende poster, og en brugerdefineret matchregel er angivet til aldrig at matche disse poster, kan disse to poster ikke blive matchet.

1. Når du har kørt matchprocessen, kan du se deduplikeringsstatistikken.
   
> [!NOTE]
> Det er ikke obligatorisk at angive regler for fjernelse af dubletter. Hvis der ikke er konfigureret sådanne regler, anvendes de systemdefinerede regler. De skjuler alle poster, der deler den samme værdikombination (nøjagtigt match) fra den primære nøgle, og de felter, der opfylder kriterierne til en enkelt post, inden objektdataene overføres til match på tværs af objekter for at opnå forbedret ydeevne og systemsikkerhed.

## <a name="run-your-match-order"></a>Køre matchrækkefølgen

Når du har defineret de matchende regler, herunder regler for matchning og deduplikering på tværs af objekter, kan du køre matchrækkefølgen. Vælg **Kør** på siden **Match** for at starte processen. Det kan tage et stykke tid at fuldføre matchningsalgoritmen. Du kan ikke ændre egenskaber på siden **Match**, før den matchende proces er fuldført. Du kan finde det samlede kundeprofilobjekt, der blev oprettet, på siden **Objekter**. Dit samlede kundeobjekt kaldes **ConflationMatchPairs: CustomerInsights**.

Hvis du vil foretage yderligere ændringer og køre trinnet igen, kan du annullere et igangværende match. Vælg teksten **Opdaterer...**, og vælg **Annuller job** nederst i den siderude, der vises.

Når matchprocessen er fuldført, ændres teksten **Opdaterer...** til **Gennemført**, og derefter kan du bruge alle funktionerne på siden igen.

Den første matchproces medfører, at der oprettes et samlet masterobjekt. Alle efterfølgende matchkørsler medfører udvidelse af dette objekt.

> [!TIP]
> Opgaver og processer indeholder [seks typer status](system.md#status-types). De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies). Du kan vælge status for en proces for at se statusdetaljer for hele jobbet. Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.

## <a name="deduplication-output-as-an-entity"></a>Deduplikere output som et objekt
Ud over det samlede masterobjekt, der er oprettet som en del af et match på tværs af objekter, oprettes der også et nyt objekt for hvert objekt ud fra matchrækkefølgen for at identificere de duplikerede poster. Disse objekter findes sammen med **ConflationMatchPairs:CustomerInsights** i afsnittet **System** på siden **Objekter** med navnet **Deduplication_Datasource_Entity**.

Et deduplikeret outputobjekt indeholder følgende oplysninger:
- Id'er / nøgler
  - Feltet Primær nøgle og dets alternative id-felt. Det alternative id-felt består af alle de alternative id'er, der er identificeret for en post.
  - Deduplication_GroupId-felt vises den gruppe eller klynge, der er identificeret i et objekt, og som grupperer alle lignende poster på baggrund af de angivne felter med deduplikering. Dette bruges til systembehandlingsformål. Hvis der ikke er angivet nogen regler for manuel deduplikering, og der gælder systemdefinerede regler for deduplikering, kan feltet muligvis ikke findes i outputobjektet.
  - Deduplication_WinnerId: Dette felt indeholder vinder-id fra de identificerede grupper eller klynger. Hvis Deduplication_WinnerId er den samme som værdien for den primære nøgle for en post, betyder det, at posten er vinderposten.
- Felter, der bruges til at definere reglerne for deduplikering.
- Felterne Regel og Resultat angiver, hvilke af de duplikeringsregler der blev anvendt, og det antal point, der returneres af den tilsvarende algoritme.

## <a name="review-and-validate-your-matches"></a>Gennemgå og validere dine matches

Evaluere kvaliteten af dine matchpar og finjustere den:

- På siden **Match** kan du finde to felter, der viser indledende indsigt i dine data.

  - **Entydige kunder**: Viser det antal entydige profiler, der identificeres i systemet.
  - **Matchede poster**: Viser antallet af matches på tværs af alle dine matchpar.

- I tabellen **Match ordre** kan du vurdere resultaterne af de enkelte matchpar ved at sammenligne det antal poster, der kommer fra dette matchpars objekt, i forhold til procentdelen af vellykkede matchede poster.

- I sektionen **Regler** for et objekt i tabellen **Match ordre** kan du finde procentdelen af vellykket matchede poster på regelniveau. Hvis du vælger tabelsymbolet ud for en regel, kan du få vist alle disse poster på regelniveau. Det anbefales, at du gennemgår et undersæt af posterne for at bekræfte, at de blev matchet korrekt.

- Eksperimentér med forskellige præcisionstærskler for dine betingelser for at identificere den optimale værdi.

  1. Vælg ellipsen (...) for matchpar-reglen, som du vil eksperimentere med, og vælg **Rediger**.

  2. Vælg den betingelse, du vil eksperimentere med. De enkelte kriterier repræsenteres ved en række i ruden **Matchregel**.

  3. Det, du kan se på siden **Kriterier for eksempel**, afhænger af det præcisionsniveau, du har valgt til en betingelse. Find antallet af matchede og ikke-matchede poster for den valgte betingelse.

     Opnå dyb forståelse af virkningerne af forskellige tærskelværdier. Du kan sammenligne, hvor mange poster der skal matches under hvert af tærskelniveauerne, og få vist posterne under de enkelte indstillinger. Vælg de enkelte felter, og gennemse dataene i tabelafsnittet.

## <a name="optimize-your-matches"></a>Optimere dine matches

Forøg kvaliteten ved at omkonfigurere nogle af dine matchparametre:

- **Ændre matchrækkefølgen** ved at vælge **Rediger** og ændre felterne i matchrækkefølgen.

  > [!div class="mx-imgBorder"]
  > ![Redigere matchrækkefølge for data](media/configure-data-match-order-edit.png "Redigere matchrækkefølge for data")

- **Du kan ændre rækkefølgen af reglerne**, hvis du har defineret flere regler. Du kan omarrangere matchreglerne ved at vælge indstillingerne **Flyt op** og **Flyt ned** i gitteret med matchregler.

  > [!div class="mx-imgBorder"]
  > ![Ændre regelrækkefølge](media/configure-data-change-rule-order.png "Ændre regelrækkefølge")

- **Dupliker dine regler**, hvis du har defineret en matchregel, og du vil oprette en lignende regel med ændringer. Gør det ved at vælge **Dupliker**.

  > [!div class="mx-imgBorder"]
  > ![Duplikere en regel](media/configure-data-duplicate-rule.png "Duplikere en regel")

- **Deaktiver en regel** for at bevare en overensstemmelsesregel, samtidig med at den udelukkes fra matchprocessen.

  > [!div class="mx-imgBorder"]
  > ![Deaktiver en regel](media/configure-data-deactivate-rule.png "Deaktiver en regel")

- **Rediger reglerne** ved at vælge **Rediger**-symbolet. Du kan anvende følgende ændringer:

  - Ændre attributter for en betingelse: Vælg nye attributter i den specifikke betingelsesrække.
  - Ændre grænsen for en betingelse: Juster præcisionsskyderen.
  - Skifte normaliseringsmetode for en betingelse: Opdater normaliseringsmetoden.

## <a name="specify-your-custom-match-records"></a>Angive dine brugerdefinerede matchposter

Du kan angive betingelser, som visse poster altid skal matche eller aldrig skal matche. Disse regler kan masseoverføres til matchprocessen.

1. Vælg indstillingen **Brugerdefineret match** på skærmen **Match ordre**.

   > [!div class="mx-imgBorder"]
   > ![Oprette et brugerdefineret match](media/custom-match-create.png "Oprette et brugerdefineret match")

2. Hvis du ikke har overførte objekter, kan du se dialogboksen **Brugerdefineret match**, der kræver, at du udfylder nogle detaljer. Hvis du tidligere har angivet disse detaljer, kan du gå til trin 8.

   > [!div class="mx-imgBorder"]
   > ![Ny dialogboks Brugerdefineret match](media/custom-match-new-dialog-box.png "Ny dialogboks Brugerdefineret match")

3. Vælg **Udfyld skabelonen** for at hente en skabelonfil, der kan angive, hvilke poster fra hvilke objekter der altid skal matche eller aldrig matche. Du skal separat udfylde posterne af typen "match altid " og "match aldrig " i to forskellige filer.

4. Skabelonen indeholder felter til angivelse af det objekt og de primære nøgleværdier for objektet, der skal bruges i det brugerdefinerede match. Hvis primær nøgle 12345 fra salgsobjektet altid skal matche med den primære nøgle 34567 fra objektet Kontakt, skal du angive følgende:
    - Entity1: Salg
    - Entity1Key: 12345
    - Entity2: Kontakt
    - Entity2Key: 34567

   Den samme skabelonfil kan angive brugerdefinerede matchposter fra flere objekter.
   
   Hvis du vil angive brugerdefineret matchning for deduplikering for et objekt, skal du angive det samme objekt som både Objekt1 og Objekt2 og angive de forskellige værdier for primære nøgler.

5. Gem skabelonfilen, når du har tilføjet alle de tilsidesættelser, du vil anvende.

6. Gå til **Data** > **Datakilder**, og indsæt skabelonfilerne som nye objekter. Når de er indtaget, kan du bruge dem til at angive matchkonfigurationen.

7. Når du har overført filerne, og objekterne er tilgængelige, skal du vælge indstillingen **Brugerdefineret match** igen. Du kan se indstillinger for at angive de objekter, du vil inkludere. Vælg de påkrævede objekter i rullemenuen.

   > [!div class="mx-imgBorder"]
   > ![Tilsidesættelser af brugerdefineret match](media/custom-match-overrides.png "Tilsidesættelser af brugerdefineret match")

8. Vælg de objekter, du vil bruge til **Match altid** og **Match aldrig**, og vælg **Udført**.

9. Vælg **Gem** på siden **Match** for den brugerdefinerede matchkonfiguration, du lige har konfigureret.

10. Vælg **Kør** på siden **Match** for at starte matchprocessen, så den brugerdefinerede matchkonfiguration vil blive anvendt. Alle systemmatchede regler tilsidesættes af konfigurationssættet.

11. Når matchningen er fuldført, kan du kontrollere objektet **ConflationMatchPair** for at bekræfte, at tilsidesættelserne er anvendt i sammenblandingsmatches.

## <a name="next-step"></a>Næste trin

Når du har fuldført matchprocessen for mindst ét matchpar, kan du løse mulige modstridende data ved at gennemgå emnet [**Flet**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]