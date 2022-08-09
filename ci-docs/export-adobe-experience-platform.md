---
title: Eksportere segmenter til Adobe Experience Platform (forhåndsversion)
description: Få mere at vide om, hvordan du bruger Customer Insights-segmenter i Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195283"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Eksportere segmenter til Adobe Experience Platform (forhåndsversion)

Eksportér de målgrupper, der er relevante for målgruppen til Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Procesdiagram over de trin, der beskrives i denne artikel.":::

## <a name="prerequisites"></a>Forudsætninger

- En Adobe Experience Platform-licens.
- En Adobe Campaign Standard-licens.
- Et [Azure Blob Storage-kontonavn](/azure/storage/blobs/create-data-lake-storage-account) og en kontonøgle. Du kan finde flere oplysninger i [Administrere lagerkontoindstillinger i Azure-portalen](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage-forbindelse](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Kampagneoversigt

For bedre at kunne forstå, hvordan du kan bruge segmenter fra Customer Insights i Adobe Experience Platform, kan vi se på en fiktiv eksempelkampagne.

Lad os antage, at din virksomhed tilbyder en månedlig, abonnementsbaseret service til kunderne i USA. Du vil identificere kunder, hvis abonnementer forfalder til fornyelse inden for de næste otte dage, men som endnu ikke har fornyet deres abonnement. Hvis du vil bevare kunderne, skal du sende dem et kampagnetilbud via mail ved hjælp af Adobe Experience Platform.

I dette eksempel vil vi køre kundemailkampagnen én gang. Denne artikel dækker ikke kørsel af kampagnen mere end én gang.

## <a name="identify-your-target-audience"></a>Identificere din målgruppe

I dette scenario antages det, at kundernes e-mailadresser er tilgængelige i Customer Insights, og at deres kampagnepræferencer er blevet analyseret for at identificere medlemmer af dette segment.

Det [segment, du definerede i Customer Insights](segments.md), kaldes **ChurnProneCustomers**, og du planlægger at sende disse kunder e-mailkampagnen.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Skærmbillede af segmentsiden med segmentet ChurnProneCustomers oprettet.":::

Den mail med tilbud, du vil sende, indeholder kundens fornavn, efternavn og slutdatoen for abonnementet. Den giver kunderne den rabat, de får, hvis de fornyer deres abonnement, inden det udløber.

## <a name="export-your-target-audience"></a>Eksportere din målgruppe

Vi konfigurerer eksporten fra Customer Insights til en Azure Blob Storage-konto.

### <a name="set-up-connection-to-azure-blob-storage"></a>Konfigurer forbindelsen til Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse,** og vælg **Azure Blob Storage**.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv **Firmanavn**, **Firmanøgle** og **Beholder** for den Blob Storage-konto, du vil eksportere segmentet til.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Skærmbillede af lagerkontoens konfiguration. ":::

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Gem** for at fuldføre forbindelsen.

### <a name="configure-an-export"></a>Konfigurere en eksport

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj eksport**.

1. Vælg en forbindelse i sektionen Azure Blob Storage i feltet **Forbindelse til eksport**. Kontakt en administrator, hvis der ikke er nogen forbindelse.

1. Angiv et navn for eksporten.

1. Vælg det segment, du vil eksportere. I dette eksempel er det **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Skærmbillede af brugergrænsefladen til valg af segment, hvor segmentet ChurnProneCustomers er valgt.":::

1. Vælg **Gem**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Kontrollér, at antallet af poster i det eksporterede segment ligger inden for den tilladte grænse for Adobe Campaign Standard-licensen.

Eksporterede data gemmes i den Azure Blob Storage-beholder, du har konfigureret. Følgende mappestier oprettes automatisk i objektbeholderen:

- For kildeobjekter og objekter, der er oprettet af systemet:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Filen *model.json* for de eksporterede objekter findes på *%ExportDestinationName%*-niveau.

  Eksempel: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definer XDM (Experience Data Model) i Adobe Experience Platform

Inden de eksporterede data fra Customer Insights kan bruges i Adobe Experience Platform, skal du definere skemaet Experience Data Model og [konfigurere dataene til kundeprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Få mere at vide om, hvad [XDM er](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html), og forstå det [grundlæggende i skemakompositionen](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importér data i Adobe Experience Platform

Importér de publikum data fra Customer Insights til Adobe Experience Platform.

1. [Opret en Azure Blob Storage-kildeforbindelse](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Konfigurer et dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) til en batchforbindelse til skylageret for at importere segmentoutput fra Customer Insights til Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Oprette en målgruppe i Adobe Campaign Standard

Når du vil sende e-mailen til denne kampagne, skal du bruge Adobe Campaign Standard.

1. [Opret en publikum](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) i Adobe Campaign Standard ved hjælp af dataene i Adobe Experience Platform.

1. [Brug af segmentgenerator](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) i Adobe Campaign Standard til at definere en målgruppebaseret på dataene i Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Oprette og sende e-mailen ved hjælp Adobe Campaign Standard

Opret mailindholdet, og [test og send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) derefter mailen.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Eksempel på e-mail med tilbud på fornyelse fra Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
