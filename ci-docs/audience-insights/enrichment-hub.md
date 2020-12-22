---
title: Forbedring af samlede kundeprofiler
description: Du kan bruge egenskaber til at forbedre dine kundedata.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667087"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Forbedring af kundeprofiler (prøveversion)

Brug data fra kilder som f.eks. Microsoft og andre partnere til at forbedre kundedataene.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Hubside for forbedring":::

Hvis du målgruppeindsigt, kan du gå til **Data** > **Forbedring** for at arbejde sammen med forbedringsmuligheder.    
Du skal have bidragyder- eller administratortilladelser for at kunne oprette eller redigere forbedringer. Du kan finde flere oplysninger under [Tilladelser](permissions.md).

Under fanen **Opdag** kan du se følgende forbedringer:

- [Varemærker](enrichment-microsoft-graph.md) leveret af Microsoft Graph
- [Interesser](enrichment-microsoft-graph.md) leveret af Microsoft Graph
- [Firmadata](enrichment-leadspace.md) leveret af Leadspace
- [Demografi](enrichment-experian.md) leveret af Experian
- [Lokationsdata](enrichment-here.md) leveret af HERE Technologies
- [Brugerdefineret data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)

Under fanen **Mine forbedringer** kan du se de forbedringer, du har konfigureret, og redigere deres egenskaber.

## <a name="manage-existing-enrichments"></a>Administrer eksisterende forbedringer

Gå til **Mine forbedringer** for at få vist alle konfigurerede forbedringer. Hver forbedring repræsenteres som en række, der indeholder yderligere oplysninger om forbedringen.

Vælg en forbedring for at få vist de tilgængelige indstillinger. Du kan også vælge ellipsen (...) på et listeelement for at få vist indstillingerne.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Indstillinger til administration af forbedringer på listen over forbedringer":::

- **Vis** oplysninger om forbedringer med antallet af forbedrede kundeprofiler.
- **Rediger** konfigurationen af forbedringen.
- **Kør** forbedringen for at opdatere kundeprofiler med de nyeste data.
- **Deaktiver** en eksisterende forbedring for at forhindre, at den opdateres automatisk i alle planlagte opdateringer. Data fra den seneste vellykkede opdatering vil fortsat være tilgængelige. **Aktivér** en inaktiv forbedring, hvis du vil genstarte automatisk opdatering for hver planlagt opdatering.
- Vil du **slette** en forbedring?

Du kan køre eller deaktivere flere forbedringer på én gang ved at vælge dem på listen. Indstillingerne Vis og Rediger er ikke tilgængelige som massehandlinger og kan kun bruges med én forbedring ad gangen.
