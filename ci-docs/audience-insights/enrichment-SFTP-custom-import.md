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
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896274"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="e1a37-103">Forbedring af kundeprofiler med brugerdefinerede data (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="e1a37-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="e1a37-104">Brugerdefineret import af SFTP (Secure File Transfer Protocol) giver dig mulighed for at importere data, der ikke behøver at gå gennem processen til samling af data.</span><span class="sxs-lookup"><span data-stu-id="e1a37-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="e1a37-105">Det er en fleksibel, sikker og nem måde at samle dine data på.</span><span class="sxs-lookup"><span data-stu-id="e1a37-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="e1a37-106">SFTP brugerdefineret import kan bruges sammen med [SFTP-eksport](export-sftp.md), der gør det muligt at eksportere de kundeprofildata, der er nødvendige for at opnå en forbedring.</span><span class="sxs-lookup"><span data-stu-id="e1a37-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="e1a37-107">Dataene kan derefter behandles og forbedres, og SFTP-brugerdefineret import kan bruges til at få de forbedrede data tilbage til målgruppeindsigt i Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e1a37-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e1a37-108">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="e1a37-108">Prerequisites</span></span>

<span data-ttu-id="e1a37-109">Følgende forudsætninger skal være opfyldt, hvis du vil konfigurere SFTP-brugerdefineret import:</span><span class="sxs-lookup"><span data-stu-id="e1a37-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e1a37-110">Du har filnavnet og placeringen (stien) til den fil, der skal importeres, på SFTP-værten.</span><span class="sxs-lookup"><span data-stu-id="e1a37-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="e1a37-111">Der findes en *model.json*-fil, der angiver [skemaet Common Data Model](/common-data-model/) for de data, der skal importeres.</span><span class="sxs-lookup"><span data-stu-id="e1a37-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="e1a37-112">Denne fil skal være i samme mappe som den fil, der skal importeres.</span><span class="sxs-lookup"><span data-stu-id="e1a37-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="e1a37-113">En SFTP-forbindelse er allerede konfigureret af en administrator *eller* du har [administratortilladelser](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="e1a37-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="e1a37-114">Du skal bruge brugerlegitimationsoplysninger, URL-adresse og portnummer til den SFTP-placering, hvor du vil importere data fra.</span><span class="sxs-lookup"><span data-stu-id="e1a37-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="e1a37-115">Konfigurer import</span><span class="sxs-lookup"><span data-stu-id="e1a37-115">Configure the import</span></span>

1. <span data-ttu-id="e1a37-116">Gå til **Data** > **Forbedring**, og vælg fanen **Opdag**.</span><span class="sxs-lookup"><span data-stu-id="e1a37-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="e1a37-117">Vælg **SFTP-brugerdefineret importfelt (Secure File Transfer Protocol)**, vælg **Forbedr mine data** og vælg derefter **Start her**.</span><span class="sxs-lookup"><span data-stu-id="e1a37-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP-brugerdefineret importfelt.":::

1. <span data-ttu-id="e1a37-119">Vælg en [forbindelse](connections.md) på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="e1a37-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="e1a37-120">Kontakt en administrator, hvis der ikke er nogen forbindelse.</span><span class="sxs-lookup"><span data-stu-id="e1a37-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="e1a37-121">Hvis du er administrator, kan du oprette en forbindelse ved at vælge **Tilføj forbindelse** og vælge **Brugerdefineret SFTP-import** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="e1a37-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="e1a37-122">Vælg **Opret forbindelse til brugerdefineret import** for at bekræfte den valgte forbindelse.</span><span class="sxs-lookup"><span data-stu-id="e1a37-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="e1a37-123">Vælg **Næste**, og angiv **filnavnet** og **stien** til den datafil, du vil importere.</span><span class="sxs-lookup"><span data-stu-id="e1a37-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Skærmbillede, når du angiver datalokation.":::

1. <span data-ttu-id="e1a37-125">Vælg **Næste**, og angiv et navn, der angiver navnet på outputobjektet.</span><span class="sxs-lookup"><span data-stu-id="e1a37-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="e1a37-126">Vælg **Gem valgmuligheder**, når du har gennemset dine valg.</span><span class="sxs-lookup"><span data-stu-id="e1a37-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="e1a37-127">Konfiguration af forbindelsen til brugerdefineret SFTP-import</span><span class="sxs-lookup"><span data-stu-id="e1a37-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="e1a37-128">Du skal være en administrator for at konfigurere forbindelser.</span><span class="sxs-lookup"><span data-stu-id="e1a37-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="e1a37-129">Vælg **Tilføj forbindelse**, når du konfigurerer en konfiguration, *eller* gå til **Admin** > **Forbindelser**, og vælg **Konfigurer** i Brugerdefineret importfelt.</span><span class="sxs-lookup"><span data-stu-id="e1a37-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="e1a37-130">Angiv et navn til forbindelsen i feltet **Vis navn**.</span><span class="sxs-lookup"><span data-stu-id="e1a37-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="e1a37-131">Angiv et gyldigt brugernavn, en gyldig adgangskode og en gyldig værts-URL-adresse til STFP-server, som dataene skal importeres fra.</span><span class="sxs-lookup"><span data-stu-id="e1a37-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="e1a37-132">Gennemgå og giv dit samtykke til **Beskyttelse af personlige data og overholdelse af angivne standarder** ved at markere afkrydsningsfeltet **Jeg accepterer**.</span><span class="sxs-lookup"><span data-stu-id="e1a37-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="e1a37-133">Vælg **Kontroller** for at validere konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="e1a37-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="e1a37-134">Når verifikationen er fuldført, kan du gemme forbindelsen ved at klikke på **Gem**.</span><span class="sxs-lookup"><span data-stu-id="e1a37-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="e1a37-135">![Side til konfiguration af Experian-forbindelse](media/enrichment-SFTP-connection.png "Side til konfiguration af Experian-forbindelse")</span><span class="sxs-lookup"><span data-stu-id="e1a37-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="e1a37-136">Definerer felttilknytninger</span><span class="sxs-lookup"><span data-stu-id="e1a37-136">Defining field mappings</span></span> 

<span data-ttu-id="e1a37-137">Den mappe, der indeholder den fil, der skal importeres på SFTP-serveren, skal også indeholde en *model.json*-fil.</span><span class="sxs-lookup"><span data-stu-id="e1a37-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="e1a37-138">Denne fil defineres det skema, der skal bruges til at importere data.</span><span class="sxs-lookup"><span data-stu-id="e1a37-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="e1a37-139">Skemaet skal bruge [Common Data Model](/common-data-model/) til at angive felttilknytningen.</span><span class="sxs-lookup"><span data-stu-id="e1a37-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="e1a37-140">Et simpelt eksempel på en model.json-fil ser ud på følgende måde:</span><span class="sxs-lookup"><span data-stu-id="e1a37-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="e1a37-141">Forbedringsresultater</span><span class="sxs-lookup"><span data-stu-id="e1a37-141">Enrichment results</span></span>

<span data-ttu-id="e1a37-142">Hvis du vil starte forbedringsprocessen, skal du vælge **Kør** fra kommandolinjen.</span><span class="sxs-lookup"><span data-stu-id="e1a37-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e1a37-143">Du kan også lade systemet køre forbedring automatisk som en del af en [planlagt opdatering](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e1a37-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e1a37-144">Behandlingstiden afhænger af størrelsen på de data, der skal importeres, og forbindelsen til SFTP-serveren.</span><span class="sxs-lookup"><span data-stu-id="e1a37-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="e1a37-145">Når forbedringsprocessen er fuldført, kan du gennemse de netop importerede brugerdefinerede forbedringsdata under **Mine forbedringer**.</span><span class="sxs-lookup"><span data-stu-id="e1a37-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="e1a37-146">Derudover kan du finde tidspunktet for den seneste opdatering og antallet af forbedrede profiler.</span><span class="sxs-lookup"><span data-stu-id="e1a37-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e1a37-147">Du kan få adgang til en detaljeret visning af hver forbedrede profil ved at vælge **Vis forbedrede data**.</span><span class="sxs-lookup"><span data-stu-id="e1a37-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e1a37-148">Næste trin</span><span class="sxs-lookup"><span data-stu-id="e1a37-148">Next steps</span></span>

<span data-ttu-id="e1a37-149">Byg oven over dine forbedrede kundedata.</span><span class="sxs-lookup"><span data-stu-id="e1a37-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e1a37-150">Opret [segmenter](segments.md), [mål](measures.md), og [eksportér data](export-destinations.md) for at give kunderne personlige erfaringer.</span><span class="sxs-lookup"><span data-stu-id="e1a37-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
