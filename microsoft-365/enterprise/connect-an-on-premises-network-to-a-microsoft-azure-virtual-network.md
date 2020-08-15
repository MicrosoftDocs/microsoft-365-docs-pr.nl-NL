---
title: Een on-premises netwerk verbinden met een Microsoft Azure Virtual Network
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 81190961-5454-4a5c-8b0e-6ae75b9fb035
description: 'Overzicht: informatie over het configureren van een cross-premises Azure virtueel netwerk voor Office Server-werkbelasting met een VPN-verbinding (site-to-site).'
ms.openlocfilehash: cddb9cfcff02f91ef76f989b87e9dda049cc1b08
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695698"
---
# <a name="connect-an-on-premises-network-to-a-microsoft-azure-virtual-network"></a>Een on-premises netwerk verbinden met een Microsoft Azure Virtual Network

Er is een on-premises Azure virtueel netwerk verbonden met uw on-premises netwerk en breidt uw netwerk uit met subnetten en virtuele machines die worden gehost in azure-infrastructuurservices. Met deze verbinding kunnen computers op uw on-premises netwerk rechtstreeks toegang krijgen tot virtuele machines in Azure en omgekeerd. 

Wanneer een adreslijstsynchronisatie server wordt uitgevoerd op een virtuele server van Azure, moet u een query uitvoeren op uw on-premises domeincontrollers om wijzigingen aan accounts aan te brengen en deze wijzigingen te synchroniseren met uw Microsoft 365-abonnement. In dit artikel leest u hoe u een VPN-verbinding (Virtual on-premises) van Azure instelt met een VPN-verbinding (Virtual Private Network) die geschikt is voor het hosten van Azure virtuele machines.

## <a name="configure-a-cross-premises-azure-virtual-network"></a>Een cross-premises Azure virtueel netwerk configureren

Uw virtuele machines in azure hoeven niet te worden geïsoleerd van uw on-premises omgeving. Als u virtuele machines van Azure wilt verbinden met uw on-premises netwerkbronnen, moet u een cross-premises Azure virtueel netwerk configureren. In het volgende diagram ziet u de vereiste onderdelen voor het implementeren van een on-premises Azure virtueel netwerk met een virtuele machine in Azure.
  
![On-premises netwerk verbonden met Microsoft Azure via een site-to-site VPN-verbinding](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
 
In het diagram zijn er twee netwerken verbonden via een VPN-verbinding (site-naar-site): het on-premises netwerk en het virtuele Azure-netwerk. De VPN-verbinding tussen sites is:

- Schakelen tussen twee eindpunten die zijn geadresseerd en zich op het openbare Internet bevinden.
- Beëindigd door een VPN-apparaat in het on-premises netwerk en een Azure VPN-gateway op het virtuele Azure-netwerk.

De virtuele machines van Azure virtueel netwerk. Netwerkverkeer dat afkomstig is van virtuele machines op het virtuele Azure-netwerk, wordt doorgestuurd naar de VPN-gateway, waarna het verkeer wordt doorgestuurd via de site-naar-site VPN-verbinding met het VPN-apparaat op het on-premises netwerk. De routeringsinfrastructuur van het on-premises netwerk stuurt het verkeer door naar de bestemming.

>[!Note]
>U kunt ook [ExpressRoute](https://azure.microsoft.com/services/expressroute/)gebruiken, een directe verbinding tussen uw organisatie en het Microsoft-netwerk. Verkeer via ExpressRoute verreist niet via het openbare Internet. In dit artikel wordt het gebruik van ExpressRoute niet beschreven.
>
  
Voer de volgende stappen uit om de VPN-verbinding in te stellen tussen uw virtuele en uw on-premises netwerk. 
  
1. **On-premises:** Definieer en maak een on-premises netwerkroute voor de adresruimte van het virtuele Azure-netwerk dat verwijst naar uw on-premises VPN-apparaat.
    
2. **Microsoft Azure:** Maak een virtueel Azure-netwerk met een VPN-verbinding tussen sites. 
    
3. **On-premises:** Configureer uw on-premises hardware-of software VPN-apparaat om de VPN-verbinding te beëindigen, dat gebruikmaakt van IPsec (Internet Protocol Security).
    
Wanneer u de site-tot-site VPN-verbinding tot stand hebt gebracht, voegt u virtuele machines van Azure toe aan de subnetten van het virtuele netwerk.
  
## <a name="plan-your-azure-virtual-network"></a>Uw virtuele Azure-netwerk plannen
<a name="PlanningVirtual"></a>

### <a name="prerequisites"></a>Vereisten
<a name="Prerequisites"></a>

- Een Azure-abonnement. Ga naar de [pagina een Azure-pagina kopen](https://azure.microsoft.com/pricing/purchase-options/)voor meer informatie over Azure-abonnementen.
    
- Een beschikbare, persoonlijke IPv4-adresruimte die moet worden toegewezen aan het virtuele netwerk en de subnetten, met voldoende ruimte voor groei, zodat het aantal benodigde virtuele machines nu en in de toekomst kan worden aangepast.
    
- Een beschikbaar VPN-apparaat in uw on-premises netwerk om de site-tot-site VPN-verbinding te beëindigen die de vereisten voor IPsec ondersteunt. Zie voor meer informatie [over VPN-apparaten voor site-to-site virtuele netwerkverbindingen](https://go.microsoft.com/fwlink/p/?LinkId=393093).
    
- Wijzigingen in uw routeringsinfrastructuur, zodat het verkeer naar de adresruimte van het virtuele Azure-netwerk wordt doorgestuurd naar het VPN-apparaat waarop de site-to-site VPN-verbinding is gehost.
    
- Een webproxy waarmee computers worden gebruikt die verbonden zijn met het on-premises netwerk en de toegang tot het Internet van Azure Virtual Network.
    
### <a name="solution-architecture-design-assumptions"></a>Ontwerp hypothesen voor oplossingen van de architectuur

De volgende lijst bevat de ontwerp keuzes die zijn gemaakt voor deze oplossingsarchitectuur. 
  
- Deze oplossing maakt gebruik van één virtueel Azure-netwerk met een VPN-verbinding tussen sites. Het Azure Virtual Network host een enkelvoudig subnet dat meerdere virtuele machines kan bevatten. 
    
- U kunt de Routing and Remote Access-service (RRAS) in Windows Server 2016 of Windows Server 2012 gebruiken voor het maken van een IPsec-site-naar-site VPN-verbinding tussen het on-premises netwerk en het Azure virtueel netwerk. U kunt ook andere opties gebruiken, zoals Cisco of Juniper Networks VPN-apparaten.
    
- Het on-premises netwerk heeft mogelijk nog steeds netwerkservices als Active Directory Domain Services (AD DS), Domain Name System (DNS) en proxyservers. Afhankelijk van de vereisten is het misschien handig om enkele van deze netwerkbronnen in het virtuele Azure-netwerk te plaatsen.
    
Voor een bestaand Azure virtueel netwerk met een of meer subnetten bepaalt u of er nog resterende adresruimte is voor een extra subnet waarop u de benodigde virtuele machines moet hosten, op basis van uw vereisten. Als u geen resterende adresruimte hebt voor een extra subnet, maakt u een extra virtueel netwerk met een eigen site-naar-site VPN-verbinding.
  
### <a name="plan-the-routing-infrastructure-changes-for-the-azure-virtual-network"></a>De wijzigingen in de routeringsinfrastructuur voor het virtuele Azure-netwerk plannen

U moet uw on-premises routeringsinfrastructuur configureren voor het doorsturen van verkeer dat bestemd is voor de adresruimte van het virtuele Azure-netwerk naar het on-premises VPN-apparaat dat de site-to-site VPN-verbinding host.
  
Welke methode u moet gebruiken om de routeringsinfrastructuur bij te werken, is afhankelijk van de manier waarop u routeringsinformatie beheert, wat de volgende oorzaken hebben:
  
- Updates van routeringstabellen op basis van handmatige configuratie.
    
- Updates van routeringstabellen op basis van routeringsprotocollen, zoals Routing Information Protocol (RIP) of Open Shortest Path First (OSPF).
    
Neem contact op met de bewerkings medewerker om na te gaan of het verkeer dat bestemd is voor het virtuele Azure-netwerk, is doorgestuurd naar het on-premises VPN-apparaat.
  
### <a name="plan-for-firewall-rules-for-traffic-to-and-from-the-on-premises-vpn-device"></a>Het plannen van firewallregels voor verkeer naar en vanaf het on-premises VPN-apparaat

Als uw VPN-apparaat gebruikmaakt van een perimeternetwerk met een firewall tussen het perimeternetwerk en Internet, moet u mogelijk de firewall voor de volgende regels configureren, zodat de VPN-verbinding tussen sites kan worden toegestaan.
  
- Verkeer naar het VPN-apparaat (inkomend via internet):
    
  - Doelpad van IP-adres van het VPN-apparaat en IP-protocol 50
    
  - Doelpad van IP-adres van het VPN-apparaat en UDP-doelpoort 500
    
  - Doelpad van IP-adres van het VPN-apparaat en UDP-doelpoort 4500
    
- Verkeer van het VPN-apparaat (uitgaand op Internet):
    
  - Bron-IP-adres van het VPN-apparaat en IP-protocol 50
    
  - Bron-IP-adres van het VPN-apparaat en UDP-bronpoort 500
    
  - Bron-IP-adres van het VPN-apparaat en UDP-bronpoort 4500
    
### <a name="plan-for-the-private-ip-address-space-of-the-azure-virtual-network"></a>Plan voor de persoonlijke IP-adresruimte van het virtuele Azure-netwerk

De persoonlijke IP-adresruimte van het virtuele netwerk van Azure moet de adressen kunnen bevatten die door Azure worden gebruikt voor het hosten van het virtuele netwerk en met minimaal één subnet met voldoende adressen voor uw virtuele machines van Azure.
  
Als u het aantal adressen wilt bepalen dat nodig is voor het subnet, telt u het aantal virtuele machines dat u nodig hebt, moet u een schatting voor toekomstige groei en gebruikt u vervolgens de volgende tabel om de grootte van het subnet te bepalen.
  
|**Aantal benodigde virtuele machines**|**Aantal benodigde host-bits**|**De grootte van het subnet**|
|:-----|:-----|:-----|
|1-3  <br/> |driefasig  <br/> |/29  <br/> |
|4-11  <br/> |3  <br/> |/28  <br/> |
|12-27  <br/> |vijf  <br/> |/27  <br/> |
|28-59  <br/> |zes  <br/> |/26  <br/> |
|60-123  <br/> |7,5  <br/> |/25  <br/> |
   
### <a name="planning-worksheet-for-configuring-your-azure-virtual-network"></a>Planningswerkblad voor het configureren van uw Azure Virtual Network
<a name="worksheet"> </a>

Voordat u een virtueel virtueel netwerk van Azure maakt om virtuele machines te hosten, moet u de benodigde instellingen voor de volgende tabellen bepalen.
  
Vul tabel V in voor de instellingen van het virtuele netwerk.
  
 **Tabel V: virtuele netwerkconfiguratie van cross-premises**
  
|**Item**|**Configuratie-element**|**Beschrijving**|**Value**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Naam van virtueel netwerk  <br/> |Een naam die moet worden toegewezen aan het virtuele Azure-netwerk (bijvoorbeeld DirSyncNet).  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) |
|2.  <br/> |Virtuele netwerklocatie  <br/> |Het Azure-datacenter dat het virtuele netwerk bevat (zoals westelijke Verenigde Staten).  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |IP-adres voor VPN-apparaat  <br/> |Het openbare IPv4-adres van de interface van uw VPN-apparaat op internet. Werk samen met uw IT-afdeling om dit adres te bepalen.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |Virtuele netwerkadres ruimte  <br/> |De adresruimte (gedefinieerd in één persoonlijke adresprefix) voor het virtuele netwerk. Werk samen met uw IT-afdeling om deze adresruimte te bepalen. De adresruimte moet in de bewerkings indeling van een Klasloze interdomein-indeling zijn, ook wel wel netwerkvoorvoegsel-indeling genoemd. Een voorbeeld is 10.24.64.0/20.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) <br/> |
|5.  <br/> |Gedeelde IPsec-sleutel  <br/> |32 een willekeurige alfanumerieke tekenreeks die wordt gebruikt voor de verificatie van beide zijden van de VPN-verbinding tussen sites. Werk samen met uw IT-of beveiligingsafdeling om deze sleutelwaarde te bepalen en op een veilige plaats op te slaan. U kunt ook [een willekeurige tekenreeks maken voor een met IPSec vooraf gedeelde sleutel](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png) <br/> |
   
Vul de tabel S in voor de subnetten van deze oplossing.
  
- Voor het eerste subnet: Bepaal een 28-bits adresruimte (met een/28 prefixlengte) voor het Azure gateway-subnet. Zie voor meer informatie over het bepalen van de adresruimte [van het gateway-subnet voor Azure VM-netwerken](https://blogs.technet.microsoft.com/solutions_advisory_board/2016/12/01/calculating-the-gateway-subnet-address-space-for-azure-virtual-networks/) .
    
- Geef voor het tweede subnet een beschrijvende naam op, een enkele IP-adresruimte op basis van de virtuele netwerkadres ruimte, en een omschrijvend doel.
    
Werk samen met uw IT-afdeling om te bepalen welke adresruimten de virtuele netwerklocatie van het adres heeft. Beide adresruimten moeten in de CIDR-indeling staan.
  
 **Tabel S: subnetten in het virtuele netwerk**
  
|**Item**|**Naam van subnet**|**Adresruimte van subnet**|**Doel**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |GatewaySubnet  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |Het subnet dat wordt gebruikt door de Azure gateway.  <br/> |
|2.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
   
Voor de on-premises DNS-servers die u wilt gebruiken voor de virtuele machines in het virtuele netwerk, moet u de tabel D invullen. Geef elke DNS-server een beschrijvende naam en één IP-adres. Deze beschrijvende naam hoeft niet overeen te komen met de host name of computernaam van de DNS-server. Houd er rekening mee dat er twee lege vermeldingen worden weergegeven, maar u kunt meer toevoegen. Werk samen met uw IT-afdeling om deze lijst te bepalen.
  
 **Tabel D: on-premises DNS-servers**
  
|**Item**|**Beschrijvende naam van de DNS-server**|**IP-adres van de DNS-server**|
|:-----|:-----|:-----|
|1.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
   
Als u pakketten van het virtuele virtuele netwerk van Azure naar het netwerk van uw organisatie wilt routeren via de site-to-site VPN-verbinding, moet u het virtuele netwerk configureren met een lokaal netwerk. Dit lokale netwerk bevat een lijst met de adresruimten (in de CIDR-indeling) voor alle locaties in het on-premises netwerk van uw organisatie waartoe de virtuele machines in het virtuele netwerk moeten zijn aangekomen. Dit kunnen alle locaties op het on-premises netwerk of een subset zijn. De lijst met adresruimten waarmee uw lokale netwerk wordt gedefinieerd, moet uniek zijn en mag niet overlappen met de adresruimten die worden gebruikt voor dit virtuele netwerk of de andere cross-premises virtuele netwerken.
  
Voor de set lokale netwerkadres ruimten, vult u tabel L in. Merk op dat er wel drie lege vermeldingen worden weergegeven, maar u hebt meestal meer nodig. Werk samen met uw IT-afdeling om deze lijst te bepalen.
  
 **Tabel L: adresprefixen voor het lokale netwerk**
  
|**Item**|**Lokale netwerkadres ruimte**|
|:-----|:-----|
|1.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
   
## <a name="deployment-roadmap"></a>Implementatie routekaart
<a name="DeploymentRoadmap"> </a>

Het maken van het cross-premises virtuele netwerk en het toevoegen van virtuele machines in azure bestaat uit drie fasen:
  
- Fase 1: uw on-premises netwerk voorbereiden.
    
- Fase 2: Maak het cross-premises virtuele netwerk in Azure.
    
- Fase 3 (optioneel): virtuele machines toevoegen.
    
### <a name="phase-1-prepare-your-on-premises-network"></a>Fase 1: uw on-premises netwerk voorbereiden
<a name="Phase1"></a>

U moet uw on-premises netwerk configureren met een route die wijst naar en uiteindelijk verkeer begeleidt voor de adresruimte van het virtuele netwerk naar de router op de Edge van het on-premises netwerk. Neem contact op met uw netwerkbeheerder om te bepalen hoe u de route moet toevoegen aan de routeringsinfrastructuur van uw on-premises netwerk.
  
Dit is de resulterende configuratie.
  
![Het on-premises netwerk moet een route hebben voor de adresruimte van het virtuele netwerk dat verwijst naar het VPN-apparaat.](../media/90bab36b-cb60-4ea5-81d5-4737b696d41c.png)
  
### <a name="phase-2-create-the-cross-premises-virtual-network-in-azure"></a>Fase 2: het cross-premises virtuele netwerk in azure maken
<a name="Phase2"></a>

Open eerst een Azure PowerShell-prompt. Als u Azure PowerShell niet hebt geïnstalleerd, raadpleegt u [aan de slag met Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).

 
Meld u vervolgens aan bij uw Azure-account met deze opdracht.
  
```powershell
Connect-AzAccount
```

Haal de naam van uw abonnement op met de volgende opdracht.
  
```powershell
Get-AzSubscription | Sort SubscriptionName | Select SubscriptionName
```

Stel uw Azure-abonnement in met deze opdrachten. Vervang alles binnen de aanhalingstekens, inclusief de < en > tekens, met de juiste naam van het abonnement.
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

Maak vervolgens een nieuwe resourcegroep voor uw virtuele netwerk. Als u de naam van een unieke resourcegroep wilt bepalen, gebruikt u deze opdracht om uw bestaande resourcegroepen weer te geven.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Maak uw nieuwe resourcegroep aan met deze opdrachten.
  
```powershell
$rgName="<resource group name>"
$locName="<Table V - Item 2 - Value column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Vervolgens maakt u het virtuele Azure-netwerk.
  
```powershell
# Fill in the variables from previous values and from Tables V, S, and D
$rgName="<name of your new resource group>"
$locName="<Azure location of your new resource group>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$gwSubnetPrefix="<Table S - Item 1 - Subnet address space column>"
$SubnetName="<Table S - Item 2 - Subnet name column>"
$SubnetPrefix="<Table S - Item 2 - Subnet address space column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the Azure virtual network and a network security group that allows incoming remote desktop connections to the subnet that is hosting virtual machines
$gatewaySubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnetPrefix
$vmSubnet=New-AzVirtualNetworkSubnetConfig -Name $SubnetName -AddressPrefix $SubnetPrefix
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gatewaySubnet,$vmSubnet -DNSServer $dnsServers
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName -Location $locShortName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$nsg=Get-AzNetworkSecurityGroup -Name $SubnetName -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $SubnetName -AddressPrefix $SubnetPrefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

Dit is de resulterende configuratie.
  
![Het virtuele netwerk is nog geen verbinding met het on-premises netwerk.](../media/54a37782-a6cc-4d48-b38d-73e128b44a82.png)
  
Vervolgens kunt u deze opdrachten gebruiken om de gateways voor de site-to-site VPN-verbinding te maken.
  
```powershell
# Fill in the variables from previous values and from Tables V and L
$vnetName="<Table V - Item 1 - Value column>"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -SubnetId $vnet.Subnets[0].Id
# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig
# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix
# Create the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway
```

Dit is de resulterende configuratie.
  
![Het virtuele netwerk heeft nu een gateway.](../media/82dd66b2-a4b7-48f6-a89b-cfdd94630980.png)
  
Configureer vervolgens uw on-premises VPN-apparaat om verbinding te maken met de Azure VPN-gateway. Zie voor meer informatie [over VPN-apparaten voor site-to-site Azure virtuele netwerkverbindingen](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).
  
Als u uw VPN-apparaat wilt configureren, hebt u het volgende nodig:
  
- Het openbare IPv4-adres van de Azure VPN-gateway voor uw virtuele netwerk. Gebruik de opdracht **Get-AzPublicIpAddress-Name $vnetGatewayIpConfigName-ResourceGroupName $rgName** om dit adres weer te geven.
    
- De vooraf gedeelde sleutel van IPsec voor de site-to-site VPN-verbinding (tabel V-artikel met een waarde van 5 kolommen).
    
Dit is de resulterende configuratie.
  
![Het virtuele netwerk is nu verbonden met het on-premises netwerk.](../media/6379c423-4f22-4453-941b-7ff32484a0a5.png)
  
### <a name="phase-3-optional-add-virtual-machines"></a>Fase 3 (optioneel): virtuele machines toevoegen

Maak de virtuele machines die u nodig hebt in Azure. Zie voor meer informatie [een virtuele Windows-computer maken met de Azure-Portal](https://go.microsoft.com/fwlink/p/?LinkId=393098).
  
Gebruik de volgende instellingen:
  
- Selecteer op het tabblad **basis** de optie hetzelfde abonnement en de resourcegroep als uw virtuele netwerk. U hebt deze later nodig om u aan te melden bij de virtuele machine. Kies in de sectie **Details van exemplaar** de juiste grootte van de virtuele computer. Neem de gebruikersnaam en het wachtwoord van het beheerdersaccount op een veilige locatie op. 
    
- Selecteer op het tabblad **netwerken** de naam van uw virtuele netwerk en het subnet voor het hosten van virtuele machines (niet de GatewaySubnet). Zorg dat u alle overige instellingen tegen hun standaardwaarden hoeft te wijzigen.
    
Controleer of de virtuele machine correct DNS gebruikt door uw interne DNS te controleren om ervoor te zorgen dat adres-of record records zijn toegevoegd voor de nieuwe virtuele machine. Voor toegang tot het Internet moet uw virtuele machines van Azure zijn geconfigureerd voor gebruik van de proxyserver van het on-premises netwerk. Neem contact op met uw netwerkbeheerder voor aanvullende configuratiestappen voor de server.
  
Dit is de resulterende configuratie.
  
![Het virtuele netwerk host nu virtuele machines die toegankelijk zijn vanuit het on-premises netwerk.](../media/86ab63a6-bfae-4f75-8470-bd40dff123ac.png)
  
## <a name="next-step"></a>Volgende stap
  
[Microsoft 365 Directory-synchronisatie implementeren in Microsoft Azure](deploy-microsoft-365-directory-synchronization-dirsync-in-microsoft-azure.md)
