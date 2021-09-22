---
title: Administrere cookies og brugerens samtykke til at lagre brugerdata
description: Forstå, hvordan cookies og brugersamtykke bruges til at identificere besøgende på webstedet.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036731"
---
# <a name="manage-cookies-and-user-consent"></a>Administrér cookies og brugersamtykke

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights-engagementsindsigtsfunktion bruger cookies og lokal lager (`localStorage`) til at identificere besøgende på webstedet.

Cookies er små filer, hvor der gemmes oplysninger om en brugers interaktion med webstedet. De gemmes i webbrowsere. Når brugere besøger et websted, hvor brugerne har gemt cookies, sender browseren disse oplysninger til serveren, som returnerer oplysninger, der er entydige for brugeren. Det er den teknologi, der f.eks. gør det muligt for en onlinebruger at beholde udvalgte elementer i den, også selvom en bruger navigerer væk fra webstedet.

## <a name="user-consent"></a>Brugersamtykke

Den [generelle forordning om databeskyttelse (GDPR)](/dynamics365/get-started/gdpr/) er en EU-regel, der forklarer, hvordan organisationer skal håndtere brugernes personlige oplysninger og sikkerhed. Cookies lagrer eller indsamler ofte "personlige data", f.eks. et online-id, som dækkes af GDPR. Hvis din virksomhed ansætter og/eller sælger til EU-dataemner, påvirker GDPR dig. [Få mere at vide om, hvordan Microsoft kan hjælpe dig med at overholde GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Hvis engagementsindsigt SDK skal kunne lagre cookies eller andre følsomme oplysninger, skal du angive, om brugerne har givet deres samtykke. Dette sker, når SDK initialiseres.

Hvis du angiver, at der ikke er brugersamtykke, gemmer SDK ingen data og sender ikke hændelser, der kan bruges til at spore brugerfunktionsmåder. Alle data, der tidligere er gemt, slettes i browseren.

Hvis der ikke angives en værdi for brugerens samtykke, antager SDK, at brugeren har accepteret dette. Det betyder, at hvis du (som kunde) ikke angiver en værdi for brugerens samtykke i SDK, indsamles der data. Hvis du angiver, at værdien for brugerens samtykke skal være "sand"-data, indsamles de dog ikke, hvis en bruger afviser eller undlader at give eksplicit samtykke.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Lagring af data for besøgende i indbliksfunktion til engagement

### <a name="cookies"></a>Småkage

- _msei
    - Gemmer det anonyme bruger-id. Cookien angives i kundedomænet og udløber efter 365 dage.

### <a name="local-storage"></a>Lokalt lager

Engagementsindsigt gør også brug af lokal lager (`localStorage`) til at spore ikke-følsomme data. Disse data lagres fuldt ud i selve browseren, uden at der sendes trafik til eller fra serverne.

- *EISession.Id* 
    - Gemmer oplysninger om den igangværende brugersession, f.eks. sessions-id, hvornår den blev startet, og hvornår den udløber.
- *EISession.Previous*
    - Gemmer webadressen til den tidligere besøgte side i den aktuelle session.
    
Nøglerne i det lokale lager udløber ikke automatisk. De nulstilles i næste session af SDK.

## <a name="deleting-cookies"></a>Sletning af cookies

Dine kunder kan til enhver tid slette cookies og lokale lagernøgler manuelt via deres browseres indstillinger.


[!INCLUDE[footer-include](../includes/footer-banner.md)]