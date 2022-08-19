---
title: Medbringe din egen Azure Key Vault (forhåndsversion)
description: Få mere at vide om, hvordan du konfigurerer Customer Insights til at bruge din egen Azure Key Vault til at administrere hemmeligheder.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: da-DK
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246148"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Medbringe din egen Azure Key Vault (forhåndsversion)

Hvis du knytter en dedikeret [Azure Key Vault](/azure/key-vault/general/basic-concepts) til et Customer Insights-miljø, kan organisationer opnå overholdelse af angivne standarder.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Knytte Key Vault til miljøet for Customer Insights

Konfigurer den dedikerede Key Vault kan bruges til at oprette og bruge hemmeligheder i en organisations grænse for overholdelse af angivne standarder.

### <a name="prerequisites"></a>Forudsætninger

- Et aktivt Azure-abonnement.

- En [Administrator](permissions.md#admin)-rolle [tildelt](permissions.md#add-users) i Customer Insights.

- [Bidragyder](/azure/role-based-access-control/built-in-roles#contributor) og [Administrator med brugeradgang](/azure/role-based-access-control/built-in-roles#user-access-administrator) i Key Vault eller den ressourcegruppe, som Key Vault tilhører. Du kan finde flere oplysninger ved at gå til [Tilføje eller fjerne Azure-rolletildelinger ved hjælp af Azure-portalen](/azure/role-based-access-control/role-assignments-portal). Hvis du ikke har rollen Administrator med brugeradgang i Key Vault, skal du konfigurere de rollebaserede adgangskontroltilladelser for Azure-tjenestesikkerhedskontoen til Dynamics 365 Customer Insights separat. Følg trinnene til at [bruge en Azure-tjenestesikkerhedskonto](connect-service-principal.md) til den Key Vault, der skal tilknyttes.

- Key Vault skal have Key Vault-firewallen **deaktiveret**.

- Key Vault findes på samme [Azure-placering](https://azure.microsoft.com/global-infrastructure/geographies/#overview) som Customer Insights-miljøet. I Customer Insights skal du gå til **Admin** > **System** og derefter til fanen **About**, hvis du vil vide mere om området i miljøet.

### <a name="recommendations"></a>Anbefalinger

- [Brug et separat eller dedikeret Key Vault](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults), der kun indeholder de hemmeligheder, der kræves til Customer Insights.

- Følg de [bedste fremgangsmåder for at bruge Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) til at styre indstillinger for adgang, sikkerhedskopiering, overvågning og gendannelse.

### <a name="link-a-key-vault-to-the-environment"></a>Knytte en Key Vault til miljøet

1. Gå til **Administration** > **Sikkerhed**, og vælg derefter fanen **Key Vault**.
1. Vælg **Installation** i feltet **Key Vault**.
1. Vælg et **Abonnement**.
1. Vælg en Key Vault på rullelisten **Key Vault**. Hvis der er for mange tilgængelige på listen, skal du vælge en ressourcegruppe for at begrænse søgeresultaterne.
1. Gennemse [Beskyttelse af personlige data og overholdelse af angivne standarder](connections.md#data-privacy-and-compliance), og vælg **Jeg accepterer**.
1. Vælg **Gem**.

I feltet **Key Vault** vises nu det tilknyttede Key Vault-navn, abonnement og ressourcegruppe. Den er klar til brug i forbindelseskonfigurationen.
Du kan finde flere oplysninger om, hvilke tilladelser i Key Vault der er tildelt til Customer Insights, ved at gå til [Tilladelser, der er tildelt på Key Vault](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Bruge Key Vault i forbindelseskonfigurationen

Når du [konfigurerer forbindelser](connections.md) til [understøttede tredjepartssystemer](#supported-connection-types), kan hemmelighederne fra det tilknyttede Key Vault bruges til at konfigurere forbindelserne.

1. Gå til **Administrator** > **Forbindelser**.
1. Vælg **Tilføj forbindelse**.
1. For de understøttede forbindelsestyper findes indstillingen **Brug Key Vault**, hvis du har sammenkædet en Key Vault.
1. I stedet for at skrive hemmeligheden manuelt, skal du vælge det hemmelighedsnavn, der peger på hemmelighedsværdien i Key Vault.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Forbindelsesrude med en SFTP-forbindelse, der bruger en Key Vault-hemmelighed.":::

1. Vælg **Gem** for at oprette forbindelsen.

## <a name="supported-connection-types"></a>Understøttede forbindelsestyper

Følgende forbindelser for [eksport](export-destinations.md) understøttes:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Tilladelser, der er tildelt til key vault

Følgende tilladelser tildeles Customer Insights i et sammenkædet Key Vault, hvis enten [Key Vault-adgangspolitik](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) eller [Azure-rollebaseret adgangskontrol](/azure/key-vault/general/rbac-guide?tabs=azure-cli) er aktiveret.

### <a name="key-vault-access-policy"></a>Key Vault-adgangspolitik

| Skriv        | Tilladelser          |
| ----------- | -------------------- |
| Nøgle         | [Hent nøgler](/rest/api/keyvault/keys/get-keys/get-keys), [Hent nøgle](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Hemmelighed      | [Hent hemmeligheder](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Hent hemmelighed](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certifikat | [Hent certifikater](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Hent certifikat](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

De foregående værdier er minimumværdierne til visning og læsning under udførelse.

### <a name="azure-role-based-access-control"></a>Azure-rollebaseret adgangskontrol

[Brugerrollerne Key Vault-læser og Key Vault-hemmeligheder](/azure/key-vault/general/rbac-guide?tabs=azure-cli) tilføjes for Customer Insights.

## <a name="frequently-asked-questions"></a>Ofte stillede spørgsmål

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Kan Customer Insights skrive hemmeligheder eller overskrive hemmeligheder i Key Vault?

Nej. Det er kun de læse- og listetilladelser, der er skitseret i afsnittet [tildelte tilladelser](#permissions-granted-on-the-key-vault) tildeles til Customer Insights. Systemet kan ikke tilføje, slette eller overskrive hemmeligheder i Key Vault. Det er også årsagen til, at du ikke kan angive legitimationsoplysninger, når en forbindelse bruger Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Kan jeg ændre en forbindelse fra at bruge Key Vault-hemmeligheder til standardgodkendelse?

Nej. Du kan ikke skifte tilbage til en standardforbindelse, når du har konfigureret den ved hjælp af en hemmelighed fra et tilknyttet Key Vault. Opret en separat forbindelse, og slet den gamle, hvis du ikke længere har brug for den.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Hvordan kan jeg tilbagekalde adgang til et Key Vault for Customer Insights?

Hvis [Key Vault-adgangspolitik](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) eller [Azure-rollebaseret adgangskontrol](/azure/key-vault/general/rbac-guide?tabs=azure-cli) er aktiveret, skal du fjerne tilladelserne for tjenestesikkerhedskontoen `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` med navnet `Dynamics 365 AI for Customer Insights`. Alle forbindelser, der bruger Key Vault, holder op med at fungere.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>En hemmelighed, der bruges i en forbindelse, blev fjernet fra Key Vault. Hvad kan jeg gøre?

Du kan se en meddelelse Customer Insights, når der ikke længere er adgang til en konfigureret hemmelighed fra Key Vault. Aktivér [manuel sletning](/azure/key-vault/general/soft-delete-overview) på Key Vault for at gendanne hemmeligheder, hvis de utilsigtet er blevet fjernet.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>En forbindelse virker ikke, men min hemmelighed er i Key Vault. Hvad kan være årsagen?

Der vises en meddelelse Customer Insights, når den ikke har adgang til Key Vault. Årsagen kan være:

- Tilladelserne til tjenestesikkerhedskontoen for Customer Insights er fjernet. De skal gendannes manuelt.

- Firewallen på Key Vault er aktiveret. Firewallen skal deaktiveres for at gøre Key Vault tilgængelig for Customer Insights igen.
