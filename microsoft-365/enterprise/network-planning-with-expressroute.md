---
title: Netwerkplanning met ExpressRoute voor Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/14/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 103208f1-e788-4601-aa45-504f896511cd
description: In dit artikel leert u over Azure ExpressRoute voor Office 365 en hoe u dit kunt gebruiken voor netwerkplanning.
ms.openlocfilehash: 440d4fafadd7e9b504dc4ffdac1123a2956ed798
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923574"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Netwerkplanning met ExpressRoute voor Office 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

ExpressRoute voor Office 365 biedt laag 3-connectiviteit tussen uw netwerk en de datacenters van Microsoft. De circuits maken gebruik van BGP-routeadvertenties (Border Gateway Protocol) van de front-endservers van Office 365. Vanuit het perspectief van uw on-premises apparaten wordt Azure ExpressRoute gezien als een alternatief voor internet als ze het juiste TCP/IP-pad naar Office 365 moeten selecteren.
  
Azure ExpressRoute voegt een direct pad toe aan een specifieke set ondersteunde functies en services die worden aangeboden door Office 365-servers in de datacenters van Microsoft. Azure ExpressRoute vervangt geen internetverbinding met Microsoft-datacenters of basisinternetservices, zoals domeinnaamresolutie. Azure ExpressRoute en uw internetcircuits moeten beveiligd en redundant zijn.
  
In de volgende tabel worden enkele verschillen belicht tussen internet- en Azure ExpressRoute-verbindingen in de context van Office 365.

|**Verschillen in netwerkplanning**|**Internetverbinding**|**ExpressRoute-netwerkverbinding**|
|:-----|:-----|:-----|
| Toegang tot vereiste internetservices, waaronder;  <br/>  DNS-naamresolutie  <br/>  Verificatie van intrekking van certificaten  <br/>  Content Delivery Networks (CDN's)  <br/> |Ja  <br/> |Aanvragen naar de DNS- en/of CDN-infrastructuur van Microsoft kunnen gebruikmaken van het ExpressRoute-netwerk.  <br/> |
| Toegang tot Office 365-services, waaronder;  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype voor Bedrijven Online  <br/>  Office in een browser  <br/>  Office 365 Portal en Verificatie  <br/> |Ja, alle toepassingen en functies  <br/> |Ja, [specifieke toepassingen en functies](./urls-and-ip-address-ranges.md) <br/> |
|On-premises beveiliging bij perimeter.  <br/> |Ja  <br/> |Ja  <br/> |
|Planning voor hoge beschikbaarheid.  <br/> |Failover naar een alternatieve internetverbinding  <br/> |Failover naar een alternatieve ExpressRoute-verbinding  <br/> |
|Directe verbinding met een voorspelbaar netwerkprofiel.  <br/> |Nee  <br/> |Ja  <br/> |
|IPv6-connectiviteit.  <br/> |Ja  <br/> |Ja  <br/> |

Vouw de onderstaande titels uit voor meer richtlijnen voor netwerkplanning. We hebben ook een 10-delige [Azure ExpressRoute voor Office 365 Training-reeks](https://channel9.msdn.com/series/aer) opgenomen die dieper gaat.

## <a name="existing-azure-expressroute-customers"></a>Bestaande Azure ExpressRoute-klanten

Als u een bestaand Azure ExpressRoute-circuit gebruikt en Office 365-connectiviteit via dit circuit wilt toevoegen, moet u het aantal circuits, uitgangslocaties en de grootte van de circuits bekijken om ervoor te zorgen dat deze voldoen aan de behoeften van uw Office 365-gebruik. De meeste klanten hebben extra bandbreedte nodig en voor veel klanten zijn extra circuits nodig.
  
Als u toegang wilt tot Office 365 via uw bestaande Azure ExpressRoute-circuits, configureert u de [routefilters](/azure/expressroute/how-to-routefilter-portal) om ervoor te zorgen dat de Office 365-services toegankelijk zijn.
  
Het Azure ExpressRoute-abonnement is klantgericht, wat betekent dat abonnementen zijn gekoppeld aan klanten. Als klant hebt u meerdere Azure ExpressRoute-circuits en hebt u toegang tot veel Microsoft-cloudbronnen via deze circuits. U kunt er bijvoorbeeld voor kiezen om toegang te krijgen tot een door Azure gehoste virtuele machine, een Office 365-testten tenant en een Office 365-productieten tenant via een paar redundante Azure ExpressRoute-circuits.
  
In deze tabel worden de twee typen peeringrelaties beschreven die u via uw circuits kunt implementeren.

|**Peering-relatie**|**Azure Private**|**Microsoft**|
|:-----|:-----|:-----|
|**Services** <br/> |IaaS: Azure Virtual Machines  <br/> |PaaS: Openbare Azure-services  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Verbindingsinitiatie**** <br/> |Klant-naar-Microsoft  <br/> Microsoft-to-Customer  <br/> |Klant-naar-Microsoft  <br/> Microsoft-to-Customer  <br/> |
|**QoS-ondersteuning** <br/> |Geen QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1 </sup> QoS ondersteunt Skype voor Bedrijven alleen op dit moment.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Bandbreedteplanning voor Azure ExpressRoute

Elke Office 365-klant heeft unieke bandbreedtebehoeften, afhankelijk van het aantal personen op elke locatie, hoe actief ze zijn met elke Office 365-toepassing en andere factoren, zoals het gebruik van on-premises of hybride apparatuur en netwerkbeveiligingsconfiguraties.
  
Als u te weinig bandbreedte hebt, leidt dit tot congestie, doorgifte van gegevens en onvoorspelbare vertragingen. Als u te veel bandbreedte hebt, worden er onnodige kosten gemaakt. In een bestaand netwerk wordt vaak naar bandbreedte verwezen in termen van de hoeveelheid beschikbare hoofdruimte op het circuit als percentage. Het hebben van 10% hoofdruimte zal waarschijnlijk leiden tot congestie en 80% hoofdruimte betekent meestal onnodige kosten. Standaardtoewijzingen voor hoofdruimte zijn 20% tot 50%.
  
Als u het juiste bandbreedteniveau wilt vinden, kunt u het beste uw bestaande netwerkverbruik testen. Dit is de enige manier om een werkelijke mate van gebruik en behoefte te krijgen, aangezien elke netwerkconfiguratie en -toepassingen op bepaalde manieren uniek zijn. Bij het meten wilt u veel aandacht besteden aan het totale bandbreedteverbruik, latentie en TCP-congestie om inzicht te krijgen in uw netwerkbehoeften.
  
Nadat u een geschatte basislijn hebt met alle netwerktoepassingen, test u Office 365 met een kleine groep die de verschillende profielen van personen in uw organisatie bevat om het werkelijke gebruik te bepalen en gebruikt u de twee metingen om de bandbreedte te schatten die u nodig hebt voor elke kantoorlocatie. Als er latentie- of TCP-congestieproblemen worden aangetroffen in uw testen, moet u mogelijk het uitgangsverkeer dichter bij de personen verplaatsen die Office 365 gebruiken of intensief netwerkscans verwijderen, zoals SSL-ontsleuteling/inspectie.
  
Al onze aanbevelingen voor welk type netwerkverwerking wordt aanbevolen, zijn van toepassing op zowel ExpressRoute- als internetcircuits. Hetzelfde geldt voor de rest van de richtlijnen op onze [prestatieafstemmingssite.](./network-planning-and-performance.md)
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Beveiligingsbesturingselementen toepassen op Azure ExpressRoute voor Office 365-scenario's

Het beveiligen van Azure ExpressRoute-connectiviteit begint met dezelfde principes als het beveiligen van internetverbinding. Veel klanten kiezen ervoor om netwerk- en perimeterbesturingselementen te implementeren langs het ExpressRoute-pad dat hun on-premises netwerk verbindt met Office 365 en andere Microsoft-clouds. Deze besturingselementen kunnen firewalls, toepassingsproxies, preventie van gegevenslekken, detectie van indringing, inbraakpreventiesystemen, en dergelijke omvatten. In veel gevallen passen klanten verschillende niveaus van besturingselementen toe op verkeer dat wordt gestart vanuit on-premises naar Microsoft gaan, versus verkeer dat wordt gestart vanuit Microsoft naar een on-premises klantnetwerk, versus verkeer dat wordt gestart vanuit on-premises naar een algemene internetbestemming.
  
Hier ziet u enkele voorbeelden van het integreren van beveiliging met het [ExpressRoute-connectiviteitsmodel](/azure/expressroute/expressroute-connectivity-models) dat u wilt implementeren.

|**ExpressRoute-integratieoptie**|**Netwerkbeveiligingsperimetermodel**|
|:-----|:-----|
|Co-located at a cloud exchange  <br/> |Installeer nieuwe of maak gebruik van bestaande beveiligings-/perimeterinfrastructuur in de colocatielocatie waar de ExpressRoute-verbinding tot stand is gebracht.  <br/> Maak uitsluitend gebruik van colocatie-faciliteit voor routerings-/interconnectiedoeleinden en trek verbindingen terug van colocatie-faciliteit naar de on-premises beveiligings-/perimeterinfrastructuur.  <br/> |
|Point-to-Point Ethernet  <br/> |Beëindig de Point-to-Point ExpressRoute-verbinding op de bestaande on-premises beveiligings-/perimeterinfrastructuurlocatie.  <br/> Installeer nieuwe beveiligings-/perimeterinfrastructuur die specifiek is voor het ExpressRoute-pad en beëindig de Point-to-Point-verbinding daar.  <br/> |
|Any-to-Any IPVPN  <br/> |Maak gebruik van een bestaande on-premises beveiligings-/perimeterinfrastructuur op alle locaties die naar de IPVPN gaan die wordt gebruikt voor ExpressRoute voor Office 365-connectiviteit.  <br/> Hairpin de IPVPN die wordt gebruikt voor ExpressRoute voor Office 365 naar specifieke on-premises locaties die zijn aangewezen om te fungeren als de beveiliging/perimeter.  <br/> |

Sommige serviceproviders bieden ook beheerde beveiligings- en perimeterfunctionaliteit als onderdeel van hun integratieoplossingen met Azure ExpressRoute.
  
Bij het overwegen van de topologiepositie van de netwerk-/beveiligingsperimeteropties die worden gebruikt voor ExpressRoute voor Office 365-verbindingen, zijn er andere aandachtspunten.
  
- De diepte en het type netwerk-/beveiligingsbesturingselementen kunnen van invloed zijn op de prestaties en schaalbaarheid van de Office 365-gebruikerservaring.

- Uitgaande (on-premises- Microsoft) en \> inkomende stromen (Microsoft- \> on-premises) [indien ingeschakeld] kunnen verschillende vereisten hebben. Deze zijn waarschijnlijk anders dan Uitgaande naar algemene internetbestemmingen.

- Office 365-vereisten voor poorten/protocollen en benodigde IP-subnetten zijn hetzelfde, ongeacht of het verkeer wordt gerouteerd via ExpressRoute voor Office 365 of via internet.

- Topologische plaatsing van het klantnetwerk/beveiligingsbesturingselement bepaalt het uiteindelijke end-to-end-netwerk tussen de gebruiker en de Office 365-service en kan een aanzienlijke invloed hebben op de netwerklatentie en congestie.

- Klanten worden aangeraden hun beveiligings-/perimetertopologie te ontwerpen voor gebruik met ExpressRoute voor Office 365 in overeenstemming met best practices voor redundantie, hoge beschikbaarheid en herstel na nood.

Hier ziet u een voorbeeld van Woodgrove Bank die de verschillende Azure ExpressRoute-connectiviteitsopties vergelijkt met de hierboven besproken perimeterbeveiligingsmodellen.
  
### <a name="example-1-securing-azure-expressroute"></a>Voorbeeld 1: Azure ExpressRoute beveiligen
  
Woodgrove Bank overweegt Azure ExpressRoute te implementeren en na het plannen van de optimale architectuur voor routering met ExpressRoute voor [Office 365](routing-with-expressroute.md) en na het gebruik van de bovenstaande richtlijnen om de bandbreedtevereisten te begrijpen, bepalen ze de beste methode voor het beveiligen van de perimeter.
  
Voor Woodgrove, een multi-nationale organisatie met locaties op meerdere continenten, moet de beveiliging alle perimeters overspannen. De optimale connectiviteitsoptie voor Woodgrove is een multipuntverbinding met meerdere peeringlocaties over de hele wereld om te voldoen aan de behoeften van hun werknemers op elk continent. Elk continent bevat redundante Azure ExpressRoute-circuits op het continent en de beveiliging moet al deze circuits omvatten.
  
De bestaande infrastructuur van Woodgrove is betrouwbaar en kan het extra werk verwerken, waardoor Woodgrove Bank de infrastructuur kan gebruiken voor de beveiliging van Azure ExpressRoute en internetperimeters. Als dit niet het geval was, kon Woodgrove ervoor kiezen om extra apparatuur aan te schaffen om hun bestaande apparatuur aan te vullen of om een ander type verbinding af te handelen.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Hoge beschikbaarheid en failover met Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Het is raadzaam om ten minste twee actieve circuits van elk uitgang met ExpressRoute in te stellen bij uw ExpressRoute-provider. Dit is de meest voorkomende plaats waar we fouten voor klanten zien en u kunt dit eenvoudig voorkomen door een paar actieve/actieve ExpressRoute-circuits in te stellen. We raden ook ten minste twee actieve/actieve internetcircuits aan, omdat veel Office 365-services alleen via internet beschikbaar zijn.
  
Binnen het uitgangspunt van uw netwerk zijn veel andere apparaten en circuits die een essentiële rol spelen in de manier waarop mensen beschikbaarheid waarnemen. Deze gedeelten van uw connectiviteitsscenario's worden niet gedekt door ExpressRoute of Office 365-sla's, maar ze spelen een essentiële rol in het einde van de beschikbaarheid van de service, zoals ervaren door personen in uw organisatie.
  
Richt u op de personen die Office 365 gebruiken en gebruiken. Als een fout van een onderdeel van invloed is op de ervaring van personen met de service, moet u zoeken naar manieren om het totale percentage van de getroffen personen te beperken. Als een failovermodus operationeel complex is, moet u rekening houden met de ervaring van de personen van lange tijd om te herstellen en te zoeken naar operationeel eenvoudige en geautomatiseerde failovermodi.
  
Buiten uw netwerk hebben Office 365, ExpressRoute en uw ExpressRoute-provider allemaal verschillende beschikbaarheidsniveaus.
  
### <a name="service-availability"></a>Beschikbaarheid van service
  
- Office 365-services worden gedekt [](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)door goed gedefinieerde serviceniveauovereenkomsten, waaronder uptime- en beschikbaarheidsgegevens voor afzonderlijke services. Een van de redenen dat Office 365 dergelijke hoge servicebeschikbaarheidsniveaus kan behouden, is de mogelijkheid voor afzonderlijke onderdelen om naadloos te mislukken tussen de vele Microsoft-datacenters, met behulp van het wereldwijde Microsoft-netwerk. Deze failover strekt zich uit van het datacenter en het netwerk tot de meerdere internet-uitgangspunten en maakt failover naadloos mogelijk vanuit het perspectief van de personen die de service gebruiken.

- ExpressRoute biedt een SLA voor [99,9%](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) beschikbaarheid op afzonderlijke toegewezen circuits tussen de Microsoft Network Edge en de ExpressRoute-provider of partnerinfrastructuur. Deze serviceniveaus worden toegepast op het ExpressRoute-circuitniveau, dat bestaat uit twee onafhankelijke [interconnecten](/azure/expressroute/expressroute-introduction) tussen de redundante Microsoft-apparatuur en de netwerkproviderapparatuur op elke peeringlocatie.

### <a name="provider-availability"></a>Beschikbaarheid van provider
  
- De service-arrangementen van Microsoft stoppen bij uw ExpressRoute-provider of -partner. Dit is ook de eerste plaats waar u keuzes kunt maken die van invloed zijn op uw beschikbaarheidsniveau. U moet nauwkeurig de architectuur-, beschikbaarheids- en tolerantiekenmerken evalueren die uw ExpressRoute-provider biedt tussen de netwerkperimeter en de verbinding van uw providers op elke Microsoft-peeringlocatie. Besteed veel aandacht aan zowel de logische als fysieke aspecten van redundantie, peeringapparatuur, door de provider geleverde WAN-circuits en eventuele aanvullende services voor toegevoegde waarde, zoals NAT-services of beheerde firewalls.

### <a name="designing-your-availability-plan"></a>Uw beschikbaarheidsplan ontwerpen
  
We raden u ten zeerste aan om hoge beschikbaarheid en tolerantie te plannen en te ontwerpen in uw end-to-endconnectiviteitsscenario's voor Office 365. Een ontwerp moet bestaan uit;
  
- geen enkele storingspunt, inclusief internet- en ExpressRoute-circuits.

- het minimaliseren van het aantal personen dat wordt beïnvloed en de duur van die impact voor de meest verwachte storingen.

- optimaliseren voor eenvoudig, herhaalbaar en automatisch herstelproces van de meest verwachte foutmodi.

- ondersteuning van de volledige eisen van uw netwerkverkeer en -functionaliteit via redundante paden, zonder aanzienlijke degradatie.

Uw connectiviteitsscenario's moeten een netwerktopologie bevatten die is geoptimaliseerd voor meerdere onafhankelijke en actieve netwerkpaden naar Office 365. Dit levert een betere end-to-endbeschikbaarheid op dan een topologie die alleen is geoptimaliseerd voor redundantie op individueel apparaat- of apparatuurniveau.
  
> [!TIP]
> Als uw gebruikers zijn verdeeld over meerdere continenten of geografische regio's en elk van deze locaties via redundante WAN-circuits verbinding maakt met één on-premises locatie waar één ExpressRoute-circuit zich bevindt, hebben uw gebruikers minder beschikbaarheid van end-to-end-service dan een netwerktopologieontwerp met onafhankelijke ExpressRoute-circuits die de verschillende regio's verbinden met de dichtstbijzijnde peeringlocatie.
  
Het is raadzaam ten minste twee ExpressRoute-circuits in te stellen met elk circuit dat verbinding maakt met een andere geografische peeringlocatie. U moet dit actieve paar circuits inrichten voor elke regio waar personen ExpressRoute-connectiviteit voor Office 365-services gebruiken. Hierdoor kan elke regio verbonden blijven tijdens een ramp die van invloed is op een belangrijke locatie, zoals een datacenter of peeringlocatie. Als u deze configureert als actief/actief, kan het eindgebruikersverkeer worden verdeeld over meerdere netwerkpaden. Hierdoor wordt het bereik beperkt van personen die worden getroffen tijdens uitval van apparaat- of netwerkapparatuur.
  
We raden u af om één ExpressRoute-circuit met internet als back-up te gebruiken.
  
### <a name="example-2-failover-and-high-availability"></a>Voorbeeld 2: Failover en Hoge beschikbaarheid
  
Het multi-geografische ontwerp van Woodgrove Bank heeft een overzicht van routering, bandbreedte, beveiliging ondergaan en moet nu een hoge beschikbaarheidsbeoordeling ondergaan. Woodgrove denkt dat hoge beschikbaarheid drie categorieën beslaat. tolerantie, betrouwbaarheid en redundantie.
  
Met tolerantie kan Woodgrove snel herstellen van fouten. Met betrouwbaarheid kan Woodgrove een consistent resultaat binnen het systeem bieden. Met redundantie kan Woodgrove tussen een of meer gespiegelde exemplaren van de infrastructuur gaan.
  
In elke edgeconfiguratie heeft Woodgrove redundante Firewalls, Proxies en IDS. Voor Noord-Amerika heeft Woodgrove een configuratie met één rand in het datacenter van Dallas en een andere randconfiguratie in het datacenter van Virginia. De redundante apparatuur op elke locatie biedt tolerantie voor die locatie.
  
De netwerkconfiguratie bij Woodgrove Bank is gebaseerd op een aantal belangrijke principes:
  
- Binnen elke geografische regio zijn er meerdere Azure ExpressRoute-circuits.

- Elk circuit in een regio kan al het netwerkverkeer in die regio ondersteunen.

- Routering geeft duidelijk de voorkeur aan een of het andere pad, afhankelijk van beschikbaarheid, locatie, en ga zo maar door.

- Failover tussen Azure ExpressRoute-circuits gebeurt automatisch zonder extra configuratie of actie vereist door Woodgrove.

- Failover tussen internetcircuits gebeurt automatisch zonder extra configuratie of actie vereist door Woodgrove.

In deze configuratie, met redundantie op fysiek en virtueel niveau, kan Woodgrove Bank op een betrouwbare manier lokale tolerantie, regionale tolerantie en globale tolerantie bieden. Woodgrove heeft deze configuratie gekozen na het evalueren van één Azure ExpressRoute-circuit per regio en de mogelijkheid om over te gaan naar internet.
  
Als Woodgrove niet meerdere Azure ExpressRoute-circuits per regio kon hebben, zou routeringsverkeer van oorsprong uit Noord-Amerika naar het Azure ExpressRoute-circuit in Asia Pacific een onacceptabele latentie toevoegen en de vereiste DNS-forwarderconfiguratie complexiteit toevoegt.
  
Gebruik maken van internet als back-upconfiguratie wordt niet aanbevolen. Hiermee wordt het betrouwbaarheidsbeginsel van Woodgrove doorgesneden, wat resulteert in een inconsistente ervaring met de verbinding. Daarnaast is handmatige configuratie vereist voor failover, gezien de BGP-advertenties die zijn geconfigureerd, NAT-configuratie, DNS-configuratie en de proxyconfiguratie. Deze toegevoegde failover-complexiteit verhoogt de tijd om te herstellen en vermindert de mogelijkheid om de betrokken stappen te diagnosticeren en op te lossen.
  
Hebt u nog vragen over het plannen en implementeren van verkeersbeheer of Azure ExpressRoute? Lees de rest van onze [netwerk- en prestatie-richtlijnen](./network-planning-and-performance.md) of de [veelgestelde vragen over Azure ExpressRoute.](/azure/expressroute/expressroute-faqs)
  
## <a name="working-with-azure-expressroute-providers"></a>Werken met Azure ExpressRoute-providers
<a name="BKMK_high-availability"> </a>

Kies de locaties van uw circuits op basis van uw bandbreedte, latentie, beveiliging en planning met hoge beschikbaarheid. Als u de optimale locaties weet die u wilt plaatsen, bekijkt u de huidige lijst [met providers per regio.](/azure/expressroute/expressroute-locations)
  
Werk samen met uw provider of providers om de beste connectiviteitsopties, point-to-point, multi-point of gehost te selecteren. Houd er rekening mee dat u de connectiviteitsopties kunt combineren en aanpassen, zolang de bandbreedte en andere redundante onderdelen uw routerings- en beschikbaarheidsontwerp ondersteunen.
  
Met deze korte koppeling kunt u teruggaan: [https://aka.ms/planningexpressroute365]()
  
## <a name="related-topics"></a>Verwante onderwerpen
<a name="BKMK_high-availability"> </a>

[Office 365-netwerkverbinding beoordelen](assessing-network-connectivity.md)
  
[Azure ExpressRoute voor Office 365](azure-expressroute.md)
  
[ExpressRoute voor Office 365-connectiviteit beheren](managing-expressroute-for-connectivity.md)
  
[Routeren met ExpressRoute voor Office 365](routing-with-expressroute.md)
  
[ExpressRoute implementeren voor Office 365](implementing-expressroute.md)
  
[BGP-community's gebruiken in ExpressRoute voor Office 365-scenario's](bgp-communities-in-expressroute.md)
  
[Mediakwaliteit en prestaties van de netwerkverbinding in Skype voor Bedrijven Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Uw netwerk instellen voor Skype voor Bedrijven Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute en QoS in Skype voor Bedrijven Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Oproepstroom met ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Office 365-prestatieafstemming met behulp van basislijnen en prestatiegeschiedenis](performance-tuning-using-baselines-and-history.md)
  
[Prestatieproblemen met Office 365 oplossen: planning](performance-troubleshooting-plan.md)
  
[URL's en IP-adresbereiken voor Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Aanpassing van Office 365-netwerk en -prestaties](network-planning-and-performance.md)
  
[Veelgestelde vragen over Office 365-eindpunten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)