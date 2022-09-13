---
title: Oversigt over forudsigelser
description: Forudsigelsesscenarier og -muligheder, der er dækket af Dynamics 365 Customer Insights-applikationen.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 32240c8c43751d8514d38b392f23ef4138d50ee2
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411824"
---
# <a name="predictions-overview"></a>Oversigt over forudsigelser

Dynamics 365 Customer Insights leveres med en række muligheder, der udnytter AI og maskinel indlæring til at forudsige data. 

## <a name="out-of-box-models"></a>Køreklare modeller

Den nemmeste måde at starte med at forudsige data på er foruddefinerede modeller, der ofte omtales som køreklare modeller. De kræver kun visse data og strukturer for hurtigt at generere indsigt. I øjeblikket er følgende modeller tilgængelige: 

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

- [Kundens levetidsværdi](predict-customer-lifetime-value.md): Forudsiger en kundes potentielle omsætning gennem hele interaktionen med en virksomhed.
- [Produktanbefaling](predict-product-recommendation.md): Foreslår sæt af prædiktive produktanbefalinger baseret på købsadfærd og kunder med lignende købsmønstre.
- [Abonnementsafgang](predict-subscription-churn.md): Forudsiger, om der er risiko for, at en kunde ikke længere vil bruge virksomhedens abonnementsprodukter eller -services.
- [Transaktionsafgang](predict-transactional-churn.md): Forudsiger, om en kunde ikke længere vil købe dine produkter eller services i en bestemt tidsramme.
- [Synspunktsanalyse](sentiment-analysis.md): Analysér synspunkt i kundefeedback, og identificer de forretningsaspekter, der ofte nævnes.

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

- [Transaktionsafgang](predict-transactional-churn.md): Forudsiger, om en kunde ikke længere vil købe dine produkter eller services i en bestemt tidsramme.

---

> [!TIP]
> Vi anbefaler, at du jævnligt opdaterer standardmodeller med opdaterede data for at sikre, at de giver en nøjagtig oplysninger om din sag i forbindelse med forretningsbrug. Data opdateres ad hoc,når systemet opdaterer nye eller opdaterede datakilder. I dette tilfælde vil modellerne dog kun score igen og fortsætte med at bruge de eksisterende træningsdata.
>
> Du kan konfigurere en **opdateringsplan** ved at angive den model, der skal planlægges igen, i konfigurationsoplevelsen. Modellen træner igen og scorer igen denne plan, som du kan ændre når som helst.

## <a name="azure-machine-learning-integration"></a>Azure Machine Learning-integration

Hvis en organisation allerede bruger scenarier til maskinel indlæring, som er baseret på Azure Machine Learning-eksperimenter, hjælper de brugerdefinerede modelfunktioner i Customer Insights med at samle brikkerne. Opret arbejdsprocesser, der hjælper dig med at vælge de data, du vil generere indsigt fra, og knyt resultaterne til dine samlede kundeprofiler. Du kan finde flere oplysninger i [Tilpasse modeller til maskinel indlæring](custom-models.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
