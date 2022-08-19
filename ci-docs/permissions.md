---
title: Tildele brugertilladelser
description: Få mere at vide om tilladelser og brugerroller.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245412"
---
# <a name="assign-user-permissions"></a>Tildele brugertilladelser

Adgang til Customer Insights er begrænset til brugere i organisationen, der er føjet til programmet af en administrator. Administratorer kan tilføje, redigere og fjerne brugere. En bruger kan være en enkelt bruger, en enkelt gruppe eller et enkelt program. Der findes tre typer roller, en bruger kan have:

## <a name="viewer"></a>Seer

- Udforsk indsigt og segmenter på siderne **Start** og **Segmenter**.
- Søg og filtrer kundeprofiler ved hjælp af siden **Kunder**. Felter skal være søgbare.
- Åbn og undersøg siden **Forbedring**.
- Udforsk og eksportér objekter ved hjælp af siden **Objekter**.
- Se status for systemprocesser ved hjælp af siden **System**.
- Vis eksporter på siden **Eksporter**.
- Installer og brug dashboard **Power BI Customer Insights**.

## <a name="contributor"></a>Bidragyder

- Alle tilladelser, der er tilgængelige for seeren.
- Indlæs og transformer data ved hjælp af siden **Datakilder**.
- Fuldfør **Datasamling**, som resulterer i objektet unified customer profile.
- Definer **Relationer** og **Aktiviteter**.
- Opret segmenter ved hjælp af siden **Segmenter**.
- Opret målinger på siden **Målinger**.
- Administrer konfiguration og forbedring af kundeprofiler på siden **Forbedring** (kun førstepartsforbedringer).
- Administrer og opret eksporter på baggrund af [forbindelser, der deles med bidragydere](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administration

- Alle tilladelser, der er tilgængelige for bidragyderen.
- Rediger indstillingerne på siden **System**, herunder arbejdssproget og opdateringsplanerne for systemprocesserne og eksport af diagnosticeringslog.
- Rediger indstillingerne på siden **Sikkerhed**, herunder brugere, API-nøgler, private links og key vault.
- Angiv søge- og filterdefinitioner for siden Kunder ved hjælp af siden **Indeks for søgning og filtrering** (tilgængelig via siden **Kunder**).
- Administrer forbindelser, og tillad dem for andre brugerroller på siden **Forbindelser**.
- Administrer konfiguration og forbedring af kundeprofiler på siden **Forbedring** (for alle forbedringer).
- Administrere og oprette eksporter på siden **Eksporter**.
- Installer og brug **tilføjelsesprogrammet Kundekort**.
- Tilføj og brug **Power Apps-connector**.
- Aktiver brug af [Customer Insights API'er](apis.md).
- [Tildel miljøejerskab](manage-environments.md#change-the-owner-of-an-environment) til en anden administrator.

## <a name="admin-owner"></a>Administrator (ejer)

- Alle tilladelser, der er tilgængelige for administratoren.
- [Nulstil og slet](manage-environments.md#reset-an-existing-environment-preview) miljøet.

## <a name="add-users"></a>Tilføj brugere

1. Gå til **Administration** > **Sikkerhed**, og vælg fanen **Brugere**.

1. Vælg **Tilføj brugere** for at åbne ruden **Tilføj/Rediger tilladelser**.

1. Brug feltet **Søg** til at finde den Azure Active Directory-bruger eller -gruppe, du vil tilføje. Vælg en **Rolle**, der skal tildeles den pågældende bruger eller gruppe.

1. Vælg **Gem**. Det aktuelle miljø deles automatisk med brugeren eller medlemmerne af gruppen. Brugerne kan få adgang til appen Customer Insights og arbejde i henhold til deres angivne rolle.

## <a name="view-current-permissions"></a>Se aktuelle tilladelser

Gå til **Administrator** > **Sikkerhed**, og vælg fanen **Brugere** for at få vist listen over aktive brugere og deres rolletildelinger. Du kan sortere listen over brugere efter en hvilken som helst kolonne eller bruge søgefeltet til at søge efter en bestemt bruger.

## <a name="manage-current-users"></a>Administrere aktuelle brugere

Gå til **Administrator** > **Sikkerhed**, og vælg fanen **Brugere**. Du kan sortere listen over brugere efter en hvilken som helst kolonne eller søge efter en bruger, du vil administrere.

Vælg en bruger for at få vist tilgængelige handlinger.

- **Rediger** for at redigere brugerens rolle i Customer Insights. Vælg **Gem** for at bekræfte ændringen.
- **Fjern** for at fjerne brugeren fra at få adgang til Customer Insights. Bekræft sletningen ved at vælge **Slet**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
