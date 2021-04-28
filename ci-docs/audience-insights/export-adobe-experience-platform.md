---
title: Eksportere Customer Insights-data til Adobe Experience Platform
description: Få at vide, hvordan du kan bruge målgruppeindsigtssegmenter i Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760094"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Bruge Customer Insights-segmenter i Adobe Experience Platform (forhåndsversion)

Som bruger af målgruppeindsigt for Dynamics 365 Customer Insights har du muligvis oprettet segmenter for at gøre marketingkampagnerne mere effektive ved at målrette relevante målgrupper. Hvis du vil bruge et segment målgruppeindsigt i Adobe Experience Platform og programmer som Adobe Campaign Standard, skal du følge et par trin, der beskrives i denne artikel.

:::image type="content" source="media/AEP-flow.png" alt-text="Procesdiagram over de trin, der beskrives i denne artikel.":::

## <a name="prerequisites"></a>Forudsætninger

-   Dynamics 365 Customer Insights-licens
-   Adobe Experience Platform-licens
-   Adobe Campaign Standard-licens
-   Azure Blob Storage-konto

## <a name="campaign-overview"></a>Kampagneoversigt

For bedre at kunne forstå, hvordan du kan bruge segmenter målgruppeindsigt i Adobe Experience Platform, kan vi se på en fiktiv eksempelkampagne.

Lad os antage, at din virksomhed tilbyder en månedlig, abonnementsbaseret service til kunderne i USA. Du vil identificere kunder, hvis abonnementer forfalder til fornyelse inden for de næste otte dage, men som endnu ikke har fornyet deres abonnement. Hvis du vil bevare disse kunder, skal du sende dem et kampagnetilbud via mail ved hjælp af Adobe Experience Platform.

I dette eksempel vil vi køre kundemailkampagnen én gang. Denne artikel dækker ikke kørsel af kampagnen mere end én gang.

## <a name="identify-your-target-audience"></a>Identificere din målgruppe

I dette scenario antages det, at mailadresserne på kunderne er tilgængelige i målgruppeindsigt, og deres kampagnepræferencer er blevet analyseret for at identificere medlemmer af dette segment.

Det [segment, du definerede i målgruppeindsigt](segments.md), kaldes **ChurnProneCustomers**, og du planlægger at sende disse kunder mailkampagnen.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skærmbillede af segmentsiden med segmentet ChurnProneCustomers oprettet.":::

Den mail med tilbud, du vil sende, indeholder kundens fornavn, efternavn og slutdatoen for abonnementet. Den giver kunderne den rabat, de får, hvis de fornyer deres abonnement, inden det udløber.

## <a name="export-your-target-audience"></a>Eksportere din målgruppe

Når målgruppen er identificeret, kan vi konfigurere eksporten fra målgruppeindsigt til en Azure Blob Storage-konto.

### <a name="configure-a-connection"></a>Konfiguration af en forbindelse

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Azure Blob Storage**, eller vælg **Konfigurer** i **Azure Blob Storage**-feltet:

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigurationsfelt til Azure Blob Storage."::: sådan konfigurerer du forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv **Firmanavn**, **Firmanøgle** og **Beholder** for den Blob-lagerkonto, du vil eksportere segmentet til.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skærmbillede af lagerkontoens konfiguration. "::: 
   
    - Du kan få mere at vide om, hvordan du finder Blob storage-kontonavnet og kontonøglen, under [Administration af indstillinger for lagerkonti i Azure-portalen](/azure/storage/common/storage-account-manage).
    - Du kan få mere at vide om, hvordan du opretter en objektbeholder, i [Oprette en objektbeholder](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Vælg **Gem** for at fuldføre forbindelsen. 

### <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Hvis du vil oprette en ny eksport, skal du vælge **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Azure Blob Storage i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Vælg det segment, du vil eksportere. I dette eksempel er det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skærmbillede af brugergrænsefladen til valg af segment, hvor segmentet ChurnProneCustomers er valgt.":::

1. Vælg **Gem**.

Når du har gemt eksportdestinationen, finder du den under **Data** > **Eksport**.

Du kan nu [eksportere segmentet efter behov](export-destinations.md#run-exports-on-demand). Eksporten vil også køre med alle [planlagte opdateringer](system.md).

> [!NOTE]
> Sørg for, at antallet af poster i det eksporterede segment ligger inden for den tilladte grænse for din Adobe Campaign Standard-licens.

Eksporterede data lagres i den Azure Blob Storage-objektbeholder, du har konfigureret ovenfor. Følgende mappesti oprettes automatisk i objektbeholderen:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Filen *model.json* for de eksporterede objekter findes på *%ExportDestinationName%*-niveau.

Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definere XDM (Experience Data Model) i Adobe Experience Platform

Før de eksporterede data fra målgruppeindsigt kan bruges i Adobe Experience Platform, skal vi definere Experience Data Model-skemaet og [konfigurere dataene til kundeprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Få mere at vide om, hvad [XDM er](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html), og forstå det [grundlæggende i skemakompositionen](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importere data til Adobe Experience Platform

Nu, hvor alt er på plads, skal vi importere de forberedte målgruppedata fra målgruppeindsigt i Adobe Experience Platform.

Du skal først [oprette en Azure Blob Storage-kildeforbindelse](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Når du har defineret kildeforbindelsen, skal du [konfigurere et dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for en batchforbindelse til skylageret for at importere segmentoutputtet fra målgruppeindsigt i Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Oprette en målgruppe i Adobe Campaign Standard

Hvis du vil sende mailen for denne kampagne, skal du bruge Adobe Campaign Standard. Når dataene er importeret til Adobe Experience Platform, skal vi [oprette en målgruppe](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) i Adobe Campaign Standard ved hjælp af dataene på Adobe Experience Platform.

Lær at [bruge segmentgeneratoren](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) i Adobe Campaign Standard til at definere en målgruppe baseret på dataene i Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Oprette og sende mailen ved hjælp af Adobe Campaign Standard

Opret mailindholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) derefter mailen.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på mail med tilbud om fornyelse fra Adobe Campaign Standard.":::
