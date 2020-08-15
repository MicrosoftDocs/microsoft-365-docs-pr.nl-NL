---
title: Herstel na herstel van SharePoint Server 2013 in Microsoft Azure
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 04/17/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Deployment
- seo-marvel-apr2020
ms.assetid: e9d14cb2-ff28-4a18-a444-cebf891880ea
description: In dit artikel wordt beschreven hoe u met Azure een omgeving voor noodherstel maakt voor uw on-premises SharePoint-farm.
ms.openlocfilehash: d1643f3fa0275ef9fbb01372869ca551b9fed495
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689075"
---
# <a name="sharepoint-server-2013-disaster-recovery-in-microsoft-azure"></a>Herstel na herstel van SharePoint Server 2013 in Microsoft Azure

 Met Azure kunt u een noodherstel omgeving maken voor uw on-premises SharePoint-farm. In dit artikel wordt beschreven hoe u deze oplossing ontwerpt en implementeert.

 **Bekijk de video over het overzicht van SharePoint Server 2013 noodherstel**
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1b73ec8f-29bd-44eb-aa3a-f7932784bfd9?autoplay=false]
  
 Wanneer u de on-premises omgeving van de SharePoint-omgeving aanneemt, kunt u het systeem weer snel weer starten. Noodherstel met SharePoint is sneller en eenvoudiger wanneer u een back-upomgeving hebt die al wordt uitgevoerd in Microsoft Azure. In deze video wordt uitgelegd wat het belangrijkste concept is van een warme SharePoint-Herstelomgeving en wordt de volledige details van dit artikel aangevuld.
  
Gebruik dit artikel met het volgende oplossings model: **herstel van SharePoint in Microsoft Azure**.
  
[![SharePoint-noodherstel proces op Azure](../media/SP-DR-Azure.png)](https://go.microsoft.com/fwlink/p/?LinkId=392555)
  
 [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555) |  [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)
  
## <a name="use-azure-infrastructure-services-for-disaster-recovery"></a>Azure-infrastructuur services gebruiken voor calamiteitenherstel

Veel organisaties hebben geen noodherstel omgeving voor SharePoint, wat kostbaar kan zijn om on-premises te bouwen en te onderhouden. Azure-infrastructuur services biedt boeiende opties voor calamiteitenherstel omgevingen die flexibeler en minder kostbaar zijn dan de on-premises alternatieven.
  
De voordelen van het gebruik van Azure-infrastructuur services zijn:
  
- **Minder kostbare resources** Behoud en betaal minder bronnen dan on-premises noodherstel omgevingen. Het aantal bronnen is afhankelijk van welke omgeving voor noodherstel u kiest: koude stand, warme stand of hot standby.
    
- **Betere resource flexibiliteit** Wanneer een ramp een ramp doet, kunt u eenvoudig uw herstel SharePoint-farm schalen om te voldoen aan de laad vereisten. Als u de bronnen niet meer nodig hebt, kunt u deze aanpassen.
    
- **Minder datacenter toezegging** Gebruik Azure-infrastructuur services in plaats van investeren in een tweede datacenter in een andere regio.
    
Er zijn minder complexe opties voor organisaties aan de slag met calamiteitenherstel en geavanceerde opties voor organisaties met een high-bestendige behoefte. De definities voor de omgeving koud, warm en hot standby zijn enigszins verschillend wanneer de omgeving wordt gehost op een Cloud platform. In de volgende tabel worden deze omgevingen beschreven voor het maken van een SharePoint-herstelfarm in Azure.
  
**Tabel: Herstelomgeving**

|**Type Herstelomgeving**|**Beschrijving**|
|:-----|:-----|
|Hot  <br/> |Er is een volledige grootte van een farm ingericht, bijgewerkt en wordt uitgevoerd op stand-by.  <br/> |
|Hete  <br/> |De farm is gebouwd en de virtuele machines worden uitgevoerd en bijgewerkt.  <br/> Herstel omvat het toevoegen van inhoudsdatabases, het inrichten van servicetoepassingen en het verkennen van inhoud.  <br/> De farm kan een kleinere versie van de productiefarm zijn en vervolgens zodanig geschaald dat de volledige gebruikersbasis van de tabel kunnen worden gebruikt.  <br/> |
|Gekoelde  <br/> |De farm is volledig gebouwd, maar de virtuele machines worden stopgezet.  <br/> Het onderhoud van de omgeving omvat het opstarten van de virtuele machines, waarbij de omgeving de enige tijd is om de omgeving te herstellen, bij te werken en te verifiëren.  <br/> De hele omgeving starten in het geval van een ramp.  <br/> |
   
Het is belangrijk dat u de tijd doelstellingen voor het herstel van uw organisatie (RTOs) en herstelpunten doelstellingen (RPOs) evalueert. Deze vereisten bepalen welke omgeving de meest geschikte investering voor uw organisatie is.
  
Aan de hand van de instructies in dit artikel wordt uitgelegd hoe u een warme standby-omgeving implementeert. U kunt de sjabloon ook aanpassen aan een koud standby-omgeving, maar u moet ook aanvullende procedures volgen ter ondersteuning van dit soort omgeving. In dit artikel wordt niet beschreven hoe u een hot standby-omgeving implementeert.
  
Zie voor meer informatie over het oplossen van hersteloplossingen voor [hoge beschikbaarheid en herstel na noodgevallen in SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkID=393114) en [Kies een strategie voor noodherstel voor SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=203228).
  
## <a name="solution-description"></a>Beschrijving van oplossing

Voor de oplossing voor de warme standby-hersteloplossing is de volgende omgeving vereist:
  
- Een on-premises SharePoint-productiefarm
    
- Een SharePoint-herstelfarm in azure
    
- Een site-tot-site VPN-verbinding tussen de twee omgevingen
    
In de volgende afbeelding ziet u deze drie elementen.
  
**Afbeelding: elementen van een warme standby-oplossing in azure**

![Elementen van een oplossing voor een ingebouwde SharePoint-oplossing in azure](../media/AZarch-AZWarmStndby.png)
  
Het verzenden van een SQL Server-logboek met een Distributed File System Replication (DFSR) wordt gebruikt voor het kopiëren van back-ups van databases en transactielogboeken naar de herstelfarm in Azure: 
  
- Met DFSR worden logboeken overgebracht van de productieomgeving naar de Herstelomgeving. In een WAN-scenario is DFSR efficiënter dan de logboeken rechtstreeks naar de secundaire server in azure verzenden.
    
- Logboeken worden opnieuw afgespeeld voor de SQL Server in de herstelomgeving van Azure.
    
- U voegt geen logboeken van SharePoint-inhoudsdatabases aan de herstelomgeving toe totdat een herstel oefening wordt uitgevoerd.
    
Voer de volgende stappen uit om de farm te herstellen:
  
1. Stop logboekverzending.
    
2. Stop het accepteren van verkeer naar de primaire farm.
    
3. Herhaal de laatste transactielog Logboeken.
    
4. Koppel de inhoudsdatabases aan de farm.
    
5. Herstelservice toepassingen uit de gerepliceerde Services-databases.
    
6. DNS-records (Domain Name System) bijwerken zodat ze verwijzen naar de herstelfarm.
    
7. Een volledige verkenning starten
    
U wordt aangeraden deze stappen regelmatig te volgen en documenten te documenteren om ervoor te zorgen dat uw Live Recovery soepel verloopt. Inhoudsdatabases bijvoegen en servicetoepassingen herstellen kan enige tijd in beslag nemen en is meestal een handmatige configuratie.
  
Wanneer een herstelbewerking is uitgevoerd, biedt deze oplossing de items die in de volgende tabel worden vermeld.
  
**Tabel: doelstellingen voor oplossings herstel**

|**Item**|**Beschrijving**|
|:-----|:-----|
|Sites en inhoud  <br/> |Sites en inhoud zijn beschikbaar in de Herstelomgeving.  <br/> |
|Een nieuw exemplaar van de zoekopdracht  <br/> |In deze warme standby-oplossing wordt de zoekopdracht niet hersteld vanuit de zoekdatabase. De zoekonderdelen in de herstelfarm zijn zo vergelijkbaar mogelijk geconfigureerd voor de productiefarm. Nadat de sites en inhoud zijn hersteld, wordt een volledige verkenning gestart met het opnieuw opbouwen van de zoekindex. U hoeft niet te wachten tot de verkenning is voltooid om de sites en de inhoud beschikbaar te maken.  <br/> |
|Reparatie  <br/> | Services die gegevens in databases opslaan, worden vanuit de databases voor logboekverzending hersteld. Services die geen gegevens in de databases opslaan, worden simpelweg gestart. <br/>  Niet alle services met databases moeten worden hersteld. De volgende services hoeven niet te worden hersteld uit databases en kunnen eenvoudig worden gestart na de failover: <br/>  Gebruik en statusgegevens verzamelen <br/>  Servicestatus <br/>  Automatisering van Word <br/>  Andere services die niet gebruikmaken van een database <br/> |
   
U kunt met Microsoft Consulting Services (MCS) of een partner samenwerken om meer ingewikkelde herstel doelstellingen op te lossen. De volgende tabel bevat een overzicht van de punten.
  
**Tabel: andere items die kunnen worden opgelost door MCS of een partner**

|**Item**|**Beschrijving**|
|:-----|:-----|
|Aangepaste Farm oplossingen synchroniseren  <br/> |In het ideale geval is de configuratie van de herstelfarm identiek aan de productiefarm. U kunt samenwerken met een consultant of partner om te beoordelen of aangepaste Farm oplossingen worden gerepliceerd en of het proces is voltooid, zodat de twee omgevingen worden gesynchroniseerd.  <br/> |
|Verbindingen met gegevensbronnen on-premises  <br/> |Het kan soms voorkomen dat verbindingen met back-end-gegevens systemen, zoals BDC-verbinding (back-updomeincontroller) en inhoudsbronnen, worden gerepliceerd.  <br/> |
|Scenario's voor herstel van zoeken  <br/> |Aangezien Enterprise Search-implementaties zeer uniek en ingewikkeld zijn, is het niet mogelijk om zoeken te herstellen vanuit databases. U kunt met een consultant of partner samen herstelscenario's identificeren en implementeren die uw organisatie nodig heeft.  <br/> |
   
Bij de richtlijnen in dit artikel wordt ervan uitgegaan dat de on-premises Farm al is ontworpen en geïmplementeerd.
  
## <a name="detailed-architecture"></a>Gedetailleerde architectuur

In het ideale geval is de configuratie van de herstelfarm in azure identiek met de on-premises productiefarm, waaronder de volgende:
  
- Dezelfde weergave van serverrollen
    
- Dezelfde configuratie van aanpassingen
    
- Dezelfde configuratie van zoekonderdelen
    
De omgeving in azure kan een kleinere versie zijn van de productiefarm. Als u van plan bent om de herstelfarm na failover te schalen, moet u eerst elk type serverrol weergeven.
  
Het is mogelijk dat sommige configuraties niet praktisch zijn voor replicatie in de failover-omgeving. Zorg ervoor dat u de failoverconfiguratie en de omgeving test om er zeker van te zijn dat de failover-farm het verwachte serviceniveau biedt.
  
Met deze oplossing wordt geen specifieke topologie voor een SharePoint-farm bedoeld. De focus van deze oplossing is het gebruik van Azure voor de failover-Farm en om logboekverzending en DFSR te implementeren tussen de twee omgevingen.
  
### <a name="warm-standby-environments"></a>Warm standby-omgevingen

In een warme standby-omgeving worden alle virtuele machines in de Azure-omgeving uitgevoerd. De omgeving is gereed voor een failover-uitvoering of-gebeurtenis.
  
In de volgende afbeelding wordt een oplossing voor noodgevallen hersteld van een lokale SharePoint-farm met een Azure SharePoint-farm die is geconfigureerd als een warme standby-omgeving.
  
**Afbeelding: topologie en belangrijkste onderdelen van een productiefarm en een warme herstelfarm voor de slaapstand**

![Topologie van een SharePoint-farm en een warme herstelfarm voor de slaapstand](../media/AZarch-AZWarmStndby.png)
  
In dit diagram:
  
- Twee omgevingen worden naast elkaar geïllustreerd: de lokale SharePoint-farm en de warme standby-Farm in Azure.
    
- Elke omgeving omvat een bestandsshare.
    
- Elke farm bevat vier lagen. Ter verkrijging van hoge beschikbaarheid bevat elke laag twee servers of virtuele machines die identiek zijn geconfigureerd voor een bepaalde functie, zoals de front-end-services, de gedistribueerde cache, de back-end services en databases. In deze afbeelding is het niet belangrijk om bepaalde onderdelen te bellen. De twee Farms zijn identiek geconfigureerd.
    
- De vierde laag is de database laag. Logboekverzending wordt gebruikt voor het kopiëren van logboeken van de secundaire databaseserver in de on-premises omgeving naar de bestandsshare in dezelfde omgeving.
    
- DFSR kopieert bestanden vanuit de bestandsshare in de on-premises omgeving naar de bestandsshare in de Azure-omgeving.
    
- Wanneer u de verzending van het logboek registreert, worden de logboeken van de bestandsshare in de Azure-omgeving afgespeeld met de primaire replica in de groeps beschikbaarheid in SQL Server in de Herstelomgeving.
    
### <a name="cold-standby-environments"></a>Omgeving voor koel stand

In een omgeving met koud standen kunnen de meeste virtuele machines van de SharePoint-farm worden uitgeschakeld. (Het is raadzaam om de virtuele machines te starten, zoals elke twee weken of een maand, zodat elke virtuele machine kan worden gesynchroniseerd met het domein.) De volgende virtuele machines in de Azure-Herstelomgeving moeten worden uitgevoerd om de voortdurende werking van Logboeken en DFSR te helpen voorkomen:
  
- De bestandsshare
    
- De primaire databaseserver
    
- Minstens één virtuele machine waarop Windows Server Active Directory Domain Services en DNS wordt uitgevoerd
    
In de volgende afbeelding ziet u een Azure-failoverconfiguratie waarin de virtuele machine van het bestanddelen en de primaire SharePoint-database virtuele machine actief zijn. Alle andere virtuele machines van SharePoint zijn gestopt. De virtuele machine waarop Windows Server Active Directory en DNS wordt uitgevoerd, wordt niet weergegeven.
  
**Afbeelding: herstelfarm met de koude-stand met actieve virtuele machines**

![Elementen van een SharePoint-oplossing voor koel stand in azure](../media/AZarch-AZColdStndby.png)
  
Na een failover naar een omgeving met koud standby worden alle virtuele machines gestart en de manier waarop u hoge beschikbaarheid van de databaseservers kunt bereiken, moet zijn geconfigureerd, zoals SQL Server AlwaysOn-beschikbaarheidsgroepen.
  
Als er meerdere opslaggroepen zijn geïmplementeerd (databases worden verspreid over meerdere SQL Server-sets van hoge beschikbaarheid), moet de primaire database voor elke opslaggroep worden uitgevoerd om de logboeken te accepteren die zijn gekoppeld aan de opslaggroep.
  
### <a name="skills-and-experience"></a>Vaardigheden en ervaring

Meerdere technologieën worden gebruikt in deze oplossing voor herstel van noodgevallen. Om ervoor te zorgen dat deze technologieën goed werken, moet elk onderdeel in de on-premises omgeving en de Azure-omgeving correct zijn geïnstalleerd en geconfigureerd. We raden aan dat de persoon of het team die deze oplossing instelt, een sterke en praktische kennis heeft van de technologieën die worden beschreven in de volgende artikelen:
  
- [DFS-replicatie Services (Distributed File System)](https://go.microsoft.com/fwlink/p/?LinkId=392698)
    
- [WSFC (Windows Server failover clustering) met SQL Server](https://go.microsoft.com/fwlink/p/?LinkId=392701)
    
- [AlwaysOn-Beschikbaarheidsgroepen (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=392725)
    
- [Back-ups van SQL Server-databases maken en terugzetten](https://go.microsoft.com/fwlink/p/?LinkId=392728)
    
- [Installatie van SharePoint Server 2013 en Farm implementatie](https://go.microsoft.com/fwlink/p/?LinkId=393119)
    
- [Microsoft Azure](https://go.microsoft.com/fwlink/p/?LinkId=392729)
    
Ten slotte kunt u beter gebruikmaken van scripts voor de automatisering die u kunt gebruiken voor het automatiseren van taken die bij deze technologieën horen. U kunt de beschikbare gebruikersinterfaces gebruiken om alle taken te voltooien die in deze oplossing worden beschreven. Een handmatige aanpak kan echter veel tijd in beslag nemen en foutgevoelige resultaten opleveren.
  
Naast Windows PowerShell zijn er ook Windows PowerShell-bibliotheken voor SQL Server, SharePoint Server en Azure. U hoeft T-SQL niet te vergeten, zodat u ook minder tijd hebt om de omgeving voor noodherstel te configureren en te onderhouden.
  
## <a name="disaster-recovery-roadmap"></a>Procedure voor noodherstel

![Visuele weergave van de routekaart voor noodherstel van SharePoint.](../media/Azure-DRroadmap.png)
  
In deze stap wordt ervan uitgegaan dat u al een SharePoint Server 2013-farm hebt geïmplementeerd in de productie.
  
**Tabel: routekaart voor calamiteitenherstel**

|**Fase**|**Beschrijving**|
|:-----|:-----|
|Fase 1  <br/> |Ontwerp de omgeving voor noodherstel.  <br/> |
|Fase 2  <br/> |Maak de virtuele Azure-verbinding en VPN-verbinding.  <br/> |
|Fase 3  <br/> |Implementeer Windows Active Directory en Domain Name Services in het virtuele Azure-netwerk.  <br/> |
|Fase 4  <br/> |Implementeer de SharePoint-herstelfarm in Azure.  <br/> |
|Fase 5  <br/> |Configureer DFSR tussen de farms.  <br/> |
|Fase 6  <br/> |Stel logboekverzending in naar de herstelfarm.  <br/> |
|Fase 7  <br/> | Validering van oplossingen voor storingen en herstel. Dit omvat de volgende procedures en technologieën: <br/>  Stop logboekverzending. <br/>  Herstel de back-up. <br/>  Inhoud verkennen. <br/>  Services herstellen. <br/>  DNS-records beheren. <br/> |
   
## <a name="phase-1-design-the-disaster-recovery-environment"></a>Fase 1: de omgeving voor noodherstel ontwerpen

Gebruik de instructies in [Microsoft Azure Architectures voor SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) om de omgeving voor noodherstel te ontwerpen, waaronder de SharePoint-herstelfarm. U kunt de afbeeldingen in de [SharePoint-oplossing voor herstel na herstel gebruiken in azure Visio-](https://go.microsoft.com/fwlink/p/?LinkId=392554) bestand om het ontwerpproces te starten. We raden u aan de hele omgeving te ontwerpen voordat u aan de Azure-omgeving begint.
  
Naast de richtlijnen in [Microsoft Azure architecturen voor SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) voor het ontwerpen van het virtuele netwerk, de VPN-verbinding, Active Directory en de SharePoint-farm, moet u een rol voor gedeelde bestanden toevoegen aan de Azure-omgeving.
  
Voor de ondersteuning van logboekverzending via een oplossing voor noodgevallen, wordt een virtuele computer met een bestandsshare toegevoegd aan het subnet waarin de databaserollen zich bevinden. De bestandsshare dient ook als derde knooppunt van een knooppuntmeerderheid voor de groeps beschikbaarheid in SQL Server. Dit is de aanbevolen configuratie voor een standaard-SharePoint-farm die gebruikmaakt van SQL Server AlwaysOn-beschikbaarheidsgroepen. 
  
> [!NOTE]
> Het is belangrijk dat u de vereisten voor een database controleert om deel te nemen aan een groeps beschikbaarheid in SQL Server. Zie [vereisten, beperkingen en aanbevelingen voor AlwaysOn-Beschikbaarheidsgroepen](https://go.microsoft.com/fwlink/p/?LinkId=510870)voor meer informatie. 
  
**Afbeelding: plaatsing van een bestandsserver die wordt gebruikt voor een oplossing voor herstel na noodgevallen**

![Geeft een bestandsshare-VM weer, die is toegevoegd aan dezelfde cloudservice die de SharePoint-databaseserver rollen bevat.](../media/AZenv-FSforDFSRandWSFC.png)
  
In dit diagram wordt een virtuele computer met een bestandsshare toegevoegd aan hetzelfde subnet in azure met de database serverrol functies. Voeg de virtuele machine van de bestandsshare niet toe aan een beschikbaarheidsset met andere serverrollen, zoals SQL Server-rollen.
  
Als u zich zorgen maakt over de hoge beschikbaarheid van de logboeken, kunt u overwegen een andere aanpak te maken met behulp van [SQL Server back-up en terugzetten met Azure Blob Storage-service](https://go.microsoft.com/fwlink/p/?LinkId=393113). Dit is een nieuwe functie in azure waarmee logboeken rechtstreeks worden opgeslagen in een URL voor de blobopslag. Deze oplossing omvat geen richtlijnen voor het gebruik van deze functie.
  
Wanneer u de herstelfarm ontwerpt, moet u er rekening mee houden dat een omgeving met een succesvolle Herstelomgeving de productiefarm die u wilt herstellen, exact weerspiegelt. De grootte van de herstelfarm is niet het belangrijkste van het ontwerp, de implementatie en het testen van het herstel bedrijf. De schaal van het bedrijf verschilt van organisatie met organisatie op basis van de bedrijfsvereisten. Het kan handig zijn om een geschaalde Farm te gebruiken voor een korte onderbreking of voor de behoeften aan de vereisten om de farm te schalen.
  
Configureer de herstelfarm zo op dezelfde manier als de productiefarm, zodat deze voldoet aan uw SLA-vereisten (Service Level Agreement) en de functies biedt die u nodig hebt om uw bedrijf te ondersteunen. Wanneer u de omgeving voor noodherstel ontwerpt, bekijkt u ook uw proces voor het wijzigen van uw productieomgeving. We raden u aan dat u het proces voor het wijzigen van het beheer naar de herstelomgeving verlengt door de herstelomgeving te wijzigen met hetzelfde interval als de productieomgeving. U wordt aangeraden als onderdeel van het proces voor wijzigingsbeheer om een gedetailleerde inventaris van uw farmconfiguratie, toepassingen en gebruikers te onderhouden. 
  
## <a name="phase-2-create-the-azure-virtual-network-and-vpn-connection"></a>Fase 2: de virtuele Azure-netwerk-en VPN-verbinding maken

[Een on-premises netwerk verbinden met een virtueel Microsoft Azure-netwerk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md) laat u zien hoe u het virtuele netwerk in azure plant en implementeert en hoe u de VPN-verbinding maakt. Volg de instructies in het onderwerp voor het uitvoeren van de volgende procedures:
  
- Plan de persoonlijke IP-adresruimte van het virtuele netwerk.
    
- Plan de wijzigingen van de routeringsinfrastructuur voor het virtuele netwerk.
    
- Plan firewallregels voor verkeer naar en vanaf het on-premises VPN-apparaat.
    
- Maak het cross-premises virtuele netwerk in Azure.
    
- Configureer routering tussen uw on-premises netwerk en het virtuele netwerk.
    
## <a name="phase-3-deploy-active-directory-and-domain-name-services-to-the-azure-virtual-network"></a>Fase 3: Active Directory en Domain name services implementeren voor het Azure virtueel netwerk

Deze fase omvat zowel Windows Server Active Directory als DNS naar het virtuele netwerk in een hybride scenario zoals beschreven in [Microsoft Azure architecturen voor SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) en zie de volgende afbeelding.
  
**Afbeelding: configuratie van hybride Active Directory-domein**

![Twee virtuele machines die zijn geïmplementeerd voor het virtuele Azure-netwerk en het subnet van de SharePoint-farm zijn replica domeincontrollers en DNS-servers](../media/AZarch-HyADdomainConfig.png)
  
In de afbeelding worden twee virtuele machines geïmplementeerd in hetzelfde subnet. Deze virtuele machines worden gebruikt om twee rollen te hosten: Active Directory en DNS.
  
Lees [richtlijnen voor het implementeren van Windows Server Active Directory op virtuele machines van Azure](https://go.microsoft.com/fwlink/p/?linkid=392681)voordat u Active Directory implementeert in Azure. Met deze richtlijnen kunt u bepalen of u een andere architectuur of andere configuratie-instellingen voor uw oplossing nodig hebt.
  
Voor uitgebreide informatie over het instellen van een domeincontroller in azure raadpleegt u [een Active Directory-domeincontroller voor replica installeren in virtuele netwerken van Azure](https://go.microsoft.com/fwlink/p/?LinkId=392687).
  
Voordat u deze fase uitvoert, hebt u geen virtuele machines geïmplementeerd voor het virtuele netwerk. De virtuele machines voor het hosten van Active Directory en DNS zijn waarschijnlijk niet de grootste virtuele machines die u nodig hebt voor de oplossing. Voordat u deze virtuele machines implementeert, maakt u eerst de grootste virtuele machine die u wilt gebruiken in uw virtuele netwerk. Dit helpt u ervoor te zorgen dat uw oplossing van een label in azure het grootste formaat mogelijk maakt. U hoeft deze virtuele machine op dit moment niet te configureren. Maak gewoon een plaats en zet ze apart. Als u dit niet doet, kunt u een beperking uitvoeren wanneer u later meer virtuele machines probeert te maken, wat een probleem was op het moment dat dit artikel werd geschreven. 
  
## <a name="phase-4-deploy-the-sharepoint-recovery-farm-in-azure"></a>Fase 4: de SharePoint-herstelfarm implementeren in azure

Implementeer de SharePoint-farm in uw virtuele netwerk volgens de ontwerp plannen. Het kan handig zijn de [planning voor SharePoint 2013 te controleren op Azure-infrastructuur services](https://go.microsoft.com/fwlink/p/?LinkId=400984) voordat u SharePoint-rollen implementeert in Azure.
  
Houd rekening met de volgende procedures die we hebben geleerd door ons proef concept van de concept omgeving te maken:
  
- Maak virtuele machines met behulp van de Azure-portal of PowerShell.
    
- Azure en Hyper-V ondersteunen geen dynamisch geheugen. Let erop dat u dit factor houdt in uw abonnement voor prestatie-en capaciteitsplanning.
    
- U moet virtuele machines opnieuw opstarten via de Azure-interface, niet vanaf de virtuele machine Logon. Het gebruik van de Azure-interface werkt beter en is voorspelbaarder.
    
- Als u een virtuele machine wilt afsluiten om kosten op te slaan, gebruikt u de Azure-interface. Als u de verbinding met de virtuele machine uitschakelt, blijven de kosten toenemen.
    
- Een naamgevingsconventie gebruiken voor de virtuele machines.
    
- Let op de locatie van het datacenter waar de virtuele machines worden geïmplementeerd.
    
- De functie voor automatisch schalen in azure wordt niet ondersteund voor SharePoint-rollen.
    
- Configureer geen items in de farm die worden hersteld, zoals siteverzamelingen. 
    
## <a name="phase-5-set-up-dfsr-between-the-farms"></a>Fase 5: DFSR instellen tussen de Farms

Als u de bestandsreplicatie wilt instellen met behulp van DFSR, gebruikt u de module DNS-beheer. Voor de installatie van DFSR, meldt u zich echter aan bij uw on-premises bestandsserver en Azure File Server en schakelt u de service in Windows in.
  
Voer in het server beheer-dashboard de volgende stappen uit:
  
- Configureer de lokale server.
    
- Start de **wizard functies en onderdelen toevoegen**.
    
- Open het knooppunt **File and Storage services** .
    
- Selecteer **DFS-naamruimten** en **DFS-replicatie**.
    
- Klik op **volgende** om de stappen van de wizard te voltooien.
    
De volgende tabel bevat koppelingen naar artikelen met naslaginformatie voor DFSR en blogberichten.
  
**Tabel: referentie artikelen voor DFSR**

|**Title**|**Beschrijving**|
|:-----|:-----|
|[Replica's](https://go.microsoft.com/fwlink/p/?LinkId=392732) <br/> |TechNet-onderwerp voor DFS-beheer met koppelingen voor replicatie  <br/> |
|[DFS-replicatie: overlevings handleiding](https://go.microsoft.com/fwlink/p/?LinkId=392737) <br/> |Wiki met koppelingen naar informatie over DFS  <br/> |
|[DFS-replicatie: veelgestelde vragen](https://go.microsoft.com/fwlink/p/?LinkId=392738) <br/> |TechNet-onderwerp voor DFS-replicatie  <br/> |
|[Blog van Jose Barreto](https://go.microsoft.com/fwlink/p/?LinkId=392739) <br/> |Blog die is geschreven door een hoofdprogramma Manager op het bestands Server team van Microsoft  <br/> |
|[Het opslag team bij een blog van Microsoft-File Cabinet](https://go.microsoft.com/fwlink/p/?LinkId=392740) <br/> |Blog over Bestandsservices en opslagfuncties in Windows Server  <br/> |
   
## <a name="phase-6-set-up-log-shipping-to-the-recovery-farm"></a>Fase 6: de verzending van het logboek instellen voor de herstelfarm

Logboekverzending is het kritieke onderdeel voor het instellen van noodherstel in deze omgeving. U kunt de functie voor het verzenden van Logboeken gebruiken om automatisch transactielogbestanden te verzenden voor databases van een primaire databaseserver-instantie naar een secundaire databaseserver. Zie [logboekverzending configureren in SharePoint 2013](https://docs.microsoft.com/sharepoint/administration/configure-log-shipping)voor informatie over het instellen van logboekverzending. 
  
> [!IMPORTANT]
> Ondersteuning voor het verzenden van een logboek in SharePoint Server is beperkt tot bepaalde databases. Zie voor meer informatie [ondersteunde opties voor hoge beschikbaarheid en herstel voor noodgevallen voor SharePoint-databases (SharePoint 2013)](https://go.microsoft.com/fwlink/p/?LinkId=393121). 
  
## <a name="phase-7-validate-failover-and-recovery"></a>Fase 7: failover en herstel valideren

Het doel van deze laatste fase is om te verifiëren dat de oplossing voor noodgevallen als gepland werkt. Als u dit wilt doen, maakt u een failover-gebeurtenis waarmee de productiefarm wordt afgesloten en de herstelfarm wordt vervangen. U kunt een failover-scenario handmatig starten of met behulp van scripts.
  
In de eerste stap stopt u de binnenkomende gebruikersaanvragen voor farm services of inhoud. U kunt dit doen door DNS-vermeldingen uit te schakelen of door de front-endwebservers af te sluiten. Wanneer de farm ' down ' is, kunt u niet meer naar de herstelfarm overstappen.
  
### <a name="stop-log-shipping"></a>Stoppen met verzenden van logboek

U dient de logboekverzending te stoppen voordat u Farm herstel. Stop de verzending van Logboeken op de secundaire server in azure eerst, en Stop vervolgens op de primaire server on-premises. Gebruik het volgende script om de verzending van Logboeken op de secundaire server eerst te beëindigen en vervolgens op de primaire server. De namen van de databases in het script kunnen afwijken, afhankelijk van uw omgeving.
  
```
-- This script removes log shipping from the server.
-- Commands must be executed on the secondary server first and then on the primary server.

SET NOCOUNT ON
DECLARE  @PriDB nvarchar(max)
,@SecDB nvarchar(250)
,@PriSrv nvarchar(250)
,@SecSrv nvarchar(250)

Set @PriDB= ''
SET @PriDB = UPPER(@PriDB)
SET @PriDB = REPLACE(@PriDB, ' ', '')
SET @PriDB = '''' + REPLACE(@PriDB, ',', ''', ''') + ''''

Set @SecDB = @PriDB

Exec ( 'Select  ''exec master..sp_delete_log_shipping_secondary_database '' + '''''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_primary_secondary '' + '''''''' + prm.Primary_Database + '''''', '''''' + sec.Secondary_Server + '''''', '''''' + sec.Secondary_database + ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_primary_database '' + '''''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_secondary_primary '' + '''''''' + prm.primary_server + '''''', '''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

```

### <a name="restore-the-backups"></a>Back-ups terugzetten

Back-ups moeten worden teruggezet in de volgorde waarin ze zijn gemaakt. Voordat u een back-up van een bepaald logboek met transacties kunt terugzetten, moet u eerst de volgende vorige back-ups herstellen zonder dat u niet-doorgevoerde transacties hoeft te herstellen (dat wil zeggen via  `WITH NORECOVERY` ):
  
- De volledige back-up van een database en de meest recente back-up – herstel de back-ups, indien van toepassing, die worden gemaakt vóór de back-up van het desbetreffende transactielogboek. Voordat de nieuwste volledige of differentiële databaseback-up is gemaakt, werd in de database het model voor het volledige herstelmodel of een bulk logboek hersteld.
    
- Back-ups van alle transactielogboeken-herstel de back-up van de transactielogbestanden die zijn gemaakt na de volledige databaseback-up of voor de back-up van de logboekregistratie (als u er een terugzet. Back-ups van logboeken moeten worden toegepast in de volgorde waarin ze zijn gemaakt, zonder hiaten in de logboekketen.
    
Als u de inhoudsdatabase op de secundaire server wilt herstellen, zodat de sites worden weergegeven, verwijdert u alle databaseverbindingen voor herstel. Als u de database wilt herstellen, voert u de volgende SQL-instructie uit.
  
```
restore database WSS_Content with recovery

```

> [!IMPORTANT]
> Wanneer u T-SQL expliciet gebruikt, geeft u een waarde op **bij** Norecovery of **met Recovery** in elke herstel instructie om ambiguïteit te elimineren, dit is zeer belangrijk bij het schrijven van scripts. Als u de volledige en differentiële back-up wilt terugzetten, kunt u de transactielogboeken herstellen in SQL Server Management Studio. Aangezien logboekverzending al is gestopt, wordt de inhoud van de database in stand-by gezet, zodat u de status in volledige toegang moet wijzigen.
  
Klik in SQL Server Management Studio met de rechtermuisknop op de **WSS_Content** database, wijs **taken**  >  **herstellen**aan en klik vervolgens op **transactielogboek** (als u de volledige back-up niet hebt hersteld, is dit niet mogelijk). Zie[een back-up van een transactielogboek terugzetten (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=392778)voor meer informatie.
  
### <a name="crawl-the-content-source"></a>De inhoudsbron verkennen

U moet een volledige verkenning starten voor elke inhoudsbron om de zoek service te herstellen. Houd er rekening mee dat u bepaalde analyse-informatie verliest van de on-premises Farm, zoals zoek aanbevelingen. Voordat u begint met het maken van de volledige verkenning, gebruikt u de Windows PowerShell **-cmdlet herstellen-SPEnterpriseSearchServiceApplication** en geeft u de database van het logboek-verzonden en repliceerbare zoekbeheer op ** <GUID> Search_Service__DB_**. Met deze cmdlet krijgt u de zoekconfiguratie, het schema, de beheerde eigenschappen, regels en bronnen en wordt een standaardverzameling van de andere onderdelen gemaakt.
  
Voer de volgende stappen uit om een volledige verkenning te starten:
  
1. Ga in het SharePoint 2013 centraal beheer naar servicetoepassingen voor **toepassingen**  >  **Service Applications**  >  **beheren**, en klik vervolgens op de zoekservicetoepassing die u wilt verkennen.
    
2. Klik op de **zoekbeheer** pagina op **Inhoudsbronnen**, wijs de gewenste inhoudsbron aan, klik op de pijl en klik vervolgens op **volledige verkenning starten**.
    
### <a name="recover-farm-services"></a>Farm services herstellen

In de volgende tabel ziet u hoe u een service met Logboeken van databases met logboekregistratie kunt herstellen, de services die databases bevatten, maar die u niet adviseert om te herstellen met logboekverzending en de services die geen databases bevatten.
  
> [!IMPORTANT]
> Als u een on-premises SharePoint-database terugzet in de Azure-omgeving, worden geen SharePoint-Services hersteld die u niet al in azure handmatig hebt geïnstalleerd. 
  
**Tabel: overzicht van service toepassingsdatabase**

|**Deze services herstellen vanuit databases met logboekverzending**|**Deze services hebben databases, maar we raden u aan deze services te starten zonder hun databases te herstellen**|**Voor deze services worden geen gegevens opgeslagen in databases. deze services starten na een failover**|
|:-----|:-----|:-----|
| Service voor automatische vertaling <br/>  Service voor beheerde metagegevens <br/>  Secure Store-service <br/>  Gebruikersprofiel. (Alleen de databases profiel en Sociaalnetwerklabels worden ondersteund. De synchronisatiedatabase wordt niet ondersteund.) <br/>  Service-instellingen voor Microsoft SharePoint Foundation-abonnement <br/> | Gebruik en statusgegevens verzamelen <br/>  Servicestatus <br/>  Automatisering van Word <br/> | Excel Services <br/>  PerformancePoint Services <br/>  PowerPoint-conversie <br/>  Visio Graphics Service <br/>  Werkbeheer <br/> |
   
In het volgende voorbeeld ziet u hoe u de beheerde metagegevensservice terugzet van een database.
  
Hiermee wordt de bestaande Managed_Metadata_DB database gebruikt. Deze database is verzonden, maar er is geen actieve servicetoepassing op de secundaire Farm, dus moet de verbinding worden gemaakt nadat de servicetoepassing is geïnstalleerd.
  
Gebruik eerst  `New-SPMetadataServiceApplication` de schakeloptie en geef deze op  `DatabaseName` met de naam van de herstelde database.
  
Configureer vervolgens de nieuwe service toepassing voor beheerde metagegevens op de secundaire server als volgt:
  
- Name: service voor beheerde metagegevens
    
- Databaseserver: de naam van de database uit het verzonden transactielogboek
    
- Database naam: Managed_Metadata_DB
    
- Groep toepassingen: SharePoint-service toepassingen 
    
### <a name="manage-dns-records"></a>DNS-records beheren

U moet handmatig DNS-records maken zodat deze verwijzen naar uw SharePoint-farm.
  
In de meeste gevallen waarbij u meerdere front-endwebservers hebt, is het handig als u gebruik wilt maken van de taak Balancing Balancing in Windows Server 2012 of met een Load Balancer van hardware om aanvragen te distribueren tussen de web-front-end servers in uw farm. Netwerktaakverdeling kan ook zorgen voor een minder risico door aanvragen naar de andere servers te distribueren, als een van de web-front-endwebservers mislukt. 
  
Normaalgesproken wordt bij het instellen van Netwerktaakverdeling een enkelvoudig IP-adres toegewezen aan uw cluster. Vervolgens maakt u een DNS-host-record in de DNS-provider van uw netwerk dat naar het cluster verwijst. (Voor dit project wordt in azure een DNS-server in azure gezet voor een situatie met een on-premises datacenter-fout.) U kunt bijvoorbeeld een DNS-record maken in DNS-beheer in Active Directory,  `https://sharepoint.contoso.com` dat verwijst naar het IP-adres voor uw cluster waarop de taak wordt gebalanceerd.
  
Voor externe toegang tot uw SharePoint-farm kunt u een host record maken op een externe DNS-server met dezelfde URL die clients gebruiken op uw intranet (bijvoorbeeld `https://sharepoint.contoso.com` ) die verwijzen naar een extern IP-adres in uw firewall. (De beste manier om het gebruik van dit voorbeeld te vermijden is om gesplitste DNS in te stellen, zodat de interne DNS-server gezaghebbend is voor `contoso.com` en routeert rechtstreeks naar het SharePoint-farm cluster, in plaats van DNS-aanvragen te routeren naar uw externe DNS-server.) Vervolgens kunt u het externe IP-adres koppelen aan het interne IP-adres van uw on-premises cluster, zodat klanten de bronnen vinden waarnaar ze op zoek zijn.
  
U kunt hier bijvoorbeeld een aantal verschillende scenario's voor noodherstel uitvoeren:
  
 **Voorbeeld van scenario: de lokale SharePoint-farm is niet beschikbaar vanwege hardware-storing in de on-premises SharePoint-farm.** In dit geval kunt u, nadat u de stappen voor het overstappen naar de Azure SharePoint-farm hebt voltooid, Netwerktaakverdeling configureren op de front-end servers van de herstel SharePoint-farm, op dezelfde manier als met de on-premises farm. U kunt vervolgens de host-record in uw interne DNS-provider omleiden zodat deze verwijst naar het IP-adres van het cluster van de herstelfarm. Let op: het kan enige tijd duren voordat DNS-records in de cache van klanten worden vernieuwd en de herstelfarm wordt aanwijsd.
  
 **Voorbeeld van scenario: het on-premises datacenter gaat helemaal verloren.** Dit scenario kan worden veroorzaakt door een natuurlijke ramp, zoals een brand of overstroming. In dit geval zou voor een onderneming waarschijnlijk een secundair datacenter worden gehost in een ander gebied, en uw Azure-subnet met zijn eigen adreslijstservices en DNS. Zoals in het vorige scenario met rampen, kunt u uw interne en externe DNS-records omleiden zodat ze verwijzen naar de Azure SharePoint-farm. Let erop dat de doorgifte van DNS-records enige tijd in beslag neemt.
  
Als u siteverzamelingen met host name gebruikt, zoals aanbevolen in [host-name Architecture en implementatie van de siteverzameling (SharePoint 2013)](https://docs.microsoft.com/SharePoint/administration/host-named-site-collection-architecture-and-deployment), hebt u mogelijk verschillende siteverzamelingen in de SharePoint-farm die worden gehost bij unieke DNS-namen (bijvoorbeeld `https://sales.contoso.com` en `https://marketing.contoso.com` ). In dit geval kunt u DNS-records maken voor elke siteverzameling die verwijst naar het IP-adres van uw cluster. Nadat een aanvraag voor de front-end SharePoint-servers is bereikt, worden deze in de juiste siteverzameling doorgestuurd.
  
## <a name="microsoft-proof-of-concept-environment"></a>Microsoft-proef-en concept omgeving

Voor deze oplossing is een proef-en-concept omgeving ontwikkeld en getest. Het ontwerpdoel voor onze testomgeving is een SharePoint-farm implementeren en herstellen, wat we in een klant omgeving kunnen vinden. We hebben verschillende hypothesen gemaakt, maar we hebben wel gewist dat de farm alle functies die niet beschikbaar zijn in de box-box moet bieden zonder aanpassingen. De topologie is ontworpen voor hoge beschikbaarheid met de beste richtlijnen van de velden en de productgroep.
  
In de volgende tabel worden de Hyper-V virtuele machines beschreven die zijn gemaakt en geconfigureerd voor de on-premises testomgeving.
  
**Tabel: virtuele machines voor de on-premises test**

|**Server naam**|**Rol**|**Configuratie**|
|:-----|:-----|:-----|
|DC1  <br/> |Domeincontroller met Active Directory.  <br/> |Twee processors  <br/> From 512 MB tot 4 GB RAM  <br/> 1 x 127-GB harde schijf  <br/> |
|RING  <br/> |Server geconfigureerd met de rol RRAS-service (Remote Access service).  <br/> |Twee processors  <br/> 2-8 GB RAM  <br/> 1 x 127-GB harde schijf  <br/> |
|FS1  <br/> |Bestandsserver met shares voor back-ups en een eindpunt voor DFSR.  <br/> |Vier processors  <br/> 2-12 GB RAM  <br/> 1 x 127-GB harde schijf  <br/> 1 x 1-TB harde schijf (SAN)  <br/> 1 x 750-GB harde schijf  <br/> |
|SP-WFE1, SP-WFE2  <br/> |Front-endwebservers.  <br/> |Vier processors  <br/> 16 GB RAM  <br/> |
|SP-APP1, SP-APP2, SP-APP3  <br/> |Toepassingsservers.  <br/> |Vier processors  <br/> 2-16 GB RAM  <br/> |
|SP-SQL-HA1, SP-SQL-HA2  <br/> |Database servers, geconfigureerd met SQL Server 2012 AlwaysOn Availability groepen om hoge beschikbaarheid te geven. Voor deze configuratie worden SP-SQL-HA1 en SP-SQL-HA2 als de primaire en secundaire Replicas gebruikt.  <br/> |Vier processors  <br/> 2-16 GB RAM  <br/> |
   
In de volgende tabel worden drive configuraties beschreven voor de Hyper-V virtuele machines die zijn gemaakt en geconfigureerd voor de front-end webserver en toepassingsservers voor de on-premises testomgeving.
  
**Tabel: vereisten voor virtuele machines voor de front-end webserver en toepassingsservers voor de on-premises test**

|**Stationsletter**|**Grootte**|**Mapnaam**|**Route**|
|:-----|:-----|:-----|:-----|
|Wisselstroom  <br/> |80  <br/> |Systeemstation  <br/> |<DriveLetter>: \\ Program Files \\ Microsoft SQL Server\\  <br/> |
|N  <br/> |80  <br/> |Logboek station (40 GB)  <br/> |<DriveLetter>: \\ Program Files \\ Microsoft SQL Server \\ MSSQL10_50. MSSQL MSSQL- \\ \\ Data  <br/> |
|F3  <br/> |80  <br/> |Pagina (36 GB)  <br/> |<DriveLetter>: \\ Program Files \\ Microsoft SQL Server \\ MSSQL \\ Data  <br/> |
   
In de volgende tabel worden drive configuraties beschreven voor de virtuele machines van Hyper-V die zijn gemaakt en geconfigureerd voor de on-premises databaseservers. Ga op de pagina met de configuratie van de **database-engine** naar het tabblad **gegevensmappen** om de instellingen die in de volgende tabel worden weergegeven in te stellen en te bevestigen.
  
**Tabel: vereisten voor virtuele machines voor de on-premises test voor de databaseserver**

|**Stationsletter**|**Grootte**|**Mapnaam**|**Route**|
|:-----|:-----|:-----|:-----|
|Wisselstroom  <br/> |80  <br/> |Hoofdmap voor data directory  <br/> |<DriveLetter>: \\ Program Files \\ Microsoft SQL Server\\  <br/> |
|N  <br/> |500  <br/> |Gebruikersdatabase Directory  <br/> |<DriveLetter>: \\ Program Files \\ Microsoft SQL Server \\ MSSQL10_50. MSSQL MSSQL- \\ \\ Data  <br/> |
|F3  <br/> |500  <br/> |Logboekmap van gebruikersdatabase  <br/> |<DriveLetter>: \\ Program Files \\ Microsoft SQL Server \\ MSSQL10_50. MSSQL MSSQL- \\ \\ Data  <br/> |
|Fin  <br/> |500  <br/> |Tijdelijke DB-map  <br/> |<DriveLetter>: \\ Program Files \\ Microsoft SQL Server \\ MSSQL10_50. MSSQL MSSQL- \\ \\ Data  <br/> |
|T  <br/> |500  <br/> |Tijdelijke directory DB logboek  <br/> |<DriveLetter>: \\ Program Files \\ Microsoft SQL Server \\ MSSQL10_50. MSSQL MSSQL- \\ \\ Data  <br/> |
   
### <a name="setting-up-the-test-environment"></a>De testomgeving instellen

Tijdens de verschillende implementatiefasen heeft het TestTeam gewoonlijk eerst gewerkt aan de on-premises architectuur en vervolgens in de bijbehorende Azure-omgeving. Dit weerspiegelt de algemene in grote wereld bestaande gevallen waarin in-house productie Farms al actief zijn. Wat is er nog belangrijker, is dat u de huidige hoeveelheid werkbelasting, capaciteit en typische prestaties moet weten. Als u niet alleen een model voor noodherstel wilt maken dat aan de bedrijfsvereisten voldoet, moet u de grootte van de Recovery farmservers wijzigen om een minimaal serviceniveau te bieden. In een koud of warm standby-omgeving is een herstelfarm meestal kleiner dan een productiefarm. Nadat de herstelfarm stabiel en in productie is, kan de farm worden aangepast om aan de werklast vereisten te voldoen.
  
Onze testomgeving is in de volgende drie fasen geïmplementeerd:
  
- De hybride infrastructuur instellen
    
- Servers inrichten
    
- SharePoint-farms implementeren
    
#### <a name="set-up-the-hybrid-infrastructure"></a>De hybride infrastructuur instellen

In deze fase wordt het instellen van een domeinomgeving voor de on-premises Farm en voor de herstelfarm in Azure. Naast de normale taken die zijn gekoppeld aan de configuratie van Active Directory, heeft het TestTeam een routerings oplossing en een VPN-verbinding tussen de twee omgevingen uitgevoerd.
  
#### <a name="provision-the-servers"></a>Servers inrichten

Naast de farmservers werd het nodig om servers voor de domeincontrollers in te richten en een server te configureren voor het verwerken van RRAS en de site-to-site VPN. Er zijn twee bestandsservers ingericht voor de DFSR-service, en er zijn diverse clientcomputers ingericht voor testers.
  
#### <a name="deploy-the-sharepoint-farms"></a>SharePoint-farms implementeren

De SharePoint-Farms werden in twee fasen geïmplementeerd om de omgeving te stabiliseren en probleemoplossing, indien nodig. In de eerste fase is een farm geïmplementeerd op het minimum aantal servers voor elke laag van de topologie ter ondersteuning van de vereiste functionaliteit.
  
We hebben de databaseservers gemaakt met SQL Server voordat ze de SharePoint 2013-servers maken. Aangezien dit een nieuwe implementatie was, hebben we de beschikbare beschikbaarheidsgroepen gemaakt voordat u SharePoint implementeert. We hebben drie groepen gemaakt op basis van richtlijnen voor best practices van MCS. 
  
> [!NOTE]
> Maak tijdelijke databases op, zodat u beschikbaarheidsgroepen vóór de SharePoint-installatie kunt maken. Zie voor meer informatie [SQL Server 2012 AlwaysOn-Beschikbaarheidsgroepen configureren voor SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=517626)
  
We hebben de farm gemaakt en zijn in de volgende volgorde lid geworden van extra servers:
  
- Inrichten SP-SQL-HA1 en SP-SQL-HA2.
    
- Configureer AlwaysOn en maak de drie beschikbaarheidsgroepen voor de farm. 
    
- Het inrichten van SP-APP1 naar host Central Administration.
    
- Inrichten SP-WFE1 en SP-WFE2 om de gedistribueerde cache te hosten. 
    
We hebben de  _skipRegisterAsDistributedCachehost_ -parameter gebruikt toen **psconfig.exe** op de opdrachtregel werd uitgevoerd. Zie voor meer informatie [het artikel feeds en de gedistribueerde cache serviceplannen in SharePoint Server 2013](https://docs.microsoft.com/sharepoint/administration/plan-for-feeds-and-the-distributed-cache-service). 
  
We hebben de volgende stappen in de herstelomgeving herhaald:
  
- Het inrichten van AZ-SQL-HA1 en AZ-SQL-HA2.
    
- Configureer AlwaysOn en maak de drie beschikbaarheidsgroepen voor de farm.
    
- Het inrichten van AZ-APP1 naar host Central Administration.
    
- Het inrichten van AZ-WFE1 en AZ-WFE2 voor het hosten van de gedistribueerde cache.
    
Nadat we de gedistribueerde cache hebben geconfigureerd en de inhoud testen en de inhoud testen, is de fase twee van de implementatie gestart. U moet de niveaus uitschalen en de farmservers configureren voor ondersteuning van de topologie voor hoge beschikbaarheid die wordt beschreven in de farm architectuur.
  
In de volgende tabel worden de virtuele machines, subnetten en beschikbare beschikbaarheidssets beschreven die we hebben ingesteld voor onze herstelfarm.
  
**Tabel: infrastructuur van herstelfarm**

|**Server naam**|**Rol**|**Configuratie**|**Subnetobject**|**Beschikbare set**|
|:-----|:-----|:-----|:-----|:-----|
|spDRAD  <br/> |Domeincontroller met Active Directory  <br/> |Twee processors  <br/> From 512 MB tot 4 GB RAM  <br/> 1 x 127-GB harde schijf  <br/> |SP-ADservers  <br/> ||
|AZ-SP-FS  <br/> |Bestandsserver met shares voor back-ups en een eindpunt voor DFSR  <br/> | A5-configuratie: <br/>  Twee processors <br/>  14 GB RAM <br/>  1 x 127-GB harde schijf <br/>  1 x 135-GB harde schijf <br/>  1 x 127-GB harde schijf <br/>  1 x 150-GB harde schijf <br/> |SP-databaseservers  <br/> |DATA_SET  <br/> |
|AZ-WFE1, AZ-WFE2  <br/> |Front-end web servers  <br/> | A5-configuratie: <br/>  Twee processors <br/>  14 GB RAM <br/>  1 x 127-GB harde schijf <br/> |SP-webservers  <br/> |WFE_SET  <br/> |
|AZ-APP1, AZ-APP2, AZ-APP3  <br/> |Toepassingsservers  <br/> | A5-configuratie: <br/>  Twee processors <br/>  14 GB RAM <br/>  1 x 127-GB harde schijf <br/> |SP-applicationservers  <br/> |APP_SET  <br/> |
|AZ-SQL-HA1, AZ-SQL-HA2  <br/> |Database servers en primaire en secundaire replica's voor AlwaysOn-beschikbaarheidsgroepen  <br/> | A5-configuratie: <br/>  Twee processors <br/>  14 GB RAM <br/> |SP-databaseservers  <br/> |DATA_SET  <br/> |
   
### <a name="operations"></a>Operations

Nadat het TestTeam de farm omgevingen heeft gestabiliseerd en de functionele test is uitgevoerd, zijn de volgende bewerkingstaken gestart die nodig zijn om de on-premises Herstelomgeving te configureren:
  
- Volledige en differentiële back-ups configureren.
    
- Configureer DFSR op de bestandsservers waarmee transactie-logboeken worden overgebracht tussen de on-premises omgeving en de Azure-omgeving.
    
- Logboekverzending configureren op de primaire databaseserver.
    
- Verstabiliseer, Valideer en los logboekverzending op, indien nodig. Dit geldt ook voor het identificeren en documenteren van gedrag dat problemen kan veroorzaken, zoals netwerklatentie, wat het mislukken van het verzenden van Logboeken of het synchroniseren van DFSR-bestanden veroorzaakt.
    
### <a name="databases"></a>Databases

Onze testfailover hebben betrekking op de volgende databases: 
  
- WSS_Content
    
- ManagedMetadata
    
- Profiel-DB
    
- DATABASE synchroniseren
    
- Sociale DB
    
- Hub van inhoudstype (een database voor een gespecialiseerde hub voor syndicatie van inhoudstype)
    
## <a name="troubleshooting-tips"></a>Tips voor probleemoplossing

In deze sectie wordt uitgelegd welke problemen er zijn opgetreden tijdens de tests en de bijbehorende oplossingen. 
  
### <a name="using-the-term-store-management-tool-caused-the-error-the-managed-metadata-store-or-connection-is-currently-not-available"></a>Het hulpmiddel voor het beheer van het Termenarchief heeft de fout veroorzaakt: ' het beheerde Metagegevensarchief of de verbinding is op dit moment niet beschikbaar '.

Zorg ervoor dat het account van de groep toepassingen dat door de webtoepassing wordt gebruikt, de machtiging leestoegang tot Termenarchief is.
  
### <a name="custom-term-sets-are-not-available-in-the-site-collection"></a>Aangepaste termensets zijn niet beschikbaar in de siteverzameling

Ga na of de koppeling naar een ontbrekende servicetoepassing tussen de siteverzameling van uw inhoud en de hub inhoudstype ontbreekt. Zorg er ook voor dat deze optie is ingeschakeld onder het scherm **beheerde metagegevens van <site collection name> verbinding** : **deze servicetoepassing is de standaardopslag locatie voor leverancierspecifieke termensets.**
  
### <a name="the-get-adforest-windows-powershell-command-generates-the-error-the-term-get-adforest-is-not-recognized-as-the-name-of-a-cmdlet-function-script-file-or-operable-program"></a>De Windows PowerShell-opdracht Get-ADForest genereert de fout "de term Get-ADForest wordt niet herkend als de naam van een cmdlet, functie, scriptbestand of programma met een programma."

Bij het instellen van gebruikersprofielen hebt u de naam van het Active Directory-forest nodig. Zorg er in de wizard functies en onderdelen toevoegen voor dat u de Active Directory-module voor Windows PowerShell hebt ingeschakeld (onder de **Beheerprogramma's van extern Server>hulpmiddelen voor het beheer van rollen>AD DS en de sectie hulpmiddelen voor AD LDS** . Voer daarnaast de volgende opdrachten uit voordat u **Get-ADForest** gebruikt om ervoor te zorgen dat uw software afhankelijkheden worden geladen.
  
```
Import-module servermanager
Import-module activedirectory

```

### <a name="availability-group-creation-fails-at-starting-the-alwayson_health-xevent-session-on-server-name"></a>Maken van beschikbaarheidsgroepen mislukt bij het starten van de ' AlwaysOn_health ' XEvent-sessie op ' <server name> '

Zorg ervoor dat beide knooppunten van het failovercluster de status ' up ' hebben en niet ' onderbroken ' of ' stopgezet '. 
  
### <a name="sql-server-log-shipping-job-fails-with-access-denied-error-trying-to-connect-to-the-file-share"></a>Fout bij het verzenden van een SQL Server-logboek met de toegang tot de bestandsshare is mislukt

Zorg ervoor dat uw SQL Server-Agent wordt uitgevoerd onder netwerkreferenties, in plaats van de standaardreferenties.
  
### <a name="sql-server-log-shipping-job-indicates-success-but-no-files-are-copied"></a>De taak van de SQL Server-logboekverzending geeft een succes aan, maar er worden geen bestanden gekopieerd

Dit gebeurt omdat de standaard voorkeur voor het maken van back-ups voor een beschikbaarheidsgroep de **tweede**voorkeur heeft. Zorg ervoor dat u de verzendings taak voor logboeken uitvoert van de secundaire server voor de beschikbaarheidsgroep in plaats van de primaire. anders mislukt de taak op de stille manier. 
  
### <a name="managed-metadata-service-or-other-sharepoint-service-fails-to-start-automatically-after-installation"></a>De beheerde metagegevensservice (of andere SharePoint-Services) kan niet automatisch worden gestart na de installatie

Het kan enkele minuten duren voordat de service is begonnen, afhankelijk van de prestaties en de huidige belasting van uw SharePoint-Server. Klik handmatig op **Start** voor de service en zorg voor voldoende tijd voor het opstarten, waarbij de services af en toe worden vernieuwd om de status ervan te kunnen controleren. Voor het geval de service blijft stopgezet, schakelt u logboekregistratie van SharePoint in, probeert u de service opnieuw te starten en schakelt u het logboek op fouten in. Voor meer informatie raadpleegt [u Diagnostische gegevens vastleggen in SharePoint 2013](https://docs.microsoft.com/sharepoint/administration/configure-diagnostic-logging)
  
### <a name="after-changing-dns-to-the-azure-failover-environment-client-browsers-continue-to-use-the-old-ip-address-for-the-sharepoint-site"></a>Nadat u DNS hebt gewijzigd in de Azure-failoverconfiguratie, blijven de clientbrowsers het oude IP-adres voor de SharePoint-site gebruiken

Uw DNS-wijziging is mogelijk niet direct zichtbaar voor alle clients. Voer op een test client de volgende opdracht uit vanaf een opdrachtprompt met verhoogde bevoegdheid en probeer opnieuw toegang te krijgen tot de site.
  
```
Ipconfig /flushdns
```

## <a name="additional-resources"></a>Overige informatiebronnen

[Ondersteunde opties voor hoge beschikbaarheid en noodherstel voor SharePoint-databases](https://docs.microsoft.com/sharepoint/administration/supported-high-availability-and-disaster-recovery-options-for-sharepoint-databas)
  
[SQL Server 2012 always Availability groepen configureren voor SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=393122)
  
## <a name="see-also"></a>Zie ook

[Microsoft 365-oplossingen- en -architectuurcentrum](../solutions/solution-architecture-center.md)



