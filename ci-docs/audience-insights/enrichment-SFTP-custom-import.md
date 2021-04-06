---
title: Forbedring af SFTP-brugerdefineret import
description: Generelle oplysninger om SFTP-brugerdefineret importforbedring.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595848"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="4ec02-103">Forbedring af kundeprofiler med brugerdefinerede data (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="4ec02-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="4ec02-104">SFTP (Secure File Transfer Protocol) brugerdefineret import giver dig mulighed for at importere data, der ikke er brug for til at gennemgå processen for datasamling.</span><span class="sxs-lookup"><span data-stu-id="4ec02-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="4ec02-105">Det er en fleksibel, sikker og nem måde at samle dine data på.</span><span class="sxs-lookup"><span data-stu-id="4ec02-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="4ec02-106">SFTP brugerdefineret import kan bruges sammen med [SFTP-eksport](export-sftp.md), der gør det muligt at eksportere de kundeprofildata, der er nødvendige for at opnå en forbedring.</span><span class="sxs-lookup"><span data-stu-id="4ec02-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="4ec02-107">Dataene kan derefter behandles og forbedres, og SFTP-brugerdefineret import kan bruges til at få de forbedrede data tilbage til målgruppeindsigt i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4ec02-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4ec02-108">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="4ec02-108">Prerequisites</span></span>

<span data-ttu-id="4ec02-109">Følgende forudsætninger skal være opfyldt, hvis du vil konfigurere SFTP-brugerdefineret import:</span><span class="sxs-lookup"><span data-stu-id="4ec02-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4ec02-110">Du har brugerlegitimationsoplysninger (brugernavn og adgangskode) til den SFTP-placering, hvorfra data skal importeres.</span><span class="sxs-lookup"><span data-stu-id="4ec02-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="4ec02-111">Du har angivet URL- og portnummer (normalt 22) til STFP-værten.</span><span class="sxs-lookup"><span data-stu-id="4ec02-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="4ec02-112">Du har filnavnet og placeringen for den fil, der skal importeres, på SFTP-værten.</span><span class="sxs-lookup"><span data-stu-id="4ec02-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="4ec02-113">Der findes en *model.json*-fil, der angiver skemaet for de data, der skal importeres.</span><span class="sxs-lookup"><span data-stu-id="4ec02-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="4ec02-114">Denne fil skal være i samme mappe som den fil, der skal importeres.</span><span class="sxs-lookup"><span data-stu-id="4ec02-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="4ec02-115">Du har [Administrator](permissions.md#administrator)-tilladelse.</span><span class="sxs-lookup"><span data-stu-id="4ec02-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="4ec02-116">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4ec02-116">Configuration</span></span>

1. <span data-ttu-id="4ec02-117">Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.</span><span class="sxs-lookup"><span data-stu-id="4ec02-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="4ec02-118">I feltet **SFTP-brugerdefineret import** skal du vælge **Forbedring af mine data**.</span><span class="sxs-lookup"><span data-stu-id="4ec02-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4ec02-119">![SFTP-brugerdefineret importfelt](media/SFTP_Custom_Import_tile.png "SFTP-brugerdefineret importfelt")</span><span class="sxs-lookup"><span data-stu-id="4ec02-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="4ec02-120">Vælg **Start her**, og angiv legitimationsoplysninger og adressen til SFTP-serveren.</span><span class="sxs-lookup"><span data-stu-id="4ec02-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="4ec02-121">Det kan f. eks. være sftp://mysftpserver.com: 22.</span><span class="sxs-lookup"><span data-stu-id="4ec02-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="4ec02-122">Angiv navnet på den fil, der indeholder data og stien til filen på SFTP-serveren, hvis den ikke findes i rodmappen.</span><span class="sxs-lookup"><span data-stu-id="4ec02-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="4ec02-123">Bekræft alle input ved at vælge **Opret forbindelse til brugerdefineret import**.</span><span class="sxs-lookup"><span data-stu-id="4ec02-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4ec02-124">![Pop op-vinduet SFTP-brugerdefineret importkonfiguration](media/SFTP_Custom_Import_Configuration_flyout.png "Pop op-vinduet SFTP-brugerdefineret importkonfiguration")</span><span class="sxs-lookup"><span data-stu-id="4ec02-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="4ec02-125">Definerer felttilknytninger</span><span class="sxs-lookup"><span data-stu-id="4ec02-125">Defining field mappings</span></span> 

<span data-ttu-id="4ec02-126">Den mappe, der indeholder den fil, der skal importeres på SFTP-serveren, skal også indeholde en *model.json*-fil.</span><span class="sxs-lookup"><span data-stu-id="4ec02-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="4ec02-127">Denne fil defineres det skema, der skal bruges til at importere data.</span><span class="sxs-lookup"><span data-stu-id="4ec02-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="4ec02-128">Skemaet skal bruge [Common Data Model](/common-data-model/) til at angive felttilknytningen.</span><span class="sxs-lookup"><span data-stu-id="4ec02-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="4ec02-129">Et simpelt eksempel på en model.json-fil ser ud på følgende måde:</span><span class="sxs-lookup"><span data-stu-id="4ec02-129">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="4ec02-130">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="4ec02-130">Enrichment results</span></span>

<span data-ttu-id="4ec02-131">Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="4ec02-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="4ec02-132">Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4ec02-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4ec02-133">Behandlingstiden afhænger af størrelsen på de data, der skal importeres, og forbindelsen til SFTP-serveren.</span><span class="sxs-lookup"><span data-stu-id="4ec02-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="4ec02-134">Når forbedringsprocessen er fuldført, kan du gennemse de netop importerede brugerdefinerede forbedringsdata under **Mine forbedringer**.</span><span class="sxs-lookup"><span data-stu-id="4ec02-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="4ec02-135">Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.</span><span class="sxs-lookup"><span data-stu-id="4ec02-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4ec02-136">Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.</span><span class="sxs-lookup"><span data-stu-id="4ec02-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4ec02-137">Næste trin</span><span class="sxs-lookup"><span data-stu-id="4ec02-137">Next steps</span></span>

<span data-ttu-id="4ec02-138">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="4ec02-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4ec02-139">Opret [segmenter](segments.md), [mål](measures.md), og [eksportér data](export-destinations.md) for at give kunderne personlige erfaringer.</span><span class="sxs-lookup"><span data-stu-id="4ec02-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]