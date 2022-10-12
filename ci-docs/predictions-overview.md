---
title: Oversigt over forudsigelser
description: Forudsigelsesscenarier og -muligheder, der er dækket af Dynamics 365 Customer Insights-applikationen.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610183"
---
# <a name="predictions-overview"></a>Oversigt over forudsigelser

Dynamics 365 Customer Insights leveres med en række muligheder, der udnytter AI og maskinel indlæring til at forudsige data.

## <a name="out-of-box-models"></a>Køreklare modeller

Den nemmeste måde at starte med at forudsige data på er foruddefinerede modeller, der ofte omtales som køreklare modeller. De kræver kun visse data og strukturer for hurtigt at generere indsigt. Følgende modeller er tilgængelige:

# <a name="individual-consumers-b-to-c"></a>[Individuelle forbrugere (B-til-C)](#tab/b2c)

- [Kundens levetidsværdi](predict-customer-lifetime-value.md): Forudsiger en kundes potentielle omsætning gennem hele interaktionen med en virksomhed.
- [Produktanbefaling](predict-product-recommendation.md): Foreslår sæt af prædiktive produktanbefalinger baseret på købsadfærd og kunder med lignende købsmønstre.
- [Abonnementsafgang](predict-subscription-churn.md): Forudsiger, om der er risiko for, at en kunde ikke længere vil bruge virksomhedens abonnementsprodukter eller -services.
- [Transaktionsafgang](predict-transactional-churn.md): Forudsiger, om en enkelt kunde ikke længere vil købe dine produkter eller services i en bestemt tidsramme.
- [Synspunktsanalyse](sentiment-analysis.md): Analyserer synspunkt i kundefeedback og identificerer de forretningsaspekter, der ofte nævnes.

# <a name="business-accounts-b-to-b"></a>[Virksomhedskonti (B-til-B)](#tab/b2b)

- [Transaktionsafgang](predict-transactional-churn.md): Forudsiger, om en kundekonto ikke længere vil købe dine produkter eller services i en bestemt tidsramme.

---

> [!TIP]
> Vi anbefaler, at du jævnligt opdaterer standardmodeller med opdaterede data for at sikre, at de giver en nøjagtig oplysninger om din sag i forbindelse med forretningsbrug. Data opdateres ad hoc,når systemet opdaterer nye eller opdaterede datakilder. I dette tilfælde vil modellerne dog kun score igen og fortsætte med at bruge de eksisterende træningsdata.
>
> Konfigurer en **opdateringsplan** ved at angive den model, der skal planlægges igen, under konfigurationen. Modellen træner igen og scorer igen denne plan, som du kan ændre når som helst.

## <a name="azure-machine-learning-integration"></a>Azure Machine Learning-integration

Hvis en organisation allerede bruger scenarier til maskinel indlæring, som er baseret på Azure Machine Learning-eksperimenter, hjælper de brugerdefinerede modelfunktioner i Customer Insights med at samle brikkerne. Opret arbejdsprocesser, der hjælper dig med at vælge de data, du vil generere indsigt fra, og knyt resultaterne til dine samlede kundeprofiler. Du kan finde flere oplysninger i [Tilpasse modeller til maskinel indlæring](custom-models.md).

## <a name="manage-existing-predictions"></a>Administrere eksisterende forudsigelser

Gå til siden **Intelligens** > **Forudsigelser**. Under fanen **Mine forudsigelser** kan du se de forudsigelser, du har oprettet, deres forudsigelsestype, navnet på outputobjektet, status, sidste gang forudsigelsen blev redigeret, og sidste gang dataene blev opdateret. Du kan sortere listen over forudsigelser efter enhver kolonne.

Vælg en forudsigelse for at få vist tilgængelige handlinger.

:::image type="content" source="media/predictions.png" alt-text="Siden Mine forudsigelser.":::

- **Rediger** forudsigelsen for at ændre dens egenskaber.
- [**Opdater**](#refresh-a-prediction) forudsigelsen, så den indeholder de seneste data.
- **Vis** detaljerne om forudsigelsen.
- I [**rapporten over inputdatas anvendelighed**](#view-the-input-data-usability-report) kan du få vist fejl, advarsler og anbefalinger.
- **Slet** forudsigelsen.

### <a name="refresh-a-prediction"></a>Opdatere en forudsigelse

Forudsigelser kan opdateres automatisk i en automatisk planlægning eller opdateres manuelt efter behov. Hvis du vil opdatere alle forudsigelser manuelt, skal du vælge **Opdater alle**. Hvis du vil opdatere en forudsigelse manuelt, skal du vælge den og vælge **Opdater**. Hvis du vil [planlægge en automatisk opdatering](schedule-refresh.md), skal du gå til **Administrator** > **System** > **Plan**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Vis rapporten over inputdatas anvendelighed

Rapporten om brugbarhed af inputdata giver en konsolideret visning af de fejl og advarsler, som dine køreklare forudsigelser kan generere. Den giver også anbefalinger til, hvordan du kan forbedre modellens ydeevne.

Rapporten er tilgængelig, når en model har fuldført sin træningsproces. Den er oprettet for hver model separat, uanset om den har fuldført træning eller ej.

Gå til fanen **Mine forudsigelser**, vælg forudsigelsen, og vælg **Rapport over inputdatas anvendelighed**. Du kan også vælge **Rapport over inputdatas anvendelighed** i detaljevisningen for forudsigelsen.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Eksempel på en rapport om brugbarhed af inputdata, der viser en tabel med fejl, advarsler og anbefalinger.":::

Rapporten inkluderer:

- **Navn:** Beskrivende navn på fejlen, advarslen eller anbefalingen.
- **Trin:** Modelfase, -træning eller -score, som oplysningerne refererer til.
- **Tilstand:** Oplysningernes alvorlighed (fejl, advarsel, anbefaling).
- **Kolonnenavn:** Kolonne i et objekt, der skal ændres for at forbedre modellens ydeevne.
- **Objektnavn:** Navn på objektet, der skal ændres for at forbedre modellens ydeevne.
- **Detaljer:** Oplysninger om fejlen, advarslen eller anbefalingen.

[!INCLUDE [footer-include](includes/footer-banner.md)]
