---
title: Eksporter Customer Insights-data til Sendinblue
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: be52554763b57e1c1ef2f960d52bbae79ac9827913c97ac73b429f66bbf4db37
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036048"
---
# <a name="export-segments-to-sendinblue-preview"></a>Eksporter segmenter til Sendinblue (forhåndsversion)

Eksportér segmenter ud fra samlede kundeprofiler til at generere kampagner, levere mailmarketing og bruge bestemte grupper af kunder med Sendinblue.

## <a name="prerequisites-for-connection"></a>Forudsætninger for forbindelse

-   Du har en [Sendinblue-konto](https://www.sendinblue.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Der findes lister i Sendinblue og de tilsvarende id'er.
-   Du har [konfigureret segmenter](segments.md).
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 1 million profiler pr. eksport til Sendinblue.
- Eksport til Sendinblue er begrænset til segmenter.
- Eksport af segmenter med i alt 1 million profiler kan tage op til 90 minutter. 
- Antallet af profiler, du kan eksportere til Sendinblue, afhænger af og er begrænset af din kontrakt med Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Konfigurer forbindelse til Sendinblue

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **Sendinblue** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Som standard er det kun administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Indtast din **[SendinBlue API-nøgle](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Vælg **Jeg accepterer** for at bekræfte **Databeskyttelse af personlige oplysninger og overholdelse af standarder** og vælge **Opret forbindelse** for at initialisere forbindelsen til Sendinblue.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen Sendinblue i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Angiv din Id for **Sendinblue-liste**. 

1. I afsnittet **Datamatching** i feltet **E-mail** skal du vælge det felt i din samlede kundeprofil, der repræsenterer en kundens e-mailadresse. 

1. Du kan også eksportere **Fornavn**, **Efternavn** og **Telefon** for at oprette mere personlige e-mails. Vælg **Tilføj attribut** for at tilknytte disse felter.

1. Vælg de segmenter, du vil eksportere. 

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du gør det muligt for Dynamics 365 Customer Insights at overfører data til Sendinblue, tillader du overførsel af data uden for grænsen for overholdelse for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks. personlige data. Microsoft overfører sådanne data efter din instruktion, men du er ansvarlig for at sikre, at Sendinblue overholder eventuelle forpligtelser til beskyttelse af personlige oplysninger eller sikkerhed, du måtte have. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
