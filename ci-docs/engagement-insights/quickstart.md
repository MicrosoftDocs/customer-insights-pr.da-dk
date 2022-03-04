---
title: Produktintroduktion til hurtig start
description: Førstegangsoplevelse med at konfigurere funktioner til engagementsindsigt.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/05/2020
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6690b016be4ad26faa797e5f87aba60caa48ddff
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232963"
---
# <a name="first-run-experience"></a>Førstegangsoplevelse

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Med engagementsindsigt, en funktion i Dynamics 365 Customer Insights, kan du indsamle og måle kundefunktionsmåder på dit websted. I denne artikel forklares, hvordan du kan tilmelde dig engagementsindsigt, konfigurere et arbejdsområde, tilføje medlemmer og foretage ændringer.

## <a name="sign-up-for-a-demo-of-engagement-insights"></a>Tilmelde dig en demonstration af engagementsindsigt

Du skal først have en aktiv Microsoft Azure Active Directory-brugerkonto. 

1. Åbn webstedet [engagementsindsigt](https://home.ci.ai.dynamics.com/app/engagement-insights). 

1. Log på med din skole- eller arbejdskonto

1. Vælg dit område, og brug afkrydsningsfeltet til at angive, om du vil tilmelde dig for at modtage opdateringer og tilbud via e-mail.

1. Gennemgå **Engagementsindsigt (forhåndsversion) Vilkår for anvendelse** og **Erklæring om beskyttelse af personlige oplysninger** og derefter vælge **Undersøg demoen** for at acceptere dem.

1. Undersøg produktet ved hjælp af et sæt eksempeldata. 

## <a name="set-up-your-first-workspace-in-engagement-insights"></a>Konfigurer dit første arbejdsområde i engagementsindsigt

Et arbejdsområde er, hvor du kan gemme og administrere hændelser og rapporter.

Opret dit første arbejdsområde

1. I engagementsindsigt skal du vælge **Opret forbindelse mellem dataene** for at starte guiden. 

:::image type="content" source="media/banner.png" alt-text="Siden Customer Insights med knappen Opret forbindelse mellem dataene.":::

2. Vælg den type aktivitet, du vil måle i et nyt arbejdsområde. I øjeblikket er det kun **webstedsaktiviteten**, der er tilgængelig. **Appaktivitet** og **Enhedsaktivitet** bliver tilgængelige i kommende versioner.

1. Vælg **Næste** for at bekræfte og oprette arbejdsområdet.

1. Tilføj et kodestykke til dit websted for at begynde at modtage data i engagementsindsigt. Du kan implementere den med det samme eller dele koden og instruktionerne med din webstedsadministrator. Hvis du vil søge efter kodestykke senere, skal du gå til **Administration** > **Arbejdsområde** > **Installationsvejledning**.

   > [!IMPORTANT]
   > Data vises først i arbejdsområdet, når koden er implementeret på dit websted.

1. Vælg **Udført** for at åbne det nye arbejdsområde. 

## <a name="add-members-to-an-existing-workspace"></a>Tilføje medlemmer til et eksisterende arbejdsområde

Det er som standard kun den person, der har oprettet arbejdsområdet, der har adgang til det. Du kan når som helst tilføje andre brugere fra din organisation til et eksisterende arbejdsområde.

:::image type="content" source="media/add-members.png" alt-text="Siden Medlemmer med knappen Tilføj medlemmer.":::

1. Gå til **Administration** > **Arbejdsområde** > **Medlemmer**.

2. Vælg **Tilføj medlemmer**. Brug feltet **Medlemmer** til at tilføje andre personer i organisationen. Du kan tilføje flere medlemmer på én gang.

3. Vælg en **Rolle**, der skal tildeles til de nye medlemmer. **Arbejdsområdeadministration** er i øjeblikket det eneste tilgængelige valg. Der tilføjes andre roller i kommende versioner.

4. Vælg **Tilføj medlemmer** for at bekræfte.

Hvis du vil fjerne medlemmer fra et arbejdsområde, skal du vælge **...** ud for deres navne på siden **Medlemmer** og derefter vælge **Slet** i rullemenuen.

## <a name="edit-a-workspace"></a>Rediger et arbejdsområde

Du kan til enhver tid redigere oplysningerne om eksisterende arbejdsområder.

:::image type="content" source="media/change-workspace-settings.png" alt-text="Siden Indstillinger for arbejdsområde med navn og beskrivelse af arbejdsområdet.":::

1. Gå til **Administration** > **Arbejdsområde** > **Indstillinger**.

1. Skift **Navn** på arbejdsområdet.

1. Vælg **Gem** for at anvende dine ændringer.

## <a name="add-another-new-workspace"></a>Tilføj et nyt arbejdsområde

:::image type="content" source="media/workspace-switcher.png" alt-text="Siden Customer Insights med opslag i navigationsrude og beskrivelse.":::

Du kan oprette flere arbejdsområder for at klassificere dataene.

1. Vælg **Nyt arbejdsområde** i arbejdsområdevælgeren.

1. Angiv et **Navn** og en valgfri **Beskrivelse**.

1. Vælg **Opret**.

## <a name="switch-between-workspaces"></a>Skifte mellem arbejdsområder

Hvis du vil skifte mellem arbejdsområder, skal du markere arbejdsområdeskifteren. Du kan også oprette et nyt arbejdsområde eller vælge **Webeksempel** for at få vist rapporter og afprøve funktioner ved hjælp af eksempeldata. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]