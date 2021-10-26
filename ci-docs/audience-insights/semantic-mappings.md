---
title: Semantiske tilknytninger (forhåndsversion)
description: Oversigt over semantiske tilknytninger, og hvordan de bruges.
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622928"
---
# <a name="semantic-mappings"></a>Semantiske tilknytninger

Med semantiske tilknytninger kan du knytte ikke-aktivitetsdataene til foruddefinerede skemaer. Disse skemaer hjælper målgruppeindsigt til bedre at forstå dine dataattributter. Semantisk tilknytning og de medfølgende data muliggør ny indsigt og funktioner i målgruppeindsigt. Hvis du vil knytte aktivitetsdataene til skemaerne, skal du gennemgå dokumentationen til [aktiviteter](activities.md).

**Semantiske tilknytninger er i øjeblikket aktiveret for miljøer baseret på forretningskonti**. *ContactProfile* er den eneste semantiske tilknytningstype, der i øjeblikket er tilgængelig i målgruppeindsigt.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Definere en semantisk objekttilknytning af ContactProfile

1. Gå i målgruppeindsigt til **Data** > **Semantiske tilknytninger (forhåndsversion)**.

1. Vælg **Tilføj semantisk tilknytning** for at starte den styrede oplevelse.

1. Angiv værdierne for følgende felter i trinnet **Objektdata**:

   - **Navn på semantisk objekttilknytning**: Angiv et navn til den semantiske objekttilknytning.
   - **Kildeobjekt**: Vælg et objekt, der indeholder kontaktdata.
   - **Primær nøgle**: Vælg det felt, der entydigt identificerer en kontaktpersonpost. Den må ikke indeholde dublerede værdier, tomme værdier eller manglende værdier.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Konfigurer den semantiske objekttilknytning med navn, kildeobjekt og primær nøgle.":::

1. Vælg **Næste** for at fortsætte.

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
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisering af relationer, der forbinder kontaktobjekter og kundeobjekter.":::

1. Vælg **Næste**, når du er færdig med relationskonfigurationen.

1. Vælg en **Semantisk type** i trinnet **Angiv semantisk type**. I øjeblikket findes der én **Semantisk type**, der kaldes *ContactProfile*.

1. Knyt dine data til den **Semantiske type** *ContactProfile* for de viste felter.
   - Obligatorisk felt: Kontakt-id
   - Valgfrie felter: Fornavn, Efternavn, Fødselsdato, Køn, Primær mail og Primær telefon

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Knyt kontaktdataattributterne til de angivne obligatoriske og valgfrie felter.":::

1. Vælg **Næste** for at fortsætte.

1. I trinnet **Gennemse** skal du se på konfigurationen af den semantiske tilknytning. Vælg **Rediger** for den tilsvarende sektion for at foretage ændringer.

1. Vælg **Gem** for at gemme den nye **semantiske tilknytning**.

1. Når du har gemt, kan du vælge **Kør** for den semantiske tilknytning, eller du kan vælge **Luk** for at gemme den semantiske tilknytning uden at behandle den.

1. Hvis du vil køre en semantisk tilknytning på et senere tidspunkt, skal du vælge den semantiske tilknytning og vælge **Opdater**.

> [!TIP]
> Opgaver og processer indeholder [seks typer status](system.md#status-types). De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies). Du kan vælge status for en proces for at se statusdetaljer for hele jobbet. Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.

## <a name="manage-existing-semantic-mappings"></a>Administrere eksisterende semantiske tilknytninger

I **Data** > **Semantiske tilknytninger (forhåndsversion)** kan du få vist alle de gemte semantiske tilknytninger og administrere dem. De enkelte semantiske tilknytninger repræsenteres af en separat række. Du kan finde oplysninger om kildeobjektet, semantisk type, tilknytningstype og status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Indstillinger for administration af semantiske tilknytninger.":::

- **Rediger**: Åbner konfigurationen af den semantiske tilknytning i trinnet Gennemse. Du kan ændre den aktuelle konfiguration. Vælg **Gem** og **Kør** for at behandle ændringerne.

- **Opdater**: Opdaterer den valgte semantiske tilknytning med de nyeste data fra de objekter, der er en del af konfigurationen. Hvis du opdaterer en bestemt semantisk tilknytning, opdateres alle semantiske tilknytninger af samme type.

- **Omdøb**: Åbner en dialogboks, hvor du kan angive et andet navn til den valgte semantiske tilknytning. Vælg **Gem** for at anvende dine ændringer.

- **Slet**: Åbner en dialogboks for at bekræfte sletningen af den valgte semantiske tilknytning. Du kan også slette mere end én semantisk tilknytning på én gang ved at vælge de semantiske tilknytninger og sletteikonet. Bekræft sletningen ved at vælge **Slet**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
