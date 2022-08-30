---
title: Bruge din egen Azure Data Lake Storage Gen2-konto
author: mukeshpo
description: Få mere at vide om kravene for at bruge din egen Azure Data Lake Storage-konto til at gemme Customer Insights-data.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304374"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Bruge din egen Azure Data Lake Storage Gen2-konto

Dynamics 365 Customer Insights giver dig mulighed for at gemme alle dine data i [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction). Når du gemmer data i Data Lake Storage, accepterer du, at data overføres til og gemmes på den relevante geografiske placering for den pågældende Azure-lagerkonto. Der er flere oplysninger i [Microsofts Sikkerhedscenter](https://www.microsoft.com/trust-center).

Administratorer i Customer Insights kan [oprette miljøer](create-environment.md) og [angive indstillingen for datalagring](create-environment.md#step-2-configure-data-storage) i processen.

## <a name="prerequisites"></a>Forudsætninger

- Azure Data Lake Storage-konti skal være i det samme Azure-område, som du valgte under oprettelse af Customer Insights-miljøet. Hvis du vil kende området i miljøet, skal du gå til **Admin** > **System** > **Om** i Customer Insights.
- Data Lake Storage-kontoen skal være Gen2. Azure Data Lake Gen1-lagerkonti understøttes ikke.
- Kontoen Data Lake Storage skal have funktionen [Hierarkisk navneområde aktiveret](/azure/storage/blobs/data-lake-storage-namespace).
- Der skal findes en beholder med navnet `customerinsights` på lagerkontoen. Du skal oprette den, før du kan bruge dit eget Data Lake Storage i Customer Insights.
- Den administrator, der konfigurerer Customer Insights-miljøet, skal bruge rollen Bidragyder til lagring af BLOB-data eller Ejer af lagring af BLOB-data til lagerkontoen eller `customerinsights`-objektbeholderen. Du kan finde flere oplysninger om tildeling af tilladelser i en lagerkonto under [Oprette en lagerkonto](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Opret forbindelse mellem Customer Insights og din lagerkonto

Når du opretter et nyt miljø, skal du sikre dig, at Data Lake Storage-kontoen findes, og at alle forudsætningerne er opfyldt.

1. I trinnet **Datalagring** under oprettelse af miljøet skal du angive **Gem outputdata** til **Azure Data Lake Storage Gen2**.
1. Vælg, hvordan du vil **oprette forbindelse til dit lager**. Du kan vælge mellem en ressourcebaseret mulighed og en abonnementsbaseret mulighed for godkendelse. Du kan finde flere oplysninger i [Oprette forbindelse til en Azure Data Lake Storage-konto ved hjælp af en Azure-tjenesteprincipal](connect-service-principal.md).
   - I forbindelse med **Azure-abonnement** skal du vælge det **abonnement**, den **ressourcegruppe** og den **lagerkonto**, der indeholder `customerinsights`-objektbeholderen.
   - For **Firmanøgle** skal du angive **Firmanavn** og **Firmanøgle** for Data Lake Storage-kontoen. Hvis du bruger denne godkendelsesmetode, bliver du informeret, hvis organisationen udskifter nøglerne. Du skal [opdatere miljøkonfigurationen](manage-environments.md#edit-an-existing-environment) med den nye nøgle, når den udskiftes.
1. Vælg, om du vil bruge Azure Private Link til at oprette forbindelse til lagerkontoen, og [opret forbindelse til Private Link](security-overview.md#set-up-an-azure-private-link).

Når systemprocesser, for eksempel dataindtagelse, er fuldført, oprettes der tilsvarende mapper på lagerkontoen. Datafiler og model.json-filer oprettes og føjes til mapper baseret på procesnavnet.

Hvis du opretter flere miljøer i Customer Insights og vælger at gemme outputobjekterne fra disse miljøer i lagerkontoen, opretter Customer Insights separate mapper for de enkelte miljøer med `ci_environmentID` i beholderen.
