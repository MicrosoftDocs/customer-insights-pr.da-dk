---
title: Oprette og administrere miljøer
description: Få mere at vide om, hvordan du tilmelder dig tjenesten, og hvordan du administrerer miljøer.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683466"
---
# <a name="manage-environments"></a>Administrere miljøer

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Skift miljøer

Vælg **Miljø**-kontrolelementet i øverste højre hjørne af siden for at skifte miljøer.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Skærmbillede af det kontrolelement, der skal ændre miljøer.":::

Administratorer kan [oprette](get-started-paid.md) og administrer miljøer.

## <a name="edit-an-existing-environment"></a>Redigere et eksisterende miljø

Du kan redigere nogle af oplysningerne i eksisterende miljøer.

1.  Vælg **Miljø**-vælgeren i appens overskrift.

2.  Vælg **Rediger**-ikonet.

3. I feltet **Rediger miljø** kan du opdatere miljøets **visningsnavn**, men du kan ikke ændre **område** eller **Type**.

4. Hvis et miljø er konfigureret til at gemme data i Azure Data Lake Storage, kan du opdatere **Firmanøglen**. Du kan dog ikke ændre **Kontonavn** eller navnet på **Objektbeholder**.

5. Du kan også vælge at opdatere fra en kontonøglebaseret forbindelse til en ressourcebaseret eller en abonnementsbaseret forbindelse. Når det er opgraderet, kan du ikke vende tilbage til kontonøglen efter opdateringen. Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md). Du kan ikke ændre **objektbeholder**-oplysninger, når du opdaterer forbindelsen.

6. Du kan også angive en Microsoft Dataverse URL-adresse til miljøet under **Konfiguration af datadeling med Microsoft Dataverse og aktivering af flere funktioner**. Disse funktioner omfatter datadeling med applikationer og løsninger baseret på Microsoft Dataverse, dataindtagelse fra datakilder i det lokale miljø eller brug af [forudsigelser](predictions.md). Vælg **Aktivér datadeling** for at dele Customer Insights-outputdata med Microsoft Dataverse -administreret Data Lake.

   > [!NOTE]
   > - Datadeling med Microsoft Dataverse Administreret Data Lake understøttes ikke i øjeblikket, når du gemmer alle data i din egen Azure Data Lake Storage.
   > - [Forudsigelse af manglende værdier i et objekt](predictions.md) og PowerBI Embedded-rapporter i målgruppeindsigt (hvis de er aktiveret i dit miljø) understøttes i øjeblikket ikke, når du aktiverer datadeling med Microsoft Dataverse-administrerede data lake.

   Når du aktiverer datadeling med Microsoft Dataverse, starter en fuldstændig opdatering af dine datakilder og andre processer. Hvis processer kører, vises indstillingen til aktivering af datadeling med Microsoft Dataverse ikke. Vent på, at disse processer fuldføres eller annulleres, for at du kan dele data. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigurationsindstillinger, der aktiverer datadeling med Microsoft Dataverse.":::
   
   Når du kører processer, f. eks. dataindsættelse eller segmentoprettelse, oprettes der tilsvarende mapper i den lagerkonto, du har angivet ovenfor. Datafiler og model.json-filer oprettes og føjes til de respektive undermapper, afhængigt af den proces du kører.

## <a name="copy-the-environment-configuration"></a>Kopier miljøkonfiguration

Når du opretter et nyt miljø, kan du vælge at kopiere konfigurationen fra et eksisterende miljø. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Skærmbillede af indstillingerne i miljøindstillingerne.":::

Du får vist en liste over alle tilgængelige miljøer i din organisation, som du kan kopiere data fra.

Følgende konfigurationsindstillinger er kopieret:

- Indtagne eller importerede datakilder
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

Følgende data kopieres *ikke*:

- Kundeprofiler.
- Legitimationsoplysninger for datakilde. Du skal angive legitimationsoplysningerne for hver datakilde og opdatere datakilderne manuelt.
- Datakilder fra mappen Common Data Model og Dataverse-administreret Data Lake. Du skal oprette disse datakilder manuelt med det samme navn som i kildemiljøet.

Når du kopierer et miljø, får du vist en bekræftelsesmeddelelse om, at det nye miljø er blevet oprettet. Vælg **gå til datakilder** for at få vist listen over datakilder.

Alle datakilderne viser en **Legitimationsoplysninger påkrævet** som status. Rediger datakilderne, og angiv legitimationsoplysninger for at opdatere dem.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste over datakilder, der er kopieret og skal godkendes.":::

Når du har opdateret datakilderne, skal du gå til **Data** > **Saml**. Her kan du finde indstillinger fra kildemiljøet. Rediger dem efter behov, eller vælg **Kør**, for at starte datasamlingsprocessen og det samlede kundeobjekt.

Når datasamlingen er fuldført, skal du gå til **Målinger** og **Segmenter** for at opdatere dem.

## <a name="reset-an-existing-environment"></a>Nulstil et eksisterende miljø

Som administrator kan du nulstille et miljø til en tom tilstand, hvis du vil slette alle konfigurationer og fjerne de data, der er indtaget.

1.  Vælg **Miljø**-vælgeren i appens overskrift. 

2.  Vælg det miljø, du vil nulstille, og vælg ellipse (**...**). 

3. Vælg indstillingen **Nulstil**. 

4.  Bekræft sletningen ved at skrive navnet på miljøet og vælge **Nulstil**.

## <a name="delete-an-existing-environment"></a>Slet et eksisterende miljø

Som en administrator kan du slette et miljø, du administrerer.

1.  Vælg **Miljø**-vælgeren i appens overskrift.

2.  Vælg det miljø, du vil nulstille, og vælg ellipse (**...**). 

3. Vælg indstillingen **Slet**. 

4.  Bekræft sletningen ved at skrive navnet på miljøet og vælge **Slet**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
