---
title: Eksportér Customer Insights-data til Marketo
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570396"
---
# <a name="connector-for-marketo-preview"></a>Connector til Marketo (prøveversion)

Eksportér segmenter fra de samlede brugerprofiler til at generere kampagner, levere e-mailmarketing og bruge bestemte grupper af kunder med Marketo.

## <a name="prerequisites"></a>Forudsætninger

-   Du har en [Marketo-konto](https://login.marketo.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Der findes eksisterende lister i Marketo og de tilsvarende id'er. Du kan finde flere oplysninger i [Marketo-lister](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Du har [konfigureret segmenter](segments.md).
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="connect-to-marketo"></a>Opret forbindelse til Marketo

1. Gå til **Adminstration** > **Eksportdestinationer**.

1. Under **Marketo** skal du vælge **Konfigurer**.

1. Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.

1. Angiv dit **[Marketo-klient-ID, klientens hemmelige og resterende værtsnavnsslutpunkt](https://developers.marketo.com/rest-api/authentication/)**.

1. Angiv dit **[Marketo-liste-id](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og kompatibilitet**, og vælg **Opret forbindelse** for at initialisere forbindelsen til Marketo.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Eksportér skærmbilleder til Marketo-forbindelse":::

1. Vælg **Næste** for at konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurer connectoren

1. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. 

1. Du kan også eksportere **Fornavn**, **Efternavn**, **By**, **Stat** og **Land/Region** som ekstra felter for at oprette mere personlige e-mails. Vælg **Tilføj attribut** for at tilknytte disse felter.

1. Vælg de segmenter, du vil eksportere. Du kan eksportere op til 1000000 kundeprofiler i alt til Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Vælg felter og segmenter, der skal eksporteres til Marketo":::

1. Vælg **Gem**.

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab). I Marketo kan du nu finde dine segmenter under [Marketo-lister](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 1000000 profiler pr. eksport til Marketo.
- Eksport til Marketo er begrænset til segmenter.
- Eksport af segmenter med i alt 1000000 profiler kan tage op til tre timer. 
- Antallet af profiler, du kan eksportere til Marketo, er afhængige og begrænsede i kontrakten med Marketo.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Marketo, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Marketo overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.
