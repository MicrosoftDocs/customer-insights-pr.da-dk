---
title: Konfigurer sikkerhedsindstillinger
description: Få mere at vide om sikkerhedsindstillinger i Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246055"
---
# <a name="configure-security-settings"></a>Konfigurer sikkerhedsindstillinger

Administrer API-nøgler, få adgang til kundedata, og konfigurer et Azure Private Link.

## <a name="manage-api-keys"></a>Administrer API-nøgler

Få vist og administrer nøglerne til at bruge [Customer Insights-API'er](apis.md) med dataene i dit miljø.

1. Gå til **System** > **Sikkerhed**, og vælg fanen **API'er**.

1. Hvis API-adgang til miljøet ikke er konfigureret, skal du vælge **Aktivér**. Eller vælg **Deaktiver** for at blokere API-adgang til miljøet, og bekræft.

1. Administrer de primære og sekundære API-nøgler:

   1. Hvis du vil have vist den primære eller sekundære API-nøgle, skal du vælge symbolet **Vis**.

   1. Hvis du vil kopiere den primære eller sekundære API-nøgle, skal du vælge symbolet **Kopier**.

   1. Du kan oprette nye primære og sekundære API-nøgler ved at vælge **Regenerer primær** eller **Regenerer sekundær**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Sikker adgang til kundedata ved hjælp af Customer Lockbox (forhåndsversion)

Customer Insights bruger Power Platform-funktionen Customer Lockbox. Customer Lockbox indeholder en brugergrænseflade, hvor du kan gennemse og godkende (eller afvise) anmodninger om dataadgang. Disse anmodninger opstår, når der skal bruges dataadgang til kundedata for at afslutte en supportsag. Customer Insights skal have en eksisterende forbindelse til et Microsoft Dataverse-miljø i lejeren, før du kan bruge denne funktion.

Du kan finde flere oplysninger om Kunde lockbox i [oversigten](/power-platform/admin/about-lockbox#summary) over Power Platform Customer lockbox. I artiklen beskrives også [arbejdsprocessen](/power-platform/admin/about-lockbox#workflow) og den påkrævede [konfiguration](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) for at aktivere Customer Lockbox.

> [!IMPORTANT]
> Globale administratorer for Power Platform eller Power Platform-administratorer kan godkende Customer Lockbox-anmodninger, der er udstedt for Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Konfigurere et privat Azure-link

[Azure Private Link](/azure/private-link/private-link-overview) lader dig oprette forbindelse fra Customer Insights til Azure Data Lake Storage-kontoen via en slutpunkt i dit private slutpunkt i dit virtuelle netværk. I forbindelse med data i en lagerkonto, der ikke er tilgængeligt for det offentlige internet, aktiverer Privat link forbindelsen til det pågældende begrænsede netværk.

> [!IMPORTANT]
> Minimumrollekrav for at konfigurere en privat linkforbindelse:
>
> - Customer Insights: Administrator
> - Den indbyggede Azure-rolle: [Bidragyder til lagerkonto](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Tilladelser til brugerdefineret Azure-rolle: [Microsoft.Storage/storageAccounts/read og Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Gå i Customer Insights til **Administration** > **Sikkerhed**, og vælg fanen **Private links**.

1. Vælg **Tilføj privat link**.

   I ruden **Tilføj privat link** vises lagerkonti fra din lejer, som du har tilladelse til at se.

1. Vælg abonnement, ressourcegruppe og lagerkonto.

1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.

1. Vælg **Gem**.

1. Gå til kontoen Data Lake-lager, og åbn det link, der vises på skærmen.

1. Godkend det private link.


[!INCLUDE [footer-include](includes/footer-banner.md)]
