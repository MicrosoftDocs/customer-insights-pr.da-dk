---
title: Eksportér Customer Insights-data til Mailchimp
description: Få mere at vide om, hvordan du konfigurerer forbindelsen til Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598194"
---
# <a name="connector-for-mailchimp-preview"></a>Connector til Mailchimp (prøveversion)

Eksportér segmenter af samlede kundeprofiler til MailChimp for at oprette nyhedsbreve og e-mailkampagner.

## <a name="prerequisites"></a>Forudsætninger

-   Du har en [Mailchimp-konto](https://mailchimp.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Der findes eksisterende målgrupper i Mailchimp og de tilsvarende id'er. Du kan finde flere oplysninger i [Mailchimp-målgrupper](https://mailchimp.com/help/create-audience/).
-   Du har [konfigureret segmenter](segments.md)
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="connect-to-mailchimp"></a>Opret forbindelse til Mailchimp

1. Gå til **Adminstration** > **Eksportdestinationer**.

1. Under **Mailchimp** skal du vælge **Konfigurer**.

1. Giv din eksportdestination et genkendeligt navn ifeltet **Vist navn**.

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Angiv dit **[Mailchimp-målgruppe-id](https://mailchimp.com/help/find-audience-id/)**, og vælg **Opret forbindelse** for at initialisere forbindelsen til Mailchimp.

1. Vælg **Godkendelse med Mailchimp**, og angiv dine Mailchimp-legitimationsoplysninger.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Eksportér skærmbilleder til Mailchimp-forbindelse":::

1. Vælg **Næste** for at konfigurere eksporten.

## <a name="configure-the-connector"></a>Konfigurer connectoren

1. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. 

1. Du kan også eksportere **Fornavn** og **Efternavn** som ekstra felter for at oprette mere personlige e-mails. Vælg **Tilføj attribut** for at tilknytte disse felter.

1. Vælg de segmenter, du vil eksportere. Du kan eksportere op til 1000000 kundeprofiler i alt til Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Vælge felter og segmenter, der skal eksporteres til MailChimp":::

1. Vælg **Gem**.

## <a name="export-the-data"></a>Eksportér dataene

Du kan [eksportere data efter behov](export-destinations.md). Eksporten vil også køre med alle [planlagte opdateringer](system.md#schedule-tab). I Mailchimp kan du nu finde dine segmenter under [Mailchimp-målgrupper](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 1000000 profiler pr. eksport til Mailchimp.
- Eksport til Mailchimp er begrænset til segmenter.
- Eksport af segmenter med det samlede antal 1000000-profiler kan tage op til tre timer på grund af begrænsninger på udbydersiden. 
- Antallet af profiler, du kan eksportere til Mailchimp, er afhængige og begrænsede i kontrakten med Mailchimp.

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til Mailchimp, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f. eks. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at Mailchimp overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]