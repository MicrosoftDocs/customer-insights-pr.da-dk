---
title: Forbedring af SFTP-brugerdefineret import
description: Generelle oplysninger om SFTP-brugerdefineret importforbedring.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304643"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="3888b-103">Forbedring af kundeprofiler med brugerdefinerede data (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="3888b-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="3888b-104">SFTP (Secure File Transfer Protocol) brugerdefineret import giver dig mulighed for at importere data, der ikke er brug for til at gennemgå processen for datasamling.</span><span class="sxs-lookup"><span data-stu-id="3888b-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="3888b-105">Det er en fleksibel, sikker og nem måde at samle dine data på.</span><span class="sxs-lookup"><span data-stu-id="3888b-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="3888b-106">SFTP brugerdefineret import kan bruges sammen med [SFTP-eksport](export-sftp.md), der gør det muligt at eksportere de kundeprofildata, der er nødvendige for at opnå en forbedring.</span><span class="sxs-lookup"><span data-stu-id="3888b-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="3888b-107">Dataene kan derefter behandles og beriges, og SFTP-brugerdefineret import kan bruges til at bringe de berigede data tilbage til publikum indsigtsfunktionen i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3888b-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3888b-108">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="3888b-108">Prerequisites</span></span>

<span data-ttu-id="3888b-109">Følgende forudsætninger skal være opfyldt, hvis du vil konfigurere SFTP-brugerdefineret import:</span><span class="sxs-lookup"><span data-stu-id="3888b-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3888b-110">Du har filnavnet og placeringen (stien) til den fil, der skal importeres på SFTP-værten.</span><span class="sxs-lookup"><span data-stu-id="3888b-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="3888b-111">Der findes en *model.json*-fil, der angiver [skemaet Common Data Model](/common-data-model/) for de data, der skal importeres.</span><span class="sxs-lookup"><span data-stu-id="3888b-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="3888b-112">Denne fil skal være i samme mappe som den fil, der skal importeres.</span><span class="sxs-lookup"><span data-stu-id="3888b-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="3888b-113">En SFTP-forbindelse er allerede konfigureret af en administrator *eller* du har [administratortilladelser](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="3888b-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="3888b-114">Du skal bruge brugerlegitimationsoplysninger, URL-adresse og portnummer til den SFTP-placering, hvor du vil importere data fra.</span><span class="sxs-lookup"><span data-stu-id="3888b-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="3888b-115">Konfigurer import</span><span class="sxs-lookup"><span data-stu-id="3888b-115">Configure the import</span></span>

1. <span data-ttu-id="3888b-116">Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.</span><span class="sxs-lookup"><span data-stu-id="3888b-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="3888b-117">Vælg **SFTP-brugerdefineret importfelt (Secure File Transfer Protocol)**, vælg **Forbedr mine data** og vælg derefter **Start her**.</span><span class="sxs-lookup"><span data-stu-id="3888b-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP-brugerdefineret importfelt.":::

1. <span data-ttu-id="3888b-119">Vælg en [værdi](connections.md) på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="3888b-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="3888b-120">Kontakt en administrator, hvis der ikke er nogen forbindelse.</span><span class="sxs-lookup"><span data-stu-id="3888b-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="3888b-121">Hvis du er administrator, kan du oprette forbindelse ved at vælge **Tilføj forbindelse** og vælge **SFTP Brugerdefineret import** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="3888b-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="3888b-122">Vælg **Opret forbindelse til brugerdefineret import** for at bekræfte den valgte forbindelse.</span><span class="sxs-lookup"><span data-stu-id="3888b-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="3888b-123">Vælg **Næste**, og angiv **Sti** og **Filnavn** på den datafil, du vil importere.</span><span class="sxs-lookup"><span data-stu-id="3888b-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Skærmbillede, når du angiver datalokation.":::

1. <span data-ttu-id="3888b-125">Vælg **Næste**, og angiv et navn, der angiver navnet på outputobjektet.</span><span class="sxs-lookup"><span data-stu-id="3888b-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="3888b-126">Vælg **Gem valgmuligheder**, når du har gennemset dine valg.</span><span class="sxs-lookup"><span data-stu-id="3888b-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="3888b-127">Konfiguration af forbindelsen til brugerdefineret SFTP-import</span><span class="sxs-lookup"><span data-stu-id="3888b-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="3888b-128">Du skal være en administrator for at konfigurere forbindelser.</span><span class="sxs-lookup"><span data-stu-id="3888b-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="3888b-129">Vælg **Tilføj forbindelse**, når du konfigurerer en konfiguration, *eller* gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i Brugerdefineret importfelt.</span><span class="sxs-lookup"><span data-stu-id="3888b-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="3888b-130">Angiv et navn til forbindelsen i feltet **Vis navn**.</span><span class="sxs-lookup"><span data-stu-id="3888b-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="3888b-131">Angiv et gyldigt brugernavn, en gyldig adgangskode og en gyldig værts-URL-adresse til den SFTP-server, som de data, der skal importeres, findes på.</span><span class="sxs-lookup"><span data-stu-id="3888b-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="3888b-132">Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**.</span><span class="sxs-lookup"><span data-stu-id="3888b-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="3888b-133">Vælg **Kontroller** for at validere konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="3888b-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="3888b-134">Når bekræftelsen er fuldført, kan forbindelsen gemmes ved at vælge **Gem**.</span><span class="sxs-lookup"><span data-stu-id="3888b-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3888b-135">![Experian forbindelseskonfigurationsside](media/enrichment-SFTP-connection.png "Experian-forbindelseskonfigurationsside")</span><span class="sxs-lookup"><span data-stu-id="3888b-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="3888b-136">Definerer felttilknytninger</span><span class="sxs-lookup"><span data-stu-id="3888b-136">Defining field mappings</span></span> 

<span data-ttu-id="3888b-137">Den mappe, der indeholder den fil, der skal importeres på SFTP-serveren, skal også indeholde en *model.json*-fil.</span><span class="sxs-lookup"><span data-stu-id="3888b-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="3888b-138">Denne fil defineres det skema, der skal bruges til at importere data.</span><span class="sxs-lookup"><span data-stu-id="3888b-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="3888b-139">Skemaet skal bruge [Common Data Model](/common-data-model/) til at angive felttilknytningen.</span><span class="sxs-lookup"><span data-stu-id="3888b-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="3888b-140">Et simpelt eksempel på en model.json-fil ser ud på følgende måde:</span><span class="sxs-lookup"><span data-stu-id="3888b-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="3888b-141">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="3888b-141">Enrichment results</span></span>

<span data-ttu-id="3888b-142">Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="3888b-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3888b-143">Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3888b-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3888b-144">Behandlingstiden afhænger af størrelsen på de data, der skal importeres, og forbindelsen til SFTP-serveren.</span><span class="sxs-lookup"><span data-stu-id="3888b-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="3888b-145">Når forbedringsprocessen er fuldført, kan du gennemse de netop importerede brugerdefinerede forbedringsdata under **Mine forbedringer**.</span><span class="sxs-lookup"><span data-stu-id="3888b-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="3888b-146">Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.</span><span class="sxs-lookup"><span data-stu-id="3888b-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3888b-147">Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.</span><span class="sxs-lookup"><span data-stu-id="3888b-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3888b-148">Næste trin</span><span class="sxs-lookup"><span data-stu-id="3888b-148">Next steps</span></span>

<span data-ttu-id="3888b-149">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="3888b-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3888b-150">Opret [segmenter](segments.md) og [målpunkter](measures.md), og endda [eksporter dataene](export-destinations.md) for at levere personlige oplevelser til dine kunder.</span><span class="sxs-lookup"><span data-stu-id="3888b-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
