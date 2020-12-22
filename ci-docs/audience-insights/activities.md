---
title: Kundeaktiviteter
description: Definer kundeaktiviteter, og få vist dem på kundetidslinjen.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667222"
---
# <a name="customer-activities"></a>Kundeaktiviteter

Du kan kombinere kundeaktiviteter fra [forskellige datakilder](data-sources.md) i Dynamics 365 Customer Insights for at oprette en kundetidslinje, der angiver aktiviteterne i kronologisk rækkefølge. Du kan medtage tidslinjen i kundeengagementsapps i Dynamics 365 via [tilføjelsesprogrammet Kundekort](customer-card-add-in.md) eller et Power BI-dashboard.

## <a name="define-an-activity"></a>Definere en aktivitet

Datakilderne inkluderer objekter med transaktions- og aktivitetsdata fra flere datakilder. Identificer disse objekter, og vælg de aktiviteter, du vil have vist på kundens tidslinje. Vælg det objekt, der indeholder målaktiviteten eller -aktiviteterne.

1. Gå til **Data** > **Aktiviteter** i målgruppeindsigt.

1. Vælg **Tilføj aktivitet**.

   > [!NOTE]
   > Et objekt skal have mindst én attribut af typen **Dato** for at blive medtaget på en kundes tidslinje, og du kan ikke tilføje objekter uden **Dato**-felter. Kontrolelementet **Tilføj aktivitet** deaktiveres, hvis der ikke findes et sådant objekt.

1. Angiv værdierne for følgende felter i ruden **Tilføj aktivitet**:

   - **Objekt**: Vælg et objekt, der indeholder transaktions- eller aktivitetsdata.
   - **Primær nøgle**: Vælg det felt, der entydigt identificerer en post. Den må ikke indeholde dublerede værdier, tomme værdier eller manglende værdier.
   - **Tidsstempel**: Markér det felt, der repræsenterer starttidspunktet for aktiviteten.
   - **Hændelse**: Markér det felt, der er hændelsen for aktiviteten.
   - **Webadresse**: Markér det felt, der repræsenterer en URL-adresse, som indeholder yderligere oplysninger om denne aktivitet. For eksempel det transaktionssystem, der er kilde til aktiviteten. Denne URL-adresse kan være et hvilket som helst felt fra datakilden, eller den kan konstrueres som et nyt felt ved hjælp af en Power Query-transformation. Disse URL-adressedata gemmes i objektet Samlet aktivitet, som kan forbruges downstream ved hjælp af API'er.
   - **Detaljer**: Vælg eventuelt det felt, der tilføjes, for at få flere oplysninger.
   - **Ikon**: Vælg eventuelt det ikon, der repræsenterer denne aktivitet.
   - **Aktivitetstype**: Definer den reference til aktivitetstype i Common Data Model, der bedst beskriver den semantiske definition af aktiviteten.

1. I sektionen **Konfigurer relation** skal du konfigurere detaljerne for at oprette forbindelse mellem aktivitetsdataene og den tilsvarende kunde.

   > [!div class="mx-imgBorder"]
   > ![Definere objektrelationen](media/activities-entities-define.png "Definere objektrelationen")

    - **Aktivitetsobjektfelt**: Vælg det felt i det aktivitetsobjekt, der skal bruges til at oprette en relation til et andet objekt.
    - **Kundeobjekt**: Vælg det tilsvarende kildekundeobjekt, som aktivitetsobjektet skal have en relation til. Du kan kun oprette forbindelse til de kildekundeobjekter, der bruges i datasamlingsprocessen.
    - **Kundeobjektfelt**: I dette felt vises den primære nøgle for kildekundeobjektet, som det er valgt i tilknytningsprocessen. Dette primære nøglefelt i kildekundeobjektet bruges til at oprette en relation til aktivitetsobjektet.
    - **Navn**: Hvis der allerede findes en relation mellem dette aktivitetsobjekt og det valgte kildekundeobjekt, vil navnet på relationen være i skrivebeskyttet tilstand. Hvis der ikke findes en sådan relation, oprettes der en ny relation med det navn, der angives her.

1. Vælg **Gem** for at anvende dine ændringer.

1. Vælg **Kør** på siden **Aktiviteter**.

> [!TIP]
> Opgaver og processer indeholder [seks typer status](system.md#status-types). De fleste processer er desuden [afhængige af andre downstream-processer](system.md#refresh-policies). Du kan vælge status for en proces for at se statusdetaljer for hele jobbet. Når du har valgt **Se detaljer** for en af opgaverne i jobbet, kan du finde flere oplysninger: behandlingstid, datoen for den seneste behandling og alle fejl og advarsler, der er knyttet til opgaven.

## <a name="edit-an-activity"></a>Redigere en aktivitet

1. Gå til **Data** > **Aktiviteter** i målgruppeindsigt.

2. Vælg det aktivitetsobjekt, du vil redigere, og vælg **Rediger**. Du kan også holde markøren over objektrækken og vælge ikonet **Rediger**.

3. Klik på ikonet **Rediger**.

4. Opdater værdierne i ruden **Rediger aktivitet**, og vælg **Gem**.

5. Vælg **Kør** på siden **Aktiviteter**.

## <a name="delete-an-activity"></a>Slette en aktivitet

1. Gå til **Data** > **Aktiviteter** i målgruppeindsigt.

2. Vælg det aktivitetsobjekt, du vil fjerne, og vælg **Slet**. Du kan også holde markøren over objektrækken og vælge ikonet **Slet**. Derudover kan du markere flere aktivitetsobjekter, der skal slettes på én gang.
   > [!div class="mx-imgBorder"]
   > ![Redigere eller slette objektrelationen](media/activities-entities-edit-delete.png "Redigere eller slette objektrelationen")

3. Vælg ikonet **Slet**.

4. Bekræft sletningen.
