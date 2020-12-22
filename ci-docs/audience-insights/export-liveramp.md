---
title: LiveRamp-connector
description: Få mere at vide om, hvordan du eksporterer data til LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667177"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp&reg;-forbindelse (forhåndsvisning)

Aktivér dine data i LiveRamp for at oprette forbindelse til mere end 500 platforme på tværs af digitale, sociale og TV-økosystemer. Arbejd med dine data i LiveRamp for at målrette, undertrykke og tilpasse reklamekampagner.

## <a name="prerequisites"></a>Forudsætninger

- Du skal have et LiveRamp-abonnement for at kunne bruge denne connector.
- Hvis du vil have et abonnement, skal du [kontakte LiveRamp](https://liveramp.com/contact/) direkte. [Få mere at vide om LiveRamp-onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Oprette forbindelse til LiveRamp

1. Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.

1. Vælg **Konfigurer** i feltet **LiveRamp**.

1. Giv din destination et genkendeligt navn i feltet **Vist navn**.

1. Angiv et **Brugernavn** og en **Adgangskode** til din LiveRamp Secure FTP (SFTP)-konto.
Disse legitimationsoplysninger kan være forskellige fra dine legitimationsoplysninger for LiveRamp-onboarding.

1. Vælg **Bekræft** for at teste forbindelsen til LiveRamp.

1. Når bekræftelsen er fuldført, skal du give dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**.

1. Vælg **Næste** for at konfigurere LiveRamp Connector.

## <a name="configure-the-connector"></a>Konfigurer connectoren

1. I feltet **Vælg din nøgle-identifikator** vælg **Email**, **Navn og adresse** eller **Telefon** som du vil sende til LiveRamp i forbindelse med identifikation.

1. Tilknyt de tilsvarende attributter fra det samlede kundeobjekt til den valgte nøgle-identifikator.

1. Vælg **Tilføj attribut** for at tilknytte yderligere attributter, der skal sendes til LiveRamp.

   > [!TIP]
   > Hvis du sender flere nøgle-identifikatorattributter til LiveRamp, får du sandsynligvis en højere match-rate.

1. Vælg de segmenter, du vil eksportere til LiveRamp.

1. Vælg **Gem**.

> [!div class="mx-imgBorder"]
> ![LiveRamp connector med attributtilknytning](media/export-liveramp-segments.png "LiveRamp connector med attributtilknytning")

## <a name="export-the-data"></a>Eksportér dataene

Eksporten starter kort tid efter, hvis alle forudsætninger for eksport er opfyldt. Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).
Når eksporten er fuldført, kan du logge på LiveRamp-onboarding for at aktivere og distribuere dine data.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Liveramp, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Liveramp overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.