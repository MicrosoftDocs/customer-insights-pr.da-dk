---
title: Tilføje kode til dit websted
description: Sådan tilføjes en kode kodestykke til hentning af hændelser på dit websted.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035087"
---
# <a name="install-the-code-snippet-on-a-website"></a>Installere kodestykke på et websted

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

I denne artikel beskrives, hvordan en administrator installerer kodestykke på et websted. Du kan se hændelser i arbejdsområdet, umiddelbart efter du har føjet scriptet til dit websted. Du kan finde flere oplysninger i [Administrere arbejdsområder og miljøer](manage-environments-workspaces.md). Hvis du vil registrere hændelser i mobilapps, skal du se [oversigt over udviklerressourcer](developer-resources.md).


### <a name="prerequisites"></a>Forudsætninger

* Du skal administratortilladelser til arbejdsområdet til at gemme dataene.
* Webstedet eller projektet skal hostes online for at kunne sende aktivitetsdata. Data, der sendes fra en lokal fil, accepteres ikke af serveren.


## <a name="add-code-to-your-website"></a>Tilføje kode til dit websted
1.  Gå til **Admin** > **Arbejdsområde**, og vælg derefter **installationsvejledning**.
1. Vælg **Kopiér kode** for at kopiere kodestykke. Nøgle til oprettelse af arbejdsområdet er som standard integreret i kodestykke.
:::image type="content" source="media/copy-code.png" alt-text="Skærmbillede af siden kodestykke.":::
3. Føj det kopierede kodestykke til webstedet i nærheden af <head> mærket og før et hvilket som helst andet script eller CSS-koder.
4.  Publicer det opdaterede websted, og vent et par minutter på at registrere den indgående webtrafik.
5.  Hvis du vil se dine data, skal du vælge arbejdsområdet fra arbejdsområdeskifteren i navigationsruden. Vælg derefter en af rapporterne i sektionen **Opdag**.

## <a name="configuration-options"></a>Konfigurationsindstillinger

Du kan ændre følgende konfigurationsindstillinger i kodestykket:

- **indtagelsesnøgle**: Den indtagelsesnøgle, der bruges til at sende hændelser til arbejdsområdet. Du kan ændre indtagelsesnøglen for at sende hændelser til et andet arbejdsområde. En indtagelsesnøgle er entydig for hvert arbejdsområde. 
- **autoCapture**: Angiver, om sidevisninger og interaktioner med webstedet hentes. Den har to muligheder:
    - **visning**: Angiv til *true* for at hente sidevisninger. Sidevisninger registreres som *Vis* [hændelser](glossary.md#event), en type [basishændelse](glossary.md#base-event).
    - **Klik på**: Angiv til *true* for at registrere besøgendes interaktioner på webstedet. Interaktioner registreres som *Handling* [hændelser](glossary.md#event), en type [basishændelse](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
