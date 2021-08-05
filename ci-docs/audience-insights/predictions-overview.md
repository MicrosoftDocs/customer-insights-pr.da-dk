---
title: Oversigt over understøttede forudsigelsesscenarier
description: Forudsigelsesscenarier og -muligheder, der er dækket af Dynamics 365 Customer Insights-applikationen.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b73046844f6009a2b163b5eaadf5f63f75cda1d8
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539154"
---
# <a name="predictions-overview"></a>Oversigt over forudsigelser

Dynamics 365 Customer Insights leveres med en række muligheder, der udnytter AI og maskinel indlæring til at forudsige data. 

## <a name="out-of-box-models"></a>Køreklare modeller

Den nemmeste måde at starte med at forudsige data på er foruddefinerede modeller, der ofte omtales som køreklare modeller. De kræver kun visse data og strukturer for hurtigt at generere indsigt. I øjeblikket er følgende modeller tilgængelige: 
- [Kundens levetidsværdi](predict-customer-lifetime-value.md): Forudsiger en kundes potentielle omsætning gennem hele interaktionen med en virksomhed. 
- [Produktanbefaling](predict-product-recommendation.md): Foreslår sæt af prædiktive produktanbefalinger baseret på købsadfærd og kunder med lignende købsmønstre.
- [Abonnementsafgang](predict-subscription-churn.md): Forudsiger, om der er risiko for, at en kunde ikke længere vil bruge virksomhedens abonnementsprodukter eller -services.
- [Transaktionsafgang](predict-transactional-churn.md): Forudsiger, om en kunde ikke længere vil købe dine produkter eller services i en bestemt tidsramme.

## <a name="azure-machine-learning-integration"></a>Azure Machine Learning-integration

Hvis en organisation allerede bruger scenarier til maskinel indlæring, som er baseret på Azure Machine Learning-eksperimenter, hjælper de brugerdefinerede modelfunktioner i Customer Insights med at samle brikkerne. Opret arbejdsprocesser, der hjælper dig med at vælge de data, du vil generere indsigt fra, og knyt resultaterne til dine samlede kundeprofiler. Du kan finde flere oplysninger i [Tilpasse modeller til maskinel indlæring](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder-forudsigelse

Nogle gange er datasættene ufuldstændige, og nogle værdier mangler. Customer Insights kan hjælpe med at forudsige manglende værdier for kundeobjektet og segmenterne. Du kan finde flere oplysninger under [Fuldføre delvise data med forudsigelser](predictions.md).
