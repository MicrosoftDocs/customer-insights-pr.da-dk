---
title: Foreslåede segmenter baseret på målinger (forhåndsversion)
description: Lad maskinel indlæring hjælpe dig med at finde nye og interessante segmenter baseret på kundeattributter.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170950"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Foreslåede segmenter baseret på målinger (forhåndsversion)

Oplev interessante segmenter af dine kunder ved hjælp af en AI-model. Denne maskinel indlæring-drevne funktion foreslår segmenter baseret på målpunkter eller kundeattributter. Det kan hjælpe med at forbedre dine KPI'er eller bedre forstå attributternes indflydelse i forbindelse med andre attributter.

> [!NOTE]
> Find lignende kunder bruger automatiserede metoder til at evaluere data og foretage forudsigelser på baggrund af disse data. Det har derfor mulighed for at bruges som en metode til profilering, da denne betegnelse er defineret i den generelle databeskyttelsesforordning ("GDPR"). Din brug af denne funktion til at behandle data kan være underlagt GDPR eller andre love eller bestemmelser. Du er ansvarlig for at sikre, at brugen af Dynamics 365 Customer Insights, herunder denne funktion, overholder alle gældende love og bestemmelser, herunder lovgivning vedrørende beskyttelse af personlige oplysninger, personlige data, biometriske data, databeskyttelse og fortrolighed i kommunikationen.

:::image type="content" source="media/suggested-segments.png" alt-text="Foreslået side med segmenter, der viser detaljer om et forslag i en siderude.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Foreslåede segmenter for at forbedre dine KPI'er

Hvis du bruger [målinger oprettet](measures.md) for at spore dine nøgletal, kan du oprette segmenter for at få vist indflydelse på nøgletallet. Du kan bruge disse oplysninger til at køre en yderst målrettet kampagne.

Du sporer f.eks. en måling, der hedder *TotalSpendPerCustomer*. Som virksomhed vil du gerne se dette antal vokse. Hvis du vælger et målpunkt som primær attribut, kan du vælge de attributter, du vil vurdere for indflydelse. Lad os sige *medlemsniveau*, *medlemsperiode* og *beskæftigelse*. Customer Insights kan derefter foreslå et segment, der fortæller dig, hvem der er den største indflydelse af den pågældende måling. For eksempel er *Bogholdere*, der er *Gold*-medlemmer, og som har været hos din virksomhed i *mindst fem år*, den største influencer af *TotalSpendPerCustomer*. Du får en anslået segmentstørrelse for hvert forslag. Du kan bruge disse oplysninger til at oprette kampagner for målgrupperne.

## <a name="understand-what-influences-a-customer-attribute"></a>Forstå, hvad der påvirker en kundeattribut

Du kan vælge en kundeattribut i stedet for et målpunkt som den primære attribut. Baseret på dit valg til at påvirke attributter opretter AI-modellen en række forslag, der viser, hvordan de valgte attributter påvirker den primære attribut.

Du kan f.eks. vælge *Belønningsmedlem (Ja/Nej)* som den primære attribut. *Ansættelse*, *Beskæftigelse* og *Antal supportbilletter* angives som andre attributter, der påvirker. AI-modellen kunne foreslå segmenter, der angiver, at de fleste it-fagfolk med ansættelse over to år er belønningsmedlemmer. Et andet forslag kunne fremhæve, at revisorer med fastansættelse over et år og færre end tre supportbilletter er belønningsmedlemmer.

## <a name="artificial-intelligence-usage"></a>Brug af kunstig intelligens

Ved hjælp af den primære attribut og indflydelsesattributter foreslår en beslutningsalgoritme interessante segmenter. Forslagene er baseret på regler eller mønstre, der blev samlet op af AI-algoritmen. Kun segmenter, der adskiller sig væsentligt fra den gennemsnitlige population, vises som forslag. Sammenligningen med den gennemsnitlige population er baseret på det valgte målpunkt eller den valgte primære attribut.

### <a name="responsible-ai"></a>Ansvarlig AI

Foreslåede målgrupper giver dig mulighed for at vælge attributter for at oprette nye målgrupper og behandle de data, du vælger. Når du vælger attributter, herunder følsomme attributter som race, seksuel orientering eller køn, skal du sikre dig, at du kan og bør behandle disse data. Du er ansvarlig for at overholde alle love, der gælder for din organisation, og overholde organisationens principper og politikker for beskyttelse af personlige oplysninger.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Forskellige resultater for primære attributter med kategoriske og numeriske værdier

Målgruppeforslag er forskellige, hvis du vælger en numerisk attribut eller en kategorisk attribut som den primære attribut. Værdier i en kategorisk attribut indeholder to eller flere kategorier eller typer. En numerisk attribut indeholder kvantitative data og har en slags måling tilknyttet.

Med en numerisk attribut som *årlig indkomst* eller *medlemskabsperiode* som den primære attribut foreslår systemet segmenter, der har en højere eller lavere gennemsnitsværdi af den numeriske attribut sammenlignet med alle kunder.

En kategorisk attribut som *kundetilfredshed* som den primære attribut resulterer i foreslåede segmenter, der har en højere eller lavere procentdel af kunder, der tilhører en bestemt kategori, sammenlignet med procentdelen af alle kunder, der tilhører samme kategori. For eksempel vælges *kundetilfredshed* som den primære attribut og består af tre kategorier (*Lav*, *Mellem* og *Høj*). For hver kategori foreslås det, at segmenterne har en højere eller lavere procentdel af kunder, der tilhører den pågældende kategori, i forhold til procentdelen af alle kunder i samme kategori. Hvis 22 % af alle kunder har *Høj* tilfredshed, foreslås der kun de segmenter, der har en højere eller lavere procentdel af kunder med en *høj* tilfredshed i forhold til 22 %, for den pågældende kategori. På samme måde vil der blive foreslået segmenter for hver af de andre kategorier (*Lav* og *Mellem*), hvis de er statistisk signifikante.

> [!NOTE]
> I øjeblikket understøtter vi kun primære kategoriske attributter, der har op til 10 kategorier. Hvis du vil se målgruppeforslag baseret på en primær attribut med mere end 10 kategorier, anbefales det at gruppere nogle af kategorierne for at reducere antallet af kategorier til 10 eller færre. Denne begrænsning gælder kun for primære attributter. For at påvirke kategoriske egenskaber understøtter vi i øjeblikket maksimalt 100 kategorier.

## <a name="generate-suggested-segments"></a>Generér foreslåede målgrupper

1. Gå til **Segmenter**, og vælg fanen **Forslag (forhåndsversion)**.

1. Vælg **Søg efter nye forslag**, og vælg **Forbedring af en måleenhed/metrikværdi**. Vælg **Start**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Valg af en bedre måleenhed i de foreslåede segmenter.":::

1. Du kan vælge en kundeattribut eller måling i stedet for en primær attribut og vælge **Næste**.

1. Vælg de attributter, der påvirker, og vælg **Kør**.

   > [!TIP]
   > Hvis du vælger flere attributter, forbedres chancerne for at evaluere, hvordan de påvirker den primære attribut. Medtag ikke attributter, der ikke har nogen indflydelse på den primære attribut. Hvis alle dine kunder f.eks. kommer fra et bestemt land, skal du ikke medtage attributten *land*, da den ikke har nogen indflydelse på outputtet.

Afhængigt af antallet af kundeprofiler og udvalgte attributter kan det tage et par minutter at behandle de valgte attributter.

## <a name="manage-suggested-segments"></a>Administrere foreslåede segmenter

Gå til **Segmenter**, og vælg fanen **Forslag (forhåndsversion**). Vælg et foreslået **segment i sektionen Forslag til** attributbaserede segmenter for at få vist tilgængelige handlinger.

- **Vis** de foreslåede segmentdetaljer og attributværdier eller -regler, som AI-modellen lærte.
- **Gem som segment** forslag som et segment. Den vises under fanen **Alle segmenter** og kan [opdateres, redigeres eller slettes](segments.md).
- **Rediger attributter,** og rediger de konfigurerede attributter, som erstatter de aktuelle forslag.
- **Opdater forslag** for at opdatere forslagene, mens du bevarer konfigurerede attributter.

## <a name="limitations"></a>Begrænsninger

1. Uoverensstemmelse i anslået segmentstørrelse: Hvis du vælger en primær attribut, der indeholder tomme værdier, kan det påvirke den anslåede segmentstørrelse i forslagene til segment. Når et sådant segment gemmes, kan den faktiske segmentstørrelse være forskellig fra det oprindelige estimat.

2. Primære booleske attributter af typen fungerer ikke: I øjeblikket understøtter vi kun streng- og numeriske datatyper som den primære attribut.

3. Foreslåede segmenter er ikke så markante: Husk på, at de valgte attributter og distributionen af værdierne for disse attributter påvirker resultaterne. Du kan ændre dine attributter, der påvirker, eller endda din primære attribut, for at få forskellige resultater.

[!INCLUDE [footer-include](includes/footer-banner.md)]