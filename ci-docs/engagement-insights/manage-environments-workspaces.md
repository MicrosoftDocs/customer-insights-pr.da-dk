---
title: Administrere arbejdsområder og miljøer
description: Sådan oprettes, omdøbes og slettes arbejdsområder og miljøer.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 279af24358a1d6ea2b4cc75d5496042af73a7cae
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645439"
---
# <a name="manage-environments-and-workspaces"></a>Administrér miljøer og arbejdsområder

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Oversigt

I emne gennemgås, hvordan du administrerer arbejdsområder og miljøer, når de allerede er oprettet. 

- Et *arbejdsområde* er et sted, hvor du kan gemme og administrere hændelser og rapporter. Det er her, du kan få vist brugeraktivitet i realtid. Når du opretter et arbejdsområde, vælger du den type data, du vil sende til arbejdsområdet. I øjeblikket understøttes webdata og mobilapps. Du kan finde flere oplysninger under [Oprette et arbejdsområde og tilføje medlemmer](create-workspace.md).

- Et *miljø* er et sted, hvor du administrerer dine arbejdsområder og forbindelser. Du kan finde flere oplysninger i [Oprette et nyt miljø](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Administrere et eksisterende arbejdsområde

Du kan vedligeholde flere arbejdsområder samtidig i et miljø. Din [rolle](user-roles.md) bestemmer, hvordan du kan arbejde med dem. 

 - Du skal være miljøadministrator eller arbejdsområdeadministrator for at administrere arbejdsområdet.
 - Som arbejdsområdeadministrator kan du omdøbe eksisterende arbejdsområder eller slette dem. 

:::image type="content" source="media/workspace-edit.png" alt-text="Administrator af arbejdsområde.":::

### <a name="edit-a-workspace-name"></a>Redigere et navn på arbejdsområdet.

1. Gå til **Administration** > **Arbejdsområde**, og vælg **Indstillinger**.

1. Angiv et nyt navn i feltet **Navn på arbejdsområde**.

1. Vælg **Gem** for at anvende dine ændringer.

### <a name="delete-a-workspace"></a>Slet et arbejdsområde

Hvis du sletter et arbejdsområde, fjernes alt indhold, data, indstillinger og tilladelser permanent. Dette kan ikke fortrydes.

1. Gå til **Administration** > **Arbejdsområde**, og vælg **Indstillinger**.

1. Vælg **Slet arbejdsområde**. 

1. Angiv **BEKRÆFT SLETNING** i ene store bogstaver i dialogboksen **Slet arbejdsområde**. 

1. Angiv **Slet** for at slette arbejdsområdet permanent.

### <a name="manage-workspace-members"></a>Administrer medlemmer af arbejdsområde

1. Gå til **Administration** > **Arbejdsområde**, og vælg **Medlemmer**.

1. Vælg **Tilføj medlemmer** for at give adgang til og [tildele roller](user-roles.md). I øjeblikket er det kun **arbejdsområdeadministratorer**, der er tilgængelige.

1. Vælg **Tilføj medlemmer** for at føje dem til dit arbejdsområde.

## <a name="manage-an-existing-environment"></a>Administrere et eksisterende miljø

Som miljøadministrator kan du få adgang til et miljø fra venstre navigationsrude. Du kan konfigurere miljøindstillinger, andre miljøadministratorer og arbejdsområder. Vælg faner for at flytte mellem forskellige områder i Administration.

:::image type="content" source="media/environment-edit.png" alt-text="Administration for miljø.":::

### <a name="rename-an-environment"></a>Omdøbe et miljø

1. Gå til **Administration** > **Miljø**, og vælg **Indstillinger**.

1. Opdater **Miljønavn**, og vælg **Gem** for at anvende ændringerne.

### <a name="manage-environment-members"></a>Administrere miljømedlemmer

1. Gå til **Administration** > **Miljø**, og vælg **Medlemmer**.

1. Vælg **Tilføj medlemmer** for at opdatere medlemmer og [tildele roller](user-roles.md). I øjeblikket er det kun **Miljøadministration**, der er tilgængelig.

1. Vælg **Tilføj medlemmer** for at føje dem til dit miljø.

### <a name="delete-an-environment"></a>Slet et miljø

Miljøadministratorer kan slette miljøer. Før du kan slette et miljø, skal du fjerne alle arbejdsområder under det.

1. Gå til **Administration** > **Miljø**, og vælg **Indstillinger**.

1. Vælg **Slet miljø**. 

1. Angiv **BEKRÆFT SLETNING** i ene store bogstaver i dialogboksen **Slet arbejdsområde**. 

1. Angiv **Slet** for at slette miljøet permanent.

## <a name="manage-connections"></a>Administrer forbindelser

Hvis du opretter forbindelser til målgruppeindsigt, kan du se rapporter i engagementsindsigt baseret på ensartede kundeprofiler. 

Flere oplysninger: [Opret et link mellem målgruppeindsigt og engagementsindsigt](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Administrere personlige data

Du kan slette eller eksportere slutbrugerens identificerbare data for at beskytte kundens personlige data.

Der er flere oplysninger i [Slette og eksportere hændelsesdata, der indeholder personlige oplysninger](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
