---
title: Vise datarapporter
description: Brug de tilgængelige rapporter til at få vist aktivitet i realtid på webstedet.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 06/18/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: cb6d9ab75b95a5f677d2267f5412a55327930987b2fc3a1a21958633a8116bd2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036641"
---
# <a name="view-reports"></a>Vis rapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En rapport er en samling datavisualiseringer, der bruger de data, der indsamles i SDK, og som hjælper dig med at måle og forstå brugerfunktionsmåden. Dynamics 365 Customer Insights Engagementsindsigt omfatter in-the-the-box-rapporter (OOB) til web- og mobilprojekter.  

## <a name="web-reports"></a>Web-rapporter

Du kan få adgang til webrapporter under **Find** i venstre navigationsrude.

:::image type="content" source="media/report-menu.png" alt-text="Navigation, der viser listen over tilgængelige rapporter.":::

### <a name="real-time-usage-report"></a>Anvendelse af rapport i realtid

Rapporten **Brug i realtid** indeholder en oversigt over den aktuelle aktivitet på webstedet, der opdateres automatisk hvert minut. Brug i realtid til at overvåge effekten af marketingkampagner, trykhændelser og andre scenarier på trafik på webstedet.

### <a name="key-metrics-reports"></a>Vigtige metrikrapporter

- **Sidevisninger** viser sidevisninger for de enkelte sider sammen med antallet af samlede sidevisninger over de valgte tidsramme.

- **Besøg** viser oplysninger om antallet af besøg og besøgets varighed.

- **Besøgende** informerer om nye og tilbagevendende entydige besøgende på dit websted.

### <a name="content-reports"></a>Rapporter om indhold

- **Links** viser oplysninger om antallet og typen af klik.

- **Afslut sider** indeholder de links, de besøgende har klikket på for at afslutte webstedet.

### <a name="traffic-sources-reports"></a>Trafikkilder-rapporter

- **Henvisende** brugere angiver de domæner og URL-adresser, der har henvist besøgende til webstedet.

- **Sporingskoder** indeholder oplysninger om sporingskoderne i de links, der har bragt besøgende til webstedet.

### <a name="visitor-profiles-reports"></a>Rapporter over besøgsprofiler

- **Enheder** indeholder de fysiske enheder, der blev brugt til at få adgang til webstedet.

- **Os &-browsere** giver indblik i de operativsystemer og browsere, der kørte, da du skulle have adgang til webstedet.

- **Steder** viser oplysninger om besøgende efter land, område og by.

- **Sprog** på lisen efter den besøgendes foretrukne sprog.

## <a name="mobile-reports"></a>Mobilrapporter

Mobilrapporter grupperes i kategorierne Brug i realtid, i appen og i brugerkategorier. Du kan få adgang til mobilrapporter under **Find** i venstre navigationsrude.   

:::image type="content" source="media/mobile-reports.png" alt-text="Brugergrænsefladen til indsigt i engagement, der viser rapporten om brug i realtid, som gengiver data i diagrammer og lister.":::   

### <a name="real-time-usage"></a>Anvendelse i realtid

**Brug i realtid** giver en oversigt over den aktuelle aktivitet i mobilappen, der opdateres automatisk hvert minut. Brug tid i realtid til at overvåge antallet af brugere og sessioner, der i øjeblikket er aktive i din app, og visningerne på den øverste skærm.

### <a name="app-reports"></a>App-rapporter

- **Skærmvisninger** viser skærmvisninger for individuelle skærmbilleder i en app og det samlede antal skærmbilleder over en valgt tidsramme. Du kan få vist skærmvisninger efter skærmnavn eller efter skærmtitel.

- **Sessioner** viser oplysninger om antallet af sessioner og sessionens varighed.

- **Returhyppighed** med gruppesessioner tæller efter det antal dage, der er gået siden sidste session.

- **Brugerne** viser nye og tilbagevendende brugere i din mobilapp.

- **Hændelser** indeholder alle de hændelser, der er indsamlet fra din app, samt det samlede antal for hver hændelse.

### <a name="user-reports"></a>Brugerrapporter

- **appversioner** viser de versioner af mobilappen, der bruges af brugerbasen.

- **Enheder og OS-versioner** giver et indblik i, hvilke enheder og operativsystemer der kører din mobilapp.

- **Steder** viser oplysninger om app-brugere efter land, område og by.

## <a name="filter-by-time-or-value"></a>Filtrer efter klokkeslæt eller værdi

Du kan vælge den tidsramme eller værdi i en web- eller mobilrapport for at fokusere på en værdi eller tidsperiode. 

- Hvis du vil tidsramme, skal du vælge **Flere [...]** på rullelisten for rapporten. Valg af tidsinterval er deaktiveret for en brugsrapport i realtid. Tidsintervallet for en brugsrapport i realtid er "nu".

- I de fleste rapporter skal du vælge en værdi i et diagram eller en liste for at filtrere rapporten for den valgte værdi.

[!INCLUDE[footer-include](../includes/footer-banner.md)]