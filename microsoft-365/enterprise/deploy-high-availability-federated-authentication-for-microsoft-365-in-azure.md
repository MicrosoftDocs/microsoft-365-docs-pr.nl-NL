---
title: Federatieverificatie met hoge beschikbaarheid implementeren voor Microsoft 365 in Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150s
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
ms.assetid: 34b1ab9c-814c-434d-8fd0-e5a82cd9bff6
description: 'Overzicht: Configureer federatief hoge beschikbaarheidsverificatie voor uw Microsoft 365 abonnement in Microsoft Azure.'
ms.openlocfilehash: 3989ebb06b4ac5dfa1cded5e07c086c4778f94e7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919150"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a>Federatieverificatie met hoge beschikbaarheid implementeren voor Microsoft 365 in Azure

Dit artikel bevat koppelingen naar de stapsgewijs instructies voor het implementeren van federatieverificatie met hoge beschikbaarheid voor Microsoft-Microsoft 365 in Azure-infrastructuurservices met deze virtuele machines:
  
- Twee proxyservers voor webtoepassing
    
- Twee Ad FS-servers (Active Directory Federation Services)
    
- Twee replicadomeincontrollers
    
- Eén adreslijstsynchronisatieserver met Azure AD-Verbinding maken
    
Hier is de configuratie, met namen van tijdelijke aanduidingen voor elke server.
  
**Een federatief hoge beschikbaarheid van verificatie voor Microsoft 365-infrastructuur in Azure**

![De uiteindelijke configuratie van de hoge beschikbaarheid Microsoft 365 federatief verificatie-infrastructuur in Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
Alle virtuele machines maken deel uit van één lokaal virtueel Azure-netwerk (VNet). 
  
> [!NOTE]
> Federatief verificatie van afzonderlijke gebruikers is niet afhankelijk van on-premises bronnen. Als de cross-premises verbinding echter niet beschikbaar wordt, ontvangen de domeincontrollers in het VNet geen updates voor gebruikersaccounts en groepen die zijn gemaakt in de on-premises Active Directory Domain Services (AD DS). Om ervoor te zorgen dat dit niet gebeurt, kunt u een hoge beschikbaarheid configureren voor uw cross-premises verbinding. Zie Zeer beschikbare [cross-premises en VNet-to-VNet-connectiviteit](/azure/vpn-gateway/vpn-gateway-highlyavailable) voor meer informatie.
  
Elk paar virtuele machines voor een specifieke rol heeft een eigen subnet en beschikbaarheidsset.
  
> [!NOTE]
> Omdat dit VNet is verbonden met het on-premises netwerk, bevat deze configuratie geen jumpbox of het bewaken van virtuele machines op een beheerssubnet. Zie VM's uitvoeren [Windows N-laagarchitectuur](/azure/guidance/guidance-compute-n-tier-vm)voor meer informatie. 
  
Het resultaat van deze configuratie is dat u federatief verificatie hebt voor al uw Microsoft 365-gebruikers, waarin ze hun AD DS-referenties kunnen gebruiken om zich aan te melden in plaats van hun Microsoft 365 account. De federatief verificatie-infrastructuur maakt gebruik van een redundante set servers die gemakkelijker kunnen worden geïmplementeerd in Azure-infrastructuurservices, in plaats van in uw on-premises edge-netwerk.
  
## <a name="bill-of-materials"></a>Factuur van materialen

Voor deze basislijnconfiguratie is de volgende set Azure-services en -onderdelen vereist:
  
- Zeven virtuele machines
    
- Eén cross-premises virtueel netwerk met vier subnetten
    
- Vier resourcegroepen
    
- Drie beschikbaarheidssets
    
- Eén Azure-abonnement
    
Hier zijn de virtuele machines en de standaardgrootten voor deze configuratie.
  
|**Item**|**Beschrijving van virtuele machine**|**Afbeelding van azuregalerie**|**Standaardgrootte**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Eerste domeincontroller  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|2.  <br/> |Tweede domeincontroller  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|3.  <br/> |Azure AD Verbinding maken server  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|4.  <br/> |Eerste AD FS-server  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|5.  <br/> |Tweede AD FS-server  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|6.  <br/> |Eerste proxyserver voor webtoepassing  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|7.  <br/> |Tweede proxyserver voor webtoepassing  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
   
Als u de geschatte kosten voor deze configuratie wilt berekenen, bekijkt u de [Azure-prijsberekening](https://azure.microsoft.com/pricing/calculator/)
  
## <a name="phases-of-deployment"></a>Implementatiefasen

U implementeert deze werkbelasting in de volgende fasen:
  
- [Fase 1: Azure configureren.](high-availability-federated-authentication-phase-1-configure-azure.md) Maak resourcegroepen, opslagaccounts, beschikbaarheidssets en een cross-premises virtueel netwerk.
    
- [Fase 2: Domeincontrollers configureren.](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) Maak en configureer replica AD DS-domeincontrollers en de adreslijstsynchronisatieserver.
    
- [Fase 3: AD FS-servers configureren.](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) Maak en configureer de twee AD FS-servers.
    
- [Fase 4: Webtoepassingsproxies configureren.](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) De twee proxyservers voor webtoepassing maken en configureren.
    
- [Fase 5: Federatief verificatie configureren voor Microsoft 365.](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) Federatief verificatie configureren voor uw Microsoft 365 abonnement.
    
Deze artikelen bevatten een prescriptieve, fase-voor-fase-handleiding voor een vooraf gedefinieerde architectuur om een functionele federatieve verificatie met hoge beschikbaarheid te maken voor Microsoft 365 in Azure-infrastructuurservices. Houd het volgende in gedachten:
  
- Als u een ervaren AD FS-implementer bent, kunt u de instructies in fasen 3 en 4 aanpassen en de set servers maken die het beste bij uw behoeften passen.
    
- Als u al een bestaande hybride Azure-cloudimplementatie met een bestaand cross-premises virtueel netwerk hebt, kunt u de instructies in fasen 1 en 2 aanpassen of overslaan en de proxyservers voor AD FS en webtoepassing op de juiste subnetten plaatsen.
    
Als u een dev/testomgeving of een proof-of-concept van deze configuratie wilt maken, zie Federatief identiteit voor uw [Microsoft 365 v/testomgeving.](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
## <a name="next-step"></a>Volgende stap

Start de configuratie van deze werkbelasting met [Fase 1: Azure configureren.](high-availability-federated-authentication-phase-1-configure-azure.md) 
