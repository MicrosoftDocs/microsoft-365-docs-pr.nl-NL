---
title: Een domein toevoegen aan een client, pacht met Windows PowerShell voor DAP partners
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
description: 'Overzicht: gebruik PowerShell voor Microsoft 365 om een alternatieve domeinnaam toe te voegen aan een bestaande Tenant van de klant.'
ms.openlocfilehash: 23137d2e2461e75a22d0403f9b8246a29e48019f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689527"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>Een domein toevoegen aan een client, pacht met Windows PowerShell voor gedelegeerde toegangsrechten (DAP)-partners

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt nieuwe domeinen maken en aan de pacht van de klant koppelen met behulp van PowerShell voor Microsoft 365, dan via het Microsoft 365-Beheercentrum.
  
De partners van de gedelegeerde toegang (machtigingen) zijn syndicaties en partners van een Cloud solution provider. Vaak zijn ze netwerk-of telecommunicatie providers van andere bedrijven. Ze bundelt Microsoft 365-abonnementen in hun serviceaanbiedingen voor hun klanten. Wanneer iemand een Microsoft 365-abonnement verkoopt, worden er automatisch beheermachtigingen verleend namens (AOBO) aan de klant tenancies zodat ze de klant tenancies kunnen beheren en rapporteren.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

Voor de procedures in dit onderwerp moet u verbinding kunnen maken met [Microsoft 365 met PowerShell](connect-to-microsoft-365-powershell.md).
  
U hebt ook uw Tenant-beheerderreferenties voor uw partners nodig.
  
Ook hebt u de volgende gegevens nodig:
  
- U hebt de FQDN-naam (Fully Qualified Domain Name) nodig die de klant wil.
    
- U hebt de **TenantId**van de klant nodig.
    
- U moet de FQDN registreren bij een DNS-registratie (Internet Domain Name Service), zoals GoDaddy. Zie [een domeinnaam kopen](https://go.microsoft.com/fwlink/p/?LinkId=532541)voor meer informatie over het openbaar registreren van een domeinnaam.
    
- U wilt weten hoe u een TXT-record kunt toevoegen aan de geregistreerde DNS-zone voor uw DNS-registratie. Zie [DNS-records toevoegen om uw domein te koppelen](https://go.microsoft.com/fwlink/p/?LinkId=532542)voor meer informatie over het toevoegen van een TXT-record. Als deze procedures niet voor u werken, moet u de procedures voor uw DNS-registratieservice vinden.
    
## <a name="create-domains"></a>Domeinen maken

 Uw klanten vragen u waarschijnlijk om extra domeinen te maken die u wilt koppelen aan hun pacht, omdat ze het standaarddomein van de <domain> onmicrosoft.com niet als primaire domein voor hun bedrijfsidentiteit voor de wereld vertegenwoordigen. In deze procedure wordt u begeleid bij het maken van een nieuw domein dat is gekoppeld aan de pacht van uw klant.
  
> [!NOTE]
> Voor het uitvoeren van enkele van deze bewerkingen moet het partner beheerdersaccount waarmee u zich aanmeldt, worden ingesteld op **volledig beheer** van de instelling **beheerderstoegang verlenen tot bedrijven die u** kunt instellen in de details van het beheerdersaccount in het Microsoft 365-Beheercentrum. Voor meer informatie over het beheren van partner beheerdersrollen raadpleegt u [partners: gedelegeerd beheer bieden](https://go.microsoft.com/fwlink/p/?LinkId=532435). 
  
### <a name="create-the-domain-in-azure-active-directory"></a>Het domein maken in azure Active Directory

Met deze opdracht maakt u het domein in azure Active Directory, maar wordt het niet gekoppeld aan het openbaar geregistreerde domein. Dit wordt geleverd wanneer u bewijzen dat u de eigenaar bent van het domein dat u de eigenaar bent van het domein voor Microsoft 365 voor ondernemingen.
  
```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

>[!Note]
>De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam. Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.
>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>De gegevens voor de DNS TXT-verificatie record weergeven

 In Microsoft 365 worden de specifieke gegevens gegenereerd die u in de DNS-TXT-verificatie record moet plaatsen. Als u de gegevens wilt weergeven, voert u deze opdracht uit.
  
```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

U krijgt dan de volgende uitvoer:
  
 `Label: domainname.com`
  
 `Text: MS=ms########`
  
 `Ttl: 3600`
  
> [!NOTE]
> U hebt deze tekst nodig voor het maken van de TXT-record in de algemeen geregistreerde DNS-zone. Zorg ervoor dat u het bestand kopieert en opslaat. 
  
### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a>Een TXT-record toevoegen aan de algemeen geregistreerde DNS-zone

Voordat Microsoft 365 het verkeer voor de naam van de algemeen geregistreerde domeinnaam accepteert, moet u bewijzen dat u de eigenaar bent van het domein en dat u beschikt over beheerdersmachtigingen voor het domein. U bewijzen dat u de eigenaar bent van het domein door een TXT-record in het domein te maken. Een TXT-record doet niets in uw domein en kan worden verwijderd nadat het eigendom van het domein is ingesteld. U maakt de TXT-records door de procedures te volgen bij [DNS-records toevoegen om uw domein te verbinden](https://go.microsoft.com/fwlink/p/?LinkId=532542). Als deze procedures niet voor u werken, moet u de procedures voor uw DNS-registratieservice vinden.
  
Bevestig dat het maken van de TXT-record via nslookup is gelukt. Volg deze syntaxis.
  
```console
nslookup -type=TXT <FQDN of registered domain>
```

U krijgt dan de volgende uitvoer:
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-microsoft-365"></a>Domein eigendom valideren in Microsoft 365

In deze laatste stap valideert u met Microsoft 365 dat u de eigenaar bent van het algemeen geregistreerde domein. Na deze stap gaat Microsoft 365 met het accepteren van verkeer naar de nieuwe domeinnaam. Voer deze opdracht uit om het maken en registreren van het domein te voltooien. 
  
```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Met deze opdracht worden geen uitvoer geretourneerd, zodat u kunt controleren of dit heeft gewerkt, en voer deze opdracht uit.
  
```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Dit retourneert iets zoals dit

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

   
## <a name="see-also"></a>Zie ook

#### 

[Help voor partners](https://go.microsoft.com/fwlink/p/?LinkID=533477)

