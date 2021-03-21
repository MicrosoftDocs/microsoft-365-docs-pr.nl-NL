---
title: Federatieverificatie met hoge beschikbaarheid Fase 1 Azure configureren
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 91266aac-4d00-4b5f-b424-86a1a837792c
description: 'Overzicht: Configureer de Microsoft Azure-infrastructuur om federatief hoge beschikbaarheid te hosten voor Microsoft 365.'
ms.openlocfilehash: 7f9a935648fedd2c6235c443f7398f97c0a06e06
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929106"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a>Federatief hoge beschikbaarheid fase 1: Azure configureren

In deze fase maakt u de resourcegroepen, virtuele netwerken (VNet) en beschikbaarheidssets in Azure die de virtuele machines hosten in fasen 2, 3 en 4. U moet deze fase voltooien voordat u verder gaat [met fase 2: Domeincontrollers configureren.](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) Zie [Federatieverificatie met hoge beschikbaarheid implementeren voor Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) voor alle fasen.
  
Azure moet zijn ingericht met deze basisonderdelen:
  
- Resourcegroepen
    
- Een cross-premises Azure Virtual Network (VNet) met subnetten voor het hosten van de Virtuele Azure-machines
    
- Netwerkbeveiligingsgroepen voor het uitvoeren van subnetisolatie
    
- Beschikbaarheidssets
    
## <a name="configure-azure-components"></a>Azure-onderdelen configureren

Voordat u Begint met het configureren van Azure-onderdelen, vult u de volgende tabellen in. Als u wilt helpen bij de procedures voor het configureren van Azure, print u deze sectie af en noteert u de benodigde informatie of kopieert u deze sectie naar een document en vult u deze in. Vul tabel V in voor de instellingen van het VNet.
  
|**Item**|**Configuratie-instelling**|**Beschrijving**|**Value**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |VNet-naam  <br/> |Een naam die u wilt toewijzen aan het VNet (bijvoorbeeld FedAuthNet).  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |VNet-locatie  <br/> |Het regionale Azure-datacenter dat het virtuele netwerk zal bevatten.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |IP-adres VPN-apparaat  <br/> |Het openbare IPv4-adres van de interface van uw VPN-apparaat op internet.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |VNet-adresruimte  <br/> |De adresruimte voor het virtuele netwerk. Werk samen met uw IT-afdeling om deze adresruimte te bepalen.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |Gedeelde IPsec-sleutel  <br/> |Een willekeurige, alfanumerieke tekenreeks van 32 tekens die wordt gebruikt om beide zijden van de SITE-naar-site VPN-verbinding te verifiëren. Werk samen met uw IT- of beveiligingsafdeling om deze sleutelwaarde te bepalen. Zie Een willekeurige tekenreeks maken voor een vooraf gedeelde [IPsec-toets.](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabel V: Configuratie van een virtueel netwerk met een cross-premises locatie**
  
Vul vervolgens tabel S in voor de subnetten van deze oplossing. Alle adressaties moeten de indeling Classless Interdomain Routing (CIDR) hebben, ook wel bekend als netwerkprefixnotatie. Een voorbeeld is 10.24.64.0/20.
  
Geef voor de eerste drie subnetten een naam en één IP-adresruimte op op basis van de virtuele netwerkadresruimte. Voor het gateway-subnet bepaalt u de 27-bits adresruimte (met een lengte van /27) voor het Azure Gateway-subnet met de volgende opties:
  
1. Stel de variabele bits in de adresruimte van het VNet in op 1, tot de bits die worden gebruikt door het gateway subnet en stel vervolgens de resterende bits in op 0.
    
2. Converteert de resulterende bits naar decimaal en druk deze uit als een adresruimte met de lengte van het voorvoegsel ingesteld op de grootte van het gateway-subnet.
    
Zie [Adresruimteberekening voor Azure Gateway-subnetten](address-space-calculator-for-azure-gateway-subnets.md) voor een PowerShell-opdrachtblok en C# of Python-consoletoepassing die deze berekening voor u uitvoert.
  
Werk samen met uw IT-afdeling om deze adresruimten te bepalen vanuit de virtuele netwerkadresruimte.
  
|**Item**|**Subnetnaam**|**Subnetadresruimte**|**Doel**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |Het subnet dat wordt gebruikt door de Ad DS-domeincontroller (Active Directory Domain Services) en virtuele adreslijstsynchronisatieserver virtuele machines (VM's).  <br/> |
|2.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |Het subnet dat wordt gebruikt door de AD FS-VM's.  <br/> |
|3.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |Het subnet dat wordt gebruikt door de proxy-VM's van de webtoepassing.  <br/> |
|4.  <br/> |GatewaySubnet  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |Het subnet dat wordt gebruikt door de Azure Gateway VM's.  <br/> |
   
 **Tabel S: Subnetten in het virtuele netwerk**
  
Vul vervolgens tabel I in voor de statische IP-adressen die zijn toegewezen aan virtuele machines en load balancer-exemplaren.
  
|**Item**|**Doel**|**IP-adres op het subnet**|**Value**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Statisch IP-adres van de eerste domeincontroller  <br/> |Het vierde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 1 van tabel S.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |Statisch IP-adres van de tweede domeincontroller  <br/> |Het vijfde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 1 van tabel S.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Statisch IP-adres van de adreslijstsynchronisatieserver  <br/> |Het zesde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 1 van tabel S.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |Statisch IP-adres van de interne load balancer voor de AD FS-servers  <br/> |Het vierde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 2 van tabel S.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |Statisch IP-adres van de eerste AD FS-server  <br/> |Het vijfde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 2 van tabel S.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|6.  <br/> |Statisch IP-adres van de tweede AD FS-server  <br/> |Het zesde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 2 van tabel S.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|7.  <br/> |Statisch IP-adres van de eerste proxyserver voor webtoepassing  <br/> |Het vierde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 3 van tabel S.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|8.  <br/> |Statisch IP-adres van de tweede proxyserver voor webtoepassing  <br/> |Het vijfde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 3 van tabel S.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabel I: Statische IP-adressen in het virtuele netwerk**
  
Voor twee DNS-servers (Domain Name System) in uw on-premises netwerk die u wilt gebruiken bij het instellen van de domeincontrollers in uw virtuele netwerk, vult u tabel D in. Werk samen met uw IT-afdeling om deze lijst te bepalen.
  
|**Item**|**NAAM VAN DNS-servervriendelijke naam**|**IP-adres dns-server**|
|:-----|:-----|:-----|
|1.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabel D: On-premises DNS-servers**
  
Als u pakketten van het cross-premises netwerk naar uw organisatienetwerk wilt doorverplaatsen via de SITE-naar-site VPN-verbinding, moet u het virtuele netwerk configureren met een lokaal netwerk met een lijst met de adressaties (in CIDR-notatie) voor alle bereikbare locaties in het on-premises netwerk van uw organisatie. De lijst met adresruimten die uw lokale netwerk definiëren, moet uniek zijn en mag niet overlappen met de adresruimte die wordt gebruikt voor andere virtuele netwerken of andere lokale netwerken.
  
Vul tabel L in voor de set lokale netwerkadressen. Houd er rekening mee dat er drie lege items worden weergegeven, maar dat u meestal meer nodig hebt. Werk samen met uw IT-afdeling om deze lijst met adressruimten te bepalen.
  
|**Item**|**Lokale netwerkadresruimte**|
|:-----|:-----|
|1.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabel L: Adres voorvoegsels voor het lokale netwerk**
  
Laten we nu beginnen met het bouwen van de Azure-infrastructuur om uw federatiele verificatie voor Microsoft 365 te hosten.
  
> [!NOTE]
> Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt. Zie [Aan de slag met Azure PowerShell](/powershell/azure/get-started-azureps). 
  
Start eerst een Azure PowerShell-prompt en meld u aan bij uw account.
  
```powershell
Connect-AzAccount
```

> [!TIP]
> Als u kant-en-klaar PowerShell-opdrachtblokken wilt genereren op basis van uw aangepaste instellingen, gebruikt u deze [Configuratiewerkboek van Microsoft Excel.](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx) 

Haal de naam van uw abonnement op met de volgende opdracht.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Gebruik deze opdracht voor oudere versies van Azure PowerShell.
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

Stel uw Azure-abonnement in. Vervang alles binnen de aanhalingstekens, inclusief de \< and >-tekens, met de juiste naam.
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

Maak vervolgens de nieuwe resourcegroepen. Als u een unieke set namen van resourcegroepen wilt bepalen, gebruikt u deze opdracht om uw bestaande resourcegroepen op te geven.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Vul de volgende tabel in voor de set unieke resourcegroepnamen.
  
|**Item**|**Naam van resourcegroep**|**Doel**|
|:-----|:-----|:-----|
|1.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |Domeincontrollers  <br/> |
|2.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |AD FS-servers  <br/> |
|3.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |Proxyservers voor webtoepassing  <br/> |
|4.  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |Infrastructuurelementen  <br/> |
   
 **Tabel R: Resourcegroepen**
  
Maak uw nieuwe resourcegroepen met deze opdrachten.
  
```powershell
$locName="<an Azure location, such as West US>"
$rgName="<Table R - Item 1 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 2 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 3 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 4 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Vervolgens maakt u het virtuele Azure-netwerk en de subnetten.
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
# Get the shortened version of the location
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the subnets
$subnet1Name="<Table S - Item 1 - Subnet name column>"
$subnet1Prefix="<Table S - Item 1 - Subnet address space column>"
$subnet1=New-AzVirtualNetworkSubnetConfig -Name $subnet1Name -AddressPrefix $subnet1Prefix
$subnet2Name="<Table S - Item 2 - Subnet name column>"
$subnet2Prefix="<Table S - Item 2 - Subnet address space column>"
$subnet2=New-AzVirtualNetworkSubnetConfig -Name $subnet2Name -AddressPrefix $subnet2Prefix
$subnet3Name="<Table S - Item 3 - Subnet name column>"
$subnet3Prefix="<Table S - Item 3 - Subnet address space column>"
$subnet3=New-AzVirtualNetworkSubnetConfig -Name $subnet3Name -AddressPrefix $subnet3Prefix
$gwSubnet4Prefix="<Table S - Item 4 - Subnet address space column>"
$gwSubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnet4Prefix

# Create the virtual network
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gwSubnet,$subnet1,$subnet2,$subnet3 -DNSServer $dnsServers

```

Vervolgens maakt u netwerkbeveiligingsgroepen voor elk subnet dat virtuele machines heeft. Als u subnetisolatie wilt uitvoeren, kunt u regels toevoegen voor de specifieke typen verkeer die zijn toegestaan of geweigerd aan de netwerkbeveiligingsgroep van een subnet.
  
```powershell
# Create network security groups
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName

New-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet1Name -AddressPrefix $subnet1Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet2Name -AddressPrefix $subnet2Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet3Name -AddressPrefix $subnet3Prefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

Gebruik vervolgens deze opdrachten om de gateways te maken voor de SITE-naar-site VPN-verbinding.
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "GatewaySubnet"

# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -Subnet $subnet

# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig

# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix

# Define the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway

```

> [!NOTE]
> Federatief verificatie van afzonderlijke gebruikers is niet afhankelijk van on-premises bronnen. Als deze SITE-naar-site VPN-verbinding echter niet beschikbaar wordt, ontvangen de domeincontrollers in het VNet geen updates voor gebruikersaccounts en groepen die zijn gemaakt in de on-premises Active Directory Domain Services. Om ervoor te zorgen dat dit niet gebeurt, kunt u een hoge beschikbaarheid configureren voor uw SITE-naar-site VPN-verbinding. Zie Zeer beschikbare [cross-premises en VNet-to-VNet-connectiviteit](/azure/vpn-gateway/vpn-gateway-highlyavailable) voor meer informatie.
  
Neem vervolgens het openbare IPv4-adres van de Azure VPN-gateway voor uw virtuele netwerk op via de weergave van deze opdracht:
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

Configureer vervolgens uw on-premises VPN-apparaat om verbinding te maken met de Azure VPN-gateway. Zie Uw [VPN-apparaat configureren voor meer informatie.](/azure/vpn-gateway/vpn-gateway-about-vpn-devices)
  
Als u uw on-premises VPN-apparaat wilt configureren, hebt u het volgende nodig:
  
- Het openbare IPv4-adres van de Azure VPN-gateway.
    
- De vooraf gedeelde IPsec-sleutel voor de SITE-naar-site VPN-verbinding (Tabel V - Item 5 - kolom Waarde).
    
Controleer vervolgens of de adresruimte van het virtuele netwerk bereikbaar is vanuit uw on-premises netwerk. Dit wordt meestal gedaan door een route toe te voegen die overeenkomt met de virtuele netwerkadresruimte aan uw VPN-apparaat en vervolgens reclame te maken voor die route naar de rest van de routeringsinfrastructuur van uw organisatienetwerk. Werk samen met uw IT-afdeling om te bepalen hoe u dit doet.
  
Definieer vervolgens de namen van drie beschikbaarheidssets. Vul tabel A in. 
  
|**Item**|**Doel**|**Naam van beschikbaarheidsset**|
|:-----|:-----|:-----|
|1.  <br/> |Domeincontrollers  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |AD FS-servers  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Proxyservers voor webtoepassing  <br/> |![regel](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabel A: Beschikbaarheidssets**
  
U hebt deze namen nodig wanneer u de virtuele machines maakt in fasen 2, 3 en 4.
  
Maak de nieuwe beschikbaarheidssets met deze Azure PowerShell-opdrachten.
  
```powershell
$locName="<the Azure location for your new resource group>"
$rgName="<Table R - Item 1 - Resource group name column>"
$avName="<Table A - Item 1 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 2 - Resource group name column>"
$avName="<Table A - Item 2 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 3 - Resource group name column>"
$avName="<Table A - Item 3 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
```

Dit is de configuratie die het resultaat is van de succesvolle voltooiing van deze fase.
  
**Fase 1: De Azure-infrastructuur voor federatief hoge beschikbaarheid voor Microsoft 365**

![Fase 1 van de hoge beschikbaarheid van Microsoft 365 federatieverificatie in Azure met de Azure-infrastructuur](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a>Volgende stap

Fase [2 gebruiken: Domeincontrollers configureren](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) om door te gaan met de configuratie van deze werkbelasting.
  
## <a name="see-also"></a>Zie ook

[Federatieverificatie met hoge beschikbaarheid implementeren voor Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federatief identiteit voor uw Microsoft 365-dev/testomgeving](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365-oplossings- en -architectuurcentrum](../solutions/index.yml)

[Microsoft 365-identiteit en Azure Active Directory begrijpen](about-microsoft-365-identity.md)