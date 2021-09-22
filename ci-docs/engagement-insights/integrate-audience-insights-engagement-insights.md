---
title: Opret et link mellem målgruppeindsigt og engagementsindsigt
description: Opret et aktivt link mellem målgruppeindsigt og engagementsindsigt for at muliggøre tovejsdeling af data.
ms.date: 07/22/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 870209a7e19fec464ec41462a02365771bd653bd
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461006"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Opret et link mellem målgruppeindsigt og engagementsindsigt

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integration mellem engagementsindsigt og målgruppeindsigt forbinder miljøer fra begge funktioner og gør det muligt at dele data tovejs mellem dem.

Brug ensartede profiler og segmenter fra målgruppeindsigt for at få flere analyseindstillinger i engagementsindsigt. Eksportér arrangementer med stor forretningsværdi ud fra engagementsindsigt. Brug disse hændelser til at føje data til ensartede profiler i målgruppeindsigt.

## <a name="prerequisites"></a>Forudsætninger

- Målgruppeindsigtsprofiler skal gemmes i et Azure Data Lake Storage-firma, du ejer, eller i en [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash;-administrerede datasø. 

- Du skal administratortilladelser til både engagementsindsigt og til målgruppeindsigtsmiljøer.

- Tilknyttede miljøer skal være i samme geografiske område.

> [!NOTE]
> - Hvis dit målgruppeindsigts-abonnement er en prøveversion, der bruger en målgruppeindsigt i internt administrerede data, kan du kontakte [pirequest@microsoft.com](mailto:pirequest@microsoft.com) for at få hjælp. 
> - Hvis dit målgruppeindsigtsmiljø bruger dit eget Azure Data Lake Storage til at gemme data, skal du føje en engagementsindsigts Azure-tjenestekonto til din lagerkonto. Du kan finde flere oplysninger ved at gå til [Oprette forbindelse til en Azure Data Lake Storage-konto med en Azure-tjenestekonto for at få målgruppeindsigt](../audience-insights/connect-service-principal.md). Desuden skal dit målgruppeindsigtsmiljø have et tilknyttet [Dataverse-miljø](../audience-insights/get-started-paid.md). 

## <a name="create-an-environment-link"></a>Oprette et miljølink

Du kan oprette et miljølink ved at opdatere indstillingerne for **Administration** > **Miljø** i engagementsindsigt.

**Opret et aktivt link mellem målgruppeindsigt og engagementsindsigt**

1. Vælg fanen **Forbind miljøer** på siden **Linkmiljøer**.

    :::image type="content" source="media/integrate1.png" alt-text="Konfigurer et miljø.":::

1. Vælg **installationsmiljøer** i øverste venstre hjørne eller nederst på skærmen.

     :::image type="content" source="media/integrate2.png" alt-text="Vælg et miljø for målgruppeindsigt.":::

1. Vælg et målgruppeindsigtsmiljø, og vælg derefter ***Næste** for at afslutte. Nu kan du vælge valgfrie funktioner til tilknyttede miljøer.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Du kan finde flere oplysninger i Aktivere målgruppeindsigts samlede profilattributter og segmenter

Når du har forbundet miljøer, kan du vælge valgfrie funktioner til tilknyttede miljøer. Disse funktioner muliggør ensartede profilattributter og segmenter fra publikum indsigt til interaktiv analyse på kundedata.

**Sådan analyseres webdata i engagementsindsigt**

1. På siden **Miljøadministrator** skal du aktivere **Deling af data fra målgruppeindsigt med engagementsindsigt** og derefter vælge **Næste**.

    :::image type="content" source="media/integrate4.png" alt-text="Vælg funktioner.":::

1. Vælg de attributter for de samlede profiler, der skal være dimensionerne i engagementsindsigt. (Ikke alle attributter er nyttige dimensioner. Det er f.eks. ikke sandsynligt, at du har **fornavn** eller **efternavn** som en attribut til analyse af webstedshændelser.)

    :::image type="content" source="media/integrate5.png" alt-text="Organisere dimensioner.":::

   >[!NOTE]
   > Alle målgruppeindsigtsprofilattributter, der repræsenterer id'er (f.eks. **id** og **alternativt id**), filtreres ud fra de tilgængelige attributter og bliver dimensionerne i engagementsindsigt.

1. Vælg **Næste**, når du er færdig med at vælge attributter.
1. Tilføj brugere, der kan se de målgruppeindsigtsprofilens dimension og segmenter i engagementsindsigt.

    :::image type="content" source="media/integrate6.png" alt-text="Administrer adgang til kundedata.":::

   > [!IMPORTANT]
   > Hvis du ikke eksplicit tilføjer brugere i dette trin, skjules dataene for brugere i engagementsindsigt.

1. Gennemse dit valg, og vælg derefter klik derefter på **Afslut**.

    :::image type="content" source="media/integrate7.png" alt-text="Gennemse indstillingerne for kundedata.":::

## <a name="export-refined-events-to-audience-insights"></a>Eksporter finjusterede hændelse med målgruppeindsigt

Når du har oprettet et link mellem miljøer, kan du eksportere hændelser fra engagementsindsigt til målgruppeindsigt og gøre dem til et nyt datakilde. 

Du kan finde flere oplysninger i [Integrer webdata fra engagementsindsigt med målgruppeindsigt](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
