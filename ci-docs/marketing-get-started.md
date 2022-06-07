---
title: Brug af ensartede profiler i Dynamics 365 Marketing
description: Få mere at vide om, hvordan du integrerer samlede profiler og segmenter med Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4cc3cbde97d0f9da198652e86c0843476393b646
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833301"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Arbejde med unified customer profiles i Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) giver en øget kundeoplevelse, så du kan organisere brugertilpassede kampagneforløb på tværs af alle kontaktpunkter og derved styrke forhold og optjene loyalitet. Dynamics 365 Marketing-appen fungerer problemfrit med Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams og andre produkter og giver dig mulighed for at træffe hurtigere og bedre beslutninger ved hjælp af data og AI.

Når du etablerer forbindelse mellem data i Customer Insights og Marketing kan du:

- Målrette ensartede kundeprofiler og -segmenter. Dette giver dig mulighed for at engagere alle kunder, uanset placeringen af kundens data.
- Basere dynamisk indhold (f.eks. personlige tokens) i mails, SMS- og push-meddelelser på målinger såsom loyalitetsstatus, fornyelsesdato for abonnement, overordnet firma eller en hvilken som helst anden måleenhed, du har registreret i den samlede Customer Insights-profil.
- Indlæse data fra Marketing til Customer Insights og kombinere dem med kundedata fra andre kilder.
- Anvende Customer Insights-datarensning, forbedring og fuzzy matching.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Brug indholdsrige profiler i realtidsmarketing

I realtidsmarketing kan du oprette [brugerdefinerede udløsere](/dynamics365/marketing/real-time-marketing-custom-triggers), der starter kundekampagneforløb baseret på en kundehandling. Jo mere personlige dine data er, jo mere relevante og personlige bliver dine kundekampagneforløb. Det er det, der gør det så effektivt at kombinere Marketing og Customer Insights. Du kan [samle data](data-unification.md) fra en hvilken som helst kilde og derefter bruge dem til at give brændstof til hypertilpassede kundekampagneforløb.

Læs mere: [Brug profiler og segmenter i Customer Insights til realtidsmarketing](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Brug af ensartede segmenter med udgående kundekampagneforløb

Med Customer Insights kan du finjustere data fra mange kilder og kombinere dem i aggregerede kundesegmenter. Hvis du [opretter forbindelse mellem Customer Insights og udgående marketing](export-dynamics365-marketing.md), vises disse segmenter automatisk *og* de opdateres automatisk i designere af kundekampagneforløb.

Flere oplysninger: [Brug segmenter fra Dynamics 365 Customer Insights med Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Trække data fra dine egne Azure Data Lake Storage

Du er ikke begrænset til skylager, hvis du vil bruge Customer Insights-data med Marketing. Hvis du allerede har din egen Azure Data Lake Storage opsætning, kan du oprette forbindelse til Customer Insights og derefter dele dataene med appen Marketing på samme måde som med en skybaseret konfiguration.

Flere oplysninger: [Aktivere datadeling med Dataverse fra din egen Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
