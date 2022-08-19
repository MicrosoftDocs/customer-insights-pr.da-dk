---
title: Oversigt over forbindelser (forhåndsversion)
description: Forbindelser til andre tjenester fra Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245504"
---
# <a name="connections-preview-overview"></a>Oversigt over forbindelser (forhåndsversion)

Forbindelser er nøglen til at gøre det muligt at dele data til og fra Customer Insights. Hver forbindelse opretter datadeling med en bestemt tjeneste. Brug forbindelser til [konfiguration af tredjepartsforbedringer](enrichment-hub.md) og [konfiguration af eksport](export-destinations.md). Den samme forbindelse kan bruges flere gange. En forbindelse til Dynamics 365 Marketing fungerer f.eks. i forbindelse med flere eksporter, og én forbindelse i Leadspace kan bruges til flere forbindelser.

## <a name="export-connections"></a>Eksportere forbindelser

Det er kun administratorer, der kan konfigurere nye forbindelser, men de kan [give bidragydere adgang](#allow-contributors-to-use-a-connection-for-exports) til at bruge eksisterende forbindelser. Administratorer kontrollerer, hvor dataene kan gå hen, og bidragyderne definerer nyttelasten og hyppigheden af deres behov.

## <a name="enrichment-connections"></a>Forbindelser til forbedring

Det er kun administratorer, der kan konfigurere nye forbindelser, men de oprettede forbindelser er altid tilgængelige for både administratorer og bidragydere. Administratorer styrer legitimationsoplysninger og giver samtykke til dataoverførsler. Forbindelserne kan derefter bruges af både administratorer og bidragydere til at hjælpe dig.

## <a name="add-a-new-connection"></a>Tilføj en ny forbindelse

### <a name="prerequisites"></a>Forudsætninger

- [Administratortilladelser](permissions.md)
- Andre Microsoft-tjenester findes i den samme organisation

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg den type forbindelse, du vil oprette. Du kan også vælge **Konfigurer** i et område på fanen **Udforsk**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Angiv de relevante oplysninger. De nøjagtige felter afhænger af, hvilken tjeneste du opretter forbindelse til. Du kan få mere at vide om detaljer om en bestemt forbindelse ved at skrive artiklen om måltjenesten.

1. Hvis du [bruger din egen Key Vault](use-azure-key-vault.md) til at gemme hemmeligheder, skal du aktivere **Brug Key Vault** og vælge hemmeligheden på listen.

1. Gennemse Beskyttelse af personlige data og overholdelse af angivne standarder, og vælg **Jeg accepterer**.

1. Vælg **Gem** for at oprette forbindelsen.

### <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du gør det muligt for Dynamics 365 Customer Insights at overføre data til tredjepart eller andre Microsoft-produkter, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder følsomme data som f.eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at tredjeparten overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).

Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne forbindelsen for at afslutte brugen af denne funktionalitet.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Tillad bidragydere at bruge en forbindelse til eksport

Når du konfigurerer eller redigerer en eksportforbindelse, vælger du, hvilke brugere der skal have tilladelse til at bruge denne specifikke forbindelse til at definere [eksport](export-destinations.md). Som standard er en forbindelse tilgængelig for brugere med en administratorrolle. Du kan ændre denne indstilling under **Vælg, hvem der kan bruge denne forbindelse**, og give brugere med bidragyder mulighed for at bruge denne forbindelse.

- Bidragydere kan ikke få vist eller redigere forbindelsen. De kan kun se visningsnavn og dens type, når de opretter en eksport.
- Ved at dele en forbindelse giver du bidragydere tilladelse til at bruge en forbindelse. Bidragydere kan se delte forbindelser, når de konfigurerer eksport. De kan administrere alle de eksporter, der bruger denne specifikke forbindelse.
- Du kan ændre denne indstilling, samtidig med at du beholder de eksporter, som allerede er defineret af bidragydere.

## <a name="manage-existing-connections"></a>Administrer eksisterende forbindelser

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg fanen **Forbedring** eller **Eksport** for at få vist en liste over forbindelser, der gør det lettere at arbejde med forbindelser eller eksportere forbindelser, forbindelsestypen, hvornår den blev oprettet, og hvem der har adgang. Du kan sortere listen over forbindelser efter enhver kolonne.

1. Vælg en forbindelse for at få vist tilgængelige handlinger.

   - **Rediger** connectoren.
   - [**Fjern**](#remove-a-connection) en forbindelse.

### <a name="remove-a-connection"></a>Fjerne en forbindelse

Hvis den forbindelse, du fjerner, bruges af forbedringer eller eksporter, skal du først ophæve eller fjerne dem. Dialogboksen Fjern fører dig til relevante produktoversigter eller eksporter.

> [!TIP]
> Deaktiverede forbedringer og fjernede eksporter bliver inaktive. Du kan genaktivere dem ved at føje endnu en forbindelse til dem på siden [Forbedringer](enrichment-hub.md) eller [Eksport](export-destinations.md).

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg fanen **Forbedring** eller **Eksporter**.

1. Vælg den forbindelse, du ønsker at fjerne.

1. Vælg **Fjern** på rullelisten. En bekræftelsesdialogboks vises.

   1. Hvis der er forbindelser eller eksporter, skal du vælge knappen for at se, hvad der bruger forbindelsen.
      - **Eksporter:** Vælg enten at **Fjerne** eksporten eller **Ophæve tilknytningen**. Hvis du afbryder forbindelsen bevares eksportkonfigurationen, men den køres først, når der er føjet en anden forbindelse til den.
      - **Forbedringer:** Vælg enten **Slet** eller **Deaktiver** forbedringerne.
   1. Når forbindelsen ikke har flere afhængigheder, skal du gå tilbage til **Administrator** > **Forbindelser** og prøve at fjerne forbindelsen igen.

1. Bekræft sletningen ved at vælge **Fjern**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Konfigurere forbindelser med hemmeligheder, der administreres af din egen Key Vault

Nogle forbindelser har brug for hemmeligheder som API-nøgler eller adgangskoder. Nogle forbindelser understøtter hemmeligheder, der er gemt i din egen Key Vault. Få mere at vide om understøttede forbindelser, og hvordan du konfigurerer [din egen Key Vault til Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
