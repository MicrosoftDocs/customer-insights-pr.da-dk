---
title: Administrer cookies og brugerens samtykke til at lagre brugerdata i Dynamics 365 Customer Insights
description: Forstå, hvordan cookies og brugersamtykke bruges til at identificere besøgende på webstedet.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558797"
---
# <a name="manage-cookies-and-user-consent"></a>Administrér cookies og brugersamtykke

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights-engagementsindsigtsfunktion bruger cookies og (`localStorage`)- nøgler til at identificere besøgende på webstedet.

Cookies er små filer, hvor der gemmes oplysninger om en brugers interaktion med webstedet. De gemmes i webbrowsere. Når brugere besøger et websted, hvor brugerne har gemt cookies, sender browseren disse oplysninger til serveren, som returnerer oplysninger, der er entydige for brugeren. Det er den teknologi, der f.eks. gør det muligt for en onlinebruger at beholde udvalgte elementer i den, også selvom en bruger navigerer væk fra webstedet.

## <a name="user-consent"></a>Brugersamtykke

Den [generelle forordning om databeskyttelse (GDPR)](/dynamics365/get-started/gdpr/) er en EU-regel, der forklarer, hvordan organisationer skal håndtere brugernes personlige oplysninger og sikkerhed. Cookies lagrer eller indsamler ofte "personlige data", f.eks. et online-id, som dækkes af GDPR. Hvis din virksomhed ansætter og/eller sælger til EU-dataemner, påvirker GDPR dig. [Få mere at vide om, hvordan Microsoft kan hjælpe dig med at overholde GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Hvis engagementsindsigt SDK skal kunne lagre cookies eller andre følsomme oplysninger, skal du angive, om brugerne har givet deres samtykke. Dette sker ved initialisering af SDK ved at angive et `userConsent`-felt i konfigurationen.

Hvis du angiver, at der ikke er brugersamtykke, gemmer SDK ingen data og sender ikke hændelser, der kan bruges til at spore brugerfunktionsmåder. Alle data, der tidligere er gemt, slettes i browseren.

Hvis der ikke angives en værdi for brugerens samtykke, antager SDK, at brugeren har accepteret dette. Det betyder, at hvis du (som kunde) ikke angiver en værdi for brugerens samtykke i SDK, indsamles der data. Hvis du angiver, at værdien for brugerens samtykke skal være "sand"-data, indsamles de dog ikke, hvis en bruger afviser eller undlader at give eksplicit samtykke.

Nedenfor vises en kode, kodestykke at initialisere web-SDK med brugerens samtykke:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Lagring af data for besøgende i indbliksfunktion til engagement

### <a name="cookies"></a>Småkage

- _msei
    - Gemmer det anonyme bruger-id. Cookien angives i kundedomænet og udløber efter 365 dage.

### <a name="local-storage"></a>Lokalt lager

Engagementsindsigt gør også brug af (`localStorage`)-nøgler til at spore ikke-følsomme data. Disse data lagres fuldt ud i selve browseren, uden at der sendes trafik til eller fra serverne.

- *EISession.Id*
    - Gemmer oplysninger om den igangværende brugersession, f.eks. sessions-id, hvornår den blev startet, og hvornår den udløber.
- *EISession.Previous*
    - Gemmer webadressen til den tidligere besøgte side i den aktuelle session.

Nøgler i lokalt lager udløber ikke automatisk, og de nulstilles i løbet af den næste SDK-session.

## <a name="deleting-cookies"></a>Sletning af cookies

Dine kunder kan til enhver tid slette cookies og lokale lagernøgler manuelt via deres browseres indstillinger.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
