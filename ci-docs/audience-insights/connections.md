---
title: Forbindelser til andre tjenester fra Customer Insights.
description: Dele data med andre tjenester.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896090"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="d07a6-103">Oversigt over forbindelser (forhåndsversion)</span><span class="sxs-lookup"><span data-stu-id="d07a6-103">Connections (preview) overview</span></span>

<span data-ttu-id="d07a6-104">Forbindelser er nøglen til at gøre det muligt at dele data til og fra Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d07a6-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="d07a6-105">Hver forbindelse opretter datadeling med en bestemt tjeneste.</span><span class="sxs-lookup"><span data-stu-id="d07a6-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="d07a6-106">Forbindelser er grundlaget for [konfiguration af tredjepartseksporter](enrichment-hub.md) og [konfiguration af eksport](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d07a6-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="d07a6-107">Den samme forbindelse kan bruges flere gange.</span><span class="sxs-lookup"><span data-stu-id="d07a6-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="d07a6-108">En forbindelse til Dynamics 365 Marketing fungerer f.eks. i forbindelse med flere eksporter, og én forbindelse i Leadspace kan bruges til flere forbindelser.</span><span class="sxs-lookup"><span data-stu-id="d07a6-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="d07a6-109">Gå til **Administrator** > **Forbindelser** for at oprette og få vist forbindelser.</span><span class="sxs-lookup"><span data-stu-id="d07a6-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="d07a6-110">Under fanen **Forbindelser** vises alle aktive forbindelser.</span><span class="sxs-lookup"><span data-stu-id="d07a6-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="d07a6-111">På listen vises en række for hver forbindelse.</span><span class="sxs-lookup"><span data-stu-id="d07a6-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="d07a6-112">Få en hurtig oversigt, en beskrivelse, og find ud af, hvad du kan gøre med hver enkelt udvidelsesindstilling, under fanen **Opdag**.</span><span class="sxs-lookup"><span data-stu-id="d07a6-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="d07a6-113">Eksport</span><span class="sxs-lookup"><span data-stu-id="d07a6-113">Exports</span></span>

<span data-ttu-id="d07a6-114">Det er kun administratorer, der kan konfigurere nye forbindelser, men de kan give bidragydere adgang til at bruge eksisterende forbindelser.</span><span class="sxs-lookup"><span data-stu-id="d07a6-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="d07a6-115">Administratorer kontrollerer, hvor dataene kan gå hen, og bidragyderne definerer nyttelasten og hyppigheden af deres behov.</span><span class="sxs-lookup"><span data-stu-id="d07a6-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="d07a6-116">Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d07a6-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="d07a6-117">Forbedringer</span><span class="sxs-lookup"><span data-stu-id="d07a6-117">Enrichments</span></span>

<span data-ttu-id="d07a6-118">Det er kun administratorer, der kan konfigurere nye forbindelser, men de oprettede forbindelser er altid tilgængelige for både administratorer og bidragydere.</span><span class="sxs-lookup"><span data-stu-id="d07a6-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="d07a6-119">Administratorer styrer legitimationsoplysninger og giver samtykke til dataoverførsler.</span><span class="sxs-lookup"><span data-stu-id="d07a6-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="d07a6-120">Forbindelserne kan derefter bruges af både administratorer og bidragydere til at hjælpe dig.</span><span class="sxs-lookup"><span data-stu-id="d07a6-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="d07a6-121">Tilføj en ny forbindelse</span><span class="sxs-lookup"><span data-stu-id="d07a6-121">Add a new connection</span></span>

<span data-ttu-id="d07a6-122">Hvis du vil tilføje forbindelser, skal du have [administratortilladelser](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d07a6-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="d07a6-123">Hvis du opretter forbindelse til andre Microsoft-tjenester, antages det, at begge tjenester findes i den samme organisation.</span><span class="sxs-lookup"><span data-stu-id="d07a6-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="d07a6-124">Gå til **Administrator** > **Forbindelser** (forhåndsversion).</span><span class="sxs-lookup"><span data-stu-id="d07a6-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="d07a6-125">Gå til fanen **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="d07a6-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="d07a6-126">Vælg **Tilføj forbindelse** for at oprette en ny forbindelse.</span><span class="sxs-lookup"><span data-stu-id="d07a6-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="d07a6-127">Vælg den type forbindelse, du vil oprette, på rullemenuen.</span><span class="sxs-lookup"><span data-stu-id="d07a6-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="d07a6-128">Angiv de nødvendige oplysninger i ruden **Konfigurer forbindelse**.</span><span class="sxs-lookup"><span data-stu-id="d07a6-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="d07a6-129">**Visningsnavn** og forbindelsestype beskriver en forbindelse.</span><span class="sxs-lookup"><span data-stu-id="d07a6-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="d07a6-130">Det anbefales, at du vælger et navn, der forklarer formålet med og målet for denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="d07a6-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="d07a6-131">De nøjagtige felter afhænger af, hvilken tjeneste du opretter forbindelse til.</span><span class="sxs-lookup"><span data-stu-id="d07a6-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="d07a6-132">Du kan få mere at vide om detaljer om en bestemt forbindelse ved at skrive artiklen om måltjenesten.</span><span class="sxs-lookup"><span data-stu-id="d07a6-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="d07a6-133">Vælg **Gem** for at oprette forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="d07a6-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="d07a6-134">Du kan også vælge **Konfigurer** i et område på fanen **Udforsk**.</span><span class="sxs-lookup"><span data-stu-id="d07a6-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="d07a6-135">Tillad bidragydere at bruge en forbindelse til eksport</span><span class="sxs-lookup"><span data-stu-id="d07a6-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="d07a6-136">Når du konfigurerer eller redigerer en eksportforbindelse, vælger du, hvilke brugere der skal have tilladelse til at bruge denne specifikke forbindelse til at definere [eksport](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d07a6-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="d07a6-137">Som standard er en forbindelse tilgængelig for brugere med en administratorrolle.</span><span class="sxs-lookup"><span data-stu-id="d07a6-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="d07a6-138">Du kan ændre denne indstilling under **Vælg, hvem der kan bruge denne forbindelse**, og give brugere med bidragyder mulighed for at bruge denne forbindelse.</span><span class="sxs-lookup"><span data-stu-id="d07a6-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="d07a6-139">Bidragydere kan ikke få vist eller redigere forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="d07a6-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="d07a6-140">De kan kun se visningsnavn og dens type, når de opretter en eksport.</span><span class="sxs-lookup"><span data-stu-id="d07a6-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="d07a6-141">Ved at dele en forbindelse giver du bidragydere tilladelse til at bruge en forbindelse.</span><span class="sxs-lookup"><span data-stu-id="d07a6-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="d07a6-142">Bidragydere kan se delte forbindelser, når de konfigurerer eksport.</span><span class="sxs-lookup"><span data-stu-id="d07a6-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="d07a6-143">De kan administrere alle de eksporter, der bruger denne specifikke forbindelse.</span><span class="sxs-lookup"><span data-stu-id="d07a6-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="d07a6-144">Du kan ændre denne indstilling, samtidig med at du beholder de eksporter, som allerede er defineret af bidragydere.</span><span class="sxs-lookup"><span data-stu-id="d07a6-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="d07a6-145">Redigere en forbindelse</span><span class="sxs-lookup"><span data-stu-id="d07a6-145">Edit a connection</span></span>

1. <span data-ttu-id="d07a6-146">Gå til **Administrator** > **Forbindelser** (forhåndsversion).</span><span class="sxs-lookup"><span data-stu-id="d07a6-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="d07a6-147">Gå til fanen **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="d07a6-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="d07a6-148">Vælg den lodrette ellipse for den forbindelse, du vil redigere.</span><span class="sxs-lookup"><span data-stu-id="d07a6-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="d07a6-149">Vælg **Rediger**.</span><span class="sxs-lookup"><span data-stu-id="d07a6-149">Select **Edit**.</span></span>

1. <span data-ttu-id="d07a6-150">Opdatér de værdier, du vil opdatere, og vælg **Gem**.</span><span class="sxs-lookup"><span data-stu-id="d07a6-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="d07a6-151">Fjerne en forbindelse</span><span class="sxs-lookup"><span data-stu-id="d07a6-151">Remove a connection</span></span>

<span data-ttu-id="d07a6-152">Hvis den forbindelse, du fjerner, bruges af produkter eller eksport, skal du først ophæve eller fjerne dem.</span><span class="sxs-lookup"><span data-stu-id="d07a6-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="d07a6-153">Dialogboksen Fjern fører dig til relevante produktoversigter eller eksporter.</span><span class="sxs-lookup"><span data-stu-id="d07a6-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="d07a6-154">Fritliggende produkter og eksporter bliver inaktive.</span><span class="sxs-lookup"><span data-stu-id="d07a6-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="d07a6-155">Du kan genaktivere dem ved at føje endnu en forbindelse til dem på siden [Forbedringer](enrichment-hub.md) eller [Eksport](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d07a6-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="d07a6-156">Gå til **Administrator** > **Forbindelser** (forhåndsversion).</span><span class="sxs-lookup"><span data-stu-id="d07a6-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="d07a6-157">Gå til fanen **Forbindelser**.</span><span class="sxs-lookup"><span data-stu-id="d07a6-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="d07a6-158">Vælg den lodrette ellipse for den forbindelse, du vil fjerne.</span><span class="sxs-lookup"><span data-stu-id="d07a6-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="d07a6-159">Vælg **Fjern** på rullelisten.</span><span class="sxs-lookup"><span data-stu-id="d07a6-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="d07a6-160">En bekræftelsesdialogboks vises.</span><span class="sxs-lookup"><span data-stu-id="d07a6-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="d07a6-161">Hvis der er forbindelser eller eksporter, skal du vælge knappen for at se, hvad der bruger forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="d07a6-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="d07a6-162">**Eksport:** Du kan vælge enten at fjerne eller afbryde forbindelsen til eksporten for at kunne fjerne forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="d07a6-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="d07a6-163">Hvis en administrator vil afbryde forbindelsen til en eksport, kan den bruge handlingen **Afbryd** forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="d07a6-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="d07a6-164">Denne handling er tilgængelig for individuelle og flere valgte eksporter.</span><span class="sxs-lookup"><span data-stu-id="d07a6-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="d07a6-165">Hvis du afbryder forbindelsen til eksportkonfigurationen, men den køres først, når der er føjet en anden forbindelse til den.</span><span class="sxs-lookup"><span data-stu-id="d07a6-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="d07a6-166">**Forbedringer:** Du kan vælge enten at fjerne eller deaktivere forbedringerne for at kunne fjerne forbindelsen.</span><span class="sxs-lookup"><span data-stu-id="d07a6-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="d07a6-167">Når forbindelsen ikke har flere afhængigheder, skal du gå tilbage til **Administrator** > **Forbindelser** og prøve at fjerne forbindelsen igen.</span><span class="sxs-lookup"><span data-stu-id="d07a6-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="d07a6-168">Bekræft sletningen ved at vælge **Fjern**.</span><span class="sxs-lookup"><span data-stu-id="d07a6-168">To confirm the deletion select **Remove**.</span></span>

