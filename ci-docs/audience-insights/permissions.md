---
title: Administrer brugertilladelser
description: Få mere at vide om tilladelser og brugerroller.
ms.date: 02/09/2022
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
ms.openlocfilehash: 85e1f4f93ac0e99ce6634dfc8fceab0c9a14885e
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376731"
---
# <a name="user-permissions"></a>Brugertilladelser

Siden **Tilladelser** er det sted, hvor du skal konfigurere roller og tilladelser til at bruge målgruppen Insights.

Du skal have administratortilladelser for at kunne se siden. Du kan få adgang til siden med tilladelser i målgruppen Insights ved at gå til **Admin** > **Tilladelser**.

Der findes tre typer roller:

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
- Udfyld sektionere *Datasamling* (**Tilknyt**, **Match** og **Flet**), som resulterer i det samlede kundeprofilobjekt.
- Definer **Relationer** og **Aktiviteter**.
- Opret segmenter ved hjælp af siden **Segmenter**.
- Opret målinger på siden **Målinger**.
- Administrer konfiguration og forbedring af kundeprofiler på siden **Forbedring** (kun førstepartsforbedringer).
- Administrer og opret eksporter på baggrund af forbindelser, der deles med bidragydere. [Få mere at vide om, hvordan administratorer tillader bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administration

- Alle tilladelser, der er tilgængelige for bidragyderen.
- Rediger indstillingerne på siden **System**, herunder arbejdssproget og opdateringsplanerne for systemprocesserne.
- Se og tilføj tilladelser på siden **Tilladelser**.
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
- [Nulstil og slet](manage-environments.md#reset-an-existing-environment) miljøet.

## <a name="assign-roles-and-permissions"></a>Tildele roller og tilladelser

1. Gå til **Adm** > **Tilladelser** i målgruppen Insights.

1. Vælg **Tilføj brugere** for at åbne ruden **Tilføj/Rediger tilladelser**.

1. Brug feltet **Søg** til at finde den Azure Active Directory-bruger eller -gruppe, du vil justere tilladelser for. Vælg en **Rolle**, der skal tildeles den pågældende bruger eller gruppe.

1. Vælg **Gem**. Det aktuelle miljø deles automatisk med brugeren eller medlemmerne af den gruppe, hvis tilladelser du har ændret. Brugerne kan få adgang til appen Customer Insights og arbejde i henhold til deres angivne rolle.

## <a name="view-current-permissions"></a>Se aktuelle tilladelser

Gå til **Admin** > **Tilladelser** i målgruppen Insights for at se, hvilke rolletildelinger der er aktive i øjeblikket.

- Kolonnen **Type** angiver en enkelt bruger, en gruppe eller et program. Systemet understøtter individuelle brugere og grupper.
- Roller angives i kolonnen **Rolle**.
- Vælg en vilkårlig kolonnetitel for at sortere resultaterne efter den pågældende kolonnes værdi.
- Brug feltet **Søg** øverst på siden til at finde bestemte brugere.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
