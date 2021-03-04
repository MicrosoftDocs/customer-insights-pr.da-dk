---
title: Opret forbindelse til en Azure Data Lake Storage Gen2-konto med en tjenestekonto
description: Brug en Azure-tjenestekonto til at få målgruppeindsigt for at oprette forbindelse til dine egen Data Lake, når du vedhæfter den til målgruppeindsigt.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267715"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Opret forbindelse til en Azure Data Lake Storage Gen2-konto med en Azure-tjenestekonto for at få målgruppeindsigt

Automatiserede værktøjer, der bruger Azure-tjenester, bør altid have begrænsede tilladelser. I stedet for at have programmer til at logge på som bruger med fuld administratorrettigheder, tilbyder Azure tjenestekonti. Læs videre for at få mere at vide om, hvordan du opretter forbindelse til målgruppeindsigt med en Azure Data Lake Storage Gen2-konto ved hjælp af en Azure-tjenestekonto i stedet for lagerkontonøgler. 

Du kan bruge tjenestekontoen til at [tilføje eller redigere en Common Data Model-mappe på en sikker måde som datakilde](connect-common-data-model.md) eller [oprette nye eller opdatere et eksisterende miljø](manage-environments.md#create-an-environment-in-an-existing-organization).

> [!IMPORTANT]
> - Azure Data Lake Gen2-lagerkontoen, hvor tjenestens hovednavn skal bruges, skal have [aktiveret HNS (hierarkisk navneplads)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).
> - Du skal have administratorrettigheder til dit Azure-abonnement for at oprette tjenestekonto.

## <a name="create-azure-service-principal-for-audience-insights"></a>Opret Azure-tjenestekonto til målgruppeindsigt

Før du opretter en ny tjenestekonto til målgruppeindsigt, skal du kontrollere, om den allerede findes i organisationen.

### <a name="look-for-an-existing-service-principal"></a>Søge efter en eksisterende tjenestekonto

1. Gå til [Azure Admin-portalen](https://portal.azure.com), og log på organisationen.

2. Vælg **Azure Active Directory** mellem Azure-tjenesterne.

3. Vælg **Administrer** under **Virksomhedsprogrammer**.

4. Søg efter målgruppeindsigt i program-ID for første part `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` eller navn `Dynamics 365 AI for Customer Insights`.

5. Hvis du finder en tilsvarende post, betyder det, at der findes en tjenestekonto til målgruppeindsigt. Du behøver ikke at oprette igen.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skærmbillede, der viser den eksisterende tjenestekonto.":::
   
6. Hvis der ikke returneres resultater, skal du oprette en ny tjenestekonto.

### <a name="create-a-new-service-principal"></a>Opret en ny tjenestekonto

1. Installer den nyeste version af **Azure Active Directory PowerShell til Graph**. Du kan finde flere oplysninger i [Installation af Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - Vælg Windows-tasten på tastaturet i din PC, og søg efter **Windows PowerShell**, og **Kør som administrator**.
   
   - I det PowerShell-vindue, der åbnes, skal du skrive `Install-Module AzureAD`.

2. Opret tjenestekonto til målgruppeindsigt i Azure AD PowerShell-modulet.
   - I det PowerShell-vindue, der åbnes, skal du skrive `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Erstat "dit lejer-ID" med det faktiske ID for din lejer, hvor du vil oprette tjenestekonto. Valgfrit navn for miljøet `AzureEnvironmentName`.
  
   - Angiv `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Denne kommando opretter tjenestekontoen for at få målgruppeindsigt i den valgte lejer.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Giv tilladelser til den pågældende tjenestekonto for at få adgang til lagerkontoen

Gå til Azure-portalen for at give tilladelser til tjenestekontoen for den lagerkonto, du vil bruge i målgruppeindsigt.

1. Gå til [Azure Admin-portalen](https://portal.azure.com), og log på organisationen.

1. Åbn den lagerkonto, som du vil have målgruppeindsigt i for at få adgang.

1. Vælg **Adgangskontrol (IAM)** i navigationsruden, og vælg **Tilføj** > **Tilføj rolletildeling**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skærmbillede, der viser Azure-portalen under tilføjelse af en rolletildeling.":::
   
1. I ruden **Tilføj rolletildeling** skal du angive følgende egenskaber:
   - Rolle: *Storage Blob Data-bidragyder*
   - Tildel adgang til: *bruger, gruppe eller tjenestekonto*
   - Vælg: *Dynamics 365 AI for Customer Insights* (den [tjenestekonto, du har oprettet](#create-a-new-service-principal))

1.  Vælg **Gem**.

Det kan tage op til 15 minutter at overføre ændringerne.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Angiv Azure Resource-id eller Azure-abonnementsoplysningerne i lagerkontoen for den vedhæftede målgruppeindsigt.

Vedhæft en Azure Data Lake-lagerkonto i målgruppeindsigter for at [gemme outputdata](manage-environments.md) eller [bruge det som en datakilde](connect-common-data-service-lake.md). Hvis du vælger indstillingen Azure Data Lake, kan du vælge mellem en ressourcebaseret eller en abonnementsbaseret metode.

Følg nedenstående fremgangsmåde for at angive de nødvendige oplysninger om den valgte fremgangsmåde.

### <a name="resource-based-storage-account-connection"></a>Ressourcebaseret forbindelse til lagerkonto

1. Gå til [Azure Admin-portalen](https://portal.azure.com), log på dit abonnement, og åbn lagerkontoen.

1. Gå til **Indstillinger** > **Egenskaber** i navigationsrude.

1. Kopiér værdien for ressource-ID for lagerkontoen.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopiér ressource-ID for lagerkontoen.":::

1. I målgruppeindsigt skal du indsætte ressource-id i det ressourcefelt, der vises på skærmen med lagerkontoforbindelsen.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Angiv oplysninger om ressource-ID for lagerkontoen.":::   
   
1. Fortsæt med de resterende trin i målgruppeindsigt for at tilknytte lagerkontoen.

### <a name="subscription-based-storage-account-connection"></a>Abonnementbaseret forbindelse til lagerkonto

1. Gå til [Azure Admin-portalen](https://portal.azure.com), log på dit abonnement, og åbn lagerkontoen.

1. Gå til **Indstillinger** > **Egenskaber** i navigationsrude.

1. Gennemse **Abonnement**, **Ressourcegruppe** og **Navn** på lagerkontoen for at sikre dig, at du vælger de rigtige værdier i målgruppeindsigt.

1. I målgruppeindsigt kan du vælge værdier eller for de tilsvarende felter, når du tilknytter lagerkontoen.
   
1. Fortsæt med de resterende trin i målgruppeindsigt for at tilknytte lagerkontoen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]