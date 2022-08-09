---
title: Forbedring til datakilder (forhåndsversion)
description: Forbedre datakilder, inden du gennemgår processen til samling af data.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207176"
---
# <a name="enrichment-for-data-sources-preview"></a>Forbedring til datakilder (forhåndsversion)

Brug data fra kilder som Microsoft og andre partnere til at forbedre dine kundedata før datasamling. Datakilde hjælper dig med at opnå højere datafuldstændighed -kvalitet, der kan være med til at opnå bedre resultater, når du har samlet dataene. Hvis du f.eks. bruger et normaliseret og standardiseret format til adresser, øges kvaliteten af resultaterne af overensstemmelsen. Du kan se en liste over understøttede valgmuligheder i [understøttede datakildevalgmuligheder](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Forbedre en datakilde

Du skal have bidragyder- eller administrator-[tilladelser](permissions.md) til at oprette eller redigere forbedringer.  

1. Gå til **Data** > **Samle**. Vælg det objekt, du vil forbedre, og vælg én attribut som [primær nøgle](map-entities.md#select-primary-key-and-semantic-type-for-attributes) for objektet.

1. Gå til **Data** > **Datakilder**.

1. Vælg den lodrette ellipse (&vellip;) ud for den datakilde, du vil forbedre, og vælg **Forbedre**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Siden Datakilder med Forbedr fremhævet":::

   Under fanen **Opdag** vises de [understøttede datakildeindstillinger for valgmuligheder](#supported-data-source-enrichments).

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="-datakildeforbedringsside":::

1. Vælg **Forbedre mine data** for at konfigurere en datakildeforbedring. Output-objektnavnet udfyldes automatisk.

## <a name="supported-data-source-enrichments"></a>Understøttede datakildeforbedringer

Følgende forbedringer er i øjeblikket tilgængelig for datakilder. Gennemgå de detaljerede trin til forbedringen for at få mere at vide om, hvordan du konfigurerer den.

- [Udvidede adresser](enrichment-enhanced-addresses.md)
- [Forbedrede virksomhedsdata](enrichment-enhanced-company-data.md)
- [Identitetsdata fra LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Administrere eksisterende datakildeforbedringer

Gå til **Data** > **Forbedring**. Under fanen **Mine forbedringer** kan du se de konfigurerede forbedringer, deres status, antallet af forbedrede kunder og den sidste gang dataene blev opdateret. Du kan sortere listen over forbedringer efter en hvilken som helst kolonne eller bruge søgefeltet til at søge efter de ønsker, der skal håndteres.

Vælg en valgmuligheder for at se de tilgængelige indstillinger. Du kan også vælge den lodrette ellipse (&vellip;) på et listeelement for at se indstillingerne.

Du kan få vist, redigere, køre eller slette en datakildeforbedring. Du kan finde flere oplysninger under [Administrere eksisterende forbedringer](enrichment-hub.md#manage-existing-enrichments).
