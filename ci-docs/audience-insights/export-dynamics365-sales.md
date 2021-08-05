---
title: Eksportér Customer Insights-data til Dynamics 365 Sales
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f11ab189117da5bcc1aee843b73962ec6615e82
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692336"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Brug segmenter i Dynamics 365 Sales (forhåndsversion)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Brug dine kundedata til at oprette marketinglister, følge op på arbejdsprocesser og udsende kampagner med Dynamics 365 Sales.

## <a name="prerequisite-for-connection"></a>Forudsætning for forbindelse

1. Kontaktposter skal være til stede i Dynamics 365 Sales, før du kan eksportere et segment fra Customer Insights til Sales. Læs mere om, hvordan du kontakter i [Dynamics 365 Sales ved hjælp af Microsoft Dataverse](connect-power-query.md).

   > [!NOTE]
   > Hvis du eksporterer segmenter fra målgruppeindsigt til Sales, oprettes der ikke nye kontaktposter i Sales-forekomsterne. Kontaktpersonposterne fra Sales skal være direkte målgruppeindsigt og bruges som en datakilde. De skal også inkluderes i den samlede brugerdefinerede enhed for at knytte kunde-ID'er til kontakt-ID'er, før segmenter kan eksporteres.

## <a name="set-up-the-connection-to-sales"></a>Konfigurer forbindelsen til Sales

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Dynamics 365 Sales** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv din organisations URL-adresse for Sales i feltet **Serveradresse**.

1. I sektionen **Serveradministratorkonto** vælg **Log på** og vælg en Dynamics 365 Sales-konto.

1. Knyt et kunde-ID-felt til Dynamics 365-kontakt-id.

1. Vælg **Gem** for at fuldføre forbindelsen. 

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen Dynamics 365 Sales i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Vælg en eller flere segmenter.

1. Vælg **Gem**

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
