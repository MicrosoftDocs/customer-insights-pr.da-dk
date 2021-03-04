---
title: Robot til Microsoft Teams
description: Søg efter samlede kundeprofiler i Microsoft Teams ved hjælp af en robot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267945"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="4d02a-103">Teams-robot til Dynamics 365 Customer Insights (prøveversion)</span><span class="sxs-lookup"><span data-stu-id="4d02a-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="4d02a-104">Opret forbindelse Microsoft Teams for at lade en robot søge efter samlede kundeprofiler i Teams-kanaler.</span><span class="sxs-lookup"><span data-stu-id="4d02a-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4d02a-105">![Teams-bot viser en kundepost](media/teams-bot.png "Teams-bot viser en kundepost")</span><span class="sxs-lookup"><span data-stu-id="4d02a-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4d02a-106">Forudsætninger</span><span class="sxs-lookup"><span data-stu-id="4d02a-106">Prerequisites</span></span>

<span data-ttu-id="4d02a-107">For at installere og konfigurere denne bot, skal følgende forudsætninger være opfyldt:</span><span class="sxs-lookup"><span data-stu-id="4d02a-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4d02a-108">Der er tilføjet mindst én [datakilde](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="4d02a-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="4d02a-109">[Samlingsprocessen](data-unification.md) er fuldført.</span><span class="sxs-lookup"><span data-stu-id="4d02a-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="4d02a-110">Der tilføjet felter til [søge- og filtreringsindekset](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="4d02a-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="4d02a-111">Customer Insights og Teams er i samme organisation.</span><span class="sxs-lookup"><span data-stu-id="4d02a-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="4d02a-112">Konfiguration af botten</span><span class="sxs-lookup"><span data-stu-id="4d02a-112">Configure the bot</span></span>

1. <span data-ttu-id="4d02a-113">Gå til **Admin** > **Eksportdestinationer** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="4d02a-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="4d02a-114">På Microsoft Teams-feltet vælges **Konfigurer**.</span><span class="sxs-lookup"><span data-stu-id="4d02a-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="4d02a-115">Du omdirigeres til området **Apps** Teams.</span><span class="sxs-lookup"><span data-stu-id="4d02a-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="4d02a-116">Du kan også åbne Teams og vælge **Apps** i nederste venstre hjørne eller [hente direkte fra AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="4d02a-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="4d02a-117">Søg efter **Customer Insights**, og vælg appen.</span><span class="sxs-lookup"><span data-stu-id="4d02a-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="4d02a-118">Vælg **Tilføj**.</span><span class="sxs-lookup"><span data-stu-id="4d02a-118">Select **Add**.</span></span>
1. <span data-ttu-id="4d02a-119">Når du har logget på Customer Insights i Teams, kan du se en velkomstmeddelelse og komme i gang.</span><span class="sxs-lookup"><span data-stu-id="4d02a-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="4d02a-120">Ting du kan gøre med botten</span><span class="sxs-lookup"><span data-stu-id="4d02a-120">Things you can do with the bot</span></span>

<span data-ttu-id="4d02a-121">Botten leverer opslagsmuligheder for samlede kundeprofiler.</span><span class="sxs-lookup"><span data-stu-id="4d02a-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="4d02a-122">Skriv **search** efterfulgt af et navn, en mailadresse eller et andet felt i den samlede kundeprofil, der er føjet til søge- og filtreringsindekset.</span><span class="sxs-lookup"><span data-stu-id="4d02a-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="4d02a-123">Du får et kort med op til 15 felter fra den resulterende kundeprofil.</span><span class="sxs-lookup"><span data-stu-id="4d02a-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="4d02a-124">Flere forekomster returnerer en liste med resultater, hvor du kan vælge en profil.</span><span class="sxs-lookup"><span data-stu-id="4d02a-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="4d02a-125">Du kan tilføje søgeudtryk i dobbelte anførselstegn for at søge efter et nøjagtigt match.</span><span class="sxs-lookup"><span data-stu-id="4d02a-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="4d02a-126">Hvis din organisation vedligeholder flere Customer Insights-miljøer i samme organisation, kan du angive **switchinstance** for at vælge, hvilket miljø en robot skal knyttes til.</span><span class="sxs-lookup"><span data-stu-id="4d02a-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="4d02a-127">Skriv **Hjælp** for at få vist en liste over tilgængelige kommandoer for botten.</span><span class="sxs-lookup"><span data-stu-id="4d02a-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]