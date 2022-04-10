---
title: Eksport af Customer Insights-data til Iterable
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4de499fcc4a5a0dcc2dfd3bae02913c81a59647b
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524139"
---
# <a name="export-segment-lists-to-iterable-preview"></a>Eksportér segmentlister til Iterable (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til Iterable, og brug dem til marketingaktiviteter.

## <a name="prerequisites"></a>Forudsætninger

-   Du har en [Iterable-konto](https://iterable.com/) og tilhørende administratorlegitimationsoplysninger.
-   Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Eksport til Iterable er begrænset til segmenter.
- Eksport af op til 1 million kundeprofiler til Iterable kan tage op til 30 minutter at fuldføre. 
- Antallet af kundeprofiler, som du kan eksportere til Iterable, er afhængig og begrænset af din kontrakt med Iterable.

## <a name="set-up-connection-to-iterable"></a>Konfigurer forbindelsen til Iterable

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Iterable** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv din [Iterable API-nøgle](https://support.iterable.com/hc/en-us/articles/360043464871), så du fortsat kan logge på. 

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til Iterable.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse fra Iterable-sektionen i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

3. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**. Det kræves, hvis du vil eksportere segmenter til Iterable. Den liste, der er oprettet i Iterable, modtager nøjagtigt det samme navn som dit segmentnavn i Dynamics 365 Customer Insights.

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights til at overføre data til Iterable, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personoplysninger. Microsoft kan overføre sådanne data efter dine instruktioner, men du er ansvarlig for at sikre, at Iterable overholder alle forpligtelser i forbindelse med sikkerhed eller beskyttelse af personlige oplysninger. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.
