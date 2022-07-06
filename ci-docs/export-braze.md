---
title: Eksportere segmenter til Braze (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081110"
---
# <a name="export-segments-to-braze-preview"></a>Eksportere segmenter til Braze (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til Braze, og brug dem til marketingaktiviteter.

## <a name="prerequisites"></a>Forudsætninger

- En [Braze-konto](https://www.braze.com/) og tilhørende administratorlegitimationsoplysninger.
- Eksisterende [segmenter i Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Konfigurerede segmenter](segments.md) i Customer Insights.
- Ensartede kundeprofiler i de eksporterede segmenter indeholder et felt, der repræsenterer en mailadresse og et Braze-kunde-id.

## <a name="known-limitations"></a>Kendte begrænsninger

- Eksport til Braze er begrænset til segmenter.
- Eksport af op til 1 million kundeprofiler til Braze kan tage op til 40 minutter at fuldføre.
- Antallet af kundeprofiler, som du kan eksportere til Braze, er afhængig og begrænset af din kontrakt med Braze.

## <a name="set-up-connection-to-braze"></a>Konfigurer forbindelsen til Braze

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Braze** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv din [Braze API-nøgle](https://www.braze.com/docs/api/basics/), så du fortsat kan logge på.

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til Braze.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse fra Braze-sektionen i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette afsnit, er der ingen forbindelser af denne type tilgængelige for dig.  

1. Tilføj **Vis navn** til din eksport.

1. Tilføj API-id'et for det Braze-segment, du vil eksportere til, i feltet **Braze Segment API Identifier**. Du kan finde id'et i segmentoplysningerne på Braze-platformen.

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**. Vælg det felt, der svarer til kundens Braze-id i feltet feltet **Kunde-id**. Det er nødvendigt at eksportere segmenter til Braze. Du kan evt. vælge flere felter.

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights til at overføre data til Braze, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personoplysninger. Microsoft kan overføre sådanne data efter dine instruktioner, men du er ansvarlig for at sikre, at Braze overholder alle forpligtelser i forbindelse med sikkerhed eller beskyttelse af personlige oplysninger. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.
