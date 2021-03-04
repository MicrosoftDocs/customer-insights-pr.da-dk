---
title: Tilknyt objekter til datasamling
description: Tilknyt data for at oprette samlede kundeprofiler.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267028"
---
# <a name="map-entities-and-attributes"></a>Tilknyt objekter og attributter

**Tilknyt** er det første trin i datasamlingsprocessen for målgruppen Insights. Tilknytning består af tre faser:

- *Objektvalg*: Identificer de kombinerbare enheder, som fører til et datasæt med mere komplette oplysninger om dine kunder.
- *Attributvalg*: Identificerer for hvert objekt de kolonner, du vil kombinere og afstemme i faserne *match* og *flet*. Disse kolonner kaldes *Attributter*.
- *Primær nøgle og semantisk valg*: For hvert objekt skal du identificere en attribut, som du vil definere som den primære nøgle for det pågældende objekt, og for hver attribut skal du identificere en semantisk type, der bedst beskriver den pågældende attribut.

Du kan finde flere oplysninger om det generelle flow af datasamling under [Samle](data-unification.md).

## <a name="select-the-first-entities"></a>Vælge de første objekter

1. Gå til **Data** > **Saml** > **Tilknyt** i målgruppen Insights.

2. Start tilknytningsfasen ved at vælge **Vælg objekter**.

3. Vælg de objekter og attributter, du vil bruge i faserne *Afstem* og *Flet*. Du kan vælge de krævede attributter individuelt for et objekt eller inkludere alle attributter fra et objekt ved at markere afkrydsningsfeltet **Medtag alle felter** på objektniveauet. Det anbefales, at du vælger mindst to objekter for at drage fordel af datasamlingsprocessen.

   > [!div class="mx-imgBorder"]
   > ![Eksempel på tilføjelse af objekter](media/data-manager-configure-map-add-entities-example.png "Eksempel på tilføjelse af objekter")

   I dette eksempel tilføjer vi objekterne **eCommerceContacts** og **loyCustomers**. Hvis du vælger disse objekter, kan du få indsigt i, hvilke online virksomhedskunder der er medlemmer af loyalitetsprogrammet.
   
   Du kan søge efter nøgleord på tværs af alle attributter og objekter for at vælge de nødvendige attributter, du vil tilknytte.
   
     > [!div class="mx-imgBorder"]
   > ![Eksempel på feltet Søg](media/data-manager-configure-map-search-fields-example.png "Eksempel på feltet Søg")

4. Vælg **Anvend** for at bekræfte de valgte indstillinger.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Vælg primær nøgle og semantisk type for attributter

Når du har valgt objekterne , viser siden **Tilknyt** de valgte objekter for anmeldelsen. Definer den primære nøgle for et objekt, og identificer den semantiske type for en attribut i objektet.

- **Primær nøgle**: Vælg en attribut som primær nøgle for hvert af objekterne. Hvis en attribut skal være en gyldig primær nøgle, må den ikke indeholde dubletværdier, manglende værdier eller null-værdier. Datatypeattributter for streng, heltal og GUID understøttes som primære nøgler, og de vises i et felt, hvor du kan vælge dem.

- **Semantisk attributtype**: Kategorier af attributter, f.eks. mailadresse eller navn. Hvis du vil bruge AI-modeller til smart forudsigelse af semantik og spare tid og øge præcisionen, skal du indstille **Intelligent tilknytning** til **TIL**. Intelligent tilknytning fremhæver den AI-baserede semantikanbefaling i feltet **Type**. Hvis du indstiller den til **FRA**, kan du se vores almindelige tilknytningsanbefalinger. Du kan vælge en hvilken som helst semantisk type på den tilgængelige liste over indstillinger og tilsidesætte den foreslåede markering.

> [!div class="mx-imgBorder"]
> ![Attributtype og semantisk forudsigelse](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attributtype og semantisk forudsigelse")

Det er også muligt at tilføje en brugerdefineret semantisk type. Vælg typefeltet for en attribut, og skriv navnet på den brugerdefinerede semantiske type. På denne måde kan du også ændre de attributtyper, der er identificeret automatisk af systemet.

Alle attributter, hvor der automatisk identificeres en semantisk type, grupperes i sektionen **Gennemse tilknyttede felter**. Gennemse disse attributter og deres semantiske typer, da de bruges til at kombinere objekterne i fletningen i forbindelse med dataensretning.

Attributter, der ikke automatisk knyttes til en semantisk type, grupperes i sektionen **Definer data i ikke-tilknyttede felter**. Vælg feltet for semantisk type for de ikke-tilknyttede attributter, eller angiv navnet på den brugerdefinerede attributtype.

> [!div class="mx-imgBorder"]
> ![Primær nøgle og attributtype](media/data-manager-configure-map-add-attributes.png "Primær nøgle og attributtype")

> [!NOTE]
> Et enkelt felt skal knyttes til den semantiske type Person.FullName for at udfylde kundenavnet på debitorkortet. Ellers vises kundekortene uden navn. 

## <a name="add-and-remove-attributes-and-entities"></a>Tilføje og fjerne attributter og objekter

1. Vælg **Rediger felter** under **Saml** > **Tilknyt**.

2. Tilføj eller fjern attributter og objekter i ruden **Rediger felter**. Brug søgning eller rulning til at søge efter og vælge de ønskede attributter og objekter. Du kan ikke fjerne en attribut eller et objekt, hvis det allerede er tilknyttet.

   > [!div class="mx-imgBorder"]
   > ![Tilføje eller fjerne attributter](media/configure-data-map-edit.png "Tilføje eller fjerne attributter")

3. Vælg **Anvend**.

## <a name="add-images-to-profiles"></a>Føje billeder til profiler

Hvis et objekt indeholder URL-adresser til offentligt tilgængelige profilbilleder eller logoer, kan du føje dem til den samlede kundeprofil.

Vælg objektet, og find det felt, der indeholder URL-adressen til profilbilledet. Angiv manuelt følgende værdi i inputfeltet **Type**. 
- For en person: Person.ProfileImage
- For en organisation: Organization.LogoImage

Fortsæt med fremgangsmåden for ensartethed, og kontrollér, at den attribut, der indeholder URL-adressen for billedet, også tilføjes i trinnet [Flet](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Angive attributter for organisationer

For organisationer (prøveversion) skal attributtypen knyttes til "Organization.Name".
> [!div class="mx-imgBorder"]
> ![Primær nøgle og attributtype B2B](media/configure-data-map-edit-b2b.png "Primær nøgle og attributtype B2B")

## <a name="next-step"></a>Næste trin

Gå til siden **Match** som en del af datasamlingsprocessen. Besøg [**Match**](match-entities.md) for at få mere at vide om denne fase.

> [!TIP]
> Se følgende video: [Introduktion: oprettelse af en samlet kundeprofil](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]