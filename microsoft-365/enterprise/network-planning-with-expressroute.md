---
title: Netwerk planning met ExpressRoute voor Office 365
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
description: In dit artikel vindt u meer informatie over Azure ExpressRoute voor Office 365 en hoe u deze kunt gebruiken voor netwerk planning.
ms.openlocfilehash: 7159640adeae1b4a4ff364683f939a97b6e06a92
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689264"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Netwerk planning met ExpressRoute voor Office 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

ExpressRoute voor Office 365 biedt laag 3 connectiviteit tussen uw netwerk en Microsoft-datacenters. Voor de circuits wordt gebruikgemaakt van BGP-route reclame (Border Gateway Protocol) voor de front-end servers van Office 365. Vanuit het perspectief van uw on-premises apparaten, wanneer ze het juiste TCP/IP-pad naar Office 365 willen selecteren, wordt Azure ExpressRoute beschouwd als alternatief voor het internet.
  
Azure ExpressRoute voegt een rechtstreeks pad toe aan een specifieke set ondersteunde functies en services die worden aangeboden door Office 365-servers in de datacenters van Microsoft. In azure ExpressRoute worden geen Internet connectiviteit vervangen door Microsoft-datacenters of basis Internet Services, zoals Domain Name Resolution. Azure ExpressRoute en uw Internet circuits moeten worden beveiligd en worden overbodig.
  
De volgende tabel geeft een aantal verschillen aan tussen de Internet-en Azure ExpressRoute-verbindingen in de context van Office 365.

|**Verschillen in netwerk planning**|**Netwerkverbinding met Internet**|**ExpressRoute-netwerkverbinding**|
|:-----|:-----|:-----|
| Toegang tot de vereiste Internet Services, met inbegrip van:  <br/>  DNS-naamomzetting  <br/>  Verificatie van certificaatintrekking  <br/>  Netwerken voor content levering (Cdn's)  <br/> |Ja  <br/> |Voor aanvragen van de Microsoft-eigen DNS-en/of CDN-infrastructuur wordt het ExpressRoute-netwerk gebruikt.  <br/> |
| Toegang tot Office 365-Services, met inbegrip van:  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype voor Bedrijven Online  <br/>  Office in een browser  <br/>  Portal en authenticatie van Office 365  <br/> |Ja, alle toepassingen en functies  <br/> |Ja, [specifieke toepassingen en functies](https://aka.ms/o365endpoints) <br/> |
|On-premises veiligheid op de omtrek.  <br/> |Ja  <br/> |Ja  <br/> |
|Planning van hoge beschikbaarheid.  <br/> |Failover naar een andere netwerkverbinding met Internet  <br/> |Failover naar een alternatieve ExpressRoute-verbinding  <br/> |
|Directe verbinding met een voorspelbaar netwerkprofiel.  <br/> |Nee  <br/> |Ja  <br/> |
|IPv6-connectiviteit.  <br/> |Ja  <br/> |Ja  <br/> |

Vouw de onderstaande titels uit voor meer informatie over netwerk planning. We hebben ook een 10-Part [Azure ExpressRoute-trainings serie voor Office 365 voor Office](https://channel9.msdn.com/series/aer) .

## <a name="existing-azure-expressroute-customers"></a>Bestaande Azure ExpressRoute-klanten

Als u een bestaand Azure ExpressRoute-circuit gebruikt en een Office 365-verbinding via dit circuit wilt toevoegen, moet u het aantal circuits, de uitgangs locaties en de grootte van de circuits bekijken om ervoor te zorgen dat ze voldoen aan de behoeften van het Office 365-gebruik. Voor de meeste klanten is extra bandbreedte vereist en er zijn veel extra circuits vereist.
  
Als u toegang tot Office 365 wilt inschakelen via uw bestaande Azure ExpressRoute-circuits, [configureert u de routefilters](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) om ervoor te zorgen dat de Office 365-services toegankelijk zijn.
  
Het Azure ExpressRoute-abonnement is door de klantgerichte, wat wil zeggen dat een abonnement is gekoppeld aan klanten. Als klant kunt u meerdere Azure ExpressRoute-circuits hebben en veel Cloud bronnen van Microsoft gebruiken voor die circuits. U kunt bijvoorbeeld kiezen voor toegang tot een virtuele Azure-computer met host, een Office 365-test Tenant en een Office 365-productie-Tenant via een paar redundante Azure ExpressRoute-circuits.
  
In deze tabel vindt u een overzicht van de twee soorten peer-relaties die u kunt kiezen voor uw circuits.

|**Peering-relatie**|**Azure private**|**Microsoft**|
|:-----|:-----|:-----|
|**Reparatie** <br/> |IaaS: virtuele machines van Azure  <br/> |PaaS: Azure openbare Services  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Start verbinding * * * * <br/> |Klant-naar-Microsoft  <br/> Microsoft-to-Customer  <br/> |Klant-naar-Microsoft  <br/> Microsoft-to-Customer  <br/> |
|**QoS-ondersteuning** <br/> |Geen QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1 </sup> QoS biedt op dit moment alleen ondersteuning voor Skype voor bedrijven.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Bandbreedte planning voor Azure ExpressRoute

Elke Office 365-klant heeft een unieke bandbreedte behoefte, afhankelijk van het aantal personen op elke locatie, hoe dit actief is bij elke Office 365-toepassing, en andere factoren zoals het gebruik van on-premises of hybride apparatuur en beveiligingsconfiguraties van een netwerk.
  
Als er te weinig bandbreedte is, levert dit een vertraging, herverzending van gegevens op en onvoorspelbare vertragingen. Als er te veel bandbreedte is, levert dit overbodige kosten op. In een bestaand netwerk wordt de bandbreedte vaak aangeduid als een percentage van de beschikbare ruimte op het circuit. Met een oplopende duur van 10% met een oplopende duur en een percentage van 80% moet u meestal onnodig kosten in rekening brengen. Standaardtoewijzingen van bestemmings doel zijn 20% naar 50%.
  
Om het juiste bandbreedte niveau te vinden, is het beste mechanisme om uw bestaande netwerkverbruik te testen. Dit is de enige manier om een echte hoeveelheid gebruik te kunnen maken en die nodig hebt voor elke netwerkconfiguratie en toepassingen op een unieke manier. Wanneer u de waardering wilt meten, moet u de aandacht vestigen op het totale aantal bandbreedte, latentie en TCP-congestie om inzicht te krijgen in uw netwerkbehoeften.
  
Wanneer u een geschatte basislijn hebt die alle netwerktoepassingen omvat, test u Office 365 met een kleine groep die de verschillende profielen van personen in uw organisatie omvat voor het bepalen van het werkelijke gebruik en gebruikt u de twee maten voor de hoeveelheid bandbreedte die u nodig hebt voor elke kantoorlocatie. Als er vertragings-en TCP-congestie problemen zijn opgetreden bij het testen, moet u mogelijk de uitgang dichter bij de gebruikers van Office 365 of de intensief netwerkscan zoals SSL-decodering/inspectie verwijderen.
  
Al onze aanbevelingen met betrekking tot het type netwerk verwerking is geschikt voor zowel ExpressRoute als Internet circuits. Dit geldt voor de rest van de instructies op onze site voor het [afstemmen van prestaties](https://aka.ms/tune).
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Beveiligingscontroles toepassen op Azure ExpressRoute voor Office 365-scenario's

Het beveiligen van Azure ExpressRoute-connectiviteit begint met dezelfde principes als het beveiligen van Internet verbindingen. Veel klanten kiezen voor distributie van netwerk-en perimeter besturingselementen langs het ExpressRoute-pad waarmee hun on-premises netwerk wordt verbonden met Office 365 en andere Microsoft-Clouds. Deze besturingselementen kunnen firewalls, toepassings proxy's, preventie van gegevens lekkage, detectie van indringers, het opsporen van systemen, enzovoort bevatten. In veel gevallen passen klanten verschillende niveaus van besturingselementen toe op verkeer van on-premises naar Microsoft, en verkeer dat werd geïnitieerd via Microsoft naar het on-premises netwerk van de klant, en verkeer dat via on-premises wordt gestart naar een algemene Internet bestemming.
  
Hier volgen enkele voorbeelden van het integreren van de beveiliging met het [ExpressRoute-verbindings model](https://docs.microsoft.com/azure/expressroute/expressroute-connectivity-models) dat u wilt implementeren.

|**Optie voor ExpressRoute-integratie**|**Perimeter model voor netwerkbeveiliging**|
|:-----|:-----|
|Mede bevindt zich in een wissel van een Cloud  <br/> |De nieuwe of de bestaande infrastructuur van beveiligings-en perimeternetwerken in de faciliteit voor co-locatie installeren of de ExpressRoute-verbinding tot stand brengen.  <br/> Gebruik de faciliteit voor de samenwerking van medewerkers, uitsluitend voor routerings-en verbindings doeleinden, en trek aansluitingen van de functie voor het overtrekken van de co-locatie naar de on-premises infrastructuur.  <br/> |
|Point-to-Point Ethernet  <br/> |Beëindig de punt-naar-punt ExpressRoute-verbinding op de bestaande on-premises locatie van de infrastructuur voor beveiliging/verbindingen.  <br/> De nieuwe beveiligings-en perimeter infrastructuur voor het ExpressRoute-pad installeren en de punt-naar-punt-verbinding daar beëindigen.  <br/> |
|Willekeurige IPVPN  <br/> |Gebruik een bestaande on-premises infrastructuur van beveiligings-en perimeternetwerken op alle locaties die worden opgetreden in de IPVPN die wordt gebruikt voor ExpressRoute voor Office 365-connectiviteit.  <br/> Maak de IPVPN die voor ExpressRoute voor Office 365 wordt gebruikt naar specifieke on-premises locaties die zijn aangewezen om als beveiliging/verbinding te fungeren.  <br/> |

Sommige service providers bieden ook beheerde beveiligings-en perimeter functionaliteit aan als onderdeel van hun integratieoplossingen met Azure ExpressRoute.
  
Wanneer u de topologie plaatsing van de netwerk-ExpressRoute voor Office 365-verbindingen overweegt, volgen aanvullende aandachtspunten
  
- De functies diepte en type voor netwerk en beveiliging kunnen invloed hebben op de prestaties en schaalbaarheid van de Office 365-gebruikerservaring.

- Uitgaande (on-premises- \> Microsoft) en binnenkomende (Microsoft- \> on-premises) [indien ingeschakeld] stromen kunnen verschillende vereisten hebben. Dit zijn waarschijnlijk afwijkend van de algemene Internet bestemmingen.

- Office 365 vereisten voor poorten/protocollen en de benodigde IP-subnetten zijn hetzelfde, ongeacht of het verkeer wordt gerouteerd via ExpressRoute voor Office 365 of via internet.

- De topologische plaatsing van de netwerk-en beveiligingscontrole van de klant bepaalt het ultieme end-to-end netwerk tussen de gebruiker en de Office 365-service en kan een aanzienlijke invloed hebben op de netwerklatentie en congestie.

- Klanten wordt aangeraden de topologie voor beveiliging/perimeter te ontwerpen voor gebruik met ExpressRoute voor Office 365 in overeenstemming met best practices voor redundantie, hoge beschikbaarheid en herstel na noodgevallen.

Hier is een voorbeeld van Woodgrove Bank waarbij de verschillende connectiviteitsopties van Azure ExpressRoute worden vergeleken met de hierboven beschreven perimeter beveiligingsmodellen.
  
### <a name="example-1-securing-azure-expressroute"></a>Voorbeeld 1: Azure ExpressRoute beveiligen
  
Woodgrove Bank gaat het implementeren van Azure ExpressRoute en het plannen van de optimale architectuur van [Routering met ExpressRoute voor Office 365](routing-with-expressroute.md) en na het gebruik van de bovenstaande richtlijnen om de bandbreedte te beveiligen.
  
Voor Woodgrove, een organisatie met meerdere nationale landen en locaties in meerdere continenten, moet de beveiliging alle omtrek van de grenzen beslaan. De optimale verbindingsoptie voor Woodgrove is een meervoudige verbinding met meerdere peer-locaties overal ter wereld en de behoeften van hun werknemers in elk continent. Elke continent omvat overbodige Azure ExpressRoute-circuits binnen het continent en de beveiliging moeten deze allemaal beslaan.
  
De bestaande infrastructuur van Woodgrove is betrouwbaarder en kan de nieuwe hoeveelheid werk behandelen, via Woodgrove Bank kan de infrastructuur worden gebruikt voor de beveiliging van Azure ExpressRoute en Internet perimeter. Als dit niet het geval is, kan Woodgrove de aankoop van extra apparatuur aanvullen om de bestaande apparatuur te kopen of om een ander type verbinding te maken.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Hoge beschikbaarheid en failover met Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

We raden u aan minstens twee actieve circuits te creëren van elke opuitgang met ExpressRoute aan uw ExpressRoute-provider. Dit is de meest voorkomende plaats van storingen voor klanten en u kunt deze eenvoudig vermijden door een paar actieve en actieve ExpressRoute-circuits te creëren. We raden u ook aan minstens twee actieve/actieve Internet circuits te maken, omdat veel Office 365-Services alleen via internet beschikbaar zijn.
  
In het uitgangspunt van uw netwerk zijn veel andere apparaten en circuits die een cruciale rol spelen bij de beschikbaarheid van personen. Deze gedeelten van uw verbindingsscenario's bevinden zich niet onder ExpressRoute of Office 365-Servicevoorwaarden, maar spelen een kritieke rol voor de beschikbaarheid van de service, zoals wordt uitgegaan van de personen in uw organisatie.
  
Richt u op de personen die gebruikmaken van en werken met Office 365, als een storing van een onderdeel van invloed is op de ervaring van mensen die de service gebruiken, kunt u het totale aantal personen beperken. Als een failoverconfiguratie zeer ingewikkeld is, kunt u de ervaring van de volkeren zeer lang voor herstel en de werking van de mensen in de failover automatiseren.
  
Buiten uw netwerk, Office 365, ExpressRoute en uw ExpressRoute-provider hebben allemaal verschillende beschikbaarheidsniveaus.
  
### <a name="service-availability"></a>Beschikbaarheid van service
  
- Office 365-services worden gedekt door goed gedefinieerde [serviceniveau overeenkomsten](https://technet.microsoft.com/library/office-365-service-level-agreement.aspx), waaronder uptime en beschikbaarheid van gegevens voor afzonderlijke services. Met Office 365 kunnen deze hoge beschikbaarheid worden bijgehouden met beschikbare onderdelen van de vele Microsoft-datacenters, met behulp van het globale Microsoft-netwerk. Deze failoverbewerking breidt uit van het datacenter en netwerk naar de Multiple-uitgangspunten en schakelt failover naadloos uit vanuit het perspectief van de personen die de service gebruiken.

- ExpressRoute [biedt een 99,9% beschikbaarheids Sla](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) op afzonderlijke speciale circuits tussen de Edge van het Microsoft-netwerk en de ExpressRoute-provider of de partner infrastructuur. Deze serviceniveaus worden toegepast op het ExpressRoute-circuitniveau, dat bestaat uit [twee onafhankelijke verbindingsnen](https://azure.microsoft.com/documentation/articles/expressroute-introduction/) tussen de redundante Microsoft-apparatuur en de netwerkprovider apparatuur in elke peering-locatie.

### <a name="provider-availability"></a>Provider beschikbaarheid
  
- De schikkingen van het Microsoft-serviceniveau worden beëindigd bij uw ExpressRoute-provider of-partner. Dit is ook de eerste plaats waarmee u keuzes kunt maken die van invloed zijn op uw beschikbaarheidsniveau. U dient de architectuur, de beschikbaarheid en de toleranties van de ExpressRoute-provider nauwkeurig te evalueren, en op elke Microsoft-site voor het bellen van uw providers. Let op de aandachtspunten voor de logische en fysische aspecten van redundante, peer-to-Equipment, verstrekte WAN-circuits en extra value Services toevoegen, zoals NAT-services of beheerde firewalls.

### <a name="designing-your-availability-plan"></a>Uw beschikbaarheids abonnement ontwerpen
  
We raden u ten zeerste aan om hoge beschikbaarheid en tolerantie te plannen en te ontwerpen in uw end-to-end verbindingsscenario's voor Office 365. Een ontwerp moet zijn opgenomen;
  
- geen enkele storings punten, waaronder de Internet-en ExpressRoute-circuits.

- het aantal personen dat wordt beïnvloed en de duur van die beïnvloeding tot een minimum beperken voor de meest verwachte fout modi.

- optimaliseren voor eenvoudig, herhaald en automatisch herstelproces vanuit de meest verwachte fout modi.

- ondersteuning van de volledige vereisten van uw netwerkverkeer en-functionaliteit via redundante paden, zonder dat dit significante vermindering verloopt.

U moet een netwerktopologie opnemen die is geoptimaliseerd voor meerdere onafhankelijke en actieve netwerkpaden naar Office 365. Dit levert een betere nauwkeurigheid op dan de topologie die alleen voor redundantie is geoptimaliseerd op het niveau van de afzonderlijke apparatuur of apparatuur.
  
> [!TIP]
> Als uw gebruikers zijn gedistribueerd via meerdere continenten of geografische regio's en elk van deze locaties verbinding maken via redundante WAN-circuits naar één on-premises locatie waarbij één ExpressRoute-circuit is opgesteld, bieden uw gebruikers de mogelijkheid om de beschikbaarheid van end-to-end services te verbinden dan een netwerktopologie waarmee u de verschillende regio's verbindt met de dichtstbijzijnde peer-locatie.
  
We raden u aan minstens twee ExpressRoute-circuits aan te creëren met elk circuit waarmee verbinding wordt gemaakt met een andere geografische locatie. U dient dit actieve paar circuits te bezorgen voor elke regio waar mensen ExpressRoute-connectiviteit voor Office 365-Services gaan gebruiken. Op deze manier blijft elk gebied verbonden tijdens een ramp die van invloed is op een belangrijke locatie zoals een datacenter of een peering. Als u ze configureert als actief/actief, kunnen eindgebruikers verkeer worden verspreid over meerdere netwerkpaden. Hierdoor wordt het bereik van personen die van invloed zijn op het apparaat of de netwerkapparatuur, verminderd.
  
U wordt niet aangeraden één ExpressRoute-circuit te gebruiken met internet als een back-up.
  
### <a name="example-2-failover-and-high-availability"></a>Voorbeeld 2: failover en hoge beschikbaarheid
  
Het multifunctionele ontwerp van de Woodgrove Bank is een beoordeling van de routering, bandbreedte, beveiliging en nu moet u een hoge beschikbaarheid controleren. Woodgrove gaat over hoge beschikbaarheid, met drie categorieën. de tolerantie en de betrouwbaarheid en de redundantie.
  
Met een tolerantie kan Woodgrove van storingen snel worden hersteld. Met betrouwbaarheid kan Woodgrove een consistent resultaat binnen het systeem bieden. Met redundantie kan Woodgrove tussen een of meer gespiegelde versies van infrastructuur.
  
In elke Edge-configuratie heeft Woodgrove de firewalls, Proxy's en ID'S van de Edge. Voor Noord-Amerika heeft Woodgrove één Edge Configuration in hun datacenter van het Groningen en een andere Edge-configuratie in hun datacenter. De overtollige apparatuur op elke locatie biedt tolerantie voor deze locatie.
  
De netwerkconfiguratie bij Woodgrove Bank is opgebouwd op basis van een aantal basisprincipes:
  
- Binnen elke geografische regio zijn er meerdere Azure ExpressRoute-circuits.

- Elk circuit in een regio kan al het netwerkverkeer in die regio ondersteunen.

- Met Routering krijgt u duidelijk een voorkeur voor een of ander pad, afhankelijk van de beschikbaarheid en locatie, enzovoort.

- Failover tussen Azure ExpressRoute-circuits gebeurt automatisch zonder dat u de benodigde configuratie of actie hoeft te ondernemen.

- Failover tussen Internet circuits gebeurt automatisch zonder dat u de benodigde configuratie of actie hoeft te ondernemen voor Woodgrove.

In deze configuratie kan via het fysieke en virtuele niveau met redundantie de vaste of gevirtualiseerde tolerantie, de regionale tolerantie en wereldwijde tolerantie op een betrouwbare manier worden aangeboden. Woodgrove heeft deze configuratie gekozen na de beoordeling van één Azure ExpressRoute-circuit per regio en de mogelijkheid om via internet te mislukken.
  
Als Woodgrove niet meerdere Azure ExpressRoute-circuits per regio kan hebben, wordt het routerings verkeer van Noord-Amerika naar het Azure ExpressRoute-circuit in Azië in Azië toegevoegd en wordt de vereiste extra DNS-doorstuur configuratie toegevoegd.
  
Het gebruik van Internet als een back-upconfiguratie wordt niet aanbevolen. Dit leidt tot het betrouwbaarheid van Woodgrove van Woodgrove, wat resulteert in een inconsistente ervaring via de verbinding. Daarnaast is handmatige configuratie vereist voor failover voor de BGP-advertenties die zijn geconfigureerd, NAT-configuratie, DNS-configuratie en de proxyconfiguratie. Door deze toegevoegde failoverbewerking wordt de tijd vergroot en verkleint, zodat de juiste stappen voor het opsporen van problemen en het oplossen van problemen met u kunnen worden opgelost.
  
Hebt u nog steeds vragen over het plannen en implementeren van Traffic Management of Azure ExpressRoute? Lees de rest van ons [netwerk en de richtlijnen](https://aka.ms/tune) voor de prestaties of de [Azure ExpressRoute Veelgestelde vragen](https://azure.microsoft.com/documentation/articles/expressroute-faqs/).
  
## <a name="working-with-azure-expressroute-providers"></a>Werken met Azure ExpressRoute-providers
<a name="BKMK_high-availability"> </a>

Kies de locatie van de circuits op basis van de bandbreedte, latentie, beveiliging en de planning van hoge beschikbaarheid. Wanneer u de optimale locaties weet waarop u de circuits wilt plaatsen [, controleert u de huidige lijst van providers per regio](https://azure.microsoft.com/documentation/articles/expressroute-locations/).
  
Werk samen met uw provider of providers om de beste verbindingsopties, Point-to-Point, meerdere punten of gehost te selecteren. Houd er rekening mee dat u de verbindingsopties moet combineren, zodat de bandbreedte en andere overbodige onderdelen het ontwerp van Routering en een hoge beschikbaarheid ondersteunen.
  
Met deze korte koppeling kunt u teruggaan: [https://aka.ms/planningexpressroute365](https://aka.ms/planningexpressroute365)
  
## <a name="related-topics"></a>Verwante onderwerpen
<a name="BKMK_high-availability"> </a>

[Een beoordeling van de netwerkverbinding van Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute voor Office 365](azure-expressroute.md)
  
[ExpressRoute voor Office 365-connectiviteit beheren](managing-expressroute-for-connectivity.md)
  
[Routeren met ExpressRoute voor Office 365](routing-with-expressroute.md)
  
[ExpressRoute voor Office 365 implementeren](implementing-expressroute.md)
  
[Het gebruik van BGP-community's in ExpressRoute voor Office 365-scenario's](bgp-communities-in-expressroute.md)
  
[Media kwaliteit en prestaties van de netwerkverbinding in Skype voor bedrijven online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Uw netwerk optimaliseren voor Skype voor bedrijven online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute en QoS in Skype voor bedrijven online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Oproep stroom met behulp van ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Prestaties afstemmen van Office 365 met basislijnen en prestatie geschiedenis](performance-tuning-using-baselines-and-history.md)
  
[Prestatieproblemen met het plannen van Office 365](performance-troubleshooting-plan.md)
  
[URL's en IP-adresbereiken voor Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 netwerk en prestaties optimaliseren](network-planning-and-performance.md)
  
[Veelgestelde vragen over Office 365-eindpunten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
