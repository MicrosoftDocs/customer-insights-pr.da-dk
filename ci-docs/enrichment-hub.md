---
title: Oversigt over dataforbedring (forhåndsversion)
description: Brug funktioner fra Microsoft og andre tredjepartstjenester til at forbedre dine kundedata.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: fb747f7adc7d87f30f66c5d0ed20bbe238558fde
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304512"
---
# <a name="data-enrichment-preview-overview"></a>Oversigt over dataforbedring (forhåndsversion)

Brug data fra kilder som f.eks. Microsoft og andre partnere til at forbedre kundedataene. Konfigurationer fra tredjeparter konfigureres ved hjælp af [forbindelser](connections.md), som en administrator konfigurerer med legitimationsoplysninger og giver samtykke til dataoverførsler. Disse forbindelser kan bruges af administratorer og bidragsydere til at konfigurere forbedringer.  

## <a name="multiple-enrichments-of-the-same-type"></a>Flere forbedringer af samme type

Det objekt, der skal forbedres, angives under forbedringskonfigurationen med mulighed for forbedring, som gør det muligt kun at forbedre et undersæt af dine profiler. Du kan f.eks. kun forbedre data for et bestemt segment. Du kan konfigurere flere forbedringer af samme type og genbruge den samme forbindelse. Nogle forbedringer har grænser for antallet af forbedringer af samme type, der kan oprettes. Grænseværdierne og den aktuelle brug kan ses i de enkelte felter under fanen **Opdag** på siden **Forbedring**.

## <a name="enrich-data-sources-before-unification"></a>Forbedre datakilder før samling

Du kan forbedre dine kundedata før datasamling for at øge kvaliteten af datamatchen. Du kan finde flere oplysninger i [datakildeforbedring](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Opret en forbedring

Du skal have bidragyder- eller administrator-[tilladelser](permissions.md) for at kunne oprette eller redigere forbedringer.

Gå til **Data** > **Forbedring**. Fanen **Opdag** viser alle understøttede forbedringsmuligheder.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Hubside for forbedring.":::

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

- [AbiliTec-identitet](enrichment-liveramp.md), der leveres af LiveRamp AbiliTec
- [Varemærker](enrichment-microsoft.md) leveret af Microsoft
- [Demografiske oplysninger](enrichment-experian.md) leveret af Experian
- [Udvidede adresser](enrichment-enhanced-addresses.md) leveret af Microsoft
- [Interesser](enrichment-microsoft.md) leveret af Microsoft
- [Lokationsdata](enrichment-azure-maps.md) fra Microsoft Azure Kort
- [Lokationsdata](enrichment-here.md) leveret af HERE Technologies
- [SFTP-brugerdefinerede data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

- [Data om firmaengagement](enrichment-office.md) leveret af Microsoft
- [Virksomhedsdata](enrichment-dnb.md) fra Dun & Bradstreet
- [Firmadata](enrichment-leadspace.md) leveret af Leadspace
- [Udvidede adresser](enrichment-enhanced-addresses.md) leveret af Microsoft
- [Forbedrede virksomhedsdata](enrichment-enhanced-company-data.md) fra Microsoft
- [Lokationsdata](enrichment-azure-maps.md) fra Microsoft Azure Kort
- [Lokationsdata](enrichment-here.md) leveret af HERE Technologies
- [SFTP-brugerdefinerede data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP)

---

## <a name="manage-existing-enrichments"></a>Administrer eksisterende forbedringer

Gå til **Data** > **Forbedring**. Under fanen **Mine forbedringer** kan du se de konfigurerede forbedringer, deres status, antallet af forbedrede kunder og den sidste gang dataene blev opdateret. Du kan sortere listen over forbedringer efter en hvilken som helst kolonne eller bruge søgefeltet til at søge efter de ønsker, der skal håndteres.

Vælg en forbedring for at få vist tilgængelige handlinger.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Indstillinger til administration af forbedringer på listen over forbedringer.":::

- **Vis** oplysninger om forbedringer med antallet af forbedrede kundeprofiler.
- **Rediger** konfigurationen af forbedringen.
- [**Kør**](#run-or-refresh-enrichments) forbedringen for at opdatere kundeprofiler med de nyeste data. Kør flere forbedringer på én gang ved at vælge dem på listen.
- **Aktiver** eller **Deaktiver** en forbedring. Inaktive forbedringer bliver ikke opdateret under en [planlagt opdatering](schedule-refresh.md).
- **Slet** forbedringen.

Du kan også oprette [segmenter](segments.md) eller [mål](measures.md) ud fra forbedringer.

## <a name="run-or-refresh-enrichments"></a>Køre eller opdatere forbedringer

Når programmet er kørt, kan det opdateres automatisk eller opdateres manuelt efter behov.

1. Hvis du manuelt vil opdatere en eller flere indstillinger, skal du vælge dem og vælge **Kør**. Hvis du vil [planlægge en automatisk opdatering](schedule-refresh.md), skal du gå til **Administrator** > **System** > **Plan**. Behandlingstiden afhænger af størrelsen på dine kundedata.

1. Du kan også [se status for procesforløbet](#see-the-progress-of-the-enrichment-process).

1. Når processen til forbedring er fuldført, skal du gå til **Mine forbedringer** for at gennemgå de netop forbedrede kundeprofildata, tidspunktet for den sidste opdatering og antallet af forbedrede profiler.

1. Vælg forbedringen for at få vist [forbedrede resultater](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Se status for processen til forbedring

Du kan finde detaljer om, hvordan en forbedring behandles, herunder dens status og potentielle problemer, mens den opdateres eller efter en opdatering er fuldført. Forstå, hvilke processer der er involveret i opdatering af forbedring, og hvor lang tid det tog at køre processerne. Status for klar til brug understøttes for Experian, Leadspace, HERE Technologies, SFTP Import og Azure Maps.

1. Gå til **Data** > **Forbedring**.
1. Vælg statussen for forbedringer under fanen **Mine forbedringer** for at åbne en siderude.
1. Udvid sektionen **Forbedringer** i ruden **Statusdetaljer**.
1. Vælg **Se detaljer** under den status, du vil have vist.
1. Vælg **Vis detaljer** i ruden med **opgavedetaljer** for at se de processer, der er involveret i opdatering af forbedringen og status.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Vise forbedringsresultater

Når forbedringskørslen er fuldført, kan du gennemgå resultaterne.

1. Gå til **Data** > **Forbedring**.
1. Under fanen **Mine forbedringer** vælger du den forbedring, du vil se.

Alle forbedringer viser grundlæggende oplysninger, f.eks. antallet af forbedrede profiler og antallet af forbedrede profiler over tid. I eksempelfelterne **for forbedrede kunder** vises et eksempel på det oprettede objekt, der giver mulighed for at bruge programmet. Hvis du vil se en detaljeret visning, skal du vælge **Se mere** og vælge fanen **Data**.

:::image type="content" source="media/enrichments-results.png" alt-text="Forbedringsresultater-side.":::

Hvis feltet **Antal kunder, der er forbedret med felt**, bliver det muligt at foretage detailudledning i dækningen af hvert enkelt forbedret felt.

Nogle forbedringer viser også oplysninger, der er specifikke for typen af forbedring. Du kan finde flere oplysninger i en relaterede dokumentation.

[!INCLUDE [footer-include](includes/footer-banner.md)]
