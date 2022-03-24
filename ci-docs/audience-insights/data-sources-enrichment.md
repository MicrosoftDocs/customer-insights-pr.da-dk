---
title: Kilde til berigelse af datakilde
description: Forbedre datakilder, inden du gennemgår processen til samling af data.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 56f6a8ad20224922f9968f0ad3b6a0e0a400214b
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376572"
---
# <a name="enrichment-for-data-sources-preview"></a>Forbedring til datakilder (forhåndsversion)

Brug data fra kilder som Microsoft og andre partnere til at forbedre dine kundedata før datasamling. Datakilde hjælper dig med at opnå højere datafuldstændighed -kvalitet, der kan være med til at opnå bedre resultater, når du har samlet dataene. Hvis du f.eks. bruger et normaliseret og standardiseret format til adresser, øges kvaliteten af resultaterne af overensstemmelsen. Du kan se en liste over understøttede valgmuligheder i [understøttede datakildevalgmuligheder](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Forbedre en datakilde

Du skal have bidragyder- eller administratortilladelse til at oprette eller redigere forbedringer. Du kan finde flere oplysninger under [Tilladelser](permissions.md).  

1. Gå til **Data** > **Samle**. Vælg det objekt, du vil forbedre, og vælg én attribut som primær nøgle for objektet. Du kan finde flere oplysninger under [Vælg primær nøgle](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Gå til **Data** > **Datakilder**.
 
1. Vælg den lodrette ellipse ud for den datakilde, du vil forbedre, og vælg **Forbedre**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="-datakildeforbedringsside":::

   Under fanen **Opdag** vises de [understøttede datakildeindstillinger for valgmuligheder](#supported-data-source-enrichments).

1. Vælg **Forbedre mine data** for at konfigurere en datakildeforbedring. Output-objektnavnet udfyldes automatisk.

## <a name="supported-data-source-enrichments"></a>Understøttede datakildeforbedringer

Følgende forbedringer er i øjeblikket tilgængelig for datakilder. Gennemgå de detaljerede trin til forbedringen for at få mere at vide om, hvordan du konfigurerer den.

- [Udvidede adresser](enrichment-enhanced-addresses.md)
- [Forbedrede virksomhedsdata](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Administrere eksisterende datakildeforbedringer

Gå til fanen **Mine forbedringer** for at se alle konfigurerede forbedringer.

Vælg en valgmuligheder for at se de tilgængelige indstillinger. Du kan også vælge ellipsen (...) på et listeelement for at se indstillingerne. Hvis du har konfigureret flere forskellige indstillinger, kan du bruge søgefeltet til at finde det hurtigt.

Du kan få vist, redigere, køre eller slette en datakildeforbedring. Du kan finde flere oplysninger under [Administrere eksisterende forbedringer](enrichment-hub.md).
