---
title: Sikkerhedsindstillinger i Dynamics 365 Customer Insights
description: Få mere at vide om sikkerhedsindstillinger i Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653714"
---
# <a name="security-overview-page"></a>Sikkerhedsoversigtsside

På siden **Sikkerhed** vises indstillinger for konfiguration af brugertilladelser og -funktioner, der er med til at gøre Dynamics 365 Customer Insights mere sikre. Det er kun administratorer, der har adgang til denne side. 

Gå til **Administrator** > **Sikkerhed** for at konfigurere indstillingerne.

Siden **Sikkerhed** indeholder følgende faner:
- [Brugere](#users-tab)
- [API'er](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Fanen Brugere

Adgang til Customer Insights er begrænset til brugere i organisationen, der er føjet til programmet af en administrator. Under fanen **Brugere** kan du administrere brugeradgang og deres tilladelser. Du kan finde flere oplysninger i [Brugertilladelser](permissions.md).

## <a name="apis-tab"></a>Fanen API'er

Få vist og administrer nøglerne til at bruge [Customer Insights-API'er](apis.md) med dataene i dit miljø.

Du kan oprette nye primære og sekundære nøgler ved at vælge **Regenerer primær** eller **Regenerer sekundær**. 

Vælg **Deaktiver** for at blokere API-adgang til miljøet. Hvis API'er er deaktiveret, kan du vælge **Aktivér** for at give adgang igen.

## <a name="key-vault-tab"></a>Fanen Key Vault

Under fanen **Key Vault** kan du kæde og administrere din egen [Azure-key vault](/azure/key-vault/general/basic-concepts) til miljøet.
Den dedikerede Key Vault kan bruges til at oprette og bruge hemmeligheder i en organisations grænse for overholdelse af angivne standarder. Customer Insights kan bruge hemmelighederne i Azure Key Vault til at [konfigurere forbindelser](connections.md) til tredjepartssystemer.

Du kan finde flere oplysninger i [Medbring dit eget Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
