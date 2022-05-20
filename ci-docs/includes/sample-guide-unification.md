---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755537"
---
Når dataene er blevet indtaget, skal du starte processen til samling af data for at oprette en unified customer profile. Du kan finde flere oplysninger i [Datasamling](../data-unification.md).

### <a name="select-source-fields"></a>Vælg kildefelter

1. Når du har indsat dataene, skal du knytte kontakterne fra eCommerce- og Loyalty-data til almindelige datatyper. Gå til **Data** > **Samle**.

1. Vælg de objekter, der repræsenterer kundeprofilen - **eCommerceContacts** og **loyCustomers**.

   ![samle eCommerce- og loyalty-datakilder.](../media/unify-ecommerce-loyalty.png)

1. Vælg **ContactId** som primær nøgle for **eCommerceContacts** og **LoyaltyID** som primær nøgle for **loyCustomers**.

1. Vælg **Næste**. Spring over dublerede poster, og vælg **Næste**.

### <a name="match-conditions"></a>Match betingelser

1. Vælg **eCommerceContacts : eCommerce** som det primære objekt, og inkluder alle poster.

1. Vælg **loyCustomers : LoyaltyScheme**, og medtag alle poster.

1. Tilføje en regel:
   - Vælg **FullName** for både eCommerceContacts og loyCustomers.
   - Vælg **Type (Telefon, Navn, Adresse, ...)** for **Normaliser**.
   - Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.
   - Angiv **FullName, Email** for navnet.

1. Tilføj endnu en betingelse for e-mailadresse:
   - Vælg **Email** for både eCommerceContacts og loyCustomers.
   - Lad Normaliser være tom.
   - Angiv **Præcisionsniveau**: **Basis** og **værdi**: **Høj**.

   ![Saml og match regel for navn og e-mail.](../media/unify-match-rule.png)

1. Vælg **Udført**.

1. Vælg **Næste**.

### <a name="unify-fields"></a>Unify felter

1. Omdøb objektet **ContactId** for **loyCustomers** til **ContactIdLOYALTY** for at adskille det fra de andre id'er.

1. Vælg **Næste** for at gennemse, og vælg derefter **Opret kundeprofiler**.
