---
title: Semantiske tilknytninger (forhåndsversion)
description: Oversigt over semantiske tilknytninger, og hvordan de bruges.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183624"
---
# <a name="semantic-mappings-preview"></a>Semantiske tilknytninger (forhåndsversion)

Med semantiske tilknytninger kan du knytte ikke-aktivitetsdataene til foruddefinerede skemaer. Disse skemaer hjælper Customer Insights til bedre at forstå dine dataattributter. Semantisk tilknytning og de medfølgende data muliggør ny indsigt og funktioner i Customer Insights. Hvis du vil knytte aktivitetsdataene til skemaerne, skal du gennemgå dokumentationen til [aktiviteter](activities.md).

**Semantiske tilknytninger er i øjeblikket aktiveret for miljøer baseret på forretningskonti**. *ContactProfile* er den eneste semantiske tilknytningstype, der i øjeblikket er tilgængelig i Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definere en semantisk objekttilknytning af ContactProfile

1. Gå til **Data** > **Semantiske tilknytninger (forhåndsversion)**.

1. Vælg **Tilføj semantisk tilknytning** for at starte den styrede oplevelse.

1. Angiv værdierne for følgende felter i trinnet **Objektdata**:

   - **Navn på semantisk objekttilknytning**: Angiv et navn til den semantiske objekttilknytning.
   - **Kildeobjekt**: Vælg et objekt, der indeholder kontaktdata.
   - **Primær nøgle**: Vælg det felt, der entydigt identificerer en kontaktpersonpost. Den må ikke indeholde dublerede værdier, tomme værdier eller manglende værdier.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Konfigurer den semantiske objekttilknytning med navn, kildeobjekt og primær nøgle.":::

1. Vælg **Næste**.

1. I trinnet **Relationer** skal du konfigurere detaljerne for at knytte din kontaktdata til de tilhørende kontodata. I dette trin visualiseres forbindelsen mellem objekter.  

   Der findes to typer relationsstier, der kan implementeres: **direkte relationer** og **indirekte relationer**. Du kan finde flere oplysninger ved at gå til [direkte og indirekte relationsstier](relationships.md#relationship-paths).

   1. Vælg **Tilføj relation** for at konfigurere relationen.
   1. Vælg den attribut fra kildeobjektet, der opretter forbindelse mellem kontaktobjektet og et andet objekt.
   1. Vælg det objekt, som kontaktobjektet skal knyttes til. Du kan vælge et objekt i sektionen **Kundeobjekter** eller **Midlertidigt objekt**. Hvis du vælger et midlertidigt objekt, skal du definere en anden relation for at oprette forbindelse til objektet for målkontoen.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Vælg enten et kundeobjekt eller et midlertidigt objekt.":::

   1. Angiv et **Relationsnavn**. Hvis der allerede findes en relation mellem objekterne, er relationsnavnet skrivebeskyttet. Hvis der ikke findes en relation, oprettes der en ny relation med det navn, du angiver.
   1. Vælg **Anvend** for at fuldføre konfigurationen af relationen.

   > [!NOTE]
   > Du kan konfigurere flere relationer mellem kontaktobjektet og andre kundeobjekter med midlertidige objekter.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisering af relationer, der forbinder kontaktobjekter og kundeobjekter.":::

1. Vælg **Næste**.

1. Vælg en **Semantisk type** i trinnet **Angiv semantisk type**. I øjeblikket findes der én **Semantisk type**, der kaldes *ContactProfile*.

1. Knyt kontakt-id'et til *ContactProfile* semantiske **kontakt-id**. Du kan også gentage de samme trin for andre felter som Fornavn, Efternavn, Køn eller e-mail.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Knyt kontaktdataattributterne til de angivne obligatoriske og valgfrie felter.":::

1. Vælg **Næste**.

1. I trinnet **Gennemse** skal du se på konfigurationen af den semantiske tilknytning. Vælg **Rediger** for den tilsvarende sektion for at foretage ændringer.

1. Vælg **Gem**.

1. Vælg **Kør** for at behandle tilknytningen. Du kan også vælge **Luk** for at gemme den semantiske tilknytning uden at behandle den. Hvis du vil køre en semantisk tilknytning på et senere tidspunkt, skal du vælge den semantiske tilknytning og vælge **Opdater**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Administrere eksisterende semantiske tilknytninger

Gå til **Data** > **Semantiske tilknytninger (forhåndsversion)** for at få vist de gemte semantiske tilknytninger, deres kildeobjekt, semantiske type, tilknytningstype og status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Indstillinger for administration af semantiske tilknytninger.":::

Vælg en semantisk tilknytning for at få vist tilgængelige handlinger.
- **Rediger** den aktuelle konfiguration. Vælg **Gem** og **Kør** for at behandle ændringerne.
- **Opdater** den semantiske tilknytning, så den indeholder de seneste data. Hvis du opdaterer en bestemt semantisk tilknytning, opdateres alle semantiske tilknytninger af samme type.
- **Omdøb** den semantiske tilknytning. Vælg **Gem**.
- **Slet** den semantiske tilknytning. Du kan slette mere end én semantisk tilknytning på én gang ved at vælge de semantiske tilknytninger og sletteikonet. Bekræft sletningen ved at vælge **Slet**.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Brug en semantisk objekttilknytning af ContactProfile til at oprette aktiviteter på kontaktniveau

Når du har oprettet en semantisk objekttilknytning af *ContactProfile*, kan du registrere kontaktaktiviteter. Det giver dig mulighed for på aktivitetstidslinjen at se, hvilken kontaktperson der var ansvarlig for hver enkelt aktivitet, på aktivitetstidslinjen. De fleste trin følger den typiske konfiguration af aktivitetstilknytning.

   > [!NOTE]
   > Hvis aktiviteter på kontaktniveau skal fungere, skal du have attributterne **AccountID** og **ContactID** for hver post i aktivitetsdataene.

1. [Definer en *ContactProfile*-semantisk objekttilknytning](#define-a-contactprofile-semantic-entity-mapping), og kør den semantiske tilknytning.

1. Gå til **Data** > **Aktiviteter**.

1. Vælg **Tilføj aktivitet** for at oprette en ny aktivitet.

1. Navngive aktiviteten, vælge kildeaktivitetsobjektet og vælge den primære nøgle til aktivitetsobjektet.

1. I trinnet med **Relationer** kan du oprette en relation mellem aktivitetskildedataene og firmaer ved at bruge kontaktdataene som et objekt, der gør det nemt at anvende dem. Du kan finde flere oplysninger ved at gå til [direkte og indirekte relationsstier](relationships.md#relationship-paths).
   - Eksempel på relation for en aktivitet, der kaldes *Køb*:
      - **Køber kildeaktivitetsdata** > **Kontaktdata** på attributten **ContactID**
      - **Kontaktdata** > **Kontodata** på attributten **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Eksempel på konfiguration af relation.":::

1. Når du har konfigureret Relationer, skal du vælge **Næste** og fuldføre konfigurationen af aktivitetstilknytningen. Du kan finde detaljerede oplysninger om oprettelse af en aktivitet i [definere en aktivitet](activities.md).

1. Kør aktivitetstilknytningerne.

1. Når der er kørt en aktivitetstilknytning på kontaktniveau, skal du vælge **Kunder**. Dine aktiviteter på kontaktniveau er nu synlige på din kundetidslinje.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Slutresultat efter konfiguration af kontaktaktiviteter":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtrering af aktivitetstidslinje på kontaktniveau

Den indeholder deres ide eller navne, afhængigt af din *ContactProfile*-konfiguration, for de aktiviteter, de har handlet på. Du kan filtrere aktiviteter efter kontaktpersoner på tidslinjen for at se bestemte kontakter, du er interesseret i. Du kan også se alle de aktiviteter, der ikke er tildelt til en bestemt kontakt, ved at vælge **Aktiviteter, der ikke er knyttet til en kontaktperson**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="De filtreringsindstillinger, der er tilgængelige for aktiviteter på kontaktniveau.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
