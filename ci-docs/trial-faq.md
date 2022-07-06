---
title: Ofte stillede spørgsmål om Dynamics 365 Customer Insights-prøveversion
description: Løsninger på almindelige spørgsmål i forbindelse med konfiguration og administration af Customer Insights-prøveversion. Få mere at vide om, hvordan du løser platform- og appspecifikke problemer.
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 41f112466d54c9923d0daf7c55d343f9b5c81d98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051492"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Ofte stillede spørgsmål om Dynamics 365 Customer Insights-prøveversion

## <a name="sign-up"></a>Tilmeld dig

### <a name="what-are-the-system-requirements-for-the-trial"></a>Hvad er systemkravene til prøveversionen?

Appen er en skybaseret tjeneste, der ikke kræver særlig software på brugernes computere bortset fra en opdateret webbrowser, selv om der gælder visse begrænsninger. Du opnår den bedste oplevelse med prøveversionen ved at undgå adgang til prøvewebstedet i inkognitotilstand og vælge den prøveplacering, der er tættest på dig. [Flere oplysninger om krav til webprogrammet.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Hvordan tilmelder jeg mig prøveversionen uden en Microsoft 365-lejer?

Du kan indtaste en anden mailadresse end din arbejdsmail, så opretter vi en konto og lejer til dig.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Kan jeg tilmelde mig flere Dynamics 365-apps som f.eks. Sales, Marketing og Customer Service?

Ja, du kan. Hvis du vil se alle tilgængelige prøveversioner, skal du [besøge hubsiden for prøveversionen](https://dynamics.microsoft.com/dynamics-365-free-trial). Du kan bruge den samme mailkonto til at tilmelde dig forskellige prøveversioner. Det er dog ikke muligt at have flere apps på det samme prøveversionswebsted. Hver prøveversion vil være i en anden organisation og have en anden URL-adresse. Prøveversionsdata deles ikke på tværs af apps.

## <a name="trial-app"></a>Prøveversionsapp

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Hvad skal jeg gøre, når jeg ikke har modtaget mailen med detaljer om prøveabonnementet?

Når du tilmelder dig prøveversionen, modtager du en mail med oplysninger om prøveversionen. Hvis du ikke kan se mailen i din indbakke, kan du prøve at se i mappen med uønsket post. Du kan også bruge følgende trin til at få adgang til din app:

1. Gå til prøveversionens websted, og vælg **Prøv gratis**.
1. Angiv det mail-id, du brugte til at tilmelde dig prøveversionen. Du bliver omdirigeret til din prøveversionsapp.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Hvordan kan jeg tilføje flere brugere til en prøveversion?

Hvis du vil tilføje brugere, skal du gå til [Microsoft 365 Administration](https://admin.microsoft.com) ved hjælp af administratorkontoen for prøveversionen. Følg [vejledningen i Administration](/microsoft-365/admin/add-users/add-users) for at tilføje brugere op til licensgrænsen for prøveversionen. Hvis den bruger, du tilføjer, allerede har en Microsoft 365-konto, skal du tildele vedkommende en relevant sikkerhedsrolle i prøveversionsorganisationen. Du kan finde flere oplysninger under [Tildele en sikkerhedsrolle til en bruger](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Hvor mange brugere kan jeg tilføje i mit prøvemiljø?

Du kan tilføje et ubegrænset antal brugere i prøvemiljøet.

### <a name="how-do-i-reset-the-trial-environment"></a>Hvordan kan jeg nulstille prøveversionsmiljøet?

Du kan ikke nulstille prøveversionsmiljøet. Men du kan vente, til prøveversionsperioden slutter, og derefter tilmelde dig igen til en ny prøveversion.

## <a name="trial-expiration-and-extension"></a>Prøveversionsudløb og forlængelse

### <a name="how-do-i-extend-the-trial"></a>Hvordan kan jeg forlænge prøveversionen?

Du kan udvide prøveversionen direkte i appen. Du kan forlænge prøveperioden én gang.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Kan jeg konvertere prøveversionen til en betalt licens?

Som regel anbefales det, at du starter med dine egne data, når du opgraderer til den betalte version af Customer Insights. 

Hvis du kun bruger Customer Insights, kan du også kopiere dataene fra et prøvemiljø, hvis du køber Customer Insights. Du skal være administrator i Customer Insights-prøveversionen og den globale administrator af din Microsoft 365-lejer eller Dynamics 365-administrator i organisationen for at overføre indstillingerne fra et prøvemiljø til et betalingsmiljø.

Når du har logget på den betalte forekomst af Customer Insights for første gang, bliver du bedt om at oprette et nyt miljø. I denne proces kan du vælge at kopiere konfigurationen fra et eksisterende miljø og overføre de fleste indstillinger. Hvis du har ovennævnte tilladelser, vises prøveversionsmiljøet på denne liste. Du kan finde flere oplysninger under [Kopiere miljøkonfigurationen](create-environment.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Hvad er prøveversionens grænser og kvoter?

- Du kan ikke bruge din egen Azure Data Lake Storage-konto til at gemme outputdata i en prøveversion af Customer Insights. Du kan dog oprette data fra en Data Lake Storage-konto.
- Du kan gemme op til 3 GB data i Dataverse-miljøet, der bliver klargjort automatisk, når du starter en Customer Insights-prøveversion.

## <a name="customer-insights-specific-questions"></a>Customer Insights-specifikke spørgsmål

### <a name="how-do-i-start-using-the-trial"></a>Hvordan begynder jeg at bruge prøveversionen?

Når du har tilmeldt dig prøveversionen, vises appens hovedskærmbillede. Hovedskærmbilledet indeholder links til brugervejledninger og selvstudier. Hvis du vil vide mere, kan du besøge linkene i [Yderligere ressourcer](trial-signup.md#additional-resources) på siden for tilmelding til prøveversionen.

### <a name="what-features-are-available-in-the-trial"></a>Hvilke funktioner er tilgængelige i prøveversionen?

De fleste funktioner i Customer Insights er tilgængelige i prøveversionen.

Følgende funktioner er **ikke tilgængelige**:

- Du kan ikke oprette nye miljøer, der bruger din egen Azure Data Lake Storage-konto.
- Du kan ikke slette prøveversionsmiljøet.

### <a name="how-long-does-the-trial-last"></a>Hvor længe varer prøveversionen?

Prøveversionen af Customer Insights varer 30 dage. Du kan forlænge prøveperioden én gang efter 23 dage, når du logger på prøvemiljøet.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Hvordan fjerner jeg eksempeldata fra prøveversionen?

Du kan ikke fjerne eksempeldata fra prøveversionen.
