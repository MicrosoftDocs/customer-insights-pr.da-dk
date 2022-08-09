---
title: Vælg kildefelter til datasamling
description: Det første trin i processen til samling er at vælge objekter, attributter, primære nøgler og semantiske typer for at knytte data til unified customer profile.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a75218c996b277e00924f2b7b38ea686a1f4dc38
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139775"
---
# <a name="select-source-fields-for-data-unification"></a>Vælg kildefelter til datasamling

Det første trin i en samling er at vælge de objekter og felter i datasæt, du vil samle. Vælg objekter, der indeholder kunderelaterede detaljer, f.eks. navn, adresse, telefonnummer og mail. Du kan vælge ét eller flere objekter.

## <a name="select-entities-and-fields"></a>Vælg objekter og felter

1. Gå til **Data** > **Samle**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Skærmbillede af unify landingsside for første kørsel med Introduktion fremhævet.":::

1. Vælg **Introduktion**.

1. Vælg **Vælg objekter og felter** på siden **Kildefelter**. Ruden **Vælg objekter og felter** vises.

1. Vælg mindst ét objekt.

1. I forbindelse med hvert enkelt valgt objekt skal du identificere de felter, du vil bruge til at matche kundeposter og felter, der skal inkluderes i den samlede profil. Disse felter kaldes *attributter*. Du kan vælge de påkrævede attributter individuelt fra et objekt eller medtage alle attributter fra et objekt ved at markere afkrydsningsfeltet på objektniveau. Du kan søge efter nøgleord på tværs af alle attributter og objekter for at vælge de nødvendige attributter, du vil tilknytte.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Skærmbillede af udvalgte objekter og attributter.":::

   I dette eksempel tilføjer vi objekterne **Kontaktpersoner** og **CustomerLoyalty**. Hvis du vælger disse objekter, kan du få indsigt i, hvilke online virksomhedskunder der er medlemmer af loyalitetsprogrammet.

1. Vælg **Anvend** for at bekræfte de valgte indstillinger. Skærmbillede af udvalgte objekter og attributter.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Vælg primær nøgle og semantisk type for attributter

   :::image type="content" source="media/m3_select_primary.png" alt-text="Skærmbillede af valgte objekter, hvor primær nøgle ikke er valgt." lightbox="media/m3_select_primary.png":::

Udfør følgende trin for hvert enkelt objekt.

1. Vælg den **primære nøgle**. Den primære nøgle er en attribut, der er entydig for objektet. Hvis en attribut skal være en gyldig primær nøgle, må den ikke indeholde dubletværdier, manglende værdier eller null-værdier. Strengattributter, heltalsattributter og GUID-datatypeattributter understøttes som primære nøgler.

1. Hvis du vil bruge AI-modeller til smart forudsigelse semantik, kan du spare tid og forbedre præcisionen ved at sikre, at **intelligent tilknytning** er tændt. Intelligent tilknytning fremhæver den AI-baserede semantikanbefaling i feltet **Type**. Du kan tilsidesætte det foreslåede valg ved at vælge en semantisk type på den tilgængelige liste over indstillinger.

1. Vælg en semantisk **type** for hver attribut, der bedst beskriver den pågældende attribut, f.eks. navn, by eller mailadresse.

   > [!NOTE]
   > Et felt skal knyttes til den semantiske type *Person.FullName* for at udfylde kundenavnet i kundekortet. Ellers vises kundekortene uden navn.

   1. Du kan ændre en attributtyper, der identificeres af systemet, ved at vælge en anden type. Hvis typen ikke findes, kan du oprette en brugerdefineret semantisk type ved at vælge feltet **Type** for attributten og angive navnet på den brugerdefinerede semantiske type.

   1. Hvis du vil tilføje en attribut, der indeholder en URL-adresse til offentligt tilgængelige profilbilleder eller logoer, skal du vælge det objekt og felt, der indeholder URL-adressen. Gør følgende i feltet **Type**:
      - For en person: Person.ProfileImage
      - For en organisation: Organization.LogoImage

   1. Angiv "Organization.Name" i feltet **Type** for en firmanavnsattribut.

1. Gennemse de attributter, hvor en semantisk type automatisk identificeres. Disse attributter vises under **Gennemse tilknyttede felter**. Det er kun attributter med samme type, der kan kombineres i felttrinnet **Unified Customer**. Semantiske typer bruges til automatisk at foreslå indsigt. Sikre, at de valgte typer er ensartede på tværs af alle valgte objekter.

1. I forbindelse med attributter, der ikke automatisk knyttes til en semantisk type, skal du vælge et semantisk felt, angive navnet på den brugerdefinerede attributtype eller lade dem være ikke-tilknyttet. Disse attributter vises under **Definer dataene i de ikke-tilknyttede felter**.

1. Når trinnene for de enkelte objekter er fuldført, skal du vælge **Gem kildefelter**.

1. Vælg **Næste**.

> [!div class="nextstepaction"]
> [Næste trin: Fjernelse af dubletter](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
