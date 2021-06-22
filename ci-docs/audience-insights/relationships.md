---
title: Forhold mellem objekter og objektstier
description: Opret og administrer forhold mellem objekter fra flere datakilder.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171157"
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

1. Gå til **Data** > **Forhold** i målgruppen Insights.

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

## <a name="view-relationships"></a>Vise relationer

På siden Relationer vises alle de relationer, der er oprettet. Hver række repræsenterer en relation, som også indeholder oplysninger om kildeobjektet, målobjektet og kardinaliteten. 

:::image type="content" source="media/relationships-list.png" alt-text="Liste over relationer og indstillinger på handlingslinjen på siden Relationer.":::

Denne side indeholder et sæt indstillinger for eksisterende og nye relationer: 
- **Ny relation**: [Opret en brugerdefineret relation](#create-a-custom-relationship).
- **Visualisering**: [Udforsk relationens visualiseringsfunktion](#explore-the-relationship-visualizer) for at få vist et netværksdiagram over de eksisterende relationer og deres kardinalitet.
- **Filtrer efter**: Vælg den type relationer, der skal vises på listen.
- **Søg efter relationer**: Brug en tekstbaseret søgning på egenskaberne for relationerne.

### <a name="explore-the-relationship-visualizer"></a>Udforsk relationens visualiseringsfunktion

Relationens visualiseringsfunktion viser et netværksdiagram over de eksisterende relationer mellem tilsluttede objekter og deres kardinalitet.

Hvis du vil tilpasse visningen, kan du ændre felternes placering ved at trække dem på lærredet.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Skærmbillede af netværksdiagrammet for relationens visualiseringsfunktion med forbindelser mellem relaterede objekter.":::

Tilgængelige indstillinger: 
- **Eksporter som billede**: Gem den aktuelle visning som en billedfil.
- **Skift til vandret/lodret layout**: Skift justering af enhederne og relationer.
- **Rediger**: Opdater egenskaber for brugerdefinerede relationer i redigeringsruden, og gem ændringerne.

## <a name="manage-existing-relationships"></a>Administrer eksisterende relationer 

På siden Relationer repræsenteres hver relation af en række. 

Vælg en relation, og vælg en af følgende indstillinger: 
 
- **Rediger**: Opdater egenskaber for brugerdefinerede relationer i redigeringsruden, og gem ændringerne.
- **Slet**: Slet brugerdefinerede relationer.
- **Vis**: Få vist systemoprettede og nedarvede relationer. 

## <a name="next-step"></a>Næste trin

System- og brugerdefinerede relationer bruges til at [oprette segmenter](segments.md) baseret på flere datakilder, der ikke længere er i en silo.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
