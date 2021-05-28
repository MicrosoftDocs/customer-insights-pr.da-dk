---
title: Forbedring af samlede kundeprofiler
description: Du kan bruge egenskaber til at forbedre dine kundedata.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954480"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Forbedring af kundeprofiler (prøveversion)

Brug data fra kilder som f.eks. Microsoft og andre partnere til at forbedre kundedataene.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Hubside for forbedring":::

Hvis du målgruppeindsigt, kan du gå til **Data** > **Forbedring** for at arbejde sammen med forbedringsmuligheder.    
Du skal have bidragyder- eller administratortilladelser for at kunne oprette eller redigere forbedringer. Du kan finde flere oplysninger under [Tilladelser](permissions.md).

Under fanen **Opdag** kan du se følgende forbedringer:

- [Varemærker](enrichment-microsoft.md) leveret af Microsoft
- [Interesser](enrichment-microsoft.md) leveret af Microsoft
- [Udvidede adresser](enrichment-enhanced-addresses.md) leveret af Microsoft
- [Firmadata](enrichment-leadspace.md) leveret af Leadspace
- [Demografi](enrichment-experian.md) leveret af Experian
- [Lokationsdata](enrichment-here.md) leveret af HERE Technologies
- [Brugerdefineret data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)

Under fanen **Mine forbedringer** kan du se de forbedringer, du har konfigureret, og redigere deres egenskaber.

## <a name="manage-existing-enrichments"></a>Administrer eksisterende forbedringer

Gå til **Mine forbedringer** for at få vist alle konfigurerede forbedringer. Hver forbedring repræsenteres som en række, der indeholder yderligere oplysninger om forbedringen.

Vælg en forbedring for at få vist de tilgængelige indstillinger. Du kan også vælge ellipsen (...) på et listeelement for at se indstillingerne.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Indstillinger til administration af forbedringer på listen over forbedringer":::

- **Vis** oplysninger om forbedringer med antallet af forbedrede kundeprofiler.
- **Rediger** konfigurationen af forbedringen.
- **Kør** forbedringen for at opdatere kundeprofiler med de nyeste data.
- **Deaktiver** en eksisterende forbedring for at forhindre, at den opdateres automatisk i alle planlagte opdateringer. Data fra den seneste vellykkede opdatering vil fortsat være tilgængelige. **Aktivér** en inaktiv forbedring, hvis du vil genstarte automatisk opdatering for hver planlagt opdatering.
- Vil du **slette** en forbedring?

Du kan køre eller deaktivere flere forbedringer på én gang ved at vælge dem på listen. Indstillingerne Vis og Rediger er ikke tilgængelige som massehandlinger og kan kun bruges med én forbedring ad gangen.

## <a name="enrichments-and-connections"></a>Forbedringer og forbindelser

Konfigurationer fra tredjeparter konfigureres ved hjælp af [forbindelser](connections.md), som en administrator konfigurerer med legitimationsoplysninger og giver samtykke til dataoverførsler. Forbindelsen kan derefter bruges af både administratorer og bidragydere til at konfigurere forbedringer.  

## <a name="multiple-enrichments-of-the-same-type"></a>Flere forbedringer af samme type

Det objekt, der skal forbedres, angives under forbedringskonfigurationen med mulighed for forbedring, som gør det muligt kun at forbedre et undersæt af dine profiler. Du kan for eksempel forbedre data for et bestemt segment. Du kan konfigurere flere forbedringer af samme type og genbruge den samme forbindelse. Nogle forbedringer har grænser for antallet af forbedringer af samme type, der kan oprettes. Grænseværdierne og den aktuelle brug kan ses på siden **Forbedring**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
