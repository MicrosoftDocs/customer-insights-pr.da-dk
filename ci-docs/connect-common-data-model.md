---
title: Tilknyt en Common Data Model med en Azure Data Lake-konto
description: Arbejd med Common Data Model-data ved hjælp af Azure Data Lake Storage.
ms.date: 07/27/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: e071bf9364b44a92d81c9ff2269ff4e8654010aa
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206992"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Opret forbindelse til data i Azure Data Lake Storage

Indtag data til Dynamics 365 Customer Insights ved hjælp af din Azure Data Lake Storage Gen2-konto. Dataindtagelse kan være fuld eller trinvis.

## <a name="prerequisites"></a>Forudsætninger

- Dataindtagelse understøtter udelukkende Azure Data Lake Storage *Gen2*-firmaer. Du kan ikke bruge Data Lake Storage Gen1-konti til indtagelse af data.

- Azure Data Lake Storage-firmaet skal have [aktiveret hierarkisk navneområde](/azure/storage/blobs/data-lake-storage-namespace). Dataene skal gemmes i et hierarkisk mappeformat, der definerer rodmappen og har undermapper til de enkelte objekter. Undermapperne kan have komplette data eller trinvise datamapper.

- Hvis du vil godkende med en Azure-tjenestekonto, skal du sørge for, at den er konfigureret i din lejer. Du kan finde flere oplysninger i [Oprette forbindelse til en Azure Data Lake Storage Gen2-konto ved hjælp af en Azure-tjenestekonto](connect-service-principal.md).

- De Azure Data Lake Storage-data, du vil oprette forbindelse fra, skal være i det samme Azure-område som Dynamics 365 Customer Insights-miljøet. Forbindelser til en Common Data Model-mappe fra en Data Lake i et andet Azure-område understøttes ikke. Hvis du vil vide mere om Azure-området i miljøet, skal du gå til **Admin** > **System** > **Om** i Customer Insights.

- Data, der lagres i onlinetjenester, kan gemmes på en anden placering end det sted, hvor dataene behandles eller lagres i Dynamics 365 Customer Insights.Ved at importere eller oprette forbindelse til data, der er gemt i onlinetjenester, accepterer du, at data kan overføres til og gemmes sammen med Dynamics 365 Customer Insights. [Få mere at vide på Microsofts center for sikkerhed og rettighedsadministration](https://www.microsoft.com/trust-center).

- Customer Insights-tjenesteprincipal skal være en af følgende roller for at få adgang til lagerkontoen. Du kan finde flere oplysninger i [Tildele tilladelser til tjenesteprincipalen til at få adgang til lagerkontoen](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Lager for Blob-datalæser
  - Lager for Blob-dataejer
  - Lager for Blob Data-bidragyder

- Data i dit Data Lake-lager skal følge standarden for Common Data Model for lagring af dine data og have et almindeligt datamodelmanifest, der repræsenterer skemaet for datafilerne (*.csv eller *.parquet). Manifestet skal indeholde oplysninger om objekterne, f.eks. objektkolonner og datatyper, samt placeringen og filtypen af datafilen. Du kan finde flere oplysninger i [Common Data Model-manifest](/common-data-model/sdk/manifest). Hvis manifestet ikke findes, kan admin-brugere med dataejeren Storage Blob eller Storage Blob Data-bidragyder definere skemaet, når dataene ændres.

## <a name="connect-to-azure-data-lake-storage"></a>Oprette forbindelse til Azure Data Lake Storage

1. Gå til **Data** > **Datakilder**.

1. Vælg **Tilføj datakilde**.

1. Vælg **Azure data lake storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dialogboksen til angivelse af forbindelsesoplysninger for Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Angiv et **navn** til datakilden og en valgfri **beskrivelse**. Navnet identificerer entydigt datakilde og refereres til i downstreamprocesser og kan ikke ændres.

1. Vælg en af følgende muligheder for at **oprette forbindelse til lagerpladsen ved hjælp af**. Du kan finde flere oplysninger i [Opret forbindelse i Customer Insights til en Azure Data Lake Storage Gen2-konto ved hjælp af en Azure-tjenestekonto](connect-service-principal.md).

   - **Azure-ressource**: Angiv **ressource-id**. Hvis du vil aktivere data fra en lagerkonto via et Azure Private Link, skal du vælge **Aktivér privat link**. Du kan finde flere oplysninger under [Private Link](security-overview.md#private-links-tab).
   - **Azure-abonnement**: Vælg **abonnementet**, og vælg derefter **ressourcegruppen** og **lagerkontoen**. Hvis du vil aktivere data fra en lagerkonto via et Azure Private Link, skal du vælge **Aktivér privat link**. Du kan finde flere oplysninger under [Private Link](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Du skal bruge en af følgende roller enten for objektbeholderen eller lagerkontoen for at kunne oprette datakilden:
   >
   >  - Læser af Blob Data-lager er tilstrækkelig, hvis du vil læse fra en lagerkonto og indtage dataene i Customer Insights. 
   >  - Bidragyder til eller ejer af lagring af BLOB-data er påkrævet, hvis du vil redigere de manifestfiler direkte i Customer Insights.  
  
1. Vælg navnet på den **beholder**, der indeholder de data og skemaer (model.json- eller manifest.json-filen), der skal importeres data fra, og vælg **Næste**.
   > [!NOTE]
   > Alle model.json- eller manifest.json-filer, der er knyttet til andre datakilder i miljøet, vises ikke på listen. Men den samme model.json- eller manifest.json-fil kan bruges til datakilder i flere miljøer.

1. Hvis du vil oprette et nyt skema, skal du gå til [Opret en ny skemafil](#create-a-new-schema-file).

1. Hvis du vil bruge et eksisterende skema, skal du navigere til den mappe, der indeholder filen model.json eller manifest.cdm.json. Du kan søge efter filen i en mappe.

1. Vælg json-filen, og vælg derefter **Næste**. En liste over tilgængelige objekter vises.

   :::image type="content" source="media/review-entities.png" alt-text="Dialogboksen med en liste over objekter, der skal vælges":::

1. Vælg de objekter, du vil bruge.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogboks, der viser Påkrævet til primær nøgle":::

   > [!TIP]
   > Hvis du vil redigere et objekt i en JSON-redigeringsgrænseflade, skal du vælge objektet og derefter **Rediger skemafil**. Foretag dine ændringer, og **Gem**.

1. For de valgte objekter, der kræver trinvis indtag, vises **Påkrævet** under **Trinvis opdatering**. For hvert af disse objekter skal du se [Konfigurere en trinvis opdatering for Azure Data Lake-datakilder](incremental-refresh-data-sources.md).

1. I forbindelse med valgte objekter, hvor der ikke er defineret en primær nøgle, vises **Obligatorisk** under **Primær nøgle**. For hvert af disse objekter:
   1. Vælg **Obligatorisk**. Panelet **Rediger objekt** vises.
   1. Vælg den **primære nøgle**. Den primære nøgle er en attribut, der er entydig for objektet. Hvis en attribut skal være en gyldig primær nøgle, må den ikke indeholde dubletværdier, manglende værdier eller null-værdier. Strengattributter, heltalsattributter og GUID-datatypeattributter understøttes som primære nøgler.
   1. Du kan også ændre partitionsmønsteret.
   1. Vælg **Luk** for at gemme og lukke panelet.

1. Vælg antallet af **attributter** for hvert inkluderet objekt. Siden **Administrer attributter** vises.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogboks til valg af dataprofilering.":::

   1. Opret nye attributter, rediger eller slet eksisterende attributter. Du kan ændre navn, dataformat eller tilføje en semantisk type.
   1. Hvis du vil aktivere analyser og andre funktioner, skal du vælge **dataprofilering** for hele objektet eller for bestemte attributter. Som standard er intet objekt aktiveret for dataprofilering.
   1. Vælg **Udført**.

1. Vælg **Gem**. Siden **Datakilder** åbnes, der viser de nye datakilde status for **Opdatering**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan tage tid at indlæse data. Når opdateringen er gennemført, kan de indtagne data gennemses fra siden [**Objekter**](entities.md).

### <a name="create-a-new-schema-file"></a>Opret en ny skemafil

1. Vælg **Ny skemafil**.

1. Skriv navnet på filen, og vælg **Gem**.

1. Vælg **Vælg nyt objekt**. Panelet **Nyt objekt** vises.

1. Angiv objektnavnet, og vælg **placeringen af datafiler**.
   - **Flere .csv- eller .parquet-filer**: Søg efter rodmappen, vælg mønstertypen, og angiv udtrykket.
   - **Enkelte .csv- eller .parquet-filer**: Gå til .csv- eller .parquet-filen, og markér den.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dialogboks til oprettelse af et nyt objekt, hvor placeringen af datafiler er fremhævet.":::

1. Vælg **Gem**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dialogboks til definition eller automatisk generering af attributter.":::

1. Vælg at **definere attributterne** for at tilføje attributterne manuelt, eller vælg **automatisk at oprette dem**. Hvis du vil definere attributterne, skal du angive et navn, vælge dataformatet og den valgfrie semantiske type. Autogenerede attributter:

   1. Når attributterne er genereret automatisk, skal du vælge **Gennemse attributter**. Siden **Administrer attributter** vises.

   1. Kontroller, at dataformatet er korrekt for hver attribut.

   1. Hvis du vil aktivere analyser og andre funktioner, skal du vælge **dataprofilering** for hele objektet eller for bestemte attributter. Som standard er intet objekt aktiveret for dataprofilering.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialogboks til valg af dataprofilering.":::

   1. Vælg **Udført**. Siden **Vælg objekter** vises.

1. Fortsæt med at tilføje objekter og attributter, hvis de er relevante.

1. Når alle objekter er tilføjet, skal du vælge **Medtag** for at inkludere objekterne i datakildeindtag.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialogboks, der viser Påkrævet til primær nøgle":::

1. For de valgte objekter, der kræver trinvis indtag, vises **Påkrævet** under **Trinvis opdatering**. For hvert af disse objekter skal du se [Konfigurere en trinvis opdatering for Azure Data Lake-datakilder](incremental-refresh-data-sources.md).

1. I forbindelse med valgte objekter, hvor der ikke er defineret en primær nøgle, vises **Obligatorisk** under **Primær nøgle**. For hvert af disse objekter:
   1. Vælg **Obligatorisk**. Panelet **Rediger objekt** vises.
   1. Vælg den **primære nøgle**. Den primære nøgle er en attribut, der er entydig for objektet. Hvis en attribut skal være en gyldig primær nøgle, må den ikke indeholde dubletværdier, manglende værdier eller null-værdier. Strengattributter, heltalsattributter og GUID-datatypeattributter understøttes som primære nøgler.
   1. Du kan også ændre partitionsmønsteret.
   1. Vælg **Luk** for at gemme og lukke panelet.

1. Vælg **Gem**. Siden **Datakilder** åbnes, der viser de nye datakilde status for **Opdatering**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Det kan tage tid at indlæse data. Når opdateringen er gennemført, kan de indtagne data gennemses fra siden [**Objekter**](entities.md).

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Rediger Azure Data Lake Storage-datakilde

Du kan opdatere *Kontoen Opret forbindelse til lager ved hjælp af*-indstillingen. Du kan finde flere oplysninger i [Opret forbindelse i Customer Insights til en Azure Data Lake Storage Gen2-konto ved hjælp af en Azure-tjenestekonto](connect-service-principal.md). Hvis du vil oprette forbindelse til en anden objektbeholder fra lagerkontoen eller ændre kontonavnet, skal du [oprette en ny datakildeforbindelse](#connect-to-azure-data-lake-storage).

1. Gå til **Data** > **Datakilder**.

1. Ud for den datakilde, du vil opdatere, og vælg  **Rediger**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dialogboks til redigering af Azure Data Lake-datakilde.":::

1. Opdater følgende oplysninger:

   - **Beskrivelse**
   - **Opret forbindelse til lagerpladsen ved hjælp af** og forbindelsesoplysninger. Du kan ikke ændre **objektbeholder**-oplysninger, når du opdaterer forbindelsen.
      > [!NOTE]
      > En af følgende roller skal tildeles lagerkontoen eller -beholderen:
        > - Lager for Blob-datalæser
        > - Lager for Blob-dataejer
        > - Lager for Blob Data-bidragyder

   - **Aktiver privat link** hvis du vil indtage data fra en lagerkonto via et Azure Private Link. Du kan finde flere oplysninger under [Private Link](security-overview.md#private-links-tab).

1. Vælg **Næste**.
1. Opdater følgende:
   - Naviger til en anden model.json- eller manifest.json-fil med et andet sæt objekter end beholderen.
   - Hvis du vil føje flere objekter til indtag, skal du vælge **Nyt objekt**.
   - Hvis du vil fjerne objekter, der allerede er markeret, hvis der ikke er nogen afhængigheder, skal du markere objektet og **Slette**.
      > [!IMPORTANT]
      > Hvis der er afhængigheder i den eksisterende model.json- eller manifest.json-fil og i sættet af objekter, vises der en fejlmeddelelse, og du kan ikke vælge en anden model.json- eller manifest.json-fil. Fjern disse afhængigheder, før du ændrer filen model.json eller manifest.json eller opretter en ny datakilde med den model.json- eller manifest.json-fil, du vil bruge for at undgå at fjerne afhængighederne.
   - Vælg **Rediger** for at ændre placeringen af datafilen eller den primære nøgle.
   - Hvis du vil ændre trinvise indtagelsesdata, skal du se [Konfigurere en trinvis opdatering af Azure Data Lake-datakilder](incremental-refresh-data-sources.md).
   - Du skal kun ændre objektnavnet, så det stemmer overens med objektnavnet i .json-filen.

     > [!NOTE]
     > Bevar altid objektnavnet i Customer Insights på samme måde som objektnavnet i filen model.json eller manifest.json efter skrivning. I Customer Insights valideres alle objektnavne med model.json eller manifest.json under alle systemopdateringer. Hvis et objektnavn ændres enten i Customer Insights eller uden for, opstår der en fejl, fordi Customer Insights ikke kan finde det nye objektnavn i .json-filen. Hvis et utilsigtet objektnavn blev ændret ved et uheld, skal du redigere objektnavnet i Customer Insights, så det stemmer overens med navnet i .json-filen.

1. Vælg **Attributter**, der skal tilføjes eller ændres attributter, eller hvis du vil aktivere dataprofilering. Vælg derefter **Udført**.

1. Klik på **Gem** for at anvende ændringerne og vende tilbage til siden **Datakilder**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
