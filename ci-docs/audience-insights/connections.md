---
title: Forbindelser til andre tjenester fra Customer Insights.
description: Dele data med andre tjenester.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304965"
---
# <a name="connections-preview-overview"></a>Oversigt over forbindelser (forhåndsversion)

Forbindelser er nøglen til at gøre det muligt at dele data til og fra Customer Insights. Hver forbindelse opretter datadeling med en bestemt tjeneste. Forbindelser er grundlaget for [konfiguration af tredjepartseksporter](enrichment-hub.md) og [konfiguration af eksport](export-destinations.md). Den samme forbindelse kan bruges flere gange. En forbindelse til Dynamics 365 Marketing fungerer f.eks. i forbindelse med flere eksporter, og én forbindelse i Leadspace kan bruges til flere forbindelser.

Gå til **Administrator** > **Forbindelser** for at oprette og få vist forbindelser.

Under fanen **Forbindelser** vises alle aktive forbindelser. På listen vises en række for hver forbindelse. 

Få en hurtig oversigt, en beskrivelse, og find ud af, hvad du kan gøre med hver enkelt udvidelsesindstilling, under fanen **Opdag**.

### <a name="exports"></a>Eksport

Det er kun administratorer, der kan konfigurere nye forbindelser, men de kan give bidragydere adgang til at bruge eksisterende forbindelser. Administratorer kontrollerer, hvor dataene kan gå hen, og bidragyderne definerer nyttelasten og hyppigheden af deres behov. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Forbedringer

Det er kun administratorer, der kan konfigurere nye forbindelser, men de oprettede forbindelser er altid tilgængelige for både administratorer og bidragydere. Administratorer styrer legitimationsoplysninger og giver samtykke til dataoverførsler. Forbindelserne kan derefter bruges af både administratorer og bidragydere til at hjælpe dig.

## <a name="add-a-new-connection"></a>Tilføj en ny forbindelse

Hvis du vil tilføje forbindelser, skal du have [administratortilladelser](permissions.md). Hvis du opretter forbindelse til andre Microsoft-tjenester, antages det, at begge tjenester findes i den samme organisation.

1. Gå til **Administrator** > **Forbindelser** (forhåndsversion).

1. Gå til fanen **Forbindelser**.

1. Vælg **Tilføj forbindelse** for at oprette en ny forbindelse. Vælg i rullemenuen, hvilken type forbindelse du vil oprette.

1. Angiv de nødvendige oplysninger i ruden **Konfigurer forbindelse**. 
   1. **Visningsnavn** og forbindelsestype beskriver en forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for denne forbindelse.
   1. De nøjagtige felter afhænger af, hvilken tjeneste du opretter forbindelse til. Du kan få mere at vide om detaljer om en bestemt forbindelse ved at skrive artiklen om måltjenesten.

1. Vælg **Gem** for at oprette forbindelsen.

Du kan også vælge **Konfigurer** i et område på fanen **Udforsk**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Tillad bidragydere at bruge en forbindelse til eksport

Når du konfigurerer eller redigerer en eksportforbindelse, vælger du, hvilke brugere der skal have tilladelse til at bruge denne specifikke forbindelse til at definere [eksport](export-destinations.md). Som standard er en forbindelse tilgængelig for brugere med en administratorrolle. Du kan ændre denne indstilling under **Vælg, hvem der kan bruge denne forbindelse**, og give brugere med bidragyder mulighed for at bruge denne forbindelse.

- Bidragydere kan ikke få vist eller redigere forbindelsen. De kan kun se visningsnavn og dens type, når de opretter en eksport.
- Ved at dele en forbindelse giver du bidragydere tilladelse til at bruge en forbindelse. Bidragydere kan se delte forbindelser, når de konfigurerer eksport. De kan administrere alle de eksporter, der bruger denne specifikke forbindelse.
- Du kan ændre denne indstilling, samtidig med at du beholder de eksporter, som allerede er defineret af bidragydere.

## <a name="edit-a-connection"></a>Redigere en forbindelse

1. Gå til **Administrator** > **Forbindelser** (forhåndsversion).

1. Gå til fanen **Forbindelser**.

1. Vælg den lodrette ellipse for den forbindelse, du vil redigere.

1. Vælg **Rediger**.

1. Opdatér de værdier, du vil opdatere, og vælg **Gem**.

## <a name="remove-a-connection"></a>Fjerne en forbindelse

Hvis den forbindelse, du fjerner, bruges af produkter eller eksport, skal du først ophæve eller fjerne dem. Dialogboksen Fjern fører dig til relevante produktoversigter eller eksporter. 

Fritliggende produkter og eksporter bliver inaktive. Du kan genaktivere dem ved at føje endnu en forbindelse til dem på siden [Forbedringer](enrichment-hub.md) eller [Eksport](export-destinations.md).

1. Gå til **Administrator** > **Forbindelser** (forhåndsversion).

1. Gå til fanen **Forbindelser**.

1. Vælg den lodrette ellipse for den forbindelse, du vil fjerne.

1. Vælg **Fjern** på rullelisten. En bekræftelsesdialogboks vises.

   1. Hvis der er forbindelser eller eksporter, skal du vælge knappen for at se, hvad der bruger forbindelsen.
      - **Eksport:** Du kan vælge enten at fjerne eller afbryde forbindelsen til eksporten for at kunne fjerne forbindelsen. Hvis en administrator vil afbryde forbindelsen til en eksport, kan den bruge handlingen **Afbryd** forbindelsen. Denne handling er tilgængelig for individuelle og flere valgte eksporter. Hvis du afbryder forbindelsen til eksportkonfigurationen, men den køres først, når der er føjet en anden forbindelse til den.
      - **Forbedringer:** Du kan vælge enten at fjerne eller deaktivere forbedringerne for at kunne fjerne forbindelsen. 
   1. Når forbindelsen ikke har flere afhængigheder, skal du gå tilbage til **Administrator** > **Forbindelser** og prøve at fjerne forbindelsen igen.

1. Bekræft sletningen ved at vælge **Fjern**.

