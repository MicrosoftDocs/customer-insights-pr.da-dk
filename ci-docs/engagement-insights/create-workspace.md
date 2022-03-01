---
title: Opret et nyt arbejdsområde
description: Formålet med et arbejdsområde, og hvordan du kan oprette et nyt.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 816f948331a06794c15000eb779f93cc7fdda202
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645303"
---
# <a name="create-a-new-workspace-and-add-members"></a>Oprette et nyt arbejdsområde og tilføje medlemmer

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Et arbejdsområde er, hvordan du kan få vist brugeraktivitet i realtid for bedre at forstå dine publikum. Det er her, du gemmer og administrerer hændelser og rapporter.

Når du opretter et arbejdsområde, vælger du den type data, du vil fokusere på. Du kan når som helst føje andre brugere eller medlemmer til et eksisterende arbejdsområde. 

## <a name="create-a-new-workspace"></a>Opret et nyt arbejdsområde

Processen til oprettelse af et arbejdsområde omfatter opsætning af *miljøet* til organisering af arbejdsområdet. Et miljø er plads, der kan indeholde et eller flere arbejdsområder. Du kan bruge et miljø til at administrere dine arbejdsområder og forbindelser til Customer Insights og målgruppeindsigtsfunktioner.

1. Vælg **Ny** i arbejdsområdeskifteren.

   :::image type="content" source="media/new-workspace.png" alt-text="Siden Customer Insights med opslag i navigationsrude og beskrivelse.":::

1. Angiv et **Navn på arbejdsområde** i ruden **Arbejdsområde**.

   :::image type="content" source="media/workspace-name.png" alt-text="Skriv et navn på arbejdsområdet.":::

1. Vælg den platformstype (Web eller Mobil), du vil måle.

1. Vælg **Vis avancerede indstillinger** for at aktivere eller deaktivere disse valgfrie indstillinger:

   - Skift **Ukendt til kendt** til "aktiveret" for at knytte webhændelser til brugere, der tidligere har godkendt. Du kan finde flere oplysninger under [Genkende webhændelser fra tidligere godkendte besøgende](unknown-to-known.md)
   - Skift **Filtrer robottrafik** til "aktiveret" for at fjerne webtrafik efter robotter for dette arbejdsområde. 

1. Vælg **Fuldfør**, når du er færdig. 

1. Installer kodestykket for at begynde at modtage data, og vælg derefter **Udfør** for at oprette arbejdsområdet. Du kan finde flere oplysninger i [Oversigt over udviklerressourcer](developer-resources.md).

> [!NOTE]
> Du kan nu tilføje medlemmer og tildele deres tilladelsesniveau fra **Rolle**-listen. Du kan finde flere oplysninger under [Roller og tilladelser](user-roles.md). 

Du kan finde flere oplysninger i [Administrere miljøer og arbejdsområder](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
