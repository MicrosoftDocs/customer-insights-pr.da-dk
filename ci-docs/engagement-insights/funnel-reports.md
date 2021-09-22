---
title: Tragtrapporter
description: Sådan bruges tragtrapporter til at forstå, hvordan målgruppen træffer beslutninger.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7c6b7b7285556f8a531ce9e29f0d1de162562be6fb43dd826a65fd9e00d87b30
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032248"
---
# <a name="create-and-manage-funnel-reports"></a>Opret, og administrer tragtrapporter

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

En tragtrapport indsamler oplysninger om de trin, der udføres under en kundekampagneforløb via dit website eller din mobilapp. Det hjælper dig med at forstå, hvad målgruppen gennemgår i en proces, og identificerer frafaldspunkter. Du kan f.eks. bruge en tragtrapport til at identificere de veje, kunderne går, før de foretager et køb. En tragtrapport indeholder data, der kan anvendes til at træffe beslutninger og identificere områder til optimering og forbedring af processer.

## <a name="create-a-funnel-report"></a>Oprette en tragtrapport

Hvis du vil oprette tragtrapporten, skal du angive de trin, du vil medtage, og aktiviteten for hvert trin. En aktivitet er en [hændelse](glossary.md), der repræsenterer brugerfunktionsmåden. I tragtrapporten vises antallet af brugere, der har fuldført hvert defineret trin. 

1. Gå til **Tragte**, og vælg **+Ny tragt** for at starte en tragtrapport.

1. I **Tragteditor** under **Trin** vælges **+Tilføj trin**. 

1. Angiv et navn i **Titel på trin**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Ny tragtrapport.":::

1. Vælg en **Aktivitet**. En aktivitet registrerer, hvornår en bruger får vist en side (**Vise** aktivitet) eller kommunikerer med indhold (**Handling** hændelse).

1. Brug **Trinkriterier** til at angive aktivitetens dimension. [Dimensioner](dimensions.md) er attributter, der kan beskrive, filtrere eller gruppere data.

1. Du kan også konfigurere tragttrin med flere betingelser. Vælg **Tilføj betingelse** for at angive flere dimensioner i et trin. Der skal bruges samme aktivitetstype i yderligere kriterier. Du kan vælge, om flere betingelser er knyttet til en AND- eller en OR-operator.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Tragteditor, der viser trinkonfigurationen med trin med flere betingelser.":::

1. Vælg **Tilføj trin**, indtil du har fuldført alle de ønskede trin i rapporten.

1. Vælg **Gem**, navngive rapporten og **Gem** igen. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Eksempel: Tragtrapport i virksomheden Fourth Coffee

I følgende scenario vises en måde at bruge en tragtrapport på. En analytiker hos firmaet Fourth Coffee vil gerne forstå påvirkningen af en nylig kampagne på abonnementspriserne. Analytikeren opretter en tragtrapport til identifikation af kundeaktiviteten. Den starter, når kunderne kommer til virksomhedens startside, indtil de bruger kampagnekoden for abonnementet. Analytikeren opretter en tragtrapport med følgende trin:

Trin 1: Kunder, der lander på startsiden   
Trin 2: Kunder, der foretager et køb   
Trin 3: Kunder, der bruger kampagnekoden for at få rabat på et abonnement   
Trin 4: Tilmelding til abonnement   

:::image type="content" source="media/funnel-report-example.png" alt-text="eksempel på tragtrapport.":::
  
Med denne tragt kan du se antallet af brugere, der har brugt kampagnekoden efter et engangskøb for at tilmelde sig abonnementsprogrammet.

### <a name="configure-advanced-settings"></a>Konfigurere avancerede indstillinger 

Med tragtrapporter kan du definere en grænse for den tid, det tager at fuldføre en tragt. Du kan f.eks. angive tidspunktet til at fuldføre tragten til fire dage. Denne indstilling tæller kun vellykkede tilmeldinger til abonnementer, som fandt sted i løbet af fire dage efter en brugers besøg på startsiden.

1. Gå til **Tragt** for at åbne **Tragtbiblioteket**.

1. Markér et navn for at åbne rapporten. 

1. Vælg **Avancerede indstillinger** i ruden **Tragteditor**. 

1. Indstil Begræns færdiggørelsestid for tragt til **Til**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Tragteditoren viser avancerede indstillinger og indstillinger for at begrænse den tid, der skal til for at fuldføre en tragt.":::

1. Vælg det tidspunkt, hvor tragten skal være fuldført, på rullelisten **Angiv grænse til**.

1. Vælg **Gem** for at anvende dine ændringer.


## <a name="cross-channel-funnel-reports"></a>Rapporter over tragt på tværs af kanaler 

Indsigt i engagement kan også indsamle adfærdsmæssige kundedata i din mobilapp. Når du har instrumenteret din mobilapp med indsigten om engagement [Android SDK](get-started-android.md) eller [iOS SDK](get-started-ios.md), kan du oprette tragtrapporter på tværs af kanaler. 

### <a name="create-a-cross-channel-funnel-report"></a>Oprette rapport over tragt på tværs af kanaler 

1. Følg trinnene for at [oprette en tragtrapport](#create-a-funnel-report).    

1. Hvis du vil spore, hvordan dine kunder interagerer med dit brand på tværs af både dit website og din mobilapp eller flere websteder, skal du bruge skifteren til arbejdsområdet til at oprette tragttrin med data fra andre arbejdsområder. Vælg, hvilket arbejdsområde dataene til tragttrinnet skal komme fra, under **Trin** i **Tragteditor**.

## <a name="manage-funnel-reports"></a>Administrer tragtrapporter

Du kan gennemse tragtrapporter for at analysere data, spore præstationen og indsamle indsigt.

> [!NOTE]
> - Tragtrapporter med engagementsindsigt understøtter i øjeblikket scenarier, hvor alle brugere i tragten er anonyme, eller alle brugere godkendes. 
> - Historiske data i tragtrapporter er tilgængelige de seneste 30 dage.

### <a name="view-funnel-reports"></a>Vise tragtrapporter

1. Gå til **Tragt** for at åbne **Tragtbiblioteket**.
1. Markér et navn for at åbne rapporten.    

### <a name="see-the-data-collected-for-a-report"></a>Få vist de data, der indsamles for en rapport   

Sådan får du vist oplysninger om en fase

- Peg på et trin i rapporten.

:::image type="content" source="media/funnel-step-data.png" alt-text="tragtdata.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Ændring af datointervallet for tragtrapporten

1. Gå til **Tragt** for at åbne **Tragtbiblioteket**.

1. Markér et navn for at åbne rapporten.

1. Åbn **tidsintervallet**, og vælg en ny tidsperiode på listen eller i **fast datointerval** for at angive et datointerval.

## <a name="edit-or-delete-funnel-reports"></a>Redigere eller slette tragtrapporter

Du kan ændre navnet på en tragtrapport, slette den eller ændre trinnene i rapporten.

### <a name="rename-or-delete-a-funnel-report"></a>Omdøbe eller slette en tragtrapport

1. Gå til **Tragt** for at åbne **Tragtbiblioteket**. 

1. Vælg **Flere** ud for den rapport, du vil ændre, og vælg **Rediger navn** eller **Slet**.

### <a name="edit-a-funnel-step"></a>Redigere et tragttrin  

1. Gå til **Tragt** for at åbne **Tragtbiblioteket**. 

1. Markér et navn for at åbne rapporten.

1. Vælg det trin, du vil redigere.

1. Vælg **Rediger**.

1. Opdater de **tragtoplysninger**, du vil ændre, i tragteditoren.  

1. Vælg **Gem**.

### <a name="reorder-a-funnel-step"></a>Omarrangere et tragttrin

1. Gå til **Tragt** for at åbne **Tragtbiblioteket**. 

1. Markér et navn for at åbne rapporten.

1. Vælg det trin, du vil omarrangere.

1. Vælg **Flyt**, og klik derefter på **Op**, **Ned**, **Til top** eller **Til bund** for at flytte trinnet.

### <a name="delete-a-funnel-step"></a>Slette et tragttrin

1. Gå til **Tragt** for at åbne **Tragtbiblioteket**. 

1. Markér et navn for at åbne rapporten.

1. Markér det trin, du vil fjerne, og vælg derefter **Slet**.

