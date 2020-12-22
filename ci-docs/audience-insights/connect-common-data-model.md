---
title: Forbind almindelig datamodeldata til en Azure Data Lake-konto
description: Arbejd med Common Data Model-data ved hjælp af Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643451"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Tilknyt en Common Data Model med en Azure Data Lake-konto

Denne artikel indeholder oplysninger om, hvordan du kan indsætte data fra en Common Data Model-mappe ved hjælp af din Azure Data Lake Storage Gen2-konto.

## <a name="important-considerations"></a>Vigtige overvejelser

- Data i Azure Data Lake skal følge Common Data Model-standarden. Andre formater understøttes ikke i øjeblikket.

- Dataindsættelse understøtter udelukkende Azure Data Lake *Gen2*-lagerkonti. Du kan ikke bruge Azure Data Lake Gen1-lagerkonti til indsættelse af data.

- Hvis du vil godkende med en Azure-tjenestekonto, skal du sørge for, at den er konfigureret i din lejer. Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md).

- Den Azure Data Lake, som du vil oprette forbindelse til og hente data fra, skal være i samme Azure-område som Dynamics 365 Customer Insights-miljøet. Forbindelser til en Common Data Model-mappe fra en Data Lake i et andet Azure-område understøttes ikke. Du kan se Azure-området for miljøet ved at gå til **Admin** > **System** > **Om** i målgruppeindsigt.

- Data, der lagres i onlinetjenester, kan gemmes på en anden placering end det sted, hvor dataene behandles eller lagres i Dynamics 365 Customer Insights.Ved at importere eller oprette forbindelse til data, der er gemt i onlinetjenester, accepterer du, at data kan overføres til og gemmes sammen med Dynamics 365 Customer Insights.  [Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Opret forbindelse til en Common Data Model-mappe

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

1. Vælg **Tilføj datakilde**.

1. Vælg **Opret forbindelse til Common Data model-mappe**, angiv et **Navn** for datakilde, og vælg **Næste**.

1. Du kan vælge mellem at bruge en ressourcebaseret indstilling og en abonnementsbaseret indstilling til godkendelse. Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md). Angiv oplysninger om **Objektbeholder**, og vælg **Næste**.
   > [!div class="mx-imgBorder"]
   > ![Dialogboksen til angivelse af forbindelsesoplysninger for Azure Data Lake](media/enter-new-storage-details.png)

1. I dialogboksen **Vælg en Common Data Model-mappe** skal du vælge den model.json-fil, du vil importere data fra, og vælg **Næste**.
   > [!NOTE]
   > Alle model.json-filer, der er knyttet til andre datakilder i miljøet, vises ikke på listen.

1. Du får vist en liste over tilgængelige objekter i den valgte model.json-fil. Du kan se og foretage valg på listen med tilgængelige objekter og vælge **Gem**. Alle de valgte objekter hentes fra den nye datakilde.
   > [!div class="mx-imgBorder"]
   > ![Dialogboks, der viser en liste over objekter fra en model.json-fil](media/review-entities.png)

8. Angiv, hvilke dataobjekter du vil aktivere dataprofilering for, og vælge **Gem**. Dataprofilering muliggør analyser og andre funktioner. Du kan vælge hele objektet, som vælger alle attributter fra objektet, eller selv vælge bestemte attributter. Som standard er intet objekt aktiveret for dataprofilering.
   > [!div class="mx-imgBorder"]
   > ![Dialogboks, der viser en dataprofil](media/dataprofiling-entities.png)

9. Når du har gemt dine valg, åbnes siden **Datakilder**. Du bør nu kunne se Common Data Model-mappeforbindelsen som en datakilde.

> [!NOTE]
> En model.json-fil kan kun knyttes til én datakilde i det samme miljø. Men den samme model.json-fil kan bruges til datakilder i flere miljøer.

## <a name="edit-a-common-data-model-folder-data-source"></a>Redigere en datakilde til en Common Data Model-mappe

Du kan opdatere adgangsnøglen til den lagerkonto, der indeholder Common Data Model-mappen. Du kan også ændre model.json-filen. Hvis du vil oprette forbindelse til en anden objektbeholder fra lagerkontoen eller ændre kontonavnet, skal du [oprette en ny datakildeforbindelse](#connect-to-a-common-data-model-folder).

1. Gå til **Data** > **Datakilder** i målgruppen Insights.

2. Vælg ellipsen ud for den datakilde, du vil opdatere.

3. Vælg indstillingen **Rediger** på listen.

4. Du kan også vælge at opdatere **Adgangsnøgle** og vælge **Næste**.

   ![Dialogboks til redigering og opdatering af en adgangsnøgle til en eksisterende datakilde](media/edit-access-key.png)

5. Du kan også vælge at opdatere fra en kontonøgleforbindelse til en ressourcebaseret eller en abonnementsbaseret forbindelse. Der er flere oplysninger i [Opret forbindelse mellem målgruppeindsigt og en Azure Data Lake Storage Gen2-konto med et Azure-tjenestekonto](connect-service-principal.md). Du kan ikke ændre **objektbeholder**-oplysninger, når du opdaterer forbindelsen.
   > [!div class="mx-imgBorder"]
   > ![Dialogboksen til angivelse af forbindelsesoplysninger for Azure Data Lake](media/enter-existing-storage-details.png)

6. Du kan også vælge en anden model.json-fil med et andet sæt objekter fra beholderen.

7. Du kan også vælge yderligere objekter, der skal indsættes. Du kan også fjerne eventuelle objekter, der allerede er valgt, hvis der ikke er afhængigheder.

   > [!IMPORTANT]
   > Hvis der er afhængigheder i den eksisterende model.json-fil og i sættet af objekter, får du vist en fejlmeddelelse, og du kan ikke vælge en anden model.json-fil. Fjern disse afhængigheder, før du ændrer model.json-filen, eller opret en ny datakilde med den model.json-fil, du vil bruge, for at undgå at fjerne afhængighederne.

8. Alternativt kan du vælge yderligere attributter eller objekter for at aktivere dataprofilering eller deaktivere allerede markerede.   
