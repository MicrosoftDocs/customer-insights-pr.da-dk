---
title: Forbedring af samlede kundeprofiler
description: Du kan bruge egenskaber til at forbedre dine kundedata.
ms.date: 03/29/2022
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
ms.openlocfilehash: 510a20306e793a5ba522a6ac0d9c7194f03472d2
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491951"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Forbedring af kundeprofiler (prøveversion)

Brug data fra kilder som f.eks. Microsoft og andre partnere til at forbedre kundedataene.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Hubside for forbedring.":::

Hvis du målgruppeindsigt, kan du gå til **Data** > **Forbedring** for at arbejde sammen med forbedringsmuligheder.  

Du skal have bidragyder- eller administratortilladelser for at kunne oprette eller redigere forbedringer. Du kan finde flere oplysninger under [Tilladelser](permissions.md).

Under fanen **Opdag** finder du alle understøttede forbedringsmuligheder.

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

- [Varemærker](enrichment-microsoft.md) leveret af Microsoft
- [Interesser](enrichment-microsoft.md) leveret af Microsoft
- [Udvidede adresser](enrichment-enhanced-addresses.md) leveret af Microsoft 
- [Demografiske oplysninger](enrichment-experian.md) leveret af Experian
- [Brugerdefineret data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) leveret af Microsoft
- [Lokationsdata](enrichment-here.md) leveret af HERE Technologies 
- [Identitet](enrichment-liveramp.md), der leveres af LiveRamp AbiliTec

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

- [Firmadata](enrichment-leadspace.md) leveret af Leadspace
- [Udvidede adresser](enrichment-enhanced-addresses.md) leveret af Microsoft 
- [Forbedrede virksomhedsdata](enrichment-enhanced-company-data.md) fra Microsoft
- [Lokationsdata](enrichment-here.md) leveret af HERE Technologies 
- [Brugerdefineret data](enrichment-SFTP-custom-import.md) via Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) leveret af Microsoft
- [Data om firmaengagement](enrichment-office.md) leveret af Microsoft

---

Under fanen **Mine forbedringer** kan du se de forbedringer, du har konfigureret, og redigere deres egenskaber.

## <a name="manage-existing-enrichments"></a>Administrer eksisterende forbedringer

Gå til fanen **Mine forbedringer** for at se alle konfigurerede forbedringer. Hver forbedring repræsenteres som en række, der indeholder yderligere oplysninger om forbedringen.

Vælg en valgmuligheder for at se de tilgængelige indstillinger. Du kan også vælge ellipsen (...) på et listeelement for at se indstillingerne. Hvis du har konfigureret flere forskellige indstillinger, kan du bruge søgefeltet til at finde det hurtigt.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Indstillinger til administration af forbedringer på listen over forbedringer.":::

- **Vis** oplysninger om forbedringer med antallet af forbedrede kundeprofiler.
- **Rediger** konfigurationen af forbedringen.
- **Kør** forbedringen for at opdatere kundeprofiler med de nyeste data.
- **Deaktiver** en eksisterende forbedring for at forhindre, at den opdateres automatisk i alle planlagte opdateringer. Data fra den seneste vellykkede opdatering vil fortsat være tilgængelige. **Aktivér** en inaktiv forbedring, hvis du vil genstarte automatisk opdatering for hver planlagt opdatering.
- **Slet** forbedringen.

Kør eller deaktiver flere lister på én gang ved at vælge dem på listen. Visnings- og redigeringsindstillinger er ikke tilgængelige som massehandling. De arbejder kun for én gang ad gangen.

## <a name="enrichments-and-connections"></a>Forbedringer og forbindelser

Konfigurationer fra tredjeparter konfigureres ved hjælp af [forbindelser](connections.md), som en administrator konfigurerer med legitimationsoplysninger og giver samtykke til dataoverførsler. Disse forbindelser kan bruges af administratorer og bidragsydere til at konfigurere forbedringer.  

## <a name="multiple-enrichments-of-the-same-type"></a>Flere forbedringer af samme type

Det objekt, der skal forbedres, angives under forbedringskonfigurationen med mulighed for forbedring, som gør det muligt kun at forbedre et undersæt af dine profiler. Du kan f.eks. kun forbedre data for et bestemt segment. Du kan konfigurere flere forbedringer af samme type og genbruge den samme forbindelse. Nogle forbedringer har grænser for antallet af forbedringer af samme type, der kan oprettes. Grænseværdierne og den aktuelle brug kan ses på siden **Forbedring**.

## <a name="enrich-data-sources-before-unification"></a>Forbedre datakilder før samling

Du kan forbedre dine kundedata før datasamling for at øge kvaliteten af datamatchen. Du kan finde flere oplysninger i [datakildeforbedring](data-sources-enrichment.md).

## <a name="see-the-progress-of-the-enrichment-process"></a>Se status for processen til forbedring

Du kan finde detaljer om, hvordan en forbedring behandles, herunder status for den og potentielle problemer, mens den opdateres eller efter en opdatering er fuldført. Forstå, hvilke processer der er involveret i opdatering af forbedring, og hvor lang tid det tog at køre processerne. Status for klar til brug understøttes for Experian, Leadspace, HERE Technologies, SFTP Import og Azure Maps.

Sådan kan du se status for en forbedring

1. Gå til **Data** > **Forbedring**. 
1. Vælg status for en forbedring ved at åbne en siderude under fanen **Mine forbedringer**. 
1. Udvid sektionen **Forbedringer** i ruden **Statusdetaljer**. 
1. Vælg **Se detaljer** under den status, du vil have vist. 
1. Vælg **Vis detaljer** i ruden med **opgavedetaljer** for at se de processer, der er involveret i opdatering af forbedringen og status. 

## <a name="enrichment-results"></a>Forbedringsresultater

Når forbedringskørslen er fuldført, kan du gennemgå resultaterne.

1. Gå til **Data** > **Forbedring**. 
1. Vælg den forbedringsperiode, du vil have oplysninger om.

Alle forbedringer viser grundlæggende oplysninger, f.eks. antallet af forbedrede profiler, et eksempel på det oprettede forbedringsobjekt og antallet af forbedrede profiler over tid. Hvis feltet **Antal kunder, der er forbedret med felt**, bliver det muligt at foretage detailudledning i dækningen af hvert enkelt forbedret felt.

:::image type="content" source="media/enrichments-results.png" alt-text="Forbedringsresultater-side.":::

Nogle forbedringer viser også oplysninger, der er specifikke for typen af forbedring. Du kan finde flere oplysninger om den relevante forbedring i dokumentationen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
