---
title: Vælg kildefelter til datasamling
description: Det første trin i processen til samling er at vælge objekter, attributter, primære nøgler og semantiske typer for at knytte data til unified customer profile.
recommendations: false
ms.date: 08/12/2022
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
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304558"
---
# <a name="select-source-fields-for-data-unification"></a>Vælg kildefelter til datasamling

Det første trin i en samling er at vælge de objekter og felter i datasæt, du vil samle. Vælg objekter, der indeholder kunderelaterede detaljer, f.eks. navn, adresse, telefonnummer og mail. Du kan vælge ét eller flere objekter.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Vælg objekter og felter

1. Gå til **Data** > **Samle**.

   For de enkelte kunder (B-til-C) vises landingssiden **Foren**, der viser **Start her** i første trin, **Kildefelter**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Skærmbillede af Foren-landingsside for første kørsel til enkeltkunder.":::

   For forretningskonti (B-til-B) vises landingssiden **Foren** med **Foren firmaer**, der viser **Start her** i første trin, **Kildefelter**. Trinnene **Foren kontakter (forhåndsversion)** er valgfrie og afventer, at firmasamlingen er fuldført.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Skærmbillede af Foren-landingsside for første kørsel til forretningskonti.":::

1. Vælg **Start her**.

1. Vælg **Vælg objekter og felter** på siden **Kildefelter**. Ruden **Vælg objekter og felter** vises.

1. Vælg mindst ét objekt.

1. I forbindelse med hvert enkelt valgt objekt skal du identificere de felter, du vil bruge til at matche kundeposter og felter, der skal inkluderes i den samlede profil. Disse felter kaldes *attributter*. Du kan vælge de påkrævede attributter individuelt fra et objekt eller medtage alle attributter fra et objekt ved at markere afkrydsningsfeltet på objektniveau. Du kan søge efter nøgleord på tværs af alle attributter og objekter for at vælge de nødvendige attributter, du vil tilknytte.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Skærmbillede af udvalgte objekter og attributter.":::

   I dette eksempel tilføjer vi objekterne **eCommerceContacts** og **loyCustomer**. Hvis du vælger disse objekter, kan du få indsigt i, hvilke online virksomhedskunder der er medlemmer af loyalitetsprogrammet.

1. Vælg **Anvend** for at bekræfte de valgte indstillinger. Skærmbillede af udvalgte objekter og attributter.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Vælg primær nøgle og semantisk type for attributter

   :::image type="content" source="media/m3_select_primary.png" alt-text="Skærmbillede af valgte objekter, hvor primær nøgle endnu ikke er valgt." lightbox="media/m3_select_primary.png":::

Udfør følgende trin for hvert enkelt objekt.

1. Vælg den **primære nøgle**. Den primære nøgle er en attribut, der er entydig for objektet. Hvis en attribut skal være en gyldig primær nøgle, må den ikke indeholde dubletværdier, manglende værdier eller null-værdier. Strengattributter, heltalsattributter og GUID-datatypeattributter understøttes som primære nøgler.

1. Hvis du vil bruge AI-modeller til smart forudsigelse af semantik, kan du spare tid og øge præcisionen ved at sikre, at **Intelligent tilknytning** er aktiveret. Intelligent tilknytning viser AI-baserede semantiske anbefalinger i feltet **Type**.

1. Vælg en semantisk **type** for hver attribut, der bedst beskriver den pågældende attribut, f.eks. navn, by eller mailadresse.

   > [!NOTE]
   > I B-til-C skal ét felt knyttes til den semantiske type *Person.FullName* for at udfylde kundenavnet i kundekortet. I B-til-B skal firmanavnet knyttes til *Organization.Name*. Ellers vises kundekortene uden navn.

   1. Du kan tilsidesætte en attributtype, der identificeres af systemet, ved at vælge en anden mulighed. Hvis typen ikke findes, kan du oprette en brugerdefineret semantisk type ved at vælge feltet **Type** for attributten og angive navnet på den brugerdefinerede semantiske type.

   1. Hvis du vil tilføje en attribut, der indeholder en URL-adresse til offentligt tilgængelige profilbilleder eller logoer, skal du vælge det objekt og felt, der indeholder URL-adressen. Gør følgende i feltet **Type**:
      - For en person: Person.ProfileImage
      - For en organisation: Organization.LogoImage

1. Gennemse de attributter, hvor en semantisk type automatisk identificeres. Disse attributter vises under **Gennemse tilknyttede felter**. Det er kun attributter med samme type, der kan kombineres i trinnet **Samle kundefelter**. Semantiske typer bruges til automatisk at foreslå indsigt. Sikre, at de valgte typer er ensartede på tværs af alle valgte objekter.

1. I forbindelse med attributter, der ikke automatisk knyttes til en semantisk type, skal du vælge et semantisk felt, angive navnet på den brugerdefinerede attributtype eller lade dem være ikke-tilknyttet. Disse attributter vises under **Definer dataene i de ikke-tilknyttede felter**.

1. Når trinnene for de enkelte objekter er fuldført, skal du vælge **Gem kildefelter**.

1. Vælg **Næste**.

> [!div class="nextstepaction"]
> [Næste trin: Fjernelse af dubletter](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
