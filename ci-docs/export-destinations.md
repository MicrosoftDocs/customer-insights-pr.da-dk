---
title: Eksportoversigt (forhåndsversion)
description: Administrer dataeksport til at dele data.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: fd234aff9021ded76d8226bf2f15e035cf75e7db
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245320"
---
# <a name="exports-preview-overview"></a>Eksportoversigt (forhåndsversion)

 Eksporter giver mulighed for at dele specifikke data med forskellige programmer. De kan omfatte kundeprofiler, objekter, skemaer og tilknytningsoplysninger. Hver eksport kræver en [forbindelse, konfigureret af en administrator, til at administrere godkendelse og adgang](connections.md). På siden **Eksport** vises alle de konfigurerede eksporter.

## <a name="export-types"></a>Eksporttyper

Der findes to hovedtyper af eksport:  

- **Eksport af dataoutput** eksportere alle objekttyper, der er tilgængelige i Customer Insights. De objekter, du vælger til eksport, eksporteres med alle datafelter, metadata, skemaer og tilknytningsdetaljer.
- **Segmenteksport**: eksportere segmentobjekter fra Customer Insights. Segmenter repræsenterer en liste over kundeprofiler. Når du konfigurerer eksporten, skal du vælge de inkluderede datafelter, afhængigt af det målsystem du eksporterer data til.

### <a name="export-segments"></a>Eksportere segmenter

**Eksportere segmenter i miljøer for forretningskonti (B-til-B) eller individuelle kunder (B-til-C)**  
De fleste eksportmuligheder understøtter begge typer miljøer. Der er særlige krav ved eksport af segmenter til forskellige destinationssystemer. 

**Segmenteksport i miljøer for individuelle forbrugere (B-til-C)**  
- Segmenter i konteksten af miljøer for individuelle kunder bygger på objektet *samlet kundeprofil*. Alle de segmenter, der opfylder kravene i destinationssystemerne (f.eks. en mailadresse), kan eksporteres.

**Segmenteksportmiljøer for forretningskonti (B-til-B)**  
- Segmenter i konteksten af miljøer for forretningskonti bygger på *firma*-objektet. Hvis du vil eksportere firmasegmenter, som de er, skal destinationssystemet understøtte firmasegmenter. Det er tilfældet for [LinkedIn](export-linkedin-ads.md), når du vælger **firma**-indstillingen, mens du definerer eksporten.
- Alle andre destinationssystemer kræver felter fra kontaktobjektet. Hvis du vil sikre, at firmasegmenter kan hente data fra relaterede kontakter, skal din segmentdefinition projicere attributter for kontaktobjektet. Få mere at vide om, hvordan du [konfigurerer segmenter og projektattributter](segment-builder.md).

**Begrænsninger for segmenteksport**  
- Tredjeparters destinationssystemer kan begrænse antallet af kundeprofiler, du kan eksportere. 
- For individuelle kunder kan du se det faktiske antal segmentmedlemmer, når du vælger et segment til eksport. Du får en advarsel, hvis et segment er for stort. 
- I forbindelse med forretningskonti kan du se antallet af firmaer i et segment. Men antallet af kontakter, der kan projiceres, vises ikke. I visse tilfælde kan det medføre, at det eksporterede segment rent faktisk indeholder flere kundeprofiler, end destinationssystemet accepterer. Hvis grænserne for destinationssystemers resultater overskrides, springes eksporten over.

## <a name="set-up-a-new-export"></a>Konfigurer en ny eksport

Hvis du vil konfigurere eller redigere en eksport, skal du have tilgængelige forbindelser. Forbindelser afhænger af [brugerrollen](permissions.md):
- **Administratorer** har adgang til alle forbindelser. De kan også oprette nye forbindelser, når en eksport konfigureres.
- **Bidragydere** kan have adgang til bestemte forbindelser. De er afhængige af administratorer, når de skal konfigurere og dele forbindelser. Eksportlisten viser bidragydere, om de kan redigere eller kun få vist en eksport i kolonnen **Dine tilladelser**. Du kan finde flere oplysninger ved at gå til [Tillade bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Seere** kan kun få vist eksisterende eksporter – ikke oprette dem.

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport** for at oprette en ny eksport.

1. Vælg, hvilken [forbindelse](connections.md) du vil bruge, i ruden **Konfigurer eksport**.

1. Angiv de nødvendige oplysninger, og vælg **Gem** for at oprette eksporten. Du kan finde de nødvendige oplysninger i dokumentationen til Customer Insights for den specifikke eksport.

## <a name="manage-existing-exports"></a>Administrere eksisterende eksport

Gå til **Data** > **Eksport** for at få vist eksporten, deres forbindelsesnavn, forbindelsestype og status. Alle brugerroller kan få vist konfigurerede eksporter. Du kan sortere listen over eksport efter en hvilken som helst kolonne eller bruge søgefeltet til at søge efter de eksportfelter, der skal håndteres.

Vælg en eksport for at få vist tilgængelige handlinger.

:::image type="content" source="media/exports_showmore.png" alt-text="Eksport-side":::

- **Vis** eller **Rediger** eksporten. Brugere uden redigeringstilladelser skal vælge **Vis** i stedet for **Rediger** for at få vist eksportoplysningerne.
- **Kør** eksporten for at eksportere de seneste data.
- **Opret en dublet** af en eksport.
- **[Planlæg](#schedule-and-run-exports)** eksport.
- **Fjern forbindelsen** for at fjerne forbindelsen til denne eksport. Forbindelsen fjernes ikke, men eksporten deaktiveres. Kolonnen **Forbindelse bruges** til at vise Ingen forbindelse.
- **Fjerne** en eksport

## <a name="schedule-and-run-exports"></a>Planlæg, og kør eksport

Hver eksport, du konfigurerer, har en opdateringsplan. Under en opdatering søger systemet efter nye eller opdaterede data, der skal medtages i en eksport. Eksport køres som standard som del af alle [planlagte systemopdateringer](schedule-refresh.md). Du kan tilpasse opdateringsplanen, eller slå den fra for at køre eksporten manuelt.

Eksportplaner afhænger af miljøets tilstand. Hvis der er opdateringer i gang om [afhængigheder](system.md#refresh-processes), når en planlagt eksport skal starte, fuldfører systemet først opdateringerne og kører derefter eksporten. Du kan få vist, hvornår en eksport sidst blev opdateret i kolonnen **Opdateret**.

### <a name="schedule-exports"></a>Planlæg eksport

Definere brugerdefinerede opdateringsplaner for individuelle eksporter eller flere eksporter på én gang. Den aktuelt definerede tidsplan vises i kolonnen **Tidsplan** på eksportlisten. Tilladelsen til at ændre tidsplanen er den samme som [redigering og definition af eksporter](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg den eksport, du vil planlægge.

1. Vælg **Tidsplan**.

1. Angiv **Planlæg kørsel** til **Til** i ruden **Planlæg eksport** for at køre eksporten automatisk. Indstil den til **Fra** for at opdatere den manuelt.

1. Ved automatisk opdaterede eksporter skal du vælge en værdi for **Gentagelse** og angive detaljerne for den. Den definerede tid gælder for alle forekomster af en gentagelse. Det er det tidspunkt, hvor en eksport skal begynde at opdatere.

1. Vælg **Gem**.

Når du redigerer tidsplanen for flere eksporter, skal du foretage et valg under **Behold eller tilsidesætte tidsplaner**:

- **Bevar individuelle tidsplaner**: Bevar den tidligere definerede tidsplan for de valgte eksporter, og deaktiver eller aktiver dem kun.
- **Definer ny tidsplan for alle valgte eksporter**: Tilsidesæt de eksisterende tidsplaner for de valgte eksporter.

### <a name="run-exports-on-demand"></a>Kør eksporter efter behov

Hvis du vil eksportere data uden at vente på en planlagt opdatering, skal du gå til **Data** > **Eksport**.

- Hvis du vil køre alle eksporter, skal du vælge **Kør alle** på kommandolinjen. Denne handling kører kun eksporter, der har en aktiv tidsplan. Hvis du vil køre en eksport, der ikke er aktiv, skal du køre en enkelt eksport.
- Hvis du vil køre en enkelt eksport, skal du markere den på listen og vælge **Kør** på kommandolinjen.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
