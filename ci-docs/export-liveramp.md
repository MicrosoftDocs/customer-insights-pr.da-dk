---
title: Eksportér segmenter til LiveRamp (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporten til LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196709"
---
# <a name="export-segments-to-liverampreg-preview"></a>Eksportér segmenter til LiveRamp&reg; (forhåndsversion)

Aktivér dine data i LiveRamp for at oprette forbindelse til over 500 platforme på tværs af digitale, sociale og tv-medier. Arbejd med dine data i LiveRamp for at målrette, undertrykke og tilpasse reklamekampagner.

## <a name="prerequisites"></a>Forudsætninger

- Du skal have et LiveRamp-abonnement for at kunne bruge denne connector. Hvis du vil have et abonnement, skal du [kontakte LiveRamp](https://liveramp.com/contact/) direkte. [Få mere at vide om LiveRamp-onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Kendte begrænsninger

- Eksporten af LiveRamp bruger en SFTP-eksport. SFTP-destinationer bag firewalls understøttes i øjeblikket ikke.
- Hvis du bruger en SSH-nøgle til godkendelse, skal du sørge for at [oprette den private nøgle](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) som PEM eller SSH.COM format. Hvis du bruger Putty, kan du konvertere din private nøgle ved at eksportere den som Open SSH. Følgende privat nøgle-formater understøttes:
  - RSA i OpenSSL-PEM- og ssh.com format
  - DSA i OpenSSL-PEM- og ssh.com format
  - ECDSA 256/384/521 i OpenSSL PEM-format
  - ED25519 og RSA i OpenSSH-nøgleformat
- Kørslen af en eksport afhænger af systemets ydeevne. Vi anbefaler to CPU-kerner og 1 GB hukommelse som minimal konfiguration af serveren.
- Det kan tage 90 minutter at eksportere objekter med op til 100 millioner kundeprofiler, når du bruger den anbefalede minimale konfiguration af to CPU-kerner og 1 GB hukommelse.
- Antallet af kundeprofiler (eller data), du kan eksportere til LiveRamp, afhænger af din kontrakt med LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Konfigurer forbindelsen til LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **LiveRamp**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vælg, om du vil godkende via SSH eller brugernavn/adgangskode for din forbindelse, og angiv de nødvendige detaljer.

1. Vælg **Bekræft** for at teste forbindelsen til LiveRamp.

1. Efter fuldført verifikation skal du gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen LiveRamp i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. I feltet **Forbind data** vælg **Email**, **Navn og adresse** eller **Telefon** som du vil sende til LiveRamp i forbindelse med identifikation.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="LiveRamp connector med attributtilknytning.":::

1. Tilknyt de tilhørende attributter fra objektet *Kunde* for det valgte nøgle-id.

1. Vælg **Tilføj attribut** for at tilknytte flere attributter, der skal sendes til LiveRamp.

   > [!TIP]
   > Hvis du sender flere nøgle-identifikatorattributter til LiveRamp, får du sandsynligvis en højere match-rate.

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
