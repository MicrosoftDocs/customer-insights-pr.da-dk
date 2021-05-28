---
title: Eksportér Customer Insights-data til Marketo
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059309"
---
# <a name="export-segments-to-marketo-preview"></a>Eksportér segmenter til Marketo (forhåndsversion)

Eksportér segmenter fra de samlede brugerprofiler til at generere kampagner, levere e-mailmarketing og bruge bestemte grupper af kunder med Marketo.

## <a name="prerequisites-for-connection"></a>Forudsætninger for forbindelse

-   Du har en [Marketo-konto](https://login.marketo.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Der findes eksisterende lister i Marketo og de tilsvarende id'er. Du kan finde flere oplysninger i [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Du har [konfigureret segmenter](segments.md).
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 1000000 profiler pr. eksport til Marketo.
- Eksport til Marketo er begrænset til segmenter.
- Eksport af segmenter med i alt 1000000 profiler kan tage op til tre timer. 
- Antallet af profiler, du kan eksportere til Marketo, er afhængige og begrænsede i kontrakten med Marketo.

## <a name="set-up-connection-to-marketo"></a>Konfigurer forbindelsen til Marketo.

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Marketo** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv dit **[Marketo-klient-ID, klientens hemmelige og resterende værtsnavnsslutpunkt](https://developers.marketo.com/rest-api/authentication/)**. Værtsnavn for REST-slutpunkt er kun værtsnavnet uden `https://`. Eksempel: `xyz-abc-123.mktorest.com`. 

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og kompatibilitet**, og vælg **Opret forbindelse** for at initialisere forbindelsen til Marketo.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen Marketo i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Angiv dit **[Marketo-liste-id](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. Liste-id'et er en rent numerisk værdi. Hvis f.eks. Marketo-liste-id'et er ST12345A7, skal du fjerne tegnet før og efter tallene og angive `12345`. 

1. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. 

1. Du kan også eksportere **Fornavn**, **Efternavn**, **By**, **Land** og **Land/Område** for at oprette mere personlige mails. Vælg **Tilføj attribut** for at tilknytte disse felter.

1. Vælg de segmenter, du vil eksportere. Du kan eksportere op til 1000000 kundeprofiler i alt til Marketo.

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). I Marketo kan du nu finde dine segmenter under [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Marketo, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Marketo overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
