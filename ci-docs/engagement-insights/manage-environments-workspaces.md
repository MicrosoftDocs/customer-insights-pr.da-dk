---
title: Administrere arbejdsområder og miljøer
description: Sådan oprettes, omdøbes og slettes arbejdsområder og miljøer.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 07/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: bf310b1a50ba7baac5d11d5f22ff42003fbba516efd7d165c00b59adc958da2e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034035"
---
# <a name="manage-environments-and-workspaces"></a>Administrér miljøer og arbejdsområder

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Oversigt

Et arbejdsområde er et sted, hvor du kan gemme og administrere hændelser og rapporter. Det er her, du kan få vist brugeraktivitet i realtid. Når du opretter et arbejdsområde, vælger du den type data, du vil sende til arbejdsområdet. I øjeblikket understøttes webdata og mobilapps.

Et miljø er et sted, hvor du administrerer dine arbejdsområder og forbindelser. Den måde, du bruger miljøer på, afhænger af organisationen og brugssagen. Du kan f.eks. oprette:

-   Enkelt miljø.
-   Separate test- og produktionsmiljøer.
-   Separate miljøer for bestemte teams eller afdelinger i organisationen, der indeholder relevante hændelser for hver målgruppe.
-   Separate miljøer til forskellige globale filialer af din virksomhed.
-   Forbindelser til funktioner i Customer Insights, målgruppeindsigt.

## <a name="choose-an-environment-and-create-a-workspace"></a>Vælg et miljø, og opret et arbejdsområde 

Alle arbejdsområder skal være i et miljø. Du kan vælge et miljø, der allerede findes, eller oprette et nyt, når du opretter et arbejdsområde. Du kan derefter vælge at tilføje medlemmer af arbejdsområdet og begynde at indsamle data.

**Opret dit første arbejdsområde**

1. I engagementsindsigt skal du vælge **Ny** fra arbejdsområdeskifteren. 

   :::image type="content" source="media/New-workspace.png" alt-text="Valg af arbejdsområde for Customer Insights-siden.":::

1. Vælg et miljø på listen, eller vælg **Opret nyt miljø**.

1. Angiv et navn i **Navn på arbejdsområde**. 

1. Vælg den type miljø, du vil oprette, afhængigt af om du vil måle, hvad der sker på et websted eller i en mobilapp. 

1. Du kan tilføje medlemmer og tildele deres tilladelsesniveau fra **Rolle**-listen. Vælg derefter **Udfør** for at oprette arbejdsområdet eller **Næste** for at installere kode. 

1. Installer koden for kodestykke at begynde at modtage data, og vælg derefter **Udført**. 

## <a name="manage-a-workspace"></a>Administrere et arbejdsområde

Du kan vedligeholde flere arbejdsområder samtidig i et miljø. Din [rolle](user-roles.md) bestemmer, hvordan du kan arbejde med dem. 

 - Du skal være miljøadministrator eller arbejdsområdeadministrator for at administrere arbejdsområdet.
 - Som arbejdsområdeadministrator kan du omdøbe eksisterende arbejdsområder eller slette dem. 

### <a name="edit-a-workspace-name"></a>Redigere et navn på arbejdsområdet.

1. Gå til **Administration** > **Arbejdsområde**, og vælg **Indstillinger**.

1. Angiv et nyt navn i feltet **Navn på arbejdsområde**.

1. Vælg **Gem** for at anvende dine ændringer.

### <a name="delete-a-workspace"></a>Slet et arbejdsområde

Hvis du sletter et arbejdsområde, fjernes alt indhold, data, indstillinger og tilladelser permanent. Dette kan ikke fortrydes.

1. Gå til **Administration** > **Arbejdsområde**, og vælg **Indstillinger**.

1. Vælg **Slet arbejdsområde**. 

1. Angiv **BEKRÆFT SLETNING** i dialogboksen **Slet arbejdsområde**. 

1. Angiv **Slet** for at slette arbejdsområdet permanent.

### <a name="manage-workspace-members"></a>Administrer medlemmer af arbejdsområde

1. Gå til **Administration** > **Arbejdsområde**, og vælg **Medlemmer**.

1. Vælg **Tilføj medlemmer** for at give adgang til og [tildele roller](user-roles.md). I øjeblikket er det kun **arbejdsområdeadministratorer**, der er tilgængelige.

1. Hvis du konfigurerer en [forbindelse til målgruppeindsigt](configure-connections.md), kan du vælge **Tillad adgang til profildata**, så medlemmet kan se rapporter på baggrund af [brugerprofiler](profile-reports.md).

1. Vælg **Tilføj medlemmer** for at føje dem til dit arbejdsområde.

## <a name="manage-an-environment"></a>Administrere et miljø

Som miljøadministrator kan du få adgang til et miljø fra venstre navigationsrude. Du kan konfigurere miljøindstillinger, andre miljøadministratorer, arbejdsområder og [forbindelser for at få målgruppeindsigt](configure-connections.md). Vælg faner for at flytte mellem forskellige områder i Administration.

:::image type="content" source="media/New-environment.png" alt-text="Administration for miljø.":::

### <a name="create-an-environment"></a>Opret et miljø

1. Vælg **Ny** i valg af arbejdsområde.

1. Åbn rullemenuen **Miljø** i den guidede oplevelse, og vælg **Opret nyt miljø**. 

1. Angiv et **Miljønavn**.

   :::image type="content" source="media/create-environment.png" alt-text="Trin i den guidede oplevelse for at angive miljødetaljerne.":::

1. Vælg **Område**, og vælg **Næste**. 

1. Angiv et arbejdsområdenavn, og vælg, hvilken type arbejdsområde du vil oprette. 

1.  Du kan også tilføje medlemmer og kopiere kodestykket for at fuldføre oprettelsesprocessen.

### <a name="rename-an-environment"></a>Omdøbe et miljø

1. Gå til **Administration** > **Miljø**, og vælg **Indstillinger**.

1. Opdater **Miljønavn**, og vælg **Gem** for at anvende ændringerne.

### <a name="manage-environment-members"></a>Administrere miljømedlemmer

1. Gå til **Administration** > **Miljø**, og vælg **Medlemmer**.

1. Vælg **Tilføj medlemmer** for at opdatere medlemmer og [tildele roller](user-roles.md). I øjeblikket er det kun **Miljøadministration**, der er tilgængelig.

1. Hvis du konfigurerer en [forbindelse til målgruppeindsigt](configure-connections.md), kan du vælge **Tillad adgang til profildata**, så medlemmet kan se rapporter på baggrund af [brugerprofiler](profile-reports.md).

1. Vælg **Tilføj medlemmer** for at føje dem til dit miljø.

### <a name="delete-an-environment"></a>Slet et miljø

Miljøadministratorer kan slette miljøer. Før du kan slette et miljø, skal du fjerne alle arbejdsområder under det.

1. Gå til **Administration** > **Miljø**, og vælg **Indstillinger**.

1. Vælg **Slet miljø**. 

1. Angiv **BEKRÆFT SLETNING** i dialogboksen **Slet arbejdsområde**. 

1. Angiv **Slet** for at slette miljøet permanent.

## <a name="manage-connections"></a>Administrer forbindelser

Hvis du opretter forbindelser til målgruppeindsigt, kan du se rapporter i engagementsindsigt baseret på ensartede kundeprofiler. 

Se [Konfigurer forbindelser](configure-connections.md) for at få flere oplysninger.

## <a name="manage-personal-data"></a>Administrere personlige data

Du kan slette eller eksportere slutbrugerens identificerbare data for at beskytte kundens personlige data.

Der er flere oplysninger i [Slette og eksportere hændelsesdata, der indeholder personlige oplysninger](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
