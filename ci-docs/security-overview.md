---
title: Sikkerhedsindstillinger for Customer Insights
description: Få mere at vide om sikkerhedsindstillinger i Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947408"
---
# <a name="security-settings-in-customer-insights"></a>Sikkerhedsindstillinger for Customer Insights

På siden **Sikkerhed** vises indstillinger for konfiguration af brugertilladelser og -funktioner, der er med til at gøre Dynamics 365 Customer Insights mere sikre. Det er kun administratorer, der har adgang til denne side.

Gå til **Administrator** > **Sikkerhed** for at konfigurere indstillingerne.

Siden **Sikkerhed** indeholder følgende faner:

- [Brugere](#users-tab)
- [API'er](#apis-tab)
- [Private link](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Sikker adgang til kundedata ved hjælp af Customer Lockbox (forhåndsversion)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Fanen Brugere

Adgang til Customer Insights er begrænset til brugere i organisationen, der er føjet til programmet af en administrator. Under fanen **Brugere** kan du administrere brugeradgang og deres tilladelser. Du kan finde flere oplysninger i [Brugertilladelser](permissions.md).

## <a name="apis-tab"></a>Fanen API'er

Få vist og administrer nøglerne til at bruge [Customer Insights-API'er](apis.md) med dataene i dit miljø.

Du kan oprette nye primære og sekundære nøgler ved at vælge **Regenerer primær** eller **Regenerer sekundær**. 

Vælg **Deaktiver** for at blokere API-adgang til miljøet. Hvis API'er er deaktiveret, kan du vælge **Aktivér** for at give adgang igen.

## <a name="private-links-tab"></a>Private links-fane

[Azure Private Link](/azure/private-link/private-link-overview) lader dig oprette forbindelse fra Customer Insights til Azure Data Lake Storage-kontoen via en slutpunkt i dit private slutpunkt i dit virtuelle netværk. I forbindelse med data i en lagerkonto, der ikke er tilgængeligt for det offentlige internet, aktiverer Privat link forbindelsen til det pågældende begrænsede netværk.

> [!IMPORTANT]
> Minimumrollekrav for at konfigurere en privat linkforbindelse:
>
> - Customer Insights: Administrator
> - Den indbyggede Azure-rolle: [Bidragyder til lagerkonto](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Tilladelser til brugerdefineret Azure-rolle: [Microsoft.Storage/storageAccounts/read og Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Opsætning af privat link i Customer Insights er en proces i to trin. Først skal du starte oprettelsen af et privat link fra private **Admin** > **Sikkerhed** > **Private links** i Customer Insights. I ruden **Tilføj privat link** vises lagerkonti fra din lejer, som du har tilladelse til at se. Vælg lagerkontoen, og giv dit samtykke til at oprette det private link.

Derefter skal du godkende det private link på kontosiden for Data Lake Storage. Åbn det link, der vises på skærmen for at godkende det nye private link.

## <a name="key-vault-tab"></a>Fanen Key Vault

Under fanen **Key Vault** kan du kæde og administrere din egen [Azure-key vault](/azure/key-vault/general/basic-concepts) til miljøet.
Den dedikerede Key Vault kan bruges til at oprette og bruge hemmeligheder i en organisations grænse for overholdelse af angivne standarder. Customer Insights kan bruge hemmelighederne i Azure Key Vault til at [konfigurere forbindelser](connections.md) til tredjepartssystemer.

Du kan finde flere oplysninger i [Medbring dit eget Azure Key Vault](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Sikker adgang til kundedata ved hjælp af Customer Lockbox (forhåndsversion)

Customer Insights bruger Power Platform-funktionen Customer Lockbox. Customer Lockbox indeholder en brugergrænseflade, hvor du kan gennemse og godkende (eller afvise) anmodninger om dataadgang. Disse anmodninger opstår, når der skal bruges dataadgang til kundedata for at afslutte en supportsag. Customer Insights skal have en eksisterende forbindelse til et Microsoft Dataverse-miljø i lejeren, før du kan bruge denne funktion.

Du kan finde flere oplysninger om Kunde lockbox i [oversigten](/power-platform/admin/about-lockbox#summary) over Power Platform Customer lockbox. I artiklen beskrives også [arbejdsprocessen](/power-platform/admin/about-lockbox#workflow) og den påkrævede [konfiguration](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) for at aktivere Customer Lockbox.

> [!IMPORTANT]
> Globale administratorer for Power Platform eller Power Platform-administratorer kan godkende Customer Lockbox-anmodninger, der er udstedt for Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
