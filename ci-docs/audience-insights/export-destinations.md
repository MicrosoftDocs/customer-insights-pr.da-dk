---
title: Eksportere data fra Customer Insights
description: Administrer dataeksport til at dele data.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 61e95e47489495e367498547687b0065169519e6
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673316"
---
# <a name="exports-preview-overview"></a>Eksportoversigt (forhåndsversion)

På siden **Eksport** vises alle de konfigurerede eksporter. Eksporter deler specifikke data med forskellige programmer. De kan omfatte kundeprofiler, objekter, skemaer og tilknytningsoplysninger. Hver eksport kræver en [forbindelse, konfigureret af en administrator, til at administrere godkendelse og adgang](connections.md).

Gå til **Data** > **Eksport** for at få vist eksportsiden. Alle brugerroller kan få vist konfigurerede eksporter. Brug søgefeltet på kommandolinjen til at finde eksporter efter navn, forbindelsesnavn eller forbindelsestype.

## <a name="export-types"></a>Eksporttyper

Der findes to hovedtyper af eksport:  

- **Eksport af dataoutput** giver dig mulighed for at eksportere alle objekttyper, der er tilgængelige i målgruppeindsigt. De objekter, du vælger til eksport, eksporteres med alle datafelter, metadata, skemaer og tilknytningsdetaljer. 
- Med **segmenteksport** kan du eksportere segmentobjekter fra målgruppeindsigt. Segmenter repræsenterer en liste over kundeprofiler. Når du konfigurerer eksporten, skal du vælge de inkluderede datafelter, afhængigt af det målsystem du eksporterer data til. 

### <a name="export-segments"></a>Eksportere segmenter

**Eksportere segmenter i miljøer for forretningskonti (B-til-B) eller individuelle kunder (B-til-C)**  
De fleste eksportmuligheder understøtter begge typer miljøer. Der er særlige krav ved eksport af segmenter til forskellige destinationssystemer. Et segmentmedlem, kundeprofilen, indeholder generelt kontaktoplysninger. Dette er normalt tilfældet for segmenter, der er baseret på individuelle kunder (B-til-C), men det er ikke nødvendigvis tilfældet for segmenter baseret på forretningskonti (B-til-B). 

**Segmenteksportmiljøer for forretningskonti (B-til-B)**  
- Segmenter i konteksten af miljøer for forretningskonti bygger på *firma*-objektet. Hvis du vil eksportere firmasegmenter, som de er, skal destinationssystemet understøtte firmasegmenter. Det er tilfældet for [LinkedIn](export-linkedin-ads.md), når du vælger **firma**-indstillingen, mens du definerer eksporten.
- Alle andre destinationssystemer kræver felter fra kontaktobjektet. Hvis du vil sikre, at firmasegmenter kan hente data fra relaterede kontakter, skal din segmentdefinition projicere attributter for kontaktobjektet. Få mere at vide om, hvordan du [konfigurerer segmenter og projektattributter](segment-builder.md).

**Segmenteksport i miljøer for individuelle forbrugere (B-til-C)**  
- Segmenter i konteksten af miljøer for individuelle kunder bygger på objektet *samlet kundeprofil*. Alle de segmenter, der opfylder kravene i destinationssystemerne (f.eks. en mailadresse), kan eksporteres.

**Begrænsninger for segmenteksport**  
- Tredjeparters destinationssystemer kan begrænse antallet af kundeprofiler, du kan eksportere. 
- For individuelle kunder kan du se det faktiske antal segmentmedlemmer, når du vælger et segment til eksport. Du får en advarsel, hvis et segment er for stort. 
- I forbindelse med forretningskonti kan du se antallet af firmaer i et segment. Men antallet af kontakter, der kan projiceres, vises ikke. I visse tilfælde kan det medføre, at det eksporterede segment rent faktisk indeholder flere kundeprofiler, end destinationssystemet accepterer. Hvis grænserne for destinationssystemers resultater overskrides, springes eksporten over. 

## <a name="set-up-a-new-export"></a>Konfigurer en ny eksport  
Hvis du vil konfigurere eller redigere en eksport, skal du have tilgængelige forbindelser. Forbindelser afhænger af [brugerrollen](permissions.md):
- **Administratorer** har adgang til alle forbindelser. De kan også oprette nye forbindelser, når en eksport konfigureres.
- **Bidragydere** kan have adgang til bestemte forbindelser. De er afhængige af administratorer, når de skal konfigurere og dele forbindelser. Eksportlisten viser bidragydere, om de kan redigere eller kun få vist en eksport i kolonnen **Dine tilladelser**. Du kan finde flere oplysninger ved at gå til [Tillade bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Seere** kan kun få vist eksisterende eksporter – ikke oprette dem.

### <a name="define-a-new-export"></a>Definer en ny eksport

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport** for at oprette en ny eksport.

1. Vælg, hvilken forbindelse du vil bruge, i ruden **Konfigurer eksport**. [Forbindelser](connections.md) administreres af administratorer. 

1. Angiv de nødvendige oplysninger, og vælg **Gem** for at oprette eksporten.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definer en ny eksport baseret på en eksisterende eksport

1. Gå til **Data** > **Eksport**.

1. Vælg den eksport, som du vil duplikere, på eksportlisten.

1. Vælg **Opret dublet** på kommandolinjen for at åbne ruden **Konfigurer eksport** med oplysninger om den valgte eksport.

1. Gennemse, og tilpas eksporten, og vælg **Gem** for at oprette en ny eksport.

### <a name="edit-an-export"></a>Rediger en eksport

1. Gå til **Data** > **Eksport**.

1. Vælg den eksport, som du vil redigere, på eksportlisten.

1. Vælg **Rediger** på kommandolinjen.

1. Opdatér de værdier, du vil opdatere, og vælg **Gem**.

## <a name="view-exports-and-export-details"></a>Få vist eksport og eksportdetaljer

Når du har oprettet eksportmål, vises de under **Data** > **Eksport**. Alle brugere kan se, hvilke data der deles, og den seneste status.

1. Gå til **Data** > **Eksport**.

1. Brugere uden redigeringstilladelser skal vælge **Vis** i stedet for **Rediger** for at få vist eksportoplysningerne.

1. I sideruden vises konfigurationen af en eksport. Uden redigeringstilladelser kan du ikke ændre værdier. Vælg **Luk** for at vende tilbage til eksportsiden.

## <a name="schedule-and-run-exports"></a>Planlæg, og kør eksport

Hver eksport, du konfigurerer, har en opdateringsplan. Under en opdatering søger systemet efter nye eller opdaterede data, der skal medtages i en eksport. Eksport køres som standard som del af alle [planlagte systemopdateringer](system.md#schedule-tab). Du kan tilpasse opdateringsplanen, eller slå den fra for at køre eksporten manuelt.

Eksportplaner afhænger af miljøets tilstand. Hvis der er opdateringer i gang om [afhængigheder](system.md#refresh-policies), når en planlagt eksport skal starte, fuldfører systemet først opdateringerne og kører derefter eksporten. Du kan få vist, hvornår en eksport sidst blev opdateret i kolonnen **Opdateret**.

### <a name="schedule-exports"></a>Planlæg eksport

Du kan definere brugerdefinerede opdateringsplaner for individuelle eksporter eller flere eksporter på én gang. Den aktuelt definerede tidsplan vises i kolonnen **Tidsplan** på eksportlisten. Tilladelsen til at ændre tidsplanen er den samme som for [redigering og definition af eksporter](export-destinations.md#set-up-a-new-export). 

1. Gå til **Data** > **Eksport**.

1. Vælg den eksport, du vil planlægge.

1. Vælg **Planlæg** på kommandolinjen.

1. Angiv **Planlæg kørsel** til **Til** i ruden **Planlæg eksport** for at køre eksporten automatisk. Indstil den til **Fra** for at opdatere den manuelt.

1. Ved automatisk opdaterede eksporter skal du vælge en værdi for **Gentagelse** og angive detaljerne for den. Den definerede tid gælder for alle forekomster af en gentagelse. Det er det tidspunkt, hvor en eksport skal begynde at opdatere.

1. Anvend og aktivér ændringerne ved at vælge **Gem**.

Når du redigerer tidsplanen for flere eksporter, skal du foretage et valg under **Behold eller tilsidesætte tidsplaner**:
- **Bevar individuelle tidsplaner**: Bevar den tidligere definerede tidsplan for de valgte eksporter, og deaktiver eller aktiver dem kun.
- **Definer ny tidsplan for alle valgte eksporter**: Tilsidesæt de eksisterende tidsplaner for de valgte eksporter.

### <a name="run-exports-on-demand"></a>Kør eksporter efter behov

Hvis du vil eksportere data uden at vente på en planlagt opdatering, skal du gå til **Data** > **Eksport**.

- Hvis du vil køre alle eksporter, skal du vælge **Kør alle** på kommandolinjen. Denne handling kører kun eksporter, der har en aktiv tidsplan.
- Hvis du vil køre en enkelt eksport, skal du markere den på listen og vælge **Kør** på kommandolinjen. Det er sådan, du kører eksporter uden aktiv tidsplan. 

## <a name="remove-an-export"></a>Fjerne en eksport

1. Gå til **Data** > **Eksport**.

1. Markér den eksport, du vil fjerne.

1. Vælg **Fjern** på kommandolinjen.

1. Bekræft fjernelsen ved at vælge **Fjern** på bekræftelsesskærmen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
