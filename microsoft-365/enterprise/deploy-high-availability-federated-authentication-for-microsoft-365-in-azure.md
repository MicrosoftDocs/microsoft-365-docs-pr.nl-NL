---
title: Federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure
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
description: 'Overzicht: Configureer federatieve authenticatie van hoge beschikbaarheid voor uw Microsoft 365-abonnement in Microsoft Azure.'
ms.openlocfilehash: abe01445b8963dcdc5693b45a680e273f5084446
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689315"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a>Federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure

Dit artikel bevat koppelingen naar de stapsgewijze instructies voor de implementatie van federatieve authenticatie van hoge beschikbaarheid voor Microsoft Microsoft 365 in azure-infrastructuurservices met deze virtuele machines:
  
- Twee toepassingen voor webtoepassingsproxy
    
- Twee servers met Active Directory Federation Services (AD FS)
    
- Twee replica domeincontrollers
    
- Eén adreslijstsynchronisatie server met Azure AD Connect
    
De configuratie bevat de naam van een tijdelijke aanduiding voor elke server.
  
**Een federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365-infrastructuur in azure**

![De laatste configuratie van de High Availability Microsoft 365 federatieve verificatie-infrastructuur in azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
Alle virtuele machines bevinden zich in één cross-premises Azure Virtual Network (VNet). 
  
> [!NOTE]
> Federatieve verificatie van afzonderlijke gebruikers is niet afhankelijk van lokale on-premises resources. Als de cross-premises verbinding echter niet meer beschikbaar is, ontvangen de domeincontrollers in de VNet geen updates voor gebruikersaccounts en groepen die zijn opgenomen in de on-premises Active Directory Domain Services (AD DS). U kunt ervoor zorgen dat dit niet gebeurt door de hoge beschikbaarheid van uw cross-premises verbinding te configureren. Zie [uiterst beschikbare cross-premises en vnet-to-VNet-verbinding](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable) voor meer informatie.
  
Elke reeks virtuele machines voor een bepaalde rol bevindt zich in zijn eigen subnet en de beschikbaarheid.
  
> [!NOTE]
> Aangezien dit VNet is verbonden met het on-premises netwerk, bevat deze configuratie geen JumpBox of virtuele machines op een management subnet. Zie [Windows Vm's uitvoeren voor een architectuur met een N-tier](https://docs.microsoft.com/azure/guidance/guidance-compute-n-tier-vm)voor meer informatie. 
  
Het resultaat van deze configuratie is dat u Federatie authenticatie onderneemt voor alle Microsoft 365-gebruikers, waarbij ze hun AD DS-referenties kunnen gebruiken om zich aan te melden in plaats van hun Microsoft 365-account. De federatieve verificatie-infrastructuur gebruikt een redundante set servers die eenvoudiger in azure-infrastructuurservices kunnen worden geïmplementeerd, in plaats van in het on-premises Edge-netwerk.
  
## <a name="bill-of-materials"></a>Stuklijsten

Voor deze basislijn configuratie is de volgende set Azure-Services en-onderdelen vereist:
  
- Zeven virtuele machines
    
- Eén cross-premises virtueel netwerk met vier subnetten
    
- Vier resourcegroepen
    
- Drie beschikbare sets
    
- Eén Azure-abonnement
    
Dit zijn de virtuele machines en de standaardformaten voor deze configuratie.
  
|**Item**|**Beschrijving van virtuele machine**|**Afbeelding van Azure-galerie**|**Standaardgrootte**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Eerste domeincontroller  <br/> |Windows Server 2016 datacenter  <br/> |Hetzelfde  <br/> |
|2.  <br/> |Tweede domeincontroller  <br/> |Windows Server 2016 datacenter  <br/> |Hetzelfde  <br/> |
|3.  <br/> |Azure AD Connect-server  <br/> |Windows Server 2016 datacenter  <br/> |Hetzelfde  <br/> |
|4.  <br/> |Eerste AD FS-server  <br/> |Windows Server 2016 datacenter  <br/> |Hetzelfde  <br/> |
|5.  <br/> |Tweede AD FS-server  <br/> |Windows Server 2016 datacenter  <br/> |Hetzelfde  <br/> |
|zes.  <br/> |Eerste proxyserver voor webtoepassingen  <br/> |Windows Server 2016 datacenter  <br/> |Hetzelfde  <br/> |
|7,5.  <br/> |Tweede toepassing voor webtoepassingsproxy  <br/> |Windows Server 2016 datacenter  <br/> |Hetzelfde  <br/> |
   
Als u de geraamde kosten voor deze configuratie wilt berekenen, raadpleegt u de [Azure tarief berekening](https://azure.microsoft.com/pricing/calculator/)
  
## <a name="phases-of-deployment"></a>Implementatiefasen

U voert de volgende stappen uit om deze werkbelasting te implementeren:
  
- [Fase 1: Azure configureren](high-availability-federated-authentication-phase-1-configure-azure.md). Maak bronnengroepen, opslagaccounts, beschikbaarheidssets en een virtueel netwerk voor cross-premises.
    
- [Fase 2: configureer domeincontrollers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md). Maak en configureer domeincontrollers voor de AD DS van de replica en de adreslijstsynchronisatie server.
    
- [Fase 3: AD FS-servers configureren](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md). De twee AD FS-servers maken en configureren.
    
- [Fase 4: proxy's voor webtoepassingen configureren](high-availability-federated-authentication-phase-4-configure-web-application-pro.md). Maak en configureer de twee webtoepassings proxyservers.
    
- [Fase 5: federatieve verificatie voor Microsoft 365 configureren](high-availability-federated-authentication-phase-5-configure-federated-authentic.md). Configureer federatieve verificatie voor uw Microsoft 365-abonnement.
    
In deze artikelen vindt u een uitgebreide, fase-phase handleiding voor een vooraf gedefinieerde architectuur voor het maken van een functionele, federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365 in azure-infrastructuurservices. Houd het volgende in gedachten:
  
- Als u een ervaring hebt met de implementatie van AD FS, kunt u de instructies in de fasen 3 en 4 aanpassen en de sets servers maken die het beste aansluit bij uw behoeften.
    
- Als u al een Azure Hybrid Cloud-implementatie met een bestaand cross-premises virtueel netwerk hebt, kunt u de instructies in de fase 1 en 2 overslaan en overslaan en de proxyservers voor de AD FS-en webtoepassingsproxy-toepassing op de juiste subnetten plaatsen.
    
Zie [federatieve identiteit voor uw Microsoft 365 dev/testomgeving](federated-identity-for-your-microsoft-365-dev-test-environment.md)als u een ontwikkelaar/testomgeving of een controle van het concept van deze configuratie wilt maken.
  
## <a name="next-step"></a>Volgende stap

Start de configuratie van deze werkbelasting met [fase 1: Azure configureren](high-availability-federated-authentication-phase-1-configure-azure.md). 
  
