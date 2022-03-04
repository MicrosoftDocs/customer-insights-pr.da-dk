---
title: Tilføje kode til dit websted
description: Sådan tilføjes en kode kodestykke til hentning af Dynamics 365 Customer Insights-hændelser på dit websted.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231003"
---
# <a name="install-the-web-sdk-on-a-website"></a>Installere web-SDK'en på et websted

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

I denne artikel beskrives, administrator installerer SDK (Web Software Development Toolkit) på et websted. Kort tid efter at du har instrumentet dit websted, kan du se hændelser i dit arbejdsområde. Du kan finde flere oplysninger i [Administrere arbejdsområder og miljøer](manage-environments-workspaces.md). Hvis du vil registrere hændelser i mobilapps, skal du se [oversigt over udviklerressourcer](developer-resources.md).


### <a name="prerequisites"></a>Forudsætninger

* Du skal administratortilladelser til arbejdsområdet til at gemme dataene.
* Webstedet eller projektet skal hostes online for at kunne sende aktivitetsdata. Data, der sendes fra en lokal fil, accepteres ikke af serveren.


## <a name="add-web-sdk-to-your-website"></a>Tilføj web-SDK til dit websted

Gå til **Admin** > **Arbejdsområde**, og vælg derefter **installationsvejledning**. Der er to indstillinger for installation af web-SDK. Den første er at bruge et overførselslink, og den anden er at installere en nodepakkestyringspakke (NPM).

### <a name="option-1-using-the-download-link"></a>Indstilling 1: Brug overførsel af link

1. Vælg **Kopiér kode** for at kopiere kodestykke. Nøgle til oprettelse af arbejdsområdet er som standard integreret i kodestykke.
  :::image type="content" source="media/copy-code.png" alt-text="Skærmbillede af siden kodestykke.":::

1. Føj den kopierede kode til webstedet i nærheden af <head> mærket og før et hvilket som helst andet script eller CSS-koder.
1. Publicer det opdaterede websted, og vent et par minutter på at registrere den indgående webtrafik.
1. Hvis du vil se dine data, skal du vælge arbejdsområdet fra arbejdsområdeskifteren i navigationsruden. Vælg derefter en af rapporterne i sektionen **Opdag**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Indstilling 2: Brug af NPM-pakken (anbefales til JavaScript-baserede webapps)

1. Gå til vores [NPM-webside](https://www.npmjs.com/package/engagementinsights-web), og følg instruktionerne i at installere og konfigurere web-SDK NPM-pakken.
1. Publicer det opdaterede websted, og vent et par minutter på at registrere den indgående webtrafik.
1. Hvis du vil se dine data, skal du vælge arbejdsområdet fra arbejdsområdeskifteren i navigationsruden. Vælg derefter en af rapporterne i sektionen **Opdag**.

## <a name="configuration-options"></a>Konfigurationsindstillinger

Du kan ændre følgende konfigurationsindstillinger i kodestykket:

- **indtagelsesnøgle**: Den indtagelsesnøgle, der bruges til at sende hændelser til arbejdsområdet. Du kan ændre indtagelsesnøglen for at sende hændelser til et andet arbejdsområde. En indtagelsesnøgle er entydig for hvert arbejdsområde.
- **autoCapture**: Angiver, om sidevisninger og interaktioner med webstedet hentes. Den har to muligheder:
    - **visning**: Angiv til *true* for at hente sidevisninger. Sidevisninger registreres som *Vis* [hændelser](glossary.md#event), en type [basishændelse](glossary.md#base-event).
    - **Klik på**: Angiv til *true* for at registrere besøgendes interaktioner på webstedet. Interaktioner registreres som *Handling* [hændelser](glossary.md#event), en type [basishændelse](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
