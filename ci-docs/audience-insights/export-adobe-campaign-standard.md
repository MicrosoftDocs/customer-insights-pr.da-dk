---
title: Eksportere Customer Insights-data til Adobe Campaign Standard
description: Få at vide, hvordan du kan bruge målgruppeindsigtssegmenter i Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760274"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Bruge Customer Insights-segmenter i Adobe Campaign Standard (forhåndsversion)

Som bruger af målgruppeindsigt for Dynamics 365 Customer Insights har du muligvis oprettet segmenter for at gøre marketingkampagnerne mere effektive ved at målrette relevante målgrupper. Hvis du vil bruge et segment målgruppeindsigt i Adobe Experience Platform og programmer som Adobe Campaign Standard, skal du følge et par trin, der beskrives i denne artikel.

:::image type="content" source="media/ACS-flow.png" alt-text="Procesdiagram over de trin, der beskrives i denne artikel.":::

## <a name="prerequisites"></a>Forudsætninger

-   Dynamics 365 Customer Insights-licens
-   Adobe Campaign Standard-licens
-   Azure Blob Storage-konto

## <a name="campaign-overview"></a>Kampagneoversigt

For bedre at kunne forstå, hvordan du kan bruge segmenter målgruppeindsigt i Adobe Experience Platform, kan vi se på en fiktiv eksempelkampagne.

Lad os antage, at din virksomhed tilbyder en månedlig, abonnementsbaseret service til kunderne i USA. Du vil identificere kunder, hvis abonnementer forfalder til fornyelse inden for de næste otte dage, men som endnu ikke har fornyet deres abonnement. Hvis du vil bevare disse kunder, skal du sende dem et kampagnetilbud via mail ved hjælp af Adobe Campaign Standard.

I dette eksempel vil vi køre kundemailkampagnen én gang. Denne artikel dækker ikke kørsel af kampagnen mere end én gang. Men målgruppeindsigt og Adobe Campaign Standard kan dog konfigureres til at fungere i et tilbagevendende kampagnescenarie.

## <a name="identify-your-target-audience"></a>Identificere din målgruppe

I dette scenario antages det, at mailadresserne på kunderne er tilgængelige i målgruppeindsigt, og deres kampagnepræferencer er blevet analyseret for at identificere medlemmer af dette segment.

Det [segment, du definerede i målgruppeindsigt](segments.md), kaldes **ChurnProneCustomers**, og du planlægger at sende disse kunder mailkampagnen.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skærmbillede af segmentsiden med segmentet ChurnProneCustomers oprettet.":::

Den mail med tilbud, du vil sende, indeholder kundens fornavn, efternavn og slutdatoen for abonnementet. Den giver kunderne den rabat, de får, hvis de fornyer deres abonnement, inden det udløber.

## <a name="export-your-target-audience"></a>Eksportere din målgruppe

### <a name="configure-a-connection"></a>Konfiguration af en forbindelse

Når målgruppen er identificeret, kan vi konfigurere eksporten fra målgruppeindsigt til en Azure Blob Storage-konto.

1. I målgruppeindsigt skal du gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Adobe-kampagne** for at konfigurere forbindelsen, eller vælg **Konfigurer** i feltet **Adobe-kampagne**

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigurationsfelt til Adobe Campaign Standard.":::

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Angiv **Firmanavn**, **Firmanøgle** og **Beholder** for den Azure Blob-lagerkonto, du vil eksportere segmentet til.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skærmbillede af lagerkontoens konfiguration. "::: 

   - Du kan få mere at vide om, hvordan du finder navnet på og kontonøglen til Azure Blob Storage-kontoen, under [Administrere indstillinger for lagerkonto i Azure-portalen](/azure/storage/common/storage-account-manage).

   - Du kan få mere at vide om, hvordan du opretter en objektbeholder, i [Oprette en objektbeholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Vælg **Gem** for at fuldføre forbindelsen.

### <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Hvis du vil oprette en ny eksport, skal du vælge **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Adobe Campaign i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Vælg det segment, du vil eksportere. I dette eksempel er det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skærmbillede af brugergrænsefladen til valg af segment, hvor segmentet ChurnProneCustomers er valgt.":::

1. Vælg **Næste**.

1. Nu skal du knytte **Kilde**-felterne fra kildekampagneindsigtssegmentet til **Mål**-feltnavnene i Adobe Campaign Standard-profilskemaet.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Felttilknytning for Adobe Campaign Standard-connector.":::

   Vælg **Tilføj attribut**, hvis du vil tilføje flere attributter. Målnavnet kan være et andet end kildefeltnavnet, så du stadig kan knytte segmentoutput fra målgruppeindsigt til Adobe Campaign Standard, hvis felterne ikke har det samme navn i de to systemer.

   > [!NOTE]
   > Mailadressen bruges som identitetsfelt, men du kan bruge et hvilket som helst andet id fra din målgruppeindsigts kundeprofil til at knytte data til Adobe Campaign Standard.

1. Vælg **Gem**.

Når du har gemt eksportdestinationen, finder du den under **Data** > **Eksport**.

Du kan nu [eksportere segmentet efter behov](export-destinations.md#run-exports-on-demand). Eksporten vil også køre med alle [planlagte opdateringer](system.md).

> [!NOTE]
> Sørg for, at antallet af poster i det eksporterede segment ligger inden for den tilladte grænse for din Adobe Campaign Standard-licens.

Eksporterede data lagres i den Azure Blob Storage-objektbeholder, du har konfigureret ovenfor. Følgende mappesti oprettes automatisk i objektbeholderen:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurere Adobe Campaign Standard

Når et segment fra målgruppeindsigt eksporteres, indeholder det de kolonner, du har valgt, mens du definerer eksportdestinationen i forrige trin. Disse data kan bruges til at [oprette profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Hvis du vil bruge segmentet i Adobe Campaign Standard, skal du udvide profilskemaet i Adobe Campaign Standard, så det inkluderer yderligere to felter. Lær at [udvide profilressourcen](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) med nye felter i Adobe Campaign Standard.

I eksemplet er disse felter *Segmentnavn og segmentdato (valgfrit).*

Vi bruger disse felter til at identificere profilerne i Adobe Campaign Standard, som vi vil målrette mod denne kampagne.

Hvis der ikke er andre poster i Adobe Campaign Standard, ud over det, du vil importere, kan du springe dette trin over.

## <a name="import-data-into-adobe-campaign-standard"></a>Importere data til Adobe Campaign Standard

Nu, hvor alt er på plads, skal vi importere de forberedte målgruppedata fra målgruppeindsigt i Adobe Campaign Standard for at oprette profiler. Lær at [importere profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) ved hjælp af en arbejdsproces.

Importarbejdsprocessen i billedet nedenfor er konfigureret til at køre hver 8. time og søger efter eksporterede segmenter til målgruppeindsigt (.csv-fil i Azure Blob Storage). I arbejdsprocessen udtrækkes indholdet af .csv-filen i en angivet kolonnerækkefølge. Arbejdsprocessen er opbygget til at udføre grundlæggende fejlbehandling og sikre, at hver post har en mailadresse, inden dataene i Adobe Campaign Standard anvendes. I arbejdsprocessen udtrækkes også segmentnavnet fra filnavnet, inden det overgives til ACS-profildata.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Skærmbillede af en importarbejdsproces i brugergrænsefladen i Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Hente målgruppe i Adobe Campaign Standard

Når dataene er importeret til Adobe Campaign Standard, kan du [oprette en arbejdsproces](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) og [forespørge](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) på kunderne baseret på *Segmentnavn* og *Segmentdato* for at vælge de profiler, der blev identificeret for eksempelkampagnen.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Oprette og sende mailen ved hjælp af Adobe Campaign Standard

Opret mailindholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) derefter mailen.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på mail med tilbud om fornyelse fra Adobe Campaign Standard.":::
