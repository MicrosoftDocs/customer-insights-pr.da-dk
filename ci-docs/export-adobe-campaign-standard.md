---
title: Eksportere Customer Insights-segmenter til Adobe Campaign Standard (forhåndsversion)
description: Få mere at vide om, hvordan du bruger Customer Insights-segmenter i Adobe Campaign Standard.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195513"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Eksportere Customer Insights-segmenter til Adobe Campaign Standard (forhåndsversion)

Eksportér de målgrupper, der er relevante for målgruppen til Adobe Campaign Standard.

:::image type="content" source="media/ACS-flow.png" alt-text="Procesdiagram over de trin, der beskrives i denne artikel.":::

## <a name="prerequisites"></a>Forudsætninger

- En Adobe Campaign Standard-licens.
- Et [Azure Blob Storage-kontonavn](/azure/storage/blobs/create-data-lake-storage-account) og en kontonøgle. Du kan finde flere oplysninger i [Administrere lagerkontoindstillinger i Azure-portalen](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage-forbindelse](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Kampagneoversigt

For bedre at kunne forstå, hvordan du kan bruge segmenter fra Customer Insights i Adobe Experience Platform, kan vi se på en fiktiv eksempelkampagne.

Lad os antage, at din virksomhed tilbyder en månedlig, abonnementsbaseret service til kunderne i USA. Du vil identificere kunder, hvis abonnementer forfalder til fornyelse inden for de næste otte dage, men som endnu ikke har fornyet deres abonnement. Hvis du vil bevare kunderne, skal du sende dem et kampagnetilbud via mail ved hjælp af Adobe Campaign Standard.

I dette eksempel vil vi køre kundemailkampagnen én gang. Denne artikel dækker ikke kørsel af kampagnen mere end én gang. Customer Insights og Adobe Campaign Standard kan dog også konfigureres til at fungere i et tilbagevendende kampagnescenarie.

## <a name="identify-your-target-audience"></a>Identificere din målgruppe

I dette scenario antages det, at kundernes e-mailadresser er tilgængelige i Customer Insights, og at deres kampagnepræferencer er blevet analyseret for at identificere medlemmer af dette segment.

Det [segment, du definerede i Customer Insights](segments.md), kaldes **ChurnProneCustomers**, og du planlægger at sende disse kunder e-mailkampagnen.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skærmbillede af segmentsiden med segmentet ChurnProneCustomers oprettet.":::

Den mail med tilbud, du vil sende, indeholder kundens fornavn, efternavn og slutdatoen for abonnementet. Den giver kunderne den rabat, de får, hvis de fornyer deres abonnement, inden det udløber.

## <a name="export-your-target-audience"></a>Eksportere din målgruppe

### <a name="set-up-connection-to-adobe-campaign"></a>Konfigurer forbindelse til Adobe Campaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Adobe Campaign**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv **Kontonavn**, **Kontonøgle** og **Beholder** for Blob Storage-kontoen.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skærmbillede af lagerkontoens konfiguration. ":::

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Gem** for at fuldføre forbindelsen.

### <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse fra sektionen Adobe Campaign i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Vælg det segment, du vil eksportere. I dette eksempel er det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skærmbillede af brugergrænsefladen til valg af segment, hvor segmentet ChurnProneCustomers er valgt.":::

1. Vælg **Næste**.

1. Tilknyt **kildefelterne** fra Customer Insights-segmentet til **målgruppe**-feltnavnene i profilskemaet Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Felttilknytning for Adobe Campaign Standard-connector.":::

   Vælg **Tilføj attribut**, hvis du vil tilføje flere attributter. Målgruppenavnet kan være et andet end kildefeltnavnet, så du stadig kan knytte segmentoutput fra Customer Insights til Adobe Campaign Standard, hvis felterne ikke har samme navn i de to systemer.

   > [!NOTE]
   > E-mail-adresse bruges som et identitetsfelt, men du kan bruge et hvilket som helst andet id fra kundeprofilen til at knytte data til Adobe Campaign Standard.

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Kontrollér, at antallet af poster i det eksporterede segment ligger inden for den tilladte grænse for Adobe Campaign Standard-licensen.

Eksporterede data lagres i den Azure Blob Storage-objektbeholder, du har konfigureret ovenfor. Følgende mappesti oprettes automatisk i beholderen: *%ContainerName%/CustomerInsights_%instanceID%/% exportmappe-name%_%segmentname%_%timestamp%.csv*

Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurer Adobe Campaign Standard

Eksporterede segmenter indeholder de kolonner, du har valgt, mens du konfigurer eksport. Disse data kan bruges til at [oprette profiler i Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Hvis du vil bruge Adobe Campaign Standard, [skal du udvide profilskemaet i](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) i Adobe Campaign Standard, så det inkluderer yderligere to felter.

I eksemplet er disse felter Segmentnavn og segmentdato. Disse felter bruges til at identificere profilerne i Adobe Campaign Standard, som vi vil målrette mod denne kampagne.

Hvis der ikke findes andre poster i Adobe Campaign Standard, ud over hvad du vil importere, kan du springe dette trin over.

## <a name="import-data-into-adobe-campaign-standard"></a>Importere data til Adobe Campaign Standard

Importer de målgruppedata fra Customer Insights til Adobe Campaign Standard for at [oprette profiler ved hjælp af en arbejdsproces](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Importarbejdsprocessen i billedet nedenfor er konfigureret til at køre hver ottende time og søge efter eksporterede Customer Insights-segmenter (.csv-fil i Azure Blob Storage). I arbejdsprocessen udtrækkes indholdet af .csv-filen i en angivet kolonnerækkefølge. Arbejdsprocessen er opbygget til at udføre grundlæggende fejlbehandling og sikre, at hver post har en e-mailadresse, inden dataene sendes til Adobe Campaign Standard. I arbejdsprocessen udtrækkes også segmentnavnet fra filnavnet, inden det overgives til Adobe Campaign Standard-profildata.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Skærmbillede af en importarbejdsproces i Adobe Campaign Standard-brugergrænseflade.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Hente målgruppe i Adobe Campaign Standard

Når dataene er importeret til Adobe Campaign Standard, [kan du oprette en arbejdsproces](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) og [forespørge](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) kunderne baseret på segmentnavnet og segmentdatoen for at vælge de profiler, der blev identificeret til eksempelkampagnen.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Oprette og sende e-mailen ved hjælp Adobe Campaign Standard

Opret mailindholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) derefter mailen.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på e-mail med tilbud på fornyelse fra Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
