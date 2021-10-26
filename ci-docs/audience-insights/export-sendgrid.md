---
title: Eksportere Customer Insights-data til SendGrid
description: Få mere at vide om, hvordan du konfigurerer forbindelsen og eksporterer til SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: da3da5ea68d178deab3b9ab31dd810dee610f607
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617824"
---
# <a name="export-segments-to-sendgrid-preview"></a>Eksportér segmenter til SendGrid (forhåndsversion)

Eksportér segmenter med ensartede kundeprofiler til SendGrid-kontaktlister, og brug dem til kampagner og mailmarketing i SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Forudsætninger for en forbindelse

-   Du har en [SendGrid-konto](https://sendgrid.com/) og tilsvarende administratorlegitimationsoplysninger.
-   Der findes eksisterende kontaktlister i SendGrid og de tilsvarende id'er. Du kan finde flere oplysninger [i SendGrid – Administrere kontakter](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Du har [konfigureret segmenter](segments.md)-tilladelser i målgruppen Insights.
-   Samlede kundeprofiler i de eksporterede segmenter indeholder felter, der repræsenterer en e-mailadresse.

## <a name="known-limitations"></a>Kendte begrænsninger

- Op til 100.000 kundeprofiler i alt til SendGrid.
- Eksport til SendGrid er begrænset til segmenter.
- Det kan tage op til et par timer at eksportere op til 100.000 kundeprofiler til SendGrid. 
- Antallet af kundeprofiler, du kan eksportere til SendGrid, er begrænset og afhænger af din kontrakt med SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Konfigurer forbindelsen til SendGrid

1. Gå til **Administrator** > **Forbindelser**.

1. Vælg **Tilføj forbindelse**, og vælg **SendGrid** for at konfigurere forbindelsen.

1. Giv din forbindelse et genkendeligt navn i feltet **Vist navn**. Visningsnavn og forbindelsestype beskriver denne forbindelse. Det anbefales, at du vælger et navn, der forklarer formålet med og målet for forbindelsen.

1. Vælg, hvem der kan bruge denne forbindelse. Hvis du ikke kan gøre noget, er standarden Administratorer. Du kan finde flere oplysninger under [Tillad bidragydere at bruge en forbindelse til eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Angiv **SendGrid API-nøglen** [SendGrid API-nøgle](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Vælg **Jeg accepterer** for at bekræfte **Beskyttelse af personlige oplysninger og overholdelse af angivne standarder**.

1. Vælg **Opret forbindelse** for at initialisere forbindelsen til SendGrid.

1. Vælg **Tilføj dig selv som eksport bruger**, og giv din Customer Insights-legitimationsoplysninger.

1. Vælg **Gem** for at fuldføre forbindelsen.

## <a name="configure-an-export"></a>Konfigurere en eksport

Du kan konfigurere denne eksport, hvis du har adgang til en forbindelse af denne type. Du kan finde flere oplysninger i [Tilladelser, der kræves for at konfigurere en eksport](export-destinations.md#set-up-a-new-export).

1. Gå til **Data** > **Eksport**.

1. Vælg **Tilføj destination** for at oprette en ny eksport.

1. Vælg en forbindelse i sektionen SendGrid i feltet **Forbindelse til eksport**. Hvis du ikke kan se dette sektionsnavn, er der ingen forbindelser af denne type tilgængelige for dig.

1. Angiv dit **[SendGrid-liste-id](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**

1. Vælg det felt, der indeholder en kundes mailadresse, i feltet **Mail** i sektionen **Datamatching**. Gentag de samme trin for andre valgfrie felter, f.eks.. **Fornavn**, **Efternavn**, **Land/Område**, **Stat**, **By** og **Postnummer**.

1. Vælg de segmenter, du vil eksportere. Det **anbefales ikke at eksportere mere end 100.000 kundeprofiler i alt** til SendGrid. 

1. Vælg **Gem**.

Når du gemmer en eksport, køres eksporten ikke med det samme.

Eksporten kører med alle [planlagte opdateringer](system.md#schedule-tab). Du kan også [eksportere data efter behov](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Beskyttelse af personlige oplysninger og overholdelse af angivne standarder

Når du aktiverer Dynamics 365 Customer Insights for at overføre data til SendGrid, tillader du overførsel af data uden for overholdelsesgrænsen for Dynamics 365 Customer Insights, herunder potentielt følsomme data, f.eks.. personlige data. Microsoft overfører sådanne data til din instruktion, men du er ansvarlig for at sikre, at SendGrid overholder eventuelle krav til beskyttelse af personlige oplysninger eller sikkerhed. Du kan finde flere oplysninger på [Microsofts erklæring om beskyttelse af personlige oplysninger](https://go.microsoft.com/fwlink/?linkid=396732).
Din Dynamics 365 Customer Insights-administrator kan til enhver tid fjerne denne eksportdestination for at afslutte brugen af denne funktionalitet.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
