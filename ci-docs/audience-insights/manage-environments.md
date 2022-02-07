---
title: Oprette og administrere miljøer
description: 'Få mere at vide om, hvordan du tilmelder dig tjenesten, og hvordan du administrerer miljøer.'
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
---

# <a name="manage-environments"></a>Administrere miljøer



## <a name="switch-environments"></a>Skift miljøer

Vælg **Miljø**-kontrolelementet i øverste højre hjørne af siden for at skifte miljøer.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Skærmbillede af det kontrolelement, der skal ændre miljøer.":::

Administratorer kan [oprette](create-environment.md) og administrer miljøer.

## <a name="edit-an-existing-environment"></a>Redigere et eksisterende miljø

Du kan redigere nogle af oplysningerne i eksisterende miljøer.

1.  Vælg **Miljø**-vælgeren i appens overskrift.

2.  Vælg **Rediger**-ikonet.

3. I feltet **Rediger miljø** kan du opdatere miljøindstillingerne.

Du kan finde flere oplysninger om miljøindstillinger i [Oprette et nyt miljø](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Opret forbindelse til Microsoft Dataverse
   
Med **Microsoft Dataverse**-trinnet kan du forbinde Customer Insights til dit Dataverse-miljø.

Hvis du vil bruge de [indbyggede forudsigelsesmodeller](predictions-overview.md#out-of-box-models), skal du konfigurere datadeling med Dataverse. Du kan også aktivere dataindtagelse fra datakilder i det lokale miljø, hvis du angiver den Microsoft Dataverse-URL-adresse til miljøet, som din organisation administrerer. Vælg **Aktivér datadeling** for at dele Customer Insights-outputdata med Dataverse -administreret datasø.

> [!IMPORTANT]
> Customer Insights og Dataverse skal være i samme område for at kunne dele data.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Konfigurationsindstillinger, der aktiverer datadeling med Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights understøtter ikke følgende scenarier til datadeling:
> - Hvis du gemmer alle data i dit eget Azure Data Lake Storage, kan du ikke aktivere datadeling med en Dataverse-administreret datasø.
> - Hvis du aktiverer datadeling med en Dataverse, kan du ikke [oprette forudsagte eller manglende værdier i et objekt](predictions.md).

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

- Datakilder fra mappen Common Data Model og Dataverse-administreret datasø. Du skal oprette disse datakilder manuelt med det samme navn som i kildemiljøet.

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
