---
title: Eksportér Customer Insights-data til SFTP-værter
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til en SFTP-vært.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643496"
---
# <a name="connector-for-sftp-preview"></a>Connector til SFTP (prøveversion)

Brug dine kundedata i tredjepartsprogrammer ved at eksportere dem til en SFTP-vært.

## <a name="prerequisites"></a>Forudsætninger

- Tilgængelighed af en SFTP-vært og tilhørende legitimationsoplysninger.

## <a name="connect-to-sftp"></a>Forbindelse til SFTP

1. Gå til **Adminstration** > **Eksportdestinationer**.

1. Vælg **Konfigurer** under **SFTP**.

1. Giv din destination et genkendeligt navn i feltet **Vist navn**.

1. Angiv et **Brugernavn**, en **adgangskode** og et **værtsnavn** til din SFTP-konto. Eksempel: Hvis SFTP-serverens rodmappe er/root/mappe, og du vil have, at dataene skal eksporteres til/root/mappe/ci_export_destination_folder, skal værten være sftp://<server_address>/ci_export_destination_folder".

1. Vælg **Bekræft** for at teste forbindelsen.

1. Når bekræftelsen er fuldført, skal du vælge, om du vil eksportere dataene **Pakket** eller **Ikke-pakket** og vælge **feltseparator** for de eksporterede filer.

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Næste** for at begynde at konfigurere eksporten.

## <a name="configure-the-connection"></a>Konfigurere forbindelsen

1. Vælg de **kundeattributter**, der skal eksporteres. Du kan eksportere en eller flere attributter.

1. Vælg **Næste**.

1. Vælg de segmenter, du vil eksportere.

1. Vælg **Gem**.

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data via SFTP, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at eksportdestinationen overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.
