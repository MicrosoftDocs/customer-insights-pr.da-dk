---
title: Sådan administrerer du miljøer
description: Få mere at vide om, hvordan du administrerer eksisterende Customer Insights-miljøer som administrator".
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833485"
---
# <a name="how-to-manage-environments"></a>Sådan administrerer du miljøer

Administratorer [opretter](create-environment.md) og administrerer miljøer. De kan ændre visse indstillinger i eksisterende miljøer. Forretning, type, område, lagerindstilling og Dataverse-indstillinger kan ikke ændres, når miljøet er oprettet. Hvis du vil ændre disse indstillinger, skal du nulstille miljøet eller oprette et nyt miljø.

## <a name="edit-an-existing-environment"></a>Redigere et eksisterende miljø

Du kan redigere nogle af oplysningerne i eksisterende miljøer.

1. Vælg **Miljø**-vælgeren i appens overskrift.

1. Vælg **Rediger**-ikonet.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikon for redigering af miljøindstillingerne.":::

1. I feltet **Rediger miljø** kan du opdatere miljøindstillingerne.

Hvis du vil starte med et nyt miljø, kan du se [Oprette et nyt miljø](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Skift ejeren af et miljø

Flere brugere kan have administratortilladelser, men kun én bruger ejer et miljø. Det er som standard administratoren, der oprindeligt opretter et miljø. Som administrator af et miljø kan du tildele ejerskab til en anden bruger med administratortilladelser.

1. Vælg **Miljø**-vælgeren i appens overskrift.

1. Vælg **Rediger**-ikonet.

1. Gå til trinnet **Grundlæggende oplysninger** i feltet **Rediger miljø**.

1. Vælg den nye ejer af miljøet i feltet **Skift ejer for miljøet**.  

1. Vælg **Gennemse og udfør**, og **opdater** for at anvende ændringerne.

## <a name="claim-ownership-of-an-environment"></a>Krav på ejerskab af et miljø

Hvis ejerens brugerkonto slettes eller annulleres, har miljøet ingen ejer. Alle brugere med administratorrettigheder kan gøre krav på ejerskabet og blive den nye ejer. De kan fortsat eje miljøet eller ændre [ejerskabet til en anden administrator](#change-the-owner-of-an-environment).

Hvis du vil kræve ejerskab, skal du vælge knappen **Tag ejerskab**, der vises øverst på alle sider i Customer Insights, når den oprindelige ejer har forladt organisationen.

## <a name="reset-an-existing-environment-preview"></a>Nulstil et eksisterende miljø (forhåndsversion)

Som ejer af et miljø kan du nulstille et miljø til en tom tilstand, hvis du vil slette alle konfigurationer og fjerne de slettede data.

1. Vælg **Miljø**-vælgeren i appens overskrift.

1. Vælg det miljø, du vil nulstille, og vælg den lodrette ellipse (&vellip;).

1. Vælg indstillingen **Nulstil**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontrolelement til nulstilling af et miljø.":::

1. Vælg, om du vil nulstille hele miljøet, alt undtagen datakilderne eller det, der konfigureres ud over unified customer profile.

1. Bekræft ved at angive navnet på miljøet og vælge **Nulstil**.

## <a name="delete-an-existing-environment"></a>Slet et eksisterende miljø

Som ejer af et miljø kan du slette et miljø, du administrerer.

1. Vælg **Miljø**-vælgeren i appens overskrift.

1. Vælg det miljø, du vil nulstille, og vælg den lodrette ellipse (&vellip;). 

1. Vælg indstillingen **Slet**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontrolelement til sletning af miljøet.":::

1. Bekræft sletningen ved at skrive navnet på miljøet og vælge **Slet**.

> [!IMPORTANT]
> Hvis du sletter et miljø, fjernes forbindelsen ikke til et Dataverse-miljø. Hvis du planlægger at oprette forbindelse mellem det samme Dataverse-miljø og et nyt Customer Insights-miljø i fremtiden, skal du fjerne den pågældende forbindelse  Få mere at vide om, hvordan du [fjerner en eksisterende forbindelse til et Dataverse-miljø](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
