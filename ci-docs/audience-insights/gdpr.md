---
title: DSR-anmodninger (Data Subject Rights) under GDPR | Microsoft Docs
description: Svar på DSR-anmodninger til muligheder i Dynamics 365 Customer Insights-målgruppen Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405439"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="c186e-103">DSR-anmodninger (Data Subject Rights) under GDPR</span><span class="sxs-lookup"><span data-stu-id="c186e-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="c186e-104">Svar på GDPR-sletteanmodninger vedrørende muligheder i dataemne i Dynamics 365 Customer Insights-målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="c186e-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="c186e-105">"Retten til at fjerne" personlige data fra en organisations kundedata er en nøglebeskyttelse i generel forordning om databeskyttelse (GDPR).</span><span class="sxs-lookup"><span data-stu-id="c186e-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="c186e-106">Fjernelse af personlige data omfatter fjernelse af alle personlige data og systemgenererede logge, undtagen oplysninger om overvågningslog.</span><span class="sxs-lookup"><span data-stu-id="c186e-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="c186e-107">Administrere anmodninger om datasletning fra den registrerede</span><span class="sxs-lookup"><span data-stu-id="c186e-107">Manage data subject delete requests</span></span>

<span data-ttu-id="c186e-108">Målgruppen Insights tilbyder følgende funktioner i produktet, hvor du kan slette personlige data for en bestemt kunde eller bruger:</span><span class="sxs-lookup"><span data-stu-id="c186e-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="c186e-109">**Administrere sletteanmodninger om kundedata**: Kundedata i Customer Insights indtages fra oprindelige datakilder uden for Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c186e-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="c186e-110">Alle GDPR-sletteanmodninger skal udføres i den oprindelige datakilde.</span><span class="sxs-lookup"><span data-stu-id="c186e-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="c186e-111">**Administrér sletteanmodninger om Customer Insights-brugerdata**: Data til brugere er oprettet af Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c186e-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="c186e-112">Alle GDPR-sletteanmodninger skal udføres i Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c186e-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="c186e-113">Administrere sletteanmodninger for kundedata</span><span class="sxs-lookup"><span data-stu-id="c186e-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="c186e-114">En Customer Insights-administrator kan følge disse trin for at fjerne de kundedata, der er blevet slettet i datakilden:</span><span class="sxs-lookup"><span data-stu-id="c186e-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="c186e-115">Log på Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c186e-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="c186e-116">Gå til **Data** > **Datakilder** i målgruppen Insights</span><span class="sxs-lookup"><span data-stu-id="c186e-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="c186e-117">For hver datakilde på listen, der indeholder slettede kundedata:</span><span class="sxs-lookup"><span data-stu-id="c186e-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="c186e-118">Vælg (...), og vælg derefter **Opdater**.</span><span class="sxs-lookup"><span data-stu-id="c186e-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="c186e-119">Tjek statussen for datakilden under **Status**.</span><span class="sxs-lookup"><span data-stu-id="c186e-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="c186e-120">En markering betyder, at opdateringen lykkedes.</span><span class="sxs-lookup"><span data-stu-id="c186e-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="c186e-121">En advarselstrekant betyder, at noget gik galt.</span><span class="sxs-lookup"><span data-stu-id="c186e-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="c186e-122">Hvis der vises en advarselstrekant, skal du kontakte D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c186e-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c186e-123">![Håndtere GDPR-sletteanmodninger for kundedata](media/gdpr-data-sources.png "Håndtere GDPR-sletteanmodninger for kundedata")</span><span class="sxs-lookup"><span data-stu-id="c186e-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="c186e-124">Administrér sletteanmodninger for brugerdata</span><span class="sxs-lookup"><span data-stu-id="c186e-124">Manage delete requests for user data</span></span>

<span data-ttu-id="c186e-125">En Customer Insights-administrator kan følge disse trin for at slette Customer Insights-brugerdata:</span><span class="sxs-lookup"><span data-stu-id="c186e-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="c186e-126">Log på Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c186e-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="c186e-127">Gå til **Adm** > **Tilladelser** i målgruppen Insights.</span><span class="sxs-lookup"><span data-stu-id="c186e-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="c186e-128">Markér afkrydsningsfeltet ud for den bruger, der skal slettes.</span><span class="sxs-lookup"><span data-stu-id="c186e-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="c186e-129">Vælg **Fjern**.</span><span class="sxs-lookup"><span data-stu-id="c186e-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c186e-130">![Håndtering af GDPR-sletteanmodninger for brugerdata](media/gdpr-permissions.png "Håndtering af GDPR-sletteanmodninger for brugerdata")</span><span class="sxs-lookup"><span data-stu-id="c186e-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="c186e-131">Besvarelse af GDPR-eksportanmodninger vedrørende dataemne</span><span class="sxs-lookup"><span data-stu-id="c186e-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="c186e-132">Som en del af vores forpligtelse i egenskab af din partner i forhold til generel forordning om databeskyttelse (GDPR) har vi udviklet dokumentation som hjælp til din forberedelse.</span><span class="sxs-lookup"><span data-stu-id="c186e-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="c186e-133">I denne dokumentation beskrives de trin, du kan tage i dag for at understøtte GDPR overholdelse, når du bruger målgrupen Insights.</span><span class="sxs-lookup"><span data-stu-id="c186e-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="c186e-134">Håndtere anmodninger om eksport og visning</span><span class="sxs-lookup"><span data-stu-id="c186e-134">Manage export and view requests</span></span>

<span data-ttu-id="c186e-135">Retten til dataportabilitet gør det muligt for registrerede personer at anmode om en kopi af deres personlige data i et elektronisk format (defineret som et "struktureret, almindeligt anvendt, maskinlæsbart og interoperativt format"), der kan overføres til en anden datacontroller.</span><span class="sxs-lookup"><span data-stu-id="c186e-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="c186e-136">Eksportere kundedata (lejeradministrator)</span><span class="sxs-lookup"><span data-stu-id="c186e-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="c186e-137">En lejeradministrator kan følge disse trin for at eksportere data:</span><span class="sxs-lookup"><span data-stu-id="c186e-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="c186e-138">Send en mail til D365CI@microsoft.com med angivelse af kundens mailadresse i anmodningen.</span><span class="sxs-lookup"><span data-stu-id="c186e-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="c186e-139">Customer Insights-teamet sender en e-mail til den registrerede lejeradministrators mailadresse og anmoder om bekræftelse på eksport af data.</span><span class="sxs-lookup"><span data-stu-id="c186e-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="c186e-140">Acceptér bekræftelsen for at eksportere dataene til den ønskede kunde.</span><span class="sxs-lookup"><span data-stu-id="c186e-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="c186e-141">Modtag de eksporterede data via mailadressen for lejeradministratoren.</span><span class="sxs-lookup"><span data-stu-id="c186e-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="c186e-142">Eksport af brugerdata (lejeradministrator)</span><span class="sxs-lookup"><span data-stu-id="c186e-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="c186e-143">Send en mail til D365CI@microsoft.com med angivelse af brugerens mailadresse i anmodningen.</span><span class="sxs-lookup"><span data-stu-id="c186e-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="c186e-144">Customer Insights-teamet sender en e-mail til den registrerede lejeradministrators mailadresse og anmoder om bekræftelse på eksport af data.</span><span class="sxs-lookup"><span data-stu-id="c186e-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="c186e-145">Acceptér bekræftelsen for at eksportere dataene til den ønskede bruger.</span><span class="sxs-lookup"><span data-stu-id="c186e-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="c186e-146">Modtag de eksporterede data via mailadressen for lejeradministratoren.</span><span class="sxs-lookup"><span data-stu-id="c186e-146">Receive the exported data through the tenant admin email address.</span></span>
