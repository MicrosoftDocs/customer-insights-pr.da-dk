---
title: Oprette og administrere miljøer
description: Få mere at vide om, hvordan du tilmelder dig tjenesten, og hvordan du administrerer miljøer.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644126"
---
# <a name="manage-environments"></a>Administrere miljøer

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

I denne artikel forklares det, hvordan du kan oprette en ny organisation, og hvordan du kan klargøre et miljø.

## <a name="sign-up-and-create-an-organization"></a>Tilmelding og oprettelse af en organisation

1. Gå til [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/)-webstedet.

2. Vælg **Introduktion**.

3. Vælg dit foretrukne tilmeldingsscenario, og vælg det tilsvarende link.

4. Accepter vilkår og betingelser, og vælg **Fortsæt** for at begynde at oprette organisationen.

5. Når miljøet er oprettet, bliver du omdirigeret til [Customer Insights](https://home.ci.ai.dynamics.com).

6. Brug demomiljøet til at udforske appen, eller opret et nyt miljø ved at udføre trinnene i næste afsnit.

7. Når du har angivet miljøindstillingerne, skal du vælge **Opret**.

8. Du bliver logget på, når du har oprettet miljøet.

## <a name="create-an-environment-in-an-existing-organization"></a>Oprette et miljø i en eksisterende organisation

Du kan oprette et nyt miljø på to måder. Du kan enten angive en helt ny konfiguration, eller du kan kopiere nogle konfigurationsindstillinger fra et eksisterende miljø.

Sådan opretter du et miljø:

1. Vælg **Indstillinger**-symbolet i overskriften i appen.

1. Vælg **Nyt miljø**.

   > [!div class="mx-imgBorder"]
   > ![Miljøindstillinger](media/environment-settings-dialog.png)

1. Vælg **Nyt miljø** i dialogboksen **Opret nyt miljø**.

   Hvis du vil [kopiere data fra det aktuelle miljø](#additional-considerations-for-copy-configuration-preview), skal du vælge **Kopiér fra eksisterende miljø**. Du får vist en liste over alle tilgængelige miljøer i din organisation, som du kan kopiere data fra.

1. Angiv følgende oplysninger:
   - **Navn**: Navnet på dette miljø. Dette felt er allerede udfyldt, hvis du har kopieret et eksisterende miljø, men du kan ændre det.
   - **Område**: Det område, hvor tjenesten er installeret og har sin vært.
   - **Type**: Vælg, om du vil oprette et produktions- eller sandkassemiljø.

2. Du kan også vælge **Avancerede indstillinger**:

   - **Gem alle data i**: Angiver, hvor du vil gemme de outputdata, der er genereret fra Customer Insights. Du har to muligheder: **Customer Insights-lager** (en Azure Data Lake, der administreres af Customer Insights-teamet) og **Azure Data Lake Storage Gen2** (dit eget Azure Data Lake Storage). Som standard er indstillingen Customer Insights-lager valgt.

   > [!NOTE]
   > Når du gemmer data i Azure Data Lake Storage, accepterer du, at data overføres til og gemmes på den relevante geografiske placering for den pågældende Azure Storage-konto, som kan være forskellig fra den placering, hvor data gemmes i Dynamics 365 Customer Insights. [Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration.](https://www.microsoft.com/trust-center)
   >
   > I øjeblikket gemmes indtagede objekter altid i den styrede datasø i Customer Insights.
   > Vi understøtter kun Azure Data Lake Gen2 Storage-konti fra det samme Azure-område, som du valgte, da du oprettede miljøet.
   > Vi understøtter kun lagerkonti, der er aktiveret med Hierarkisk navneområde (HNS), i Azure Data Lake Gen2.

   - For Azure Data Lake Storage Gen2 kan du vælge mellem at bruge en ressourcebaseret indstilling og en abonnementsbaseret indstilling til godkendelse. Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md). Navnet på **Beholder** kan ikke ændres og vil være "customerinsights".
   
   - Hvis du vil bruge [forudsigelser](predictions.md), skal du angive Common Data Service-forekomst URL-adresse i feltet **Server-adresse** under **Brug af forudsigelser**.

   Når du kører processer, f. eks. dataindsættelse eller segmentoprettelse, oprettes der tilsvarende mapper i den lagerkonto, du har angivet ovenfor. Datafiler og model.json-filer oprettes og føjes til de respektive undermapper, afhængigt af den proces du kører.

   Hvis du opretter flere miljøer med Customer Insights og vælger at gemme outputenhederne fra de pågældende miljøer i lagerkontoen, oprettes der separate mapper for hvert miljø med ci_<environmentid> i beholderen.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Flere overvejelser i forbindelse med kopieringskonfiguration (eksempel)

Følgende konfigurationsindstillinger er kopieret:

- Funktionskonfigurationer
- Indtagne/importerede datakilder
- Konfiguration af dataforening (tilknytte, matche, flette)
- Segmenter
- Målinger
- Relationer
- Aktiviteter
- Indeks for søgning og filtrering
- Eksportdestinationer
- Planlagt opdatering
- Forbedringer
- Modeladministration
- Rolletildelinger

Følgende konfigurationsindstillinger er *ikke* kopieret:

- Kundeprofiler.
- Legitimationsoplysninger for datakilde. Du skal angive legitimationsoplysningerne for hver datakilde og opdatere datakilderne manuelt.
- Datakilder fra Common Data Model-mappen og Common Data Service-administreret sø. Du skal oprette disse datakilder manuelt med det samme navn som i kildemiljøet.

Når du kopierer et miljø, får du vist en bekræftelsesmeddelelse om, at det nye miljø er blevet oprettet. Vælg **gå til datakilder** for at få vist listen over datakilder.

Alle datakilderne viser en **Legitimationsoplysninger påkrævet** som status. Rediger datakilderne, og angiv legitimationsoplysninger for at opdatere dem.

> [!div class="mx-imgBorder"]
> ![Kopierede datakilder](media/data-sources-copied.png)

Når du har opdateret datakilderne, skal du gå til **Data** > **Saml**. Her kan du finde indstillinger fra kildemiljøet. Rediger dem efter behov, eller vælg **Kør**, for at starte datasamlingsprocessen og det samlede kundeobjekt.

Når datasamlingen er fuldført, skal du gå til **Målinger** og **Segmenter** for at opdatere dem.

## <a name="edit-an-existing-environment"></a>Redigere et eksisterende miljø

Du kan redigere nogle af oplysningerne i eksisterende miljøer.

1. Gå til **Administration** > **System** > **Om**.

2. Vælg **Rediger**.

3. Du kan opdatere miljøets **Vist navn**, men du kan ikke ændre **Område** eller **Type**.

4. Hvis et miljø er konfigureret til at lagre data i Azure Data Lake Storage Gen2, kan du opdatere **Kontonøgle**. Du kan dog ikke ændre **Kontonavn** eller navnet på **Objektbeholder**.

5. Du kan også vælge at opdatere fra en kontonøglebaseret forbindelse til en ressourcebaseret eller en abonnementsbaseret forbindelse. Når det er opgraderet, kan du ikke vende tilbage til kontonøglen efter opdateringen. Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md). Du kan ikke ændre **objektbeholder**-oplysninger, når du opdaterer forbindelsen.

## <a name="reset-an-existing-environment"></a>Nulstil et eksisterende miljø

Du kan nulstille et miljø til en tom tilstand, hvis du vil slette alle konfigurationer og fjerne de påtagede data.

1.  Gå til **Administration** > **System** > **Om**.

2.  Vælg **Nulstil**. 

3.  Bekræft sletningen ved at skrive navnet på miljøet og vælge **Nulstil**.


## <a name="delete-an-existing-environment"></a>Slet et eksisterende miljø

1. Gå til **Administration** > **System** > **Om**.

1. Vælg **Slet**.

1. Bekræft sletningen ved at skrive navnet på miljøet og vælge **Slet**.
