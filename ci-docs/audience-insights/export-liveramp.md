---
title: LiveRamp-connector
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporten til LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: f9a0a88fb58897e4d279c181f4cdb4f6c852da60
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618928"
---
# <a name="export-segments-to-liverampreg-preview"></a>Eksportér segmenter til LiveRamp&reg; (forhåndsversion)

Aktivér dine data i LiveRamp for at oprette forbindelse til over 500 platforme på tværs af digitale, sociale og tv-medier. Arbejd med dine data i LiveRamp for at målrette, undertrykke og tilpasse reklamekampagner.

## <a name="prerequisites-for-a-connection"></a>Forudsætninger for en forbindelse

- Du skal have et LiveRamp-abonnement for at kunne bruge denne connector.
- Hvis du vil have et abonnement, skal du [kontakte LiveRamp](https://liveramp.com/contact/) direkte. [Få mere at vide om LiveRamp-onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Konfigurer forbindelsen til LiveRamp

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **LiveRamp** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv et **Brugernavn** og en **Adgangskode** til din LiveRamp Secure FTP (SFTP)-konto.
Disse legitimationsoplysninger kan være forskellige fra dine legitimationsoplysninger for LiveRamp-onboarding.

1. Vælg **Bekræft** for at teste forbindelsen til LiveRamp.

1. Når bekræftelsen er fuldført, skal du give dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen LiveRamp i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. I feltet **Vælg din nøgle-identifikator** vælg **Email**, **Navn og adresse** eller **Telefon** som du vil sende til LiveRamp i forbindelse med identifikation.
   > [!div class="mx-imgBorder"]
   > ![LiveRamp connector med attributtilknytning.](media/export-liveramp-segments.png "LiveRamp connector med attributtilknytning")

1. Tilknyt de tilhørende attributter fra objektet *Kunde* for det valgte nøgle-id.

1. Vælg **Tilføj attribut** for at tilknytte flere attributter, der skal sendes til LiveRamp.

   > [!TIP]
   > Hvis du sender flere nøgle-identifikatorattributter til LiveRamp, får du sandsynligvis en højere match-rate.

1. Vælg de segmenter, du vil eksportere til LiveRamp.

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Liveramp, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Liveramp overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
