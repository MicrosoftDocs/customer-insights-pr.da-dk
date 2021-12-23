---
title: Oprette forbindelse til en Azure Data Lake Storage-konto ved hjælp af en tjenestekonto
description: Brug en Azure-tjenestekonto til at oprette forbindelse til din egen Data Lake.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: faef3583337fd495e7baf40b0a208f1d9f10281a
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900236"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Oprette forbindelse til en Azure Data Lake Storage-konto ved hjælp af en Azure-tjenestekonto

I denne artikel beskrives, hvordan du opretter forbindelse mellem Dynamics 365 Customer Insights og en Azure Data Lake Storage-konto ved hjælp af Azure-tjenestekonto i stedet for nøglerne til en lagerkonto. 

Automatiserede værktøjer, der bruger Azure-tjenester, bør altid have begrænsede tilladelser. I stedet for at have programmer til at logge på som bruger med fuld administratorrettigheder, tilbyder Azure tjenestekonti. Du kan bruge servicechefer til på sikker måde at [tilføje eller redigere en mappe med Common Data Model som en datakilde](connect-common-data-model.md) eller [oprette eller opdatere et miljø](create-environment.md).

> [!IMPORTANT]
> - Den lagerkonto for Data Lake, der skal bruge tjenestekontoen, skal have [aktiveret hierarkisk navneområde](/azure/storage/blobs/data-lake-storage-namespace).
> - Du skal have administratortilladelser til dit Azure-abonnement for at oprette en servicechef.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Oprettelse af en Azure-servicekonto til Customer Insights

Før du opretter en ny servicekonto til Customer Insights, skal du kontrollere, om den allerede findes i din organisation.

### <a name="look-for-an-existing-service-principal"></a>Søge efter en eksisterende tjenestekonto

1. Gå til [Azure Admin-portalen](https://portal.azure.com), og log på organisationen.

2. Fra **Azure-tjenester** skal du vælge **Azure Active Directory**.

3. Vælg **Administrer** under **Virksomhedsprogrammer**.

4. Søg efter Microsoft-program-id:
   - Målgruppeindsigt: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` med navnet `Dynamics 365 AI for Customer Insights`
   - Engagementsindsigt: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` med navnet `Dynamics 365 AI for Customer Insights engagement insights`

5. Hvis du finder en tilsvarende post, betyder det, at tjenestekontoen allerede findes. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skærmbillede, der viser en eksisterende tjenestekonto.":::
   
6. Hvis der ikke returneres resultater, skal du oprette en ny tjenestekonto.

>[!NOTE]
>Hvis du vil udnytte alle kræfterne i Dynamics 365 Customer Insights, anbefaler vi, at du føjer begge apps til tjenestekontoen.

### <a name="create-a-new-service-principal"></a>Opret en ny tjenestekonto

1. Installer den nyeste version af Azure Active Directory PowerShell til Graph. Du kan finde flere oplysninger i [Installere Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. På din pc skal du vælge Windows-tasten på tastaturet og søge efter **Windows PowerShell** og vælge **Kør som administrator**.
   
   1. I det PowerShell-vindue, der åbnes, skal du skrive `Install-Module AzureAD`.

2. Opret tjenestekontoen til Customer Insights med Azure AD PowerShell-modulet.

   1. I det PowerShell-vindue, der åbnes, skal du skrive `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Erstat *[dit lejer-id]* med det faktiske ID for din lejer, hvor du vil oprette tjenestekonto. Valgfrit navn for miljøet `AzureEnvironmentName`.
  
   1. Angiv `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Denne kommando opretter tjenestekontoen for at få målgruppeindsigt i den valgte lejer. 

   1. Angiv `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Denne kommando opretter tjenestekontoen til engagementsindsigt på udvalgt lejer.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Giv tilladelser til den pågældende tjenestekonto for at få adgang til lagerkontoen

Gå til Azure-portalen for at give tilladelser til tjenestekontoen for den lagerkonto, du vil bruge i målgruppeindsigt.

1. Gå til [Azure Admin-portalen](https://portal.azure.com), og log på organisationen.

1. Åbn den lagerkonto, som du vil have målgruppeindsigt i for at få adgang.

1. Vælg **Adgangskontrolelementet (IAM)** i venstre rude, og vælg derefter **Tilføj** > **rolletildeling**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skærmbillede, der viser Azure-portalen, mens du tilføjer en rolletildeling.":::

1. Angiv følgende egenskaber i ruden **Tilføj rolletildeling**:
   - Rolle: **Storage Blob Data-bidragyder**
   - Tildel adgang til: **bruger, gruppe eller tjenestekonto**
   - Vælg: **Dynamics 365 AI for Customer Insights** og **Dynamics 365 AI for Customer Insights-engagementsindsigt** (de to [tjenestekonti](#create-a-new-service-principal), du har oprettet tidligere i denne procedure)

1.  Vælg **Gem**.

Det kan tage op til 15 minutter at overføre ændringerne.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Angiv Azure Resource-id eller Azure-abonnementsoplysningerne i lagerkontoen for den vedhæftede målgruppeindsigt.

Vedhæft en Data Lake Storage-konto i målgruppeindsigter for at [gemme outputdata](manage-environments.md) eller [bruge det som en datakilde](connect-common-data-service-lake.md). Med denne indstilling kan du vælge mellem en ressourcebaseret eller abonnementsbaseret fremgangsmåde. Afhængigt af den fremgangsmåde, du vælger, skal du følge proceduren i et af følgende afsnit.

### <a name="resource-based-storage-account-connection"></a>Ressourcebaseret forbindelse til lagerkonto

1. Gå til [Azure Admin-portalen](https://portal.azure.com), log på dit abonnement og åbn lagerkontoen.

1. Gå til **Indstillinger** > **egenskaber** i venstre rude.

1. Kopiér værdien for ressource-ID for lagerkontoen.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopiér ressource-ID for lagerkontoen.":::

1. I målgruppeindsigt skal du indsætte ressource-id i det ressourcefelt, der vises på skærmbilledet for forbindelsen til lagerkontoen.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Angiv oplysninger om ressource-ID for lagerkontoen.":::   

1. Fortsæt med de resterende trin i målgruppeindsigt for at tilknytte lagerkontoen.

### <a name="subscription-based-storage-account-connection"></a>Abonnementbaseret forbindelse til lagerkonto

1. Gå til [Azure Admin-portalen](https://portal.azure.com), log på dit abonnement og åbn lagerkontoen.

1. Gå til **Indstillinger** > **egenskaber** i venstre rude.

1. Gennemse **Abonnement**, **Ressourcegruppe** og **Navn** på lagerkontoen for at sikre dig, at du vælger de rigtige værdier i målgruppeindsigt.

1. I målgruppeindsigt skal du vælge værdierne for de tilsvarende felter, når du tilknytter lagerkontoen.

1. Fortsæt med de resterende trin i målgruppeindsigt for at tilknytte lagerkontoen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
