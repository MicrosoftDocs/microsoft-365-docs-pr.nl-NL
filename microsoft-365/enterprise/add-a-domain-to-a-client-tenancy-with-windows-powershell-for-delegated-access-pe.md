---
title: Een domein toevoegen aan een client tenancy met Windows PowerShell voor DAP-partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: 'Overzicht: Gebruik PowerShell voor Microsoft 365 om een alternatieve domeinnaam toe te voegen aan een bestaande klant tenant.'
ms.openlocfilehash: 5ebbe11da9a93669945e7e3b096ce7afa18b5d3a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288429"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>Een domein toevoegen aan een client tenancy met Windows PowerShell voor DAP-partners (Gedelegeerde toegangsmachtiging)

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt nieuwe domeinen maken en koppelen aan de huurovereenkomst van uw klant met PowerShell Microsoft 365 sneller dan het gebruik van de Microsoft 365-beheercentrum.

DAP-partners (Gedelegeerde Access Permission) zijn Syndication- en Cloud Solution Providers (CSP)-partners. Ze zijn vaak netwerk- of telecomproviders voor andere bedrijven. Ze bundelen Microsoft 365 abonnementen in hun serviceaanbiedingen voor hun klanten. Wanneer ze een Microsoft 365-abonnement verkopen, worden ze automatisch machtigingen voor beheer namens (AOBO) verleend aan de klanten, zodat ze de klantentenancies kunnen beheren en rapporteren.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

Voor de procedures in dit onderwerp moet u verbinding maken met Verbinding maken [met Microsoft 365 PowerShell.](connect-to-microsoft-365-powershell.md)

U hebt ook de referenties van de partnertenatiebeheerder nodig.

U hebt ook de volgende informatie nodig:

- U hebt de volledig gekwalificeerde domeinnaam (FQDN) nodig die uw klant wil.

- U hebt de **TenantId** van de klant nodig.

- De FQDN moet zijn geregistreerd bij een DNS-registrar (Internet Domain Name Service), zoals GoDaddy. Zie Een domeinnaam kopen voor meer informatie over het openbaar registreren van [een domeinnaam.](../admin/get-help-with-domains/buy-a-domain-name.md)

- U moet weten hoe u een TXT-record toevoegt aan de geregistreerde DNS-zone voor uw DNS-registrar. Zie [DNS-records](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)toevoegen om uw domein te verbinden voor meer informatie over het toevoegen van een TXT-record. Als deze procedures niet voor u werken, moet u de procedures voor uw DNS-registrar vinden.

## <a name="create-domains"></a>Domeinen maken

 Uw klanten zullen u waarschijnlijk vragen om extra domeinen te maken om te koppelen aan hun huurovereenkomst, omdat ze niet willen dat het standaard .onmicrosoft.com-domein het primaire domein is dat hun bedrijfsidentiteiten aan de wereld <domain> vertegenwoordigt. Met deze procedure maakt u een nieuw domein dat is gekoppeld aan de huurovereenkomst van uw klant.

> [!NOTE]
> Als u een aantal van deze bewerkingen wilt uitvoeren,  moet het  account van de partnerbeheerder bij wie u zich aanlogt, zijn ingesteld op Volledig beheer voor de instelling Beheerderstoegang toewijzen aan bedrijven die u ondersteunt in de details van het beheerdersaccount in de Microsoft 365-beheercentrum. Zie Partners: Gedelegeerd beheer aanbieden voor meer informatie over het beheren van rollen van [partnerbeheerders.](https://go.microsoft.com/fwlink/p/?LinkId=532435)

### <a name="create-the-domain-in-azure-active-directory"></a>Het domein maken in Azure Active Directory

Met deze opdracht wordt het domein in Azure Active Directory gemaakt, maar niet aan het openbaar geregistreerde domein. Dat komt wanneer u bewijst dat u eigenaar bent van het openbaar geregistreerde domein van Microsoft Microsoft 365 voor ondernemingen.

```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

> [!NOTE]
> PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>De gegevens voor de DNS TXT-verificatierecord

 Microsoft 365 worden de specifieke gegevens gegenereerd die u in de DNS TXT-verificatierecord moet plaatsen. Voer deze opdracht uit om de gegevens op te halen.

```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

Hierdoor krijgt u de volgende uitvoer:

 `Label: domainname.com`

 `Text: MS=ms########`

 `Ttl: 3600`

> [!NOTE]
> U hebt deze tekst nodig om de TXT-record te maken in de openbaar geregistreerde DNS-zone. Kopieer en sla het op.

### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a>Een TXT-record toevoegen aan de openbaar geregistreerde DNS-zone

Voordat Microsoft 365 het verkeer dat wordt doorgestuurd naar de openbaar geregistreerde domeinnaam, accepteert, moet u bewijzen dat u de eigenaar bent van het domein en dat u beheerdersmachtigingen voor het domein hebt. U bewijst dat u de eigenaar bent van het domein door een TXT-record in het domein te maken. Een TXT-record doet niets in uw domein en kan worden verwijderd nadat u eigenaar bent van het domein. Als u de TXT-records wilt maken, volgt u de procedures bij [DNS-records toevoegen om uw domein te verbinden.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) Als deze procedures niet voor u werken, moet u de procedures voor uw DNS-registrar vinden.

Bevestig de succesvolle creatie van de TXT-record via nslookup. Volg deze syntaxis.

```console
nslookup -type=TXT <FQDN of registered domain>
```

Hierdoor krijgt u de volgende uitvoer:

 `Non-authoritative answer:`

 `FQDN of the registered domain`

 `text=MS=ms########`

### <a name="validate-domain-ownership-in-microsoft-365"></a>Domeineigenschap valideren in Microsoft 365

In deze laatste stap valideert u Microsoft 365 dat u de eigenaar bent van het openbaar geregistreerde domein. Na deze stap wordt Microsoft 365 met het accepteren van verkeer dat wordt doorgeleid naar de nieuwe domeinnaam. Voer deze opdracht uit om het proces voor het maken en registreren van domeinen te voltooien.

```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Met deze opdracht wordt geen uitvoer als resultaat gegeven, dus voer deze opdracht uit om te bevestigen dat dit heeft gewerkt.

```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Dit zal zoiets als dit retourneren

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

## <a name="see-also"></a>Zie ook

[Help voor partners](https://go.microsoft.com/fwlink/p/?LinkID=533477)
