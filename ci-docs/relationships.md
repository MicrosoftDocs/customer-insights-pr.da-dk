---
title: Forhold mellem objekter og objektstier
description: Opret og administrer forhold mellem objekter fra flere datakilder.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: a7b10d985d5cba64b25595a3d7c101d6cb5c62a5
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646392"
---
# <a name="relationships-between-entities"></a>Relationer mellem objekter

Relationer forbinde objekter og definere en graf over dine data, når objekter deler et fælles id, en fremmednøgle. Der kan refereres til denne fremmednøgle fra et objekt til et andet. Forbundne objekter giver dig mulighed for at definere segmenter og målinger, der er baseret på flere datakilder.

Der findes tre typer relationer: 
- Systemrelationer, som ikke kan redigeres. Disse oprettes af systemet som del af datasamlingen
- Nedarvede relationer, som ikke kan redigeres. Disse oprettes automatisk ud fra indtagelse af datakilder 
- Brugerdefinerede relationer, der kan redigeres. Disse oprettes og konfigureres af brugere

## <a name="non-editable-system-relationships"></a>Systemrelationer, der ikke kan redigeres

Under datasamling oprettes systemrelationer automatisk baseret på intelligent matchning. Disse relationer hjælper med at relatere kundeprofilposter til tilsvarende poster. I følgende diagram illustreres oprettelsen af tre systembaserede relationer. Kundeobjektet matches med andre enheder for at producere den samlede *kundeenhed*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram med relationsstier for kundeobjektet med tre 1-n-relationer.":::

- ***CustomerToContact*-relationen** blev oprettet mellem objektet *Kunde* og objektet *Kontakt*. Objektet *Kunde* får nøglefeltet **Contact_contactID** til at relatere til nøglefeltet *contactID* for objektet **Kontakt**.
- ***CustomerToAccount*-relationen** blev oprettet mellem objektet *Kunde* og objektet *Konto*. Objektet *Kunde* får nøglefeltet **Account_accountID** til at relatere til nøglefeltet *accountID* for objektet **Konto**.
- ***CustomerToWebAccount*-relationen** blev oprettet mellem objektet *Kunde* og objektet *WebAccount*. Objektet *Kunde* får nøglefeltet **WebAccount_webaccountID** til at relatere til nøglefeltet *webaccountID* for **WebAccount**.

## <a name="non-editable-inherited-relationships"></a>Nedarvede relationer, der ikke kan redigeres

Under dataindtagelsesprocessen kontrollerer systemet datakilder for eksisterende relationer. Hvis der ikke findes relationer, opretter systemet dem automatisk. Disse relationer anvendes også i downstream-processer.

## <a name="create-a-custom-relationship"></a>Oprette en brugerdefineret relation

Relationen består af et *kildeobjekt*, der indeholder fremmednøglen, og et *destinationsobjekt*, som kildeobjektets fremmednøgle peger på. 

1. Gå til **Data** > **Relationer**.

2. Vælg **Ny relation**.

3. Angiv følgende oplysninger i ruden **Ny relation**:

   :::image type="content" source="media/relationship-add.png" alt-text="Rude på siden Ny relation med tomme inputfelter.":::

   - **Relationsnavn**: Navn, der afspejler relationens formål. Eksempel: CustomerToSupportCase.
   - **Beskrivelse**: Beskrivelsen af relationen.
   - **Kildeobjekt**: Objekt, der bruges som kilde i relationen. Eksempel: SupportCase.
   - **Målobjekt**: Objekt, der bruges som målet i relationen. Eksempel: Kunde.
   - **Kildekardinalitet**: Angiv kardinaliteten for kildeobjektet. Kardinalitet beskriver antallet af mulige elementer i et sæt. Det vedrører altid målets kardinalitet. Du kan vælge mellem **En** og **Mange**. Det er kun mange-til-én- og én-til-én-relationer, der understøttes.  
     - Mange-til-en: Flere kildeposter kan relateres til én målpost. Eksempel: Flere supportsager fra en enkelt kunde.
     - En-til-en: En enkelt kildepost vedrører én målpost. Eksempel: Ét loyalitets-id for en enkelt kunde.

     > [!NOTE]
     > Mange-til-mange-relationer kan oprettes ved hjælp af to mange-til-en-relationer og et sammenkædningsobjekt, der forbinder kildeobjektet og destinationsobjektet.

   - **Målkardinalitet**: Vælg kardinaliteten for målobjektposterne. 
   - **Kildenøglefelt**: Feltet med fremmednøglen i kildeobjektet. Eksempel: SupportCase kan bruge CaseID som et fremmednøgle-felt.
   - **Målnøglefelt**: Nøglefeltet for målobjektet. Eksempel: Kunde kan bruge nøglefeltet **CustomerID**.

4. Vælg **Gem** for at oprette den brugerdefinerede relation.

## <a name="set-up-account-hierarchies"></a>Konfigurere kontohierarkier

Miljøer, der er konfigureret til at bruge forretningskonti som primær målgruppe, kan konfigurere kontohierarkier for relaterede forretningskonti. Det kan f.eks. være en virksomhed, der har separate afdelinger. 

Organisationer kan oprette kontohierarkier for bedre at administrere konti og deres relationer med hinanden. Customer Insights understøtter hierarkier for overordnede og underordnede konti, der allerede findes i kundedata, der er indtaget. Det kan f.eks. være konti fra Dynamics 365 Sales. Disse hierarkier kan konfigureres på siden **Relationer**.

1. Gå til **Data** > **Relationer**.
1. Vælg fanen **Kontohierarki**.
1. Vælg **Nyt kontohierarki**. 
1. Angiv et navn til hierarkiet i ruden **Kontohierarki**. Der oprettes et navn til outputobjektet. Du kan ændre navnet på outputobjektet.
1. Vælg det objekt, der indeholder kontohierarkiet. Det findes som regel i det samme objekt, som indeholder kontiene.
1. Vælg **Konto-id** og **Overordnet konto-id** fra det valgte objekt 
1. Vælg **Gem** for at anvende indstillingerne og færdiggøre kontohierarkiet.

## <a name="view-relationships"></a>Vise relationer

På siden Relationer vises alle de relationer, der er oprettet. Hver række repræsenterer en relation, som også indeholder oplysninger om kildeobjektet, målobjektet og kardinaliteten. 

:::image type="content" source="media/relationships-list.png" alt-text="Liste over relationer og indstillinger på handlingslinjen på siden Relationer.":::

Denne side indeholder et sæt indstillinger for eksisterende og nye relationer: 
- **Ny relation**: [Opret en brugerdefineret relation](#create-a-custom-relationship).
- **Visualisering**: [Udforsk relationens visualiseringsfunktion](#explore-the-relationship-visualizer) for at få vist et netværksdiagram over de eksisterende relationer og deres kardinalitet.
- **Filtrer efter**: Vælg den type relationer, der skal vises på listen.
- **Søg efter relationer**: Brug en tekstbaseret søgning på egenskaberne for relationerne.

### <a name="explore-the-relationship-visualizer"></a>Udforsk relationens visualiseringsfunktion

Relationens visualiseringsfunktion viser et netværksdiagram over de eksisterende relationer mellem tilsluttede objekter og deres kardinalitet. Relationsstien visualiseres også.

Hvis du vil tilpasse visningen, kan du ændre felternes placering ved at trække dem på lærredet.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Skærmbillede af netværksdiagrammet for relationens visualiseringsfunktion med forbindelser mellem relaterede objekter.":::

Tilgængelige indstillinger: 
- **Eksporter som billede**: Gem den aktuelle visning som en billedfil.
- **Skift til vandret/lodret layout**: Skift justering af enhederne og relationer.
- **Rediger**: Opdater egenskaber for brugerdefinerede relationer i redigeringsruden, og gem ændringerne.

## <a name="relationship-paths"></a>Relationsstier

En relationssti beskriver de objekter, der er knyttet til relationer mellem et kildeobjekt og et destinationsobjekt. Det bruges, når du opretter et segment eller en måleenhed, der omfatter andre objekter end objektet for den samlede profil, og der er flere indstillinger, du kan bruge til at oprette forbindelse til objektet for den samlede profil. 

En relationssti giver det system, relationer har adgang til, oplysninger om adgang til det samlede profilobjekt. Forskellige relationsstier kan give forskellige resultater.

Objektenheden indeholder f.eks. *eCommerce_eCommercePurchases* følgende relationer til objektet *Kunde* i den samlede profil:

- eCommerce_eCommercePurchases > kunde
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > kunde
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > kunde 

En relationssti bestemmer, hvilke objekter du kan bruge, når du opretter regler for mål eller segmenter. Hvis du vælger indstillingen med overensstemmelsesforløbet for relationer, giver det højst sandsynligt færre resultater, da de tilsvarende poster skal være en del af alle objekter. I dette eksempel skal en kunde have købt varer via e-handel (eCommerce_eCommercePurchases) på et salgspunkt (POS_posPurchases) og deltage i vores loyalitetsprogram (loyaltyScheme_loyCustomers). Når du vælger den første indstilling, får du sandsynligvis flere resultater, fordi kunderne kun skal findes i ét yderligere objekt.

### <a name="direct-relationship"></a>Direkte relation

En relation klassificeres som en **direkte relation**, når et kildeobjekt er relateret til et målobjekt med kun én relation.

Hvis et aktivitetsobjekt, der kaldes *eCommerce_eCommercePurchases*, f.eks. kun opretter forbindelse til et målobjekt *eCommerce_eCommerceContacts* via *ContactId*, er det en direkte relation.

:::image type="content" source="media/direct_Relationship.png" alt-text="Kildeobjektet opretter direkte forbindelse til destinationsobjektet.":::

#### <a name="multi-path-relationship"></a>Relation med flere forbindelser

En **relation med flere forbindelser** er en særlig type direkte relation, der opretter forbindelse mellem et kildeobjekt og mere end ét destinationsobjekt.

Hvis et aktivitetsobjekt, der kaldes *eCommerce_eCommercePurchases*, f.eks. er relateret til to målobjekter, både *eCommerce_eCommerceContacts* og *loyaltyScheme_loyCustomers*, er det en relation med flere forbindelser.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Kildeobjektet opretter direkte forbindelse til mere end ét destinationsobjekt via en relation til flere forbindelser.":::

### <a name="indirect-relationship"></a>Indirekte relation

En relation klassificeres som en **indirekte relation**, når et kildeobjekt er relateret til et eller flere yderligere objekter, før det relaterer til é målobjekt.

#### <a name="multi-hop-relationship"></a>Multi-hop-relation

En *multi-hop-relation* er en et *indirekte relation*, der bruges til at tilknytte et kildeobjekt til et destinationsobjekt via et eller flere objekter.

Hvis et aktivitetsobjekt kaldet *eCommerce_eCommercePurchasesWest* f.eks. opretter forbindelse til et mellemliggende objekt, der kaldes *eCommerce_eCommercePurchasesEast* og derefter opretter forbindelse til et målobjekt, der kaldes *eCommerce_eCommerceContacts*, er det en multi-hop-relation.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Kildeobjektet opretter direkte forbindelse til et destinationsobjekt med et mellemliggende objekt.":::

### <a name="multi-hop-multi-path-relationship"></a>Multi-hop, relation med flere forbindelser

Multi-hop-relation og relation med flere forbindelser kan bruges sammen til at oprette **multi-hop-relation, relation med flere forbindelser**. Denne specielle type kombinerer funktionerne for **multi-hop-relation** og **relation med flere forbindelser**. Du kan oprette forbindelse til mere end ét destinationsobjekt, mens du bruger mellemliggende objekter.

Hvis et aktivitetsobjekt kaldet *eCommerce_eCommercePurchasesWest* f.eks. opretter forbindelse til et mellemliggende objekt, der kaldes *eCommerce_eCommercePurchasesEast* og derefter opretter forbindelse til to målobjekter, både *eCommerce_eCommerceContacts* og *loyaltyScheme_loyCustomers*, er det en multi-hop-relation, relation med flere forbindelser.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Kildeobjektet opretter direkte forbindelse til ét destinationsobjekt og opretter forbindelse til et andet målobjekt via et mellemobjekt.":::

## <a name="manage-existing-relationships"></a>Administrer eksisterende relationer 

På siden Relationer repræsenteres hver relation af en række. 

Vælg en relation, og vælg en af følgende indstillinger: 
 
- **Rediger**: Opdater egenskaber for brugerdefinerede relationer i redigeringsruden, og gem ændringerne.
- **Slet**: Slet brugerdefinerede relationer.
- **Vis**: Få vist systemoprettede og nedarvede relationer. 

## <a name="next-step"></a>Næste trin

System- og nrugerdefinerede relationer bruges til at [oprette segmenter](segments.md) og [mål](measures.md) baseret på flere datakilder, der ikke længere er tilgængelige.

[!INCLUDE [footer-include](includes/footer-banner.md)]
