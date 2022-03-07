---
title: Opret et nyt miljø
description: Formålet med et miljø, og hvordan du kan oprette et nyt.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648110"
---
# <a name="create-a-new-environment"></a>Opret et nyt miljø 

## <a name="overview"></a>Oversigt

Et miljø er et sted, hvor du administrerer dine arbejdsområder og forbindelser. Den måde, du bruger miljøer på, afhænger af organisationen og brugssagen. Du kan f.eks. oprette:

- Enkelt miljø.
- Separate test- og produktionsmiljøer.
- Separate miljøer for bestemte teams eller afdelinger i organisationen, der indeholder relevante hændelser for hver målgruppe.
- Separate miljøer til forskellige globale filialer af din virksomhed.
- Forbindelser til funktioner i Customer Insights, målgruppeindsigt.

## <a name="create-a-new-environment"></a>Opret et nyt miljø

1. Vælg miljøvælgeren i højre side af hovedbanneret og derefter **+Ny**.

   :::image type="content" source="media/environment-picker.png" alt-text="Vælg miljøvælgeren.":::

1. Skriv et **Miljønavn** i ruden **Installation**.

1. Vælg **Type** af konto, afhængigt af din plantype.

1. Vælg **Område**, og vælg **Næste**. 

1. Skriv et **Navn på arbejdsområde**, som giver dig mulighed for at indsamle data til bestemte websteder eller apps. Du kan finde flere oplysninger i [Oprette et arbejdsområde](create-workspace.md).

1. Vælg den **Arbejdsområdetype** (Web eller Mobil), du vil oprette. 

1. Vælg **Vis avancerede indstillinger** for at aktivere eller deaktivere disse valgfrie indstillinger:

   - Skift **Ukendt til kendt** til "aktiveret" for at knytte webhændelser til brugere, der tidligere har godkendt. Du kan finde flere oplysninger under [Genkende webhændelser fra tidligere godkendte besøgende](unknown-to-known.md)
   - Skift **Filtrer robottrafik** til "aktiveret" for at fjerne webtrafik efter robotter for dette arbejdsområde. 

1. Vælg **Fuldfør**, når du er færdig. 

1. Installer kodestykket for at begynde at modtage data, og vælg derefter **Udfør** for at oprette arbejdsområdet. Du kan finde flere oplysninger i [Oversigt over udviklerressourcer](developer-resources.md).

> [!NOTE]
> Du kan nu tilføje medlemmer og tildele deres tilladelsesniveau fra **Rolle**-listen. Du kan finde flere oplysninger under [Roller og tilladelser](user-roles.md). 

Du kan finde flere oplysninger i [Administrere miljøer og arbejdsområder](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Arbejde med dit nye miljø

- [Opret et arbejdsområde](../engagement-insights/create-workspace.md), og tilføj medlemmer.
- [Føj kode til dit websted](../engagement-insights/instrument-website.md) eller [mobilappen](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Få vist en [rapport i realtid](../engagement-insights/view-reports.md), eller opret [brugerdefinerede rapporter](../engagement-insights/custom-reports.md).
- [Oprette forfinede hændelser](../engagement-insights/refined-events.md) til eksport.
- [Eksportér data](../engagement-insights/export-events.md) til Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
