---
title: Microsoft Azure architecturen voor SharePoint 2013
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
- seo-marvel-apr2020
ms.assetid: 98fc1006-9399-4ff0-a216-c7c05820d822
description: Meer informatie over welke typen SharePoint 2013-oplossingen u kunt hosten op Microsoft Azure virtuele machines en hoe u Azure instelt voor een host.
ms.openlocfilehash: 37d7eb2a746e30ad560949a933783beb6b971a08
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695769"
---
# <a name="microsoft-azure-architectures-for-sharepoint-2013"></a>Microsoft Azure architecturen voor SharePoint 2013

Azure is een goede omgeving voor het hosten van een oplossing van SharePoint Server 2013. In de meeste gevallen is het raadzaam Microsoft 365 te gebruiken, maar een SharePoint server-farm die wordt gehost in azure, kan een goede optie zijn voor specifieke oplossingen. In dit artikel wordt uitgelegd hoe u SharePoint-oplossingen adviseert, zodat deze geschikt zijn voor het Azure-platform. In dit voorbeeld worden de volgende twee specifieke oplossingen gebruikt:
  
- [Herstel na herstel van SharePoint Server 2013 in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)
    
- [Internet sites in Microsoft Azure met behulp van SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
    
## <a name="recommended-sharepoint-solutions-for-azure-infrastructure-services"></a>Aanbevolen SharePoint-oplossingen voor Azure-infrastructuur services

Azure-infrastructuurservices is een boeiende optie voor het hosten van SharePoint-oplossingen. Sommige oplossingen zijn beter geschikt voor dit platform dan andere oplossingen. De volgende tabel bevat aanbevolen oplossingen.
  
|**Oplossing**|**Waarom deze oplossing wordt aanbevolen voor Azure**|
|:-----|:-----|
|Omgevingen ontwikkelen en testen  <br/> |Het is gemakkelijk om deze omgevingen te maken en te beheren.  <br/> |
|Noodherstel van on-premises SharePoint Farms naar Azure  <br/> |**Gehoste secundaire datacenter** Gebruik Azure in plaats van investeren in een tweede datacenter in een andere regio. <br/> **Omgevingen met een voordelig Herstelomgeving voor noodgevallen** Minder resources bewaren en betalen in plaats van een on-premises Herstelomgeving voor noodgevallen. Het aantal bronnen is afhankelijk van de noodherstel omgeving die u kiest: koude stand, warme stand of hot standby. <br/> **Meer Elastic platform** Wanneer een ramp een ramp doet, kunt u eenvoudig de SharePoint-farm voor herstel schalen om te voldoen aan de laad vereisten. Als u de bronnen niet meer nodig hebt, kunt u deze aanpassen. <br/> Zie [herstel van SharePoint Server 2013 in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md).  <br/> |
|Sites op Internet die gebruikmaken van functies en schaal die niet beschikbaar zijn in Microsoft 365  <br/> |**Uw activiteiten richten** Richt zich op het gebouw van een fantastische site in plaats van een infrastructuur van gebouwen. <br/> Profiteren **van de elasticiteit in azure** Het formaat van de farm voor de vraag door nieuwe servers toe te voegen en alleen te betalen voor bronnen die u nodig hebt. Dynamische machine toewijzingen worden niet ondersteund (automatisch schalen). <br/> **Azure Active Directory (AD) gebruiken** Profiteer van Azure AD voor klant accounts. <br/> **SharePoint-functionaliteit toevoegen niet beschikbaar in Microsoft 365** Uitgebreide rapporten en Web Analytics toevoegen. <br/> Zie [Internet sites in Microsoft Azure met behulp van SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md).  <br/> |
|App-farms voor ondersteuning van Microsoft 365 of on-premises omgevingen  <br/> |U kunt apps in azure **samenstellen, testen en hosten** voor de ondersteuning van zowel on-premises als Cloud omgevingen. <br/> **Host deze rol** in Azure in plaats van nieuwe hardware te kopen voor on-premises omgevingen. <br/> |
   
Voor intranet-en samenwerkingsoplossingen en-werkbelasting kunt u de volgende opties overwegen:
  
- Bepalen of Microsoft 365 voldoet aan de vereisten van uw bedrijf of kan deelnemen aan de oplossing. Microsoft 365 biedt uitgebreide functiesets die altijd up-to-date is.
    
- Als Microsoft 365 niet aan al uw bedrijfsvereisten voldoet, kunt u een standaardimplementatie van SharePoint 2013 on-premises van Microsoft Consulting Services (MCS) overwegen. Een standaardarchitectuur kan een snellere, goedkopere en eenvoudiger oplossing zijn om ondersteuning te bieden voor een aangepast abonnement. 
    
- Als een standaardimplementatie niet aan uw bedrijfsvereisten voldoet, kunt u een aangepaste on-premises oplossing overwegen.
    
- Als het gebruik van een Cloud platform belangrijk is voor uw bedrijfsvereisten, moet u rekening houden met een standaard-of aangepaste implementatie van SharePoint 2013, gehost in azure Infrastructure Services. SharePoint-oplossingen zijn veel gemakkelijker te ondersteunen in azure dan andere niet-ingebouwde Microsoft Public Cloud-platformen.
    
## <a name="before-you-design-the-azure-environment"></a>Voordat u de Azure-omgeving ontwerpt

In dit artikel wordt gebruikgemaakt van voorbeelden van SharePoint-topologieën met een SharePoint-farmtopologie. Voordat u de Azure-omgeving ontwerpt, gebruikt u de volgende topologie, architectuur, capaciteit en prestatie-richtlijnen voor het ontwerpen van de SharePoint-farm:
  
- [Architectuurontwerp voor SharePoint 2013 IT-professionals](https://technet.microsoft.com/sharepoint/fp123594.aspx)
    
- [Plan voor prestaties en capaciteitsbeheer in SharePoint Server 2013](https://technet.microsoft.com/library/8dd52916-f77d-4444-b593-1f7d6f330e5f.aspx)
    
## <a name="determine-the-active-directory-domain-type"></a>Het Active Directory-domeintype bepalen

Elke SharePoint-server farm is afhankelijk van Active Directory voor het instellen van beheeraccounts voor de farmconfiguratie. Op dit moment zijn er twee opties voor SharePoint-oplossingen in Azure. Deze worden beschreven in de volgende tabel.
  
|**Optie**|**Beschrijving**|
|:-----|:-----|
|Toegewijd domein  <br/> |U kunt een toegewijd en geïsoleerd Active Directory-domein implementeren in azure om uw SharePoint-farm te ondersteunen. Dit is een goede optie voor openbare Internet sites.  <br/> |
|Het on-premises domein verlengen via een cross-premises verbinding  <br/> |Wanneer u het on-premises domein via een cross-premises verbinding verlengt, krijgen gebruikers toegang tot de SharePoint-farm via uw intranet alsof ze on-premises worden gehost. U kunt profiteren van uw on-premises Active Directory en DNS-implementatie.  <br/> Een cross-premises verbinding is vereist voor het maken van een noodherstel omgeving in azure zodat deze niet kan worden overgenomen van uw on-premises farm.  <br/> |
   
Dit artikel bevat ontwerp concepten voor het uitbreiden van het on-premises domein via een cross-premises verbinding. Als uw oplossing gebruikmaakt van een toegewijd domein, hebt u geen cross-premises verbinding nodig.
  
## <a name="design-the-virtual-network"></a>Het virtuele netwerk ontwerpen

Eerst hebt u een virtueel netwerk in azure nodig, waaronder de subnetten waarop u uw virtuele machines wilt plaatsen. Het virtuele netwerk heeft een persoonlijke IP-adresruimte nodig, waarvan de deel van de subnets aan de subnetten is toegewezen.
  
Als u uw on-premises netwerk verlengt via een cross-premises verbinding (vereist voor een Herstelomgeving voor noodgevallen), moet u een persoonlijke adresruimte kiezen die nog niet elders in het netwerk van uw organisatie wordt gebruikt, zoals uw on-premises omgeving en andere Azure VM-netwerken. 
  
**Afbeelding 1: on-premises omgeving met een virtueel netwerk in azure**

![Microsoft Azure Virtual Network-ontwerp voor een SharePoint-oplossing. Eén subnet voor de Azure gateway. Eén subnet voor de virtuele machines.](../media/OPrrasconWA-AZarch.png)
  
In dit diagram:
  
- Een virtueel netwerk in azure wordt weergegeven naast elkaar in de on-premises omgeving. De twee omgevingen zijn nog niet verbonden via een cross-premises verbinding, wat kan een VPN-verbinding voor site-naar-site zijn of ExpressRoute.
    
- Op dit moment bevat het virtuele netwerk alleen de subnetten en geen andere architecturale elementen. Eén subnet host de Azure gateway en andere subnetten host de lagen van de SharePoint-farm, met een extra voor Active Directory en DNS.
    
## <a name="add-cross-premises-connectivity"></a>Cross-premises connectiviteit toevoegen

De volgende implementatie stap is het maken van de cross-premises verbinding (als dit van toepassing is op uw oplossing). Voor verbindingen tussen meerdere locaties moet een Azure-gateway zijn opgeslagen in een afzonderlijk gateway subnet, waarvoor u een adresruimte moet maken en toewijzen. 
  
Wanneer u een cross-premises verbinding plant, definieert en maakt u een Azure gateway en een verbinding met een on-premises gatewayapparaat.
  
**Afbeelding 2: een Azure gateway en een on-premises gatewayapparaat gebruiken om tussen de on-premises omgeving en Azure verbinding te maken met de site**

![On-premises omgeving die is verbonden met een virtueel Azure-netwerk via een cross-premises verbinding, wat kan een site-naar-site VPN-verbinding of ExpressRoute zijn.](../media/AZarch-VPNgtwyconnct.png)
  
In dit diagram:
  
- Als u een voorbeeld van een koppeling toevoegt aan het vorige diagram, wordt de on-premises omgeving verbonden met het virtuele Azure-netwerk via een cross-premises verbinding, wat kan een VPN-verbinding voor site-naar-site of ExpressRoute zijn.
    
- Een Azure-gateway bevindt zich op een gateway-subnet.
    
- De on-premises omgeving bevat een gatewayapparaat, zoals een router of een VPN-server.
    
Zie [een on-premises netwerk verbinden met een Microsoft Azure Virtual Network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)voor meer informatie over het plannen en maken van een cross-premises virtueel netwerk.
  
## <a name="add-active-directory-domain-services-ad-ds-and-dns"></a>Active Directory Domain Services (AD DS) en DNS toevoegen

Voor calamiteitenherstel in azure moet u Windows Server AD en DNS implementeren in een hybride scenario waarbij Windows Server AD zowel on-premises als on Azure virtuele machines wordt geïmplementeerd.
  
**Afbeelding 3: configuratie van hybride Active Directory-domein**

![STwo virtuele machines die zijn geïmplementeerd op het virtuele Azure-netwerk en het subnet van de SharePoint-farm zijn replica domeincontrollers en DNS-servers](../media/AZarch-HyADdomainConfig.png)
  
In dit diagram worden de eerdere diagrammen samengesteld door twee virtuele machines toe te voegen aan een AD-en DNS-subnet van Windows Server. Deze virtuele machines zijn replica domeincontrollers en DNS-servers. Ze zijn een uitbreiding van de on-premises Windows Server AD-omgeving. 
  
De volgende tabel bevat aanbevelingen voor de configuratie van deze virtuele machines in Azure. U kunt deze gebruiken als uitgangspunt voor het ontwerpen van uw eigen omgeving, zelfs voor een toegewijd domein waarbij de Azure-omgeving niet communiceert met uw on-premises omgeving.
  
|**Item**|**Configuratie**|
|:-----|:-----|
|Grootte van virtuele machine in azure  <br/> |De grootte a1 of a2 in de standaard laag  <br/> |
|Besturingssysteem  <br/> |Windows Server 2012 R2  <br/> |
|Active Directory Role  <br/> |Active Directory-domeincontroller aangegeven als een globale catalogusserver. Met deze configuratie wordt het uitvullen van verkeer via de cross-premises verbinding beperkt.  <br/> In een omgeving met meerdere domeinen met een hoge wijzigingssnelheid (dit geldt niet gebruikelijk), configureert u domeincontrollers on-premises niet synchroniseren met de globale catalogusservers in azure om het replicatieverkeer te beperken.  <br/> |
|DNS-functie  <br/> |Installeer en configureer de DNS Server-service op de domeincontrollers.  <br/> |
|Gegevensschijven  <br/> |Plaats de Active Directory-database, logboeken en SYSVOL op extra Azure-gegevensschijven. Plaats deze niet op de schijf van het besturingssysteem of de tijdelijke schijven van Azure.  <br/> |
|IP-adressen  <br/> |Gebruik statische IP-adressen en configureer het virtuele netwerk om deze adressen toe te wijzen aan de virtuele machines in het virtuele netwerk nadat de domeincontrollers zijn geconfigureerd.  <br/> |
   
> [!IMPORTANT]
> Lees de [richtlijnen voor het implementeren van Windows Server Active Directory op virtuele machines van Azure](https://go.microsoft.com/fwlink/p/?linkid=392681)voordat u Active Directory implementeert in Azure. Met deze functie kunt u bepalen of een andere architectuur of verschillende configuratie-instellingen voor uw oplossing nodig zijn. 
  
## <a name="add-the-sharepoint-farm"></a>SharePoint-farm toevoegen

Plaats de virtuele machines van de SharePoint-farm in niveaus op de juiste subnetten.
  
**Afbeelding 4: plaatsing van virtuele machines van SharePoint**

![Database servers en SharePoint Server-functies die zijn toegevoegd aan het virtuele Azure-netwerk binnen het subnet van de SharePoint-farm](../media/AZarch-SPVMsinCloudSer.png)
  
In dit diagram worden de bestaande diagrammen samengesteld door de functies van de SharePoint-farm server toe te voegen aan de desbetreffende lagen.
  
- Twee database lagen met SQL Server maken de databasemap.
    
- Twee virtuele machines waarop SharePoint Server 2013 wordt uitgevoerd voor alle volgende lagen: front-endservers, servers met gedistribueerde cache en back-endservers.
    
## <a name="design-and-fine-tune-server-roles-for-availability-sets-and-fault-domains"></a>Serverrollen ontwerpen en verfijnen voor beschikbaarheidssets en foutdomeinen

Een foutdomein is een groepering van hardware waarbij rollen exemplaren worden uitgevoerd. Virtuele machines binnen hetzelfde foutdomein kunnen tegelijkertijd worden bijgewerkt door de Azure-infrastructuur. Het kan ook zijn dat ze op hetzelfde moment kunnen mislukken omdat ze hetzelfde rack delen. Om te voorkomen dat er twee virtuele machines in hetzelfde foutdomein zijn, kunt u uw virtuele machines configureren als beschikbare set, zodat elke virtuele machine zich in een ander foutdomein bevindt. Als drie virtuele machines zijn geconfigureerd als een beschikbaarheidsset, garandeert Azure dat er niet meer dan twee van de virtuele machines in hetzelfde foutdomein zich bevinden.
  
Wanneer u de Azure-architectuur voor een SharePoint-farm ontwerpt, configureert u identieke serverrollen om deel te nemen aan een beschikbare set. Zo zorgt u ervoor dat uw virtuele machines worden verspreid over meerdere foutdomeinen.
  
**Afbeelding 5: Azure-beschikbaarheids sets gebruiken om hoge beschikbaarheid te geven voor de SharePoint-farm lagen**

![Configuratie van beschikbaarheidssets in de Azure-infrastructuur voor een SharePoint 2013-oplossing](../media/AZenv-WinAzureAvailSetsHA.png)
  
Dit diagram roept de configuratie van beschikbare beschikbaarheidssets binnen de Azure-infrastructuur aan. Elke volgende functie deelt een afzonderlijke beschikbare set:
  
- Active Directory en DNS
    
- Database
    
- Back-end
    
- Cache distribueren
    
- Front-end
    
De SharePoint-farm moet mogelijk worden afgestemd op het Azure-platform. Voor een hoge beschikbaarheid van alle onderdelen zorgt u ervoor dat de serverrollen allemaal identiek zijn geconfigureerd.
  
Hier ziet u een voorbeeld met een standaardarchitectuur voor Internet sites die voldoet aan specifieke capaciteit en prestatiedoelstellingen. Dit voorbeeld wordt aanbevolen in het volgende architectuur model: [Zoek architecturen voor Internet sites voor SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=261519).
  
**Afbeelding 6: voorbeeld van de planning voor de capaciteit en prestatiedoelstellingen in een farm met drie lagen**

![Standaardarchitectuur voor SharePoint 2013-sites op Internet sites met behulp van onderdeeltoewijzingen die voldoen aan specifieke capaciteit en prestatiedoelstellingen](../media/AZarch-CapPerfexmpArch.png)
  
In dit diagram:
  
- Een farm met drie lagen wordt weergegeven: webservers, toepassingsservers en databaseservers.
    
- De drie webservers zijn identiek geconfigureerd met meerdere onderdelen.
    
- De twee databaseservers zijn identiek geconfigureerd.
    
- De drie toepassingsservers zijn niet identiek geconfigureerd. Voor deze serverrollen moet de beschikbaarheid van beschikbaarheidssets in azure nauwkeurig worden afgestemd.
    
Laten we eens kijken naar de gegevenslaagtoepassing van Application Server.
  
**Afbeelding 7: een gegevenslaagtoepassing voor de toepassingsserver voordat u het afstemmen**

![Voorbeeld van een gegevenslaagtoepassing van SharePoint Server 2013 voordat u gaat afstemmen voor Microsoft Azure Availability sets](../media/AZarch-AppServtierBefore.png)
  
In dit diagram:
  
- Drie servers worden opgenomen in de gegevenslaagtoepassing.
    
- De eerste server bevat vier onderdelen.
    
- De tweede server bevat drie onderdelen.
    
- De derde server bevat twee onderdelen.
    
U bepaalt het aantal onderdelen op basis van de prestaties en capaciteits doelstellingen voor de farm. Om deze architectuur voor Azure aan te passen, worden de vier onderdelen van alle drie servers gerepliceerd. Het aantal onderdelen dat groter is dan het aantal voor prestaties en capaciteit. De versterkings graad is dat dit ontwerp zorgt voor een hoge beschikbaarheid van alle vier de onderdelen van het Azure-platform wanneer deze drie virtuele machines worden toegewezen aan een beschikbare set.
  
**Afbeelding 8: toepassingsserver-tier na nauwkeurig afstemmen**

![Voorbeeld van een gegevenslaagtoepassing van SharePoint Server 2013 na de aanpassing voor Microsoft Azure Availability sets](../media/AZarch-AppServtierAfter.png)
  
Dit diagram toont alle drie toepassingsservers die identiek zijn geconfigureerd met dezelfde vier onderdelen.
  
Wanneer we beschikbaarheidssets toevoegen aan de lagen van de SharePoint-farm, is de implementatie voltooid.
  
**Afbeelding 9: de voltooide SharePoint-farm in azure-infrastructuurservices**

![Voorbeeld van een SharePoint 2013-Farm in azure-infrastructuurservices met virtueel netwerk, cross-premises connectiviteit, subnetten, Vm's en beschikbaarheidssets](../media/7256292f-bf11-485b-8917-41ba206153ee.png)
  
In dit diagram ziet u de SharePoint-farm die is geïmplementeerd in azure-infrastructuurservices, met beschikbaarheidssets voor het aanbrengen van foutdomeinen voor de servers in elke laag.
  
## <a name="see-also"></a>Zie ook

[Microsoft 365-oplossingen- en -architectuurcentrum](../solutions/solution-architecture-center.md)
  
[Internet sites in Microsoft Azure met behulp van SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
  
[Herstel na herstel van SharePoint Server 2013 in Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)


