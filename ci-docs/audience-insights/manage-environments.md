---
title: Oprette og administrere miljøer
description: 'Få mere at vide om, hvordan du tilmelder dig tjenesten, og hvordan du administrerer miljøer.'
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
  - ci-system-about
  - customerInsights
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

Tildel dit eget Microsoft Dataverse-miljø mulighed for at dele data (profiler og indsigt) med virksomhedsprogrammer, der er baseret på Dataverse, f.eks. Dynamics 365 Marketing eller modelbaserede programmer i Power Apps.

Hvis du vil bruge de [indbyggede forudsigelsesmodeller](predictions-overview.md#out-of-box-models), skal du konfigurere datadeling med Dataverse. Du kan også aktivere dataindtagelse fra datakilder i det lokale miljø, hvis du angiver den Microsoft Dataverse-URL-adresse til miljøet, som din organisation administrerer.

Aktivering af datadeling med Microsoft Dataverse ved at markere afkrydsningsfeltet datadeling udløser en fuldstændig opdatering af datakilderne og alle andre processer én gang.

> [!IMPORTANT]
> 1. Customer Insights og Dataverse skal være i samme område for at kunne dele data.
> 1. Du skal have en global administratorrolle i Dataverse-miljøet. Kontrollér, om dette [Dataverse-miljø er knyttet](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) til visse sikkerhedsgrupper, og kontrollér, at du er føjet til de pågældende sikkerhedsgrupper.
> 1. Der er ikke allerede knyttet et eksisterende Customer Insights-miljø til det pågældende Dataverse-miljø. Få mere at vide om , hvordan du [fjerner en eksisterende forbindelse til et Dataverse-miljø](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Konfigurationsindstillinger, der aktiverer datadeling med Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Aktivere datadeling med Dataverse fra dit eget Azure Data Lake Storage (forhåndsversion)

Hvis dit miljø er konfigureret til at bruge dit eget Azure Data Lake Storage til at gemme Customer Insights-data, kan du aktivere datadeling med Microsoft Dataverse-behov for ekstra konfiguration.

1. Opret to sikkerhedsgrupper i dit Azure-abonnement – en **Læser**-sikkerhedsgruppe og en **bidragyder**-sikkerhedsgruppe, og angiv Microsoft Dataverse-tjenesten som ejer for begge sikkerhedsgrupper.
2. Administrer ACL (Access Control List) på CustomerInsights-beholderen på din lagerkonto via disse sikkerhedsgrupper. Tilføj tjenesten Microsoft Dataverse og alle Dataverse-baserede virksomhedsprogrammer, f.eks. Dynamics 365 Marketing til **Læser**-sikkerhedsgruppen med **skrivebeskyttede** tilladelser. Tilføj *kun* programmet Customers Insights til sikkerhedsgruppen **Bidragyder** for at give både **læse- og skrivetilladelser** til at skrive profiler og indsigt.
   
#### <a name="prerequisites"></a>Forudsætninger

Hvis du vil udføre PowerShell-scripts, skal følgende tre moduler importeres. 

1. Installer den nyeste version af [Azure Active Directory PowerShell til Graph](/powershell/azure/active-directory/install-adv2).
   1. På din pc skal du vælge Windows-tasten på tastaturet og søge efter **Windows PowerShell** og vælge **Kør som administrator**.
   1. I det PowerShell-vindue, der åbnes, skal du skrive `Install-Module AzureAD`.
2. Importér tre moduler.
    1. Skriv `Install-Module -Name Az.Accounts` i PowerShell-vinduet, og følg trinnene. 
    1. Gentag for `Install-Module -Name Az.Resources` og `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Konfigurationstrin

1. Hent de to PowerShell-scripts, du skal bruge for at køre fra vores udviklers [GitHub-repo](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Du skal bruge *lejer-admin*-tilladelser til at køre dette PowerShell-script. 
       - Med dette PowerShell-script oprettes der to sikkerhedsgrupper i dit Azure-abonnement. Et for Læsergruppen og et andet for gruppen Bidragyder og Microsoft Dataverse-tjenesten gøres til ejer af begge disse sikkerhedsgrupper.
       - Udfør dette PowerShell-script i Windows PowerShell ved at angive det Azure-abonnements-id, der indeholder dit Azure Data Lake Storage. Åbn PowerShell-scriptet i en editor for at gennemse flere oplysninger og den implementerede logik.
       - Gem begge id-værdier for sikkerhedsgrupper, der er genereret med dette script, da vi bruger dem i `ByolSetup.ps1`-scriptet.
       
        > [!NOTE]
        > Oprettelse af sikkerhedsgrupper kan deaktiveres for lejeren. I det tilfælde skal du konfigurere manuelt, og din Azure AD-administrator skal aktivere[ oprettelse af sikkerhedsgruppe](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Du skal have tilladelser som *Lager Blob-dataejer* på lagerkonto/beholderniveau for at køre dette script, ellers oprettes der en for dig i dette script. Rolletildelingen kan fjernes manuelt, når scriptet er kørt korrekt.
        - Dette PowerShell-script tilføjer det påkrævede rollebaserede adgangskontrolelement (RBAC) for Microsoft Dataverse-tjenesten og alle Dataverse-baserede virksomhedsprogrammer. Den opdaterer også ACL (Access Control List) i CustomerInsights-beholderen for de sikkerhedsgrupper, der er oprettet med `CreateSecurityGroups.ps1`-scriptet. Gruppen bidragyder har kun *rwx*-tilladelsen, og gruppen Læsere har kun *r-x*-tilladelsen.
        - Kør dette PowerShell-script i Windows PowerShell ved at angive det Azure-abonnements-id, der indeholder dit Azure Data Lake Storage, navnet på din lagerkonto, navnet på ressourcegruppen og id for Læser- og Bidragyder-sikkerhedsgruppen. Åbn PowerShell-scriptet i en editor for at gennemse flere oplysninger og den implementerede logik.
        - Kopiér outputstrengen, når scriptet er kørt. Outputstrengen ser således ud: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Angiv den outputstreng, der er kopieret ovenfra, til feltet **Tilladelser-id** i trinnet til miljøkonfiguration for Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigurationsindstillinger, der gør det muligt at dele data direkte fra det eget Azure Data Lake Storage med Microsoft Dataverse.":::

Customer Insights understøtter ikke følgende scenarier til datadeling:
- Hvis du aktiverer datadeling med en Dataverse, kan du ikke [oprette forudsagte eller manglende værdier i et objekt](predictions.md).
- Hvis du aktiverer datadeling med Dataverse, kan du ikke få vist valgfrie PowerBI-integrerede rapporter i dit Customer Insights-miljø.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Fjern en eksisterende forbindelse til et Dataverse-miljø

Når der oprettes forbindelse til et Dataverse-miljø, betyder fejlmeddelelsen **Denne CDS-organisation er allerede knyttet til en anden forekomst af Customer Insights**, at Dataverse-miljøet allerede er brugt i et Customer Insights-miljø. Du kan fjerne den eksisterende forbindelse som en global administrator i Dataverse-miljøet. Det kan tage et par timer at udfylde ændringerne.

1. Gå til [Power Apps](https://make.powerapps.com).
1. Vælg miljøet på miljøvælgeren.
1. Gå til **Løsninger**
1. Fjern eller slet løsningen med navnet **Dynamics 365 Customer Insights Kundekort-tilføjelsesprogrammet (forhåndsversion)**.

ELLER 

1. Åbn dit Dataverse-miljø.
1. Gå til **Avancerede indstillinger** > **Løsninger**.
1. Fjern løsningen **CustomerInsightsCustomerCard**.

## <a name="copy-the-environment-configuration"></a>Kopier miljøkonfiguration

Som administrator kan du vælge at kopiere konfigurationen fra et eksisterende miljø, når du opretter et nyt. 

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

## <a name="set-up-a-copied-environment"></a>Konfigurere et kopieret miljø

Når du kopierer miljøkonfigurationen, kopieres følgende data *ikke*:

- Kundeprofiler.
- Legitimationsoplysninger for datakilde. Du skal angive legitimationsoplysningerne for hver datakilde og opdatere datakilderne manuelt.
- Datakilder fra mappen Common Data Model og Dataverse-administreret datasø. Du skal oprette disse datakilder manuelt med det samme navn som i kildemiljøet.
- Forbindelseshemmeligheder, der bruges til eksport og forbedringer. Du skal godkende forbindelserne igen og derefter genaktivere forbedringerne og eksporter. 

Når du kopierer et miljø, får du vist en bekræftelsesmeddelelse om, at det nye miljø er blevet oprettet. Vælg **gå til datakilder** for at få vist listen over datakilder.

Alle datakilderne viser en **Legitimationsoplysninger påkrævet** som status. Rediger datakilderne, og angiv legitimationsoplysninger for at opdatere dem.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste over datakilder, der er kopieret og skal godkendes.":::

Når du har opdateret datakilderne, skal du gå til **Data** > **Saml**. Her kan du finde indstillinger fra kildemiljøet. Rediger dem efter behov, eller vælg **Kør**, for at starte datasamlingsprocessen og det samlede kundeobjekt.

Når datasamlingen er fuldført, skal du gå til **Målinger** og **Segmenter** for at opdatere dem.

Før du genaktiverer eksport og forbedringer, skal du gå **til Admin** > **Forbindelser** for at genaktivere forbindelserne i det nye miljø.

## <a name="change-the-owner-of-an-environment"></a>Skift ejeren af et miljø

Flere brugere kan have administratortilladelser i Customer Insights, men kun én bruger ejer et miljø. Det er som standard administratoren, der oprindeligt opretter et miljø. Som administrator af et miljø kan du tildele ejerskab til en anden bruger med administratortilladelser.

1. Vælg **Miljø**-vælgeren i appens overskrift.

1. Vælg **Rediger**-ikonet.

1. Gå til trinnet **Grundlæggende oplysninger** i feltet **Rediger miljø**.

1. Vælg den nye ejer af miljøet i feltet **Skift ejer for miljøet**.  

1. Vælg **Gennemse og udfør**, og **opdater** for at anvende ændringerne. 

## <a name="claim-ownership-of-an-environment"></a>Krav på ejerskab af et miljø

Hvis ejeren af et miljø forlader organisationen, eller brugerens brugerkonto slettes, har miljøet ingen ejer. En bruger med administratorrettigheder kan kræve ejerskabet og blive den nye ejer. De kan fortsat eje miljøet eller ændre [ejerskabet til en anden administrator](#change-the-owner-of-an-environment). 

Hvis du vil kræve ejerskab, skal du vælge knappen **Tag ejerskab**, der vises øverst på alle sider i Customer Insights, når den oprindelige ejer har forladt organisationen.

## <a name="reset-an-existing-environment"></a>Nulstil et eksisterende miljø

Som ejer af et miljø kan du nulstille et miljø til en tom tilstand, hvis du vil slette alle konfigurationer og fjerne de slettede data.

1.  Vælg **Miljø**-vælgeren i appens overskrift. 

2.  Vælg det miljø, du vil nulstille, og vælg ellipse (**...**). 

3. Vælg indstillingen **Nulstil**. 

4.  Bekræft sletningen ved at skrive navnet på miljøet og vælge **Nulstil**.

## <a name="delete-an-existing-environment"></a>Slet et eksisterende miljø

Som ejer af et miljø kan du slette et miljø, du administrerer.

1.  Vælg **Miljø**-vælgeren i appens overskrift.

2.  Vælg det miljø, du vil nulstille, og vælg ellipse (**...**). 

3. Vælg indstillingen **Slet**. 

4.  Bekræft sletningen ved at skrive navnet på miljøet og vælge **Slet**.

> [!NOTE]
> Hvis du sletter et miljø, fjernes tilknytningen ikke til et Dataverse-miljø. Få mere at vide om, hvordan du [fjerner en eksisterende forbindelse til et Dataverse-miljø](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
