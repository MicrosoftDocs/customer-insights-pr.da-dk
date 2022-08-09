---
title: Eksportere data fra SFTP-værter (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til en SFTP-lokation.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207222"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Eksportere data til SFTP-værter (forhåndsversion)

Brug dine kundedata i tredjepartsprogrammer ved at eksportere dem til en SFTP (Secure File Transfer Protocol)-lokation.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Forudsætninger

- Tilgængeligheden af en SFTP-vært og de tilhørende legitimationsoplysninger.

## <a name="known-limitations"></a>Kendte begrænsninger

- SFTP-destinationer bag firewalls understøttes i øjeblikket ikke.
- Kørslen af en eksport afhænger af systemets ydeevne. Vi anbefaler to CPU-kerner og 1 GB hukommelse som minimal konfiguration af serveren.
- Det kan tage 90 minutter at eksportere objekter med op til 100 millioner kundeprofiler, når du bruger den anbefalede minimale konfiguration af to CPU-kerner og 1 GB hukommelse.
- Hvis du bruger en SSH-nøgle til godkendelse, skal du sørge for at [oprette den private nøgle](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) som PEM eller SSH.COM format. Hvis du bruger Putty, kan du konvertere din private nøgle ved at eksportere den som Open SSH. Følgende privat nøgle-formater understøttes:
  - RSA i OpenSSL-PEM- og ssh.com format
  - DSA i OpenSSL-PEM- og ssh.com format
  - ECDSA 256/384/521 i OpenSSL PEM-format
  - ED25519 og RSA i OpenSSH-nøgleformat

## <a name="set-up-connection-to-sftp"></a>Konfigurer forbindelse til SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **SFTP**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Vælg, om du vil godkende via SSH eller brugernavn/adgangskode for din forbindelse, og angiv de nødvendige detaljer. Hvis du bruger en SSH-nøgle til godkendelse, skal du sørge for at [oprette den private nøgle](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) som PEM eller SSH.COM format. Hvis du bruger Putty, kan du konvertere din private nøgle ved at eksportere den som Open SSH. Følgende privat nøgle-formater understøttes:
   - RSA i OpenSSL-PEM- og ssh.com format
   - DSA i OpenSSL-PEM- og ssh.com format
   - ECDSA 256/384/521 i OpenSSL PEM-format
   - ED25519 og RSA i OpenSSH-nøgleformat

1. Vælg **Bekræft** for at teste forbindelsen.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen SFTP i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Vælg, om du vil eksportere dataene **Gzippet** eller **Pakket ud** og **feltseparator** for de eksporterede filer.

1. Markér de objekter, f.eks. segmenter, du vil eksportere.

   > [!NOTE]
   > Hvert enkelt valgt objekt opdeles i op til maks. fem outputfiler, når de eksporteres.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Eksport af objekter, der indeholder en stor mængde data, kan føre til flere CSV-filer i den samme mappe for hver eksport. Opdeling af eksport sker af ydelseshensyn for at minimere den tid, det tager at udføre en eksport.

[!INCLUDE [footer-include](includes/footer-banner.md)]
