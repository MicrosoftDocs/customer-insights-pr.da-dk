---
title: Oprette forbindelse til en Azure Data Lake Storage-konto ved hjælp af en Azure-servicesikkerhedskonto
description: Brug en Azure-servicesikkerhedskonto til at oprette forbindelse til din egen Data Lake.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304190"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Oprette forbindelse til en Azure Data Lake Storage-konto ved hjælp af en Azure-servicesikkerhedskonto

Dynamics 365 Customer Insights giver mulighed for at oprette forbindelse til en Azure Data Lake Storage-konto ved hjælp af en Azure-servicesikkerhedskonto i stedet for nøglerne til lagerkontoen.

Automatiserede værktøjer, der bruger Azure-tjenester, skal have begrænsede tilladelser. I stedet for at have programmer til at logge på som bruger med fuld administratorrettigheder, tilbyder Azure tjenestekonti. Brug tjenestekonti til på sikker måde at [tilføje eller redigere en mappe med Common Data Model som datakilde](connect-common-data-model.md) eller [oprette eller opdatere et miljø](create-environment.md).

## <a name="prerequisites"></a>Forudsætninger

- Den Data Lake Storage-konto, der skal bruge servicesikkerhedskontoen, skal være Gen2. Azure Data Lake Gen1-lagerkonti understøttes ikke.
- Kontoen Data Lake Storage har funktionen [hierarkisk navneområde aktiveret](/azure/storage/blobs/data-lake-storage-namespace).
- Administratortilladelser til din Azure-lejer, hvis du skal oprette en ny servicesikkerhedskonto.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Oprettelse af en Azure-servicekonto til Customer Insights

Før du opretter en ny servicekonto til Customer Insights, skal du kontrollere, om den allerede findes i din organisation. I de fleste tilfælde findes den allerede.

### <a name="look-for-an-existing-service-principal"></a>Søge efter en eksisterende servicesikkerhedskonto

1. Gå til [Azure Admin-portalen](https://portal.azure.com), og log på organisationen.

2. Fra **Azure-tjenester** skal du vælge **Azure Active Directory**.

3. Vælg **Microsoft-program** under **Administrer**.

4. Tilføj et filter for **program-id'et start med** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff`, eller søg efter navnet `Dynamics 365 AI for Customer Insights`.

5. Hvis du finder en tilsvarende post, betyder det, at servicesikkerhedskontoen allerede findes. [Giv tilladelser](#grant-permissions-to-the-service-principal-to-access-the-storage-account) til den pågældende servicesikkerhedskonto for at få adgang til lagerkontoen.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Skærmbillede, der viser en eksisterende servicesikkerhedskonto.":::

6. Hvis der ikke returneres resultater, skal du [oprette en ny servicesikkerhedskonto](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Opret en ny servicesikkerhedskonto

1. Installer den nyeste version af Azure Active Directory PowerShell til Graph. Du kan finde flere oplysninger i [Installere Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. På din pc skal du trykke på Windows-tasten på tastaturet, søge efter **Windows PowerShell** og vælge **Kør som administrator**.

   1. I det PowerShell-vindue, der åbnes, skal du skrive `Install-Module AzureAD`.

2. Opret servicesikkerhedskontoen til Customer Insights med Azure AD PowerShell-modulet.

   1. I det PowerShell-vindue, der åbnes, skal du skrive `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Erstat *[dit mappe-id]* med det faktiske Directory-id for dit Azure-abonnement, hvor du vil oprette tjenestens hovednavn. Valgfrit navn for miljøet `AzureEnvironmentName`.
  
   1. Angiv `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Denne kommando opretter servicekontoen for Customer Insights på det valgte Azure-abonnement.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Giv tilladelser til den pågældende servicesikkerhedskonto for at få adgang til lagerkontoen

Hvis du vil tildele tilladelser til servicesikkerhedskontoen for den lagerkonto, du vil bruge i Customer Insights, skal en af følgende roller tildeles lagerkontoen eller -beholderen:

|Legitimationsoplysninger|Krav|
|----------|------------|
|Aktuel bruger logget på|**Rolle**: Storage Blob Data Læser, Storage Blob bidragyder Eller Storage Blob Owner.<br>**Niveau**: Tildelte tilladelser til lagerkontoen eller beholderen.</br>|
|Customer Insights-servicesikkerhedskonto -<br>Brug Azure Data Lake Storage som en datakilde</br>|Indstilling 1<ul><li>**Rolle**: Storage Blob Data Læser, Storage Blob Data     Bidragyder Eller Storage Blob Data-ejer.</li><li>**Niveau**: Tildelte tilladelser til lagerkontoen.</li></ul>Mulighed 2 *(uden deling af tjenestens hovedadgang til lagerkontoen)*<ul><li>**Rolle 1**: Storage Blob Data Læser, Storage Blob Data Bidragyder eller Storage Blob Data-ejer.</li><li>**Niveau**: Tildelte tilladelser til beholderen.</li><li>**Rolle 2**: Storage Blob-datadelegator.</li><li>**Niveau**: Tildelte tilladelser til lagerkontoen.</li></ul>|
|Customer Insights-servicesikkerhedskonto - <br>Brug Azure Data Lake Storage som output eller destination</br>|Indstilling 1<ul><li>**Rolle**: Storage Blob Data Læser, Storage Blob bidragyder eller Storage Blob Owner.</li><li>**Niveau**: Tildelte tilladelser til lagerkontoen.</li></ul>Mulighed 2 *(uden deling af tjenestens hovedadgang til lagerkontoen)*<ul><li>**Rolle**: Storage Blob Data Læser, Storage Blob bidragyder eller Storage Blob Owner.</li><li>**Niveau**: Tildelte tilladelser til beholderen.</li><li>**Rolle 2**: Storage Blob-delegator.</li><li>**Niveau**: Tildelte tilladelser til lagerkontoen.</li></ul>|

1. Gå til [Azure Admin-portalen](https://portal.azure.com), og log på organisationen.

1. Åbn den lagerkonto, som servicechefen for Customer Insights skal have adgang til.

1. Vælg **Adgangskontrolelementet (IAM)** i venstre rude, og vælg derefter **Tilføj** > **rolletildeling**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Skærmbillede, der viser Azure-portalen, mens du tilføjer en rolletildeling.":::

1. Angiv følgende egenskaber i ruden **Tilføj rolletildeling**:
   - **Rolle**: Storage Blob Data Læser, Storage Blob Data Bidragyder eller Storage Blob Data-ejer baseret på legitimationsoplysninger ovenfor.
   - **Tildel adgang til**: **bruger, gruppe eller servicesikkerhedskonto**
   - **Vælg** medlemmer: **Dynamics 365 AI til Customer Insights** (den [servicesikkerhedskonto](#create-a-new-service-principal), du fandt tidligere i denne procedure)

1. Vælg **Gennemgå + tildel**.

Det kan tage op til 15 minutter at overføre ændringerne.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Angiv Azure-ressource-id eller Azure-abonnementsoplysningerne i lagerkontoens vedhæftede fil til Customer Insights

Tilknyt en Data Lake Storage-konto i Customer Insights for at [gemme outputdata](manage-environments.md) eller [bruge det som en datakilde](connect-dataverse-managed-lake.md). Vælg mellem en [ressourcebaseret](#resource-based-storage-account-connection) eller [abonnementsbaseret](#subscription-based-storage-account-connection) fremgangsmåde, og følg disse trin.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
