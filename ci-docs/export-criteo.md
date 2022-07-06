---
title: Eksportere segmenter til Criteo (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081127"
---
# <a name="export-segments-to-criteo-preview"></a>Eksportere segmenter til Criteo (forhåndsversion)

Eksportér segmenter af samlede kundeprofiler for at generere kampagner, levere mailmarketing og bruge bestemte kundegrupper med Criteo.

## <a name="prerequisites-for-connection"></a>Forudsætninger for forbindelse

-   Du har en [Criteo Dynamics Retargeting-konto](https://www.criteo.com/login/) og tilhørende administratorlegitimationsoplysninger.
-   Du har [konfigureret segmenter](segments.md).
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 1 million kundeprofiler pr. eksport til Criteo.
- Eksport til Criteo er begrænset til segmenter.
- Eksport af segmenter med i alt 1 million kundeprofiler kan tage op til 30 minutter. 
- Antallet af kundeprofiler, som du kan eksportere til Criteo, er afhængig og begrænset af din kontrakt med Criteo.

## <a name="set-up-connection-to-criteo"></a>Konfigurer forbindelsen til Criteo

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Criteo** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**, og vælg **Opret forbindelse** for at initialisere forbindelsen til Criteo.

1. Vælg **Godkend med Criteo**, og angiv brugernavnet og legitimationsoplysningerne for administrator for Criteo. 

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse fra Criteo-sektionen i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig. 

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**. 

1. Du kan også eksportere **Annoncør-id** og **Navn**

1. Vælg de segmenter, du vil eksportere. 

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights til at overføre data til Criteo, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personoplysninger. Microsoft kan overføre sådanne data efter dine instruktioner, men du er ansvarlig for at sikre, at Criteo overholder alle forpligtelser i forbindelse med sikkerhed eller beskyttelse af personlige oplysninger. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](includes/footer-banner.md)]
