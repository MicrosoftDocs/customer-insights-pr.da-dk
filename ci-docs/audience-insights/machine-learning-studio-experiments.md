---
title: Eksperimenter i Machine Learning Studio (klassisk)
description: Brug Machine Learning Studio (klassisk)-modeller i Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 71881f7e1f9448fe0a7d6d92b8102b8b42de7c2a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598332"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Brug modeller baseret på Azure Machine Learning Studio (klassisk)

De samlede data i Dynamics 365 Customer Insights er en kilde til opbygning af maskinelle indlæringsmodeller, der kan generere yderligere forretningsindsigt. Customer Insights er integreret med Machine Learning Studio (classic) til brug af dine egne brugerdefinerede modeller. Hvis du vil se, hvordan modeller, der er udviklet i Azure Machine Learning, er integreret med Customer Insights, kan du gå til [Azure Machine Learning-eksperimenter](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Forudsætninger

- Adgang til Customer Insights
- Aktivt abonnement på Azure Enterprise
- [Samlede kundeprofiler](data-unification.md)
- Konfiguration af [Eksport af objekter til Azure Blob Storage](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Konfiguration af Machine Learning Studio, klassisk

I første trin skal vi oprette et arbejdsområde, som Machine Learning Studio (classic) kan åbnes i.

1. Gå til [https://www.portal.azure.com](https://www.portal.azure.com/), og log på.

1. Vælg **Opret en ressource**.

1. Søg i **Machine Learning Studio-arbejdsområde**, og vælg **Opret**.

1. Angiv de nødvendige detaljer for at [oprette arbejdsområdet](/azure/machine-learning/studio/create-workspace). Vælg **Prissætningsniveau for webtjenesteplan** baseret på den mængde data, du vil importere. Du opnår den bedste ydeevne, hvis du vælger den **Placering**, der er geografisk nærmest.

1. Når ressourcen er oprettet, vises dashboardet i arbejdsområdet for Machine Learning Studio. Vælg **Start Machine Learning Studio**.

   ![Brugergrænsefladen i Azure Machine Learning Studio](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Arbejde med Azure Machine Learning Studio

Du kan nu oprette et nyt eksperiment eller importere en fra en eksisterende eksperimentskabelon fra eksempelgalleriet. Der findes prøveeksperimenter i tre standardscenarier:

- [Forudsigelse af afgang](#churn-analysis)

- [Kundens levetidsværdi](#customer-lifetime-value-prediction)

- [Produktanbefaling eller næstbedste handling](#productrecommendation-or-next-best-action)

1. Hvis du opretter et nyt eksperiment eller bruger en eksperimentskabelon fra galleriet, skal du konfigurere egenskaberne for **Importér data**. Brug automatiseret oplevelse, eller angiv direkte oplysninger for at få adgang til det Azure Blob Storage, der indeholder dine data.  

   ![Azure Machine Learning Studio-eksperiment](media/azure-machine-learning-studio-experiment.png)

1. Nu kan du oprette en brugerdefineret behandlingspipeline for at rense og forbehandle dataene, udtrække funktioner og oplære en egnet model.

1. Test og optimer modellens ydeevne.

1. Når du er tilfreds med kvaliteten af en model, skal du vælge **Konfigurer webtjeneste** > **Webtjeneste til forudsigelse**. Denne indstilling importerer den oplærte model og din pipeline til videreudvikling af funktioner fra oplæringseksperimentet til en forudsigelsestjeneste. Forudsigelsestjenesten kan anvende et andet sæt inputdata i det skema, der bruges i oplæringseksperimentet, til at levere forudsigelser.

   ![Konfigurere en webtjeneste til forudsigelse](media/predictive-webservice-control.png)

1. Når forudsigelseseksperimentet på webtjenesten er vellykket udført, kan du implementere det til automatisk planlægning. Hvis webtjenesten skal fungere sammen med Customer Insights, skal du vælge **Installer webtjeneste** > **Installer prøveversion af webtjeneste [ny]**. [Få mere at vide om installation af webtjeneste](/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Installere en webtjeneste til forudsigelse](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Eksempelmodeller fra galleriet

Vi bruger et fiktivt scenario med Contoso Hotel til modellerne i denne artikel. Contoso Hotel indsamler følgende data:

- CRM-data, der består af aktivitet under hotelophold. Datasættet indeholder oplysninger om datoerne for hver registreret kundes ophold. Det indeholder også oplysninger om reservation, værelsestyper, detaljer om forbrug osv. Dataene strækker sig over fire år, fra januar 2014 til januar 2018.
- Kundeprofiler for hotelgæster. Disse profiler indeholder oplysninger om hver enkelt kunde, herunder navn, fødselsdato, postadresse, køn og telefonnummer.
- Brug af servicer, der tilbydes af hotellet, f.eks. spa, vask, WiFi eller kurer. Disse oplysninger logføres for hver registrerede kunde. Brug af servicer er typisk knyttet til opholdet. I nogle tilfælde kan servicer bruges af kunder, der ikke bor på hotellet.

## <a name="churn-analysis"></a>Afgangsanalyse

Afgangsanalyse gælder for forskellige forretningsområder. I dette eksempel ser vi på ophør af brug af en tjeneste, særligt i forbindelse med hoteltjenester, som beskrevet ovenfor. Eksemplet indeholder et arbejdseksempel på en komplet modelpipeline, der kan bruges som udgangspunkt for alle andre afgangsmodeltyper.

### <a name="definition-of-churn"></a>Definition af afgang

Definitionen af afgang kan variere afhængigt af scenariet. I dette eksempel skal en gæst, som ikke har besøgt hotellet inden for det seneste år, betragtes som værende forsvundet som kunde.  

Eksperimentskabelonen kan importeres fra galleriet. Du skal først sikre dig, at du importerer dataene for **Aktivitet under hotelophold**, **Kundedata** og **Serviceforbrugsdata** fra Azure Blob Storage.

   ![Importere data til afgangsmodel](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Videreudvikling af funktioner

På baggrund af definitionen af afgang skal vi først identificere de rå funktioner, som har indflydelse på navnet. Derefter behandler vi disse rå funktioner i numeriske funktioner, der kan bruges sammen med de maskinelle indlæringsmodeller. Dataintegration sker i Customer Insights, så vi kan forbinde disse tabeller ved hjælp af *Kunde-id*.

   ![Joinforbinde importerede data](media/join-imported-data.png)

Videreudvikling af funktioner til opbygning af modellen til afgangsanalyse kan være lidt vanskelig. Disse data er en funktion af tid, hvor der registreres nye hotelaktiviteter dagligt. Under videreudviklingen af funktionerne vil vi generere statiske funktioner ud fra de dynamiske data. I dette tilfælde skal vi generere flere funktioner ud fra hotelaktivitet med et glidende vindue på ét år. Vi vil også udvide kategorifunktionerne, f.eks. værelsestype eller reservationstype i separate funktioner ved hjælp af engangskodning.  

Endelig liste over funktioner:

| **Tal**  | **Original_Column**          | **Afledte funktioner**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Værelsestype                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Reservationstype                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Rejsekategori              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Anvendt beløb                | TotalDollarSpent                                                                                                                          |
| 5           | Datoer for ind- og udtjekning  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Brug af service                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Modeludvælgelse

Nu skal vi vælge den optimale algoritme, der skal bruges. I dette tilfælde er de fleste funktioner baseret på kategorifunktioner. Modeller, der er baseret på et beslutningstræ, fungerer som regel godt. Hvis der kun er numeriske funktioner, kan neurale netværk være et bedre valg. Support Vector Machine (SVM) er også en god kandidat i disse situationer. Det kræver dog en vis justering for at opnå den bedste ydeevne. Vi vælger en **Boostet beslutningstræ med to klasser**-model som første valg efterfulgt af **SVM med to klasser** som den anden model. Med Azure Machine Learning Studio kan du udføre A/B-test, så det er fordelagtigt at starte med to modeller i stedet for én.

Følgende billede viser modeloplæringen og evalueringspipelinen fra Azure Machine Learning Studio:

![Afgangsmodel i Azure Machine Learning Studio](media/azure-machine-learning-model.png)

Vi anvender også en teknik, der kaldes **Permutation af funktioners vigtighed**, et vigtigt aspekt i forbindelse med modeloptimering. Indbyggede modeller har kun lidt eller ingen indsigt i en bestemt funktions indflydelse på den endelige forudsigelse. Ved beregning af vigtigheden af funktioner bruges en brugerdefineret algoritme til at beregne de enkelte funktioners indflydelse på resultatet for en bestemt model. Vigtigheden af funktionen normaliseres mellem + 1 og -1. En negativ indflydelse betyder, at den tilsvarende funktion har en kontraintuitiv indvirkning på resultatet og bør fjernes fra modellen. En positiv indflydelse indikerer, at funktionen i høj grad bidrager til at opfylde forudsigelsen. Disse værdier er ikke korrelationskoefficienter, da de er forskellige målepunkter. Du kan finde flere oplysninger i [Permutation af funktioners vigtighed](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Hele [afgangseksperimentet er tilgængeligt i Azure AI Gallery](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Forudsigelse af kundens levetidsværdi

Beregningen af værdien for kundens levetid (customer lifetime value – CLTV) er et af de vigtigste målepunkter, som en virksomhed kan bruge til at vurdere og segmentere kunder. For hotelvirksomheden er det vigtigt at kende deres kunder. For eksempel er det vigtigt at have oplysninger, der kan hjælpe med at forstå, hvilke faktorer der skaber gode kunder. Det hjælper hotellets ledelse at vurdere, hvilke funktioner de skal fokusere på og forbedre for at imødekomme deres højt betalende kunder. Disse beslutninger kan have direkte indvirkning på salg og indtjening.  

### <a name="definition-of-cltv"></a>Definition af CLTV

I dette eksempel definerer vi CLTV for en kunde som det samlede beløb, som kunden forventes at bruge inden for de næste 365 dage. Vi vil bruge værdien af de seneste tre års data for alle kunder til at forudse denne værdi.

### <a name="featurization"></a>Videreudvikling af funktioner

I dette tilfælde vil videreudvikling af funktioner (featurization) være ligesom i afgangsscenariet. Men navnene og de forudberegnede værdier adskiller sig fra de ovenfor definerede.

### <a name="model-selection"></a>Modeludvælgelse

Forudsigelse af CLTV er et regressionsproblem, da den forudberegnede værdi er en positiv, fortløbende variabel. Afhængigt af funktionsegenskaberne vælger vi **Boostet regression for beslutningstræ** som én algoritme og **Neuralt netværksregression** som en anden algoritme til oplæring af modellen.

## <a name="product-recommendation-or-next-best-action"></a>Produktanbefaling eller næstbedste handling

Produktanbefalinger i et hotelscenarie fortolkes som anbefaling af servicer, som hotellet tilbyder til kunderne. Målet er at vælge de rette servicer for kunderne, så deres forbrug maksimeres. Det svarer til anbefalinger af film for brugere af videostreamingstjenester.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definition af produktanbefaling eller næstbedste handling

Vi definerer målet som maksimering af beløbet til serviceforbrug ved at tilbyde de bedst egnede servicer til hotelkunder i henhold til deres interesse.

### <a name="featurization"></a>Videreudvikling af funktioner

På samme måde som i afgangsmodellen forbinder vi hotellets ServiceCustomerID med CustomerID for at opbygge anbefalinger konsekvent pr. CustomerID.

![Videreudvikling af funktioner i anbefalingsmodellen](media/azure-machine-learning-model-featurization.png)

Dataene hentes fra tre forskellige objekter, og funktionerne er afledt derfra. Videreudvikling af funktioner for problemet med anbefaling adskiller sig fra afgangs- eller CLTV-scenarier. Den anbefalede model kræver inputdata i form af tre sæt funktioner.

### <a name="model-selection"></a>Modeludvælgelse

Vi anbefaler produkter eller servicer ved hjælp af algoritmen **Train Matchbox Recommender** for at oplære anbefalingsmodellen.

![Produktanbefalingsalgoritme](media/azure-machine-learning-model-recommendation-algorithm.png)

De tre inputporte for **Train Matchbox Recommender**-modellen bruger oplæringstjenestens forbrugsdata, kundebeskrivelse (valgfri) og servicebeskrivelse. Der er tre forskellige måder at give modellen point på. Den ene gælder modelevaluering, hvor NDCG-resultatet (Normalized Discounted Cumulative Gain) beregnes for at rangordne de klassificerede varer. I dette eksperiment har vi NDCG-resultatet 0,97. De to andre indstillinger er, at modellen gives point i hele det anbefalede servicekatalog, eller at det kun gives point for elementer, som brugerne ikke har brugt før.

Hvis du vil søge yderligere efter fordelingerne af anbefalingerne i hele servicekataloget, bemærker vi, at telefon, WiFi og kurer er de bedste servicer, der kan anbefales. Dette stemmer overens med det, vi har fundet fra fordelingerne i dataene for serviceforbruget:

![Anbefalingsmodellens output](media/azure-machine-learning-model-output.png)

Du kan få adgang til hele [produktanbefalingseksperimentet i Azure AI Gallery.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrer brugerdefinerede modeller

Hvis du vil bruge disse forudsigelser i Customer Insights, skal du **eksportere** forudsigelserne sammen med kunde-id'er. [Eksportér dem til den samme Azure Blob-lagerplacering](/azure/storage/common/storage-import-export-data-from-blobs), som du eksporterer kildedataene til. Webtjenesten til forudsigelse kan planlægges til at køre jævnligt og opdatere resultaterne.

Data, der genereres af den brugerdefinerede model, kan bruges til yderligere at forbedre dine kundedata. Du kan finde flere oplysninger i [Tilpasse modeller til maskinel indlæring](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]