---
title: Oprette forbindelse til en Azure Data Lake Storage-konto ved hjælp af en tjenestekonto
description: Brug en Azure-tjenestekonto til at oprette forbindelse til din egen Data Lake.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: b18d1f42b9510ebf23f0666322819865d132173b
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833378"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Oprette forbindelse til en Azure Data Lake Storage-konto ved hjælp af en Azure-tjenestekonto

I denne artikel beskrives, hvordan du opretter forbindelse mellem Dynamics 365 Customer Insights og en Azure Data Lake Storage-konto ved hjælp af Azure-tjenestekonto i stedet for nøglerne til en lagerkonto.

Automatiserede værktøjer, der bruger Azure-tjenester, bør altid have begrænsede tilladelser. I stedet for at have programmer til at logge på som bruger med fuld administratorrettigheder, tilbyder Azure tjenestekonti. Du kan bruge servicechefer til på sikker måde at [tilføje eller redigere en mappe med Common Data Model som en datakilde](connect-common-data-model.md) eller [oprette eller opdatere et miljø](create-environment.md).

> [!IMPORTANT]
>
> - Den Data Lake-lagerkonto, der skal bruge tjenestekontoen, skal være Gen2 og have [hierarkisk navneområde aktiveret](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1-lagerkonti understøttes ikke.
> - Du skal have administratortilladelser til din Azure-lejer for at oprette en tjenesteprincipal.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Oprettelse af en Azure-servicekonto til Customer Insights

Før du opretter en ny servicekonto til Customer Insights, skal du kontrollere, om den allerede findes i din organisation.

### <a name="look-for-an-existing-service-principal"></a>Søge efter en eksisterende tjenestekonto

1. Gå til [Azure Admin-portalen](https://portal.azure.com), og log på organisationen.

2. Fra **Azure-tjenester** skal du vælge **Azure Active Directory**.

3. Vælg **Microsoft-program** under **Administrer**.

4. Tilføj et filter for **program-id'et start med** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`, eller søg efter navnet `Dynamics 365 AI for Customer Insights`.

5. Hvis du finder en tilsvarende post, betyder det, at tjenestekontoen allerede findes.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skærmbillede, der viser en eksisterende tjenestekonto.":::

6. Hvis der ikke returneres nogen resultater, kan du [oprette en ny tjenesteprincipal](#create-a-new-service-principal). I de fleste tilfælde findes den allerede, og du behøver kun at give tjenesteprincipalen tilladelse til at få adgang til lagerkontoen.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Giv tilladelser til den pågældende tjenestekonto for at få adgang til lagerkontoen

Gå til Azure-portalen for at give tilladelser til servicekontoen for den lagerkonto, du vil bruge i Customer Insights.

1. Gå til [Azure Admin-portalen](https://portal.azure.com), og log på organisationen.

1. Åbn den lagerkonto, som servicechefen for Customer Insights skal have adgang til.

1. Vælg **Adgangskontrolelementet (IAM)** i venstre rude, og vælg derefter **Tilføj** > **rolletildeling**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skærmbillede, der viser Azure-portalen, mens du tilføjer en rolletildeling.":::

1. Angiv følgende egenskaber i ruden **Tilføj rolletildeling**:
   - Rolle: **Storage Blob Data-bidragyder**
   - Tildel adgang til: **bruger, gruppe eller tjenestekonto**
   - Vælg medlemmer: **Dynamics 365 AI til Customer Insights** (den [tjenesteprincipal](#create-a-new-service-principal), du fandt tidligere i denne procedure)

1. Vælg **Gennemgå + tildel**.

Det kan tage op til 15 minutter at overføre ændringerne.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Angiv Azure-ressource-id eller Azure-abonnementsoplysningerne i lagerkontoens vedhæftede fil til Customer Insights

Du kan vedhæfte en Data Lake-lagerkonto i Customer Insights for at [gemme outputdata](manage-environments.md) eller [bruge den som en datakilde](connect-dataverse-managed-lake.md). Med denne indstilling kan du vælge mellem en ressourcebaseret eller abonnementsbaseret fremgangsmåde. Afhængigt af den fremgangsmåde, du vælger, skal du følge proceduren i et af følgende afsnit.

### <a name="resource-based-storage-account-connection"></a>Ressourcebaseret forbindelse til lagerkonto

1. Gå til [Azure Admin-portalen](https://portal.azure.com), log på dit abonnement og åbn lagerkontoen.

1. Gå til **Indstillinger** > **Slutpunkter** i ruden til venstre.

1. Kopiér værdien for ressource-ID for lagerkontoen.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopiér ressource-ID for lagerkontoen.":::

1. I Customer Insights skal du indsætte ressource-id i det ressourcefelt, der vises på skærmbilledet for forbindelsen til lagerkontoen.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Angiv oplysninger om ressource-ID for lagerkontoen.":::   

1. Fortsæt med de resterende trin i Customer Insights for at vedhæfte lagerkontoen.

### <a name="subscription-based-storage-account-connection"></a>Abonnementbaseret forbindelse til lagerkonto

1. Gå til [Azure Admin-portalen](https://portal.azure.com), log på dit abonnement og åbn lagerkontoen.

1. Gå til **Indstillinger** > **egenskaber** i venstre rude.

1. Gennemse **Abonnement**, **Ressourcegruppe** og **Navn** på lagerkontoen for at sikre dig, at du vælger de rette værdier i Customer Insights.

1. I Customer Insights skal du vælge værdierne for de tilsvarende felter, når du tilknytter lagerkontoen.

1. Fortsæt med de resterende trin i Customer Insights for at vedhæfte lagerkontoen.

### <a name="create-a-new-service-principal"></a>Opret en ny tjenestekonto

1. Installer den nyeste version af Azure Active Directory PowerShell til Graph. Du kan finde flere oplysninger i [Installere Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. På din pc skal du trykke på Windows-tasten på tastaturet, søge efter **Windows PowerShell** og vælge **Kør som administrator**.

   1. I det PowerShell-vindue, der åbnes, skal du skrive `Install-Module AzureAD`.

2. Opret tjenestekontoen til Customer Insights med Azure AD PowerShell-modulet.

   1. I det PowerShell-vindue, der åbnes, skal du skrive `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Erstat *[dit mappe-id]* med det faktiske Directory-id for dit Azure-abonnement, hvor du vil oprette tjenestens hovednavn. Valgfrit navn for miljøet `AzureEnvironmentName`.
  
   1. Angiv `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Denne kommando opretter servicekontoen for Customer Insights på det valgte Azure-abonnement.

[!INCLUDE [footer-include](includes/footer-banner.md)]