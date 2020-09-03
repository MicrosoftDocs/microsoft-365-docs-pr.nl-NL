---
title: Federatieve authenticatiefase 1 voor hoge beschikbaarheid 1 Azure configureren
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
description: 'Overzicht: Configureer de Microsoft Azure-infrastructuur voor het hosten van hoge beschikbaarheid federatieve authenticatie voor Microsoft 365.'
ms.openlocfilehash: d2a9fe3c31468cd53576a82639e0e61901192d8e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332338"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a>Federatieve authenticatiefase van hoge beschikbaarheid 1: Azure configureren

In deze fase maakt u de resourcegroepen, virtuele netwerk (VNet) en beschikbaarheidssets in azure waarmee de virtuele machines worden gehost in de fasen 2, 3 en 4. U moet deze fase voltooien voordat u overstapt op [fase 2: domeincontrollers configureren](high-availability-federated-authentication-phase-2-configure-domain-controllers.md). Zie [federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) voor alle fasen.
  
Azure moet worden ingericht met de volgende basiscomponenten:
  
- Resource groepen
    
- Een cross-premises Azure Virtual Network (VNet) met subnetten voor het hosten van de virtuele machines van Azure
    
- Netwerkbeveiligingsgroepen voor het uitvoeren van subnet-isolatie
    
- Beschikbaarheidssets
    
## <a name="configure-azure-components"></a>Azure-onderdelen configureren

Vul de volgende tabellen in voordat u de onderdelen van Azure gaat configureren. Om u te helpen bij het configureren van Azure, moet u dit gedeelte afdrukken en de benodigde informatie noteren of de benodigde informatie naar een document kopiëren en deze sectie invullen. Voor de instellingen van het VNet vult u tabel V in.
  
|**Item**|**Configuratie-instelling**|**Beschrijving**|**Value**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |VNet-naam  <br/> |Een naam die moet worden toegewezen aan de VNet (bijvoorbeeld FedAuthNet).  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |VNet-locatie  <br/> |Het regionale Azure-datacenter dat het virtuele netwerk omvat.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |IP-adres voor VPN-apparaat  <br/> |Het openbare IPv4-adres van de interface van uw VPN-apparaat op internet.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |VNet-adresruimte  <br/> |De adresruimte voor het virtuele netwerk. Werk samen met uw IT-afdeling om deze adresruimte te bepalen.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |Gedeelde IPsec-sleutel  <br/> |32 een willekeurige alfanumerieke tekenreeks die wordt gebruikt voor de verificatie van beide zijden van de VPN-verbinding tussen sites. Werk samen met uw IT-of beveiligingsafdeling om deze sleutelwaarde te bepalen. U kunt ook [een willekeurige tekenreeks maken voor een met IPSec vooraf gedeelde sleutel](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabel V: virtuele netwerkconfiguratie van cross-premises**
  
Vul vervolgens tabel S in voor de subnetten van deze oplossing. Alle adresruimten moeten in de bewerkings indeling van een Klasloze interdomein-indeling staan, ook wel wel netwerkvoorvoegsel-indeling genoemd. Een voorbeeld is 10.24.64.0/20.
  
Voor de eerste drie subnetten geeft u een naam en een enkele IP-adresruimte op op basis van de adresruimte van het virtuele netwerk. Voor het gateway-subnet bepaalt u de 27-bits adresruimte (met een/27 prefixlengte) voor het Azure gateway-subnet met de volgende opties:
  
1. Stel de variabele bits in de adresruimte van de VNet in op 1, tot de gebruikte bits in de gateway-subnet en stel de resterende bits in op 0.
    
2. Zet de resultaten van de omliggende bits om in decimalen en druk deze als een adresruimte met de lengte van het voorvoegsel in op de grootte van het gateway subnet.
    
Zie de Adresboek tijdtoren [voor Azure gateway-subnetten](address-space-calculator-for-azure-gateway-subnets.md) voor een PowerShell-opdrachten blok en C#-of python-consoletoepassing waarmee deze berekening wordt uitgevoerd.
  
Werk samen met uw IT-afdeling om te bepalen welke adresruimten de virtuele netwerklocatie van het adres heeft.
  
|**Item**|**Naam van subnet**|**Adresruimte van subnet**|**Doel**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |Het subnet dat wordt gebruikt door de domeincontroller voor Active Directory Domain Services (AD DS) van Active Directory Domain Services en adreslijstsynchronisatie servers (VMs).  <br/> |
|2.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |Het subnet dat wordt gebruikt door de AD FS-Vm's.  <br/> |
|3.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |Het subnet dat wordt gebruikt door de Vm's van webtoepassingsproxy.  <br/> |
|4.  <br/> |GatewaySubnet  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |Het subnet dat wordt gebruikt door de Azure gateway-VMs.  <br/> |
   
 **Tabel S: subnetten in het virtuele netwerk**
  
Vul vervolgens tabel I in voor de statische IP-adressen die zijn toegewezen aan virtuele machines en Load Balancer-exemplaren.
  
|**Item**|**Doel**|**IP-adres in het subnet**|**Value**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Statisch IP-adres van de eerste domeincontroller  <br/> |Het vierde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 1 van tabel S.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |Statisch IP-adres van de tweede domeincontroller  <br/> |Het vijfde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 1 van tabel S.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Statisch IP-adres van de adreslijstsynchronisatie server  <br/> |Het zesde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 1 van tabel S.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|4.  <br/> |Statisch IP-adres van de interne Load Balancer voor de AD FS-servers  <br/> |Het vierde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 2 van tabel S.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|5.  <br/> |Statisch IP-adres van de eerste AD FS-server  <br/> |Het vijfde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 2 van tabel S.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|zes.  <br/> |Statisch IP-adres van de tweede AD FS-server  <br/> |Het zesde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in item 2 van tabel S.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|7,5.  <br/> |Statisch IP-adres van de eerste proxyserver voor webtoepassingen  <br/> |Het vierde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in artikel 3 van tabel S.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|8:00.  <br/> |Statisch IP-adres van de tweede server van de webtoepassingsproxy  <br/> |Het vijfde mogelijke IP-adres voor de adresruimte van het subnet dat is gedefinieerd in artikel 3 van tabel S.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
   
 **Table I: statische IP-adressen in het virtuele netwerk**
  
Voor twee DNS-servers (Domain Name System) in het on-premises netwerk dat u wilt gebruiken bij het instellen van de domeincontrollers in uw virtuele netwerk, vult u de tabel D in en werkt u met uw IT-afdeling voor het bepalen van deze lijst.
  
|**Item**|**Beschrijvende naam van de DNS-server**|**IP-adres van de DNS-server**|
|:-----|:-----|:-----|
|1.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabel D: on-premises DNS-servers**
  
Als u pakketten van het cross-premises netwerk naar het netwerk van uw organisatie wilt routeren tussen de site-to-site VPN-verbinding, moet u het virtuele netwerk configureren met een lokaal netwerk met een lijst met de adresruimten (in CIDR-notatie) voor alle bereikbare locaties in het on-premises netwerk van uw organisatie. De lijst met adresruimten die uw lokale netwerk definiëren, moet uniek zijn en mag niet overlappen met de adresruimte die wordt gebruikt voor andere virtuele netwerken of andere lokale netwerken.
  
Voor de set lokale netwerkadres ruimten, vult u tabel L in. Merk op dat er wel drie lege vermeldingen worden weergegeven, maar u hebt meestal meer nodig. Werk samen met uw IT-afdeling om deze lijst met adresruimten te bepalen.
  
|**Item**|**Lokale netwerkadres ruimte**|
|:-----|:-----|
|1.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabel L: adresprefixen voor het lokale netwerk**
  
We gaan nu beginnen met de totstandbrenging van de Azure-infrastructuur om uw federatieve verificatie voor Microsoft 365 te hosten.
  
> [!NOTE]
> Met de volgende opdrachtsets wordt de meest recente versie van Azure PowerShell gebruikt. Zie [aan de slag met Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps). 
  
Start eerst een Azure PowerShell-prompt en meld u aan bij uw account.
  
```powershell
Connect-AzAccount
```

> [!TIP]
> Als u kant-en-klare PowerShell-opdrachten blokken wilt genereren op basis van uw aangepaste instellingen, gebruikt u deze [Microsoft Excel-configuratie werkmap](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx). 

Haal de naam van uw abonnement op met de volgende opdracht.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Voor oudere versies van Azure PowerShell gebruikt u deze opdracht.
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

Stel uw Azure-abonnement in. Vervang alles binnen de aanhalingstekens, inclusief de \< and >-tekens, met de juiste naam.
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

Vervolgens maakt u de nieuwe resourcegroepen. Als u een unieke reeksnamen voor de resourcegroepen wilt bepalen, gebruikt u deze opdracht om een lijst met de bestaande resourcegroepen weer te geven.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Vul de volgende tabel in voor de namen van de afzonderlijke resourcegroepen.
  
|**Item**|**Naam van resource groep**|**Doel**|
|:-----|:-----|:-----|
|1.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |Domeincontrollers  <br/> |
|2.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |AD FS-servers  <br/> |
|3.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |Webtoepassingsproxy-servers  <br/> |
|4.  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |Infrastructuur elementen  <br/> |
   
 **Tabel R: resource groepen**
  
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

Vervolgens maakt u het virtuele virtuele netwerk van Azure en de subnetten hiervan.
  
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

Vervolgens maakt u netwerkbeveiligingsgroepen voor elk subnet met virtuele machines. Als u de isolatie van subnet wilt uitvoeren, kunt u regels toevoegen voor de specifieke typen verkeer die zijn toegestaan of geweigerd voor de netwerkbeveiligingsgroep van een subnet.
  
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

Vervolgens kunt u deze opdrachten gebruiken om de gateways voor de site-to-site VPN-verbinding te maken.
  
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
> Federatieve verificatie van afzonderlijke gebruikers is niet afhankelijk van lokale on-premises resources. Als deze site-naar-site-VPN-verbinding echter niet beschikbaar is, ontvangen de domeincontrollers in de VNet geen updates voor gebruikersaccounts en groepen die zijn gemaakt in de on-premises Active Directory Domain Services. U kunt dit voorkomen door de hoge beschikbaarheid van uw site-tot-site VPN-verbinding te configureren. Zie [uiterst beschikbare cross-premises en vnet-to-VNet-verbinding](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable) voor meer informatie.
  
Neem vervolgens de openbare IPv4-adressen van de Azure VPN-gateway voor uw virtuele netwerk op bij de weergave van deze opdracht:
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

Configureer vervolgens uw on-premises VPN-apparaat om verbinding te maken met de Azure VPN-gateway. Zie [uw VPN-apparaat configureren](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices)voor meer informatie.
  
Als u uw on-premises VPN-apparaat wilt configureren, hebt u het volgende nodig:
  
- Het openbare IPv4-adres van de Azure VPN-gateway.
    
- De vooraf gedeelde sleutel van IPsec voor de site-to-site VPN-verbinding (tabel V-artikel met een waarde van 5 kolommen).
    
Zorg er vervolgens voor dat de adresruimte van het virtuele netwerk bereikbaar is vanaf uw on-premises netwerk. Dit gebeurt meestal door een route die correspondeert met de adresruimte van het virtuele netwerk, toe te voegen aan uw VPN-apparaat en vervolgens aan te kondigen dat routering naar de rest van de routeringsinfrastructuur van het netwerk van uw organisatie. Werk samen met uw IT-afdeling om te bepalen hoe u dit moet doen.
  
Vervolgens definieert u de namen van drie beschikbare sets. Vul tabel A in. 
  
|**Item**|**Doel**|**Naam van beschikbaarheidsset**|
|:-----|:-----|:-----|
|1.  <br/> |Domeincontrollers  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|2.  <br/> |AD FS-servers  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
|3.  <br/> |Webtoepassingsproxy-servers  <br/> |![Bovenlijn](../media/Common-Images/TableLine.png)  <br/> |
   
 **Tabel A: beschikbaarheidssets**
  
U hebt deze namen nodig wanneer u de virtuele machines maakt in de fasen 2, 3 en 4.
  
Maak de nieuwe beschikbaarheidssets met deze opdrachten van Azure PowerShell.
  
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
  
**Fase 1: de Azure-infrastructuur voor federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365**

![Fase 1 van de High Availability Microsoft 365 federatieve authenticatie in azure met de Azure-infrastructuur](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a>Volgende stap

Gebruik [fase 2: configureer domeincontrollers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) om door te gaan met de configuratie van deze werkbelasting.
  
## <a name="see-also"></a>Zie ook

[Federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Federatieve identiteit voor uw Microsoft 365 dev/testomgeving](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Microsoft 365-oplossings- en architectuurcentrum](../solutions/solution-architecture-center.md)

[Informatie over Microsoft 365 identiteit en Azure Active Directory](about-microsoft-365-identity.md)


