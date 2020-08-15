---
title: ExpressRoute voor Office 365 implementeren
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/5/2017
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
ms.assetid: 77735c9d-8b80-4d2f-890e-a8598547dea6
description: Meer informatie over het implementeren van ExpressRoute voor Office 365, dat een ander routerings traject biedt voor veel Internet Facing Office 365-Services.
ms.openlocfilehash: 767a99f3a27f30b7193fd0d0b8376ff4923daffb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689459"
---
# <a name="implementing-expressroute-for-office-365"></a>ExpressRoute voor Office 365 implementeren

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

ExpressRoute voor Office 365 biedt een alternatief routerings traject voor veel Internet Facing Office 365-Services. De architectuur van ExpressRoute voor Office 365 is gebaseerd op het adverteren van openbare IP-voorvoegsels van Office 365-services die al via internet toegankelijk zijn in uw ingerichte ExpressRoute-circuits voor toekomstige herdistributie van die IP-voorvoegsels in uw netwerk. Met ExpressRoute kunt u verschillende routeringspaden met internet en via ExpressRoute gebruiken voor veel Office 365-Services. Dit staat van routering op uw netwerk kan een belangrijke wijziging aangeven voor de manier waarop uw interne netwerktopologie is ontworpen.
  
 **Status:** Volledige handleiding v2
  
U moet uw ExpressRoute voor Office 365-implementatie zorgvuldig plannen, zodat u kunt voorkomen dat de verbinding via een specifiek circuit via een toegewijd circuit via een toegewijd circuit via een specifiek circuit wordt geïnjecteerd via een routerings netwerk en Internet. Als u en uw team niet de gedetailleerdere planning en testen in deze handleiding uitvoeren, is er een groot risico dat u geen ondersteuning ondervindt of een totaal verlies van connectiviteit met Office 365-Services als het ExpressRoute-circuit is ingeschakeld.
  
Als u een succesvolle implementatie wilt uitvoeren, moet u de vereisten voor de infrastructuur analyseren, de gedetailleerdste evaluatieversie van het netwerk en het ontwerp zorgvuldig plannen, de implementatie op een gefaseerde en gecontroleerde manier plannen en een gedetailleerd validatie-en testplan maken. Voor een grote, gedistribueerde omgeving is het niet ongebruikelijk om de implementaties van enkele maanden te zien. Deze handleiding is bedoeld om u te helpen bij het plannen van tevoren.
  
Grote succesvolle implementaties kunnen zes maanden duren in de planning en bevatten vaak teamleden van veel gebieden in de organisatie, waaronder netwerk-, firewall-en proxy server-beheerders, Office 365-beheerders, beveiliging, eindgebruikers ondersteuning, project management en Executive sponsoring. Uw investering in het planningsproces vermindert de kans dat u implementatiefouten ondervindt die het resultaat zijn van downtime of ingewikkelde en voordelige probleemoplossing.
  
We gaan ervan uit dat u aan de volgende vereisten hebt voldaan voordat u aan de slag gaat met deze Implementatiehandleiding.
  
1. U hebt een netwerkanalyse uitgevoerd om te bepalen of ExpressRoute wordt aanbevolen en goedgekeurd.

2. U hebt een ExpressRoute-netwerkserviceprovider geselecteerd. U vindt meer informatie over de [ExpressRoute partners en de peering locaties](https://azure.microsoft.com/documentation/articles/expressroute-locations/).

3. U de [documentatie van ExpressRoute](https://azure.microsoft.com/documentation/services/expressroute/) al hebt gelezen en begrijpt en uw interne netwerk kan aan de vereisten voor ExpressRoute end to end voldoen.

4. Uw team heeft alle openbare richtlijnen en documentatie gelezen, [https://aka.ms/expressrouteoffice365](https://aka.ms/expressrouteoffice365) [https://aka.ms/ert](https://aka.ms/ert) en zie de [Azure ExpressRoute voor Office 365-trainings](https://channel9.msdn.com/series/aer) serie in kanaal 9 voor informatie over belangrijke technische details, waaronder:

      - De Internet afhankelijkheden van SaaS-Services.

      - Voorkom dat asymmetrische routes en ingewikkelde routering worden afgehandeld.

      - Het opnemen van perimeter beveiliging, beschikbaarheid en besturingselementen voor toepassingsniveaus.

## <a name="begin-by-gathering-requirements"></a>Beginnen met het verzamelen van vereisten
<a name="requirements"> </a>

Bepaal eerst welke functies en services u wilt overnemen binnen uw organisatie. U dient te bepalen welke functies van de verschillende Office 365-services worden gebruikt en welke locaties in uw netwerk personen met deze functies kunnen hosten. Met de catalogus met scenario's, moet u de netwerk kenmerken toevoegen waarmee elk van deze scenario's is vereist. zoals inkomende en uitgaande netwerkverkeer en als de Office 365-eindpunten beschikbaar zijn via ExpressRoute of niet.
  
De vereisten van uw organisatie verzamelen:
  
- Catalogiseer het inkomende en uitgaande netwerkverkeer voor de Office 365-services die uw organisatie gebruikt. Raadpleeg de pagina Url's van Office 365 en IP-adresbereiken voor de beschrijving van de stromen die verschillende scenario's voor Office 365 vereisen.

- De documentatie verzamelen van een bestaande netwerktopologie met details van uw interne WAN-backbone en-topologie, connectiviteit van satelliet sites, laatste kilometer gebruikers verbindingen, routering naar uitgangspunten van de netwerkverbinding en proxyservices.

  - Identificeer inkomende service-eindpunten op de netwerkdiagrammen waarmee Office 365 en andere Microsoft-Services verbinding maken, waarbij de verbindingspaden op internet en de voorgestelde ExpressRoute worden weergegeven.

  - Identificeer alle geografische gebruikerslocaties en de WAN-verbinding tussen locaties samen met welke locaties momenteel een uitgangspunt hebben voor het internet en welke locaties worden voorgesteld om een uitstap te maken met een ExpressRoute-peer-locatie.

  - Identificeer alle edge-apparaten, zoals proxy's, firewalls, enzovoort, en verbind hun relaties met stromen via internet en ExpressRoute.

  - Documenteer of eindgebruikers toegang hebben tot Office 365-Services via directe routering of via een indirecte toepassingsproxy voor Internet-en ExpressRoute-stromen.

- Voeg de locatie van de Tenant en meet-me-locaties toe aan het netwerkdiagram.

- Geschatte en geschatte eigenschappen van het netwerk en de latentie van grote gebruikerslocaties in Office 365. Houd er rekening mee dat Office 365 een globale en gedistribueerde set services is, en dat gebruikers verbinding maken met locaties die afwijken van de locatie van de Tenant. Daarom wordt u aangeraden om de latentie tussen de gebruiker en de dichtstbijzijnde Edge van het globale netwerk van Microsoft te meten en te optimaliseren via ExpressRoute en Internet verbindingen. U kunt uw bevindingen van de netwerkanalyse gebruiken om te helpen met deze taak.

- Vermeld de vereisten voor netwerkbeveiliging en de vereisten voor hoge beschikbaarheid die moeten worden voldaan met de nieuwe ExpressRoute-verbinding. Hoe kan een gebruiker bijvoorbeeld toegang krijgen tot Office 365 in het geval van een Internet-uittreding of een ExpressRoute-circuit fout.

- Document welke inkomende en uitgaande netwerk stromen van Office 365 gebruikmaken van het Internet traject en gebruikmaken van ExpressRoute. Voor de specifieke geografische locaties van uw gebruikers en gegevens van uw on-premises netwerktopologie moet het plan van de ene naar de andere locatie moeten afwijken.

### <a name="catalog-your-outbound-and-inbound-network-traffic"></a>Uw uitgaande en binnenkomende netwerkverkeer catalogiseren
<a name="trafficCatalog"> </a>

Als u de Routering en andere netwerkbehoeften wilt minimaliseren, is het raadzaam dat u ExpressRoute voor Office 365 gebruikt voor de netwerkverkeer die nodig zijn om een speciale verbinding te verkrijgen als gevolg van wettelijke vereisten of als het resultaat van de netwerk beoordeling. Daarnaast is het raadzaam het bereik van ExpressRoute-Routering en de bewerkings stroom voor uitgaande en binnenkomende netwerkverkeer te verwerken als verschillende en verschillende fasen van het implementatieproject. Deploy ExpressRoute voor Office 365 voor alleen gebruikers die een uitgaand netwerkverkeer hebben geïnitieerd en binnenkomende netwerkverkeer via internet kunnen helpen de toename van de topologische complexiteit en Risico's van het introduceren van extra asymmetrische Routeringsmogelijkheden te regelen.
  
Uw netwerkverkeer catalogus moet vermeldingen bevatten van alle binnenkomende en uitgaande netwerkverbindingen tussen uw on-premises netwerk en Microsoft.
  
- Uitgaande netwerkverkeer zijn scenario's waarin een verbinding wordt geïnitieerd vanuit uw on-premises omgeving, zoals van interne clients of servers, met een bestemming van de Microsoft-services. Deze verbindingen kunnen verwijzen naar Office 365 of indirect, bijvoorbeeld wanneer de verbinding tot stand komt via proxyservers, firewalls of andere netwerkapparaten op het pad naar Office 365.

- Binnenkomende netwerkverkeer vormen een scenario waarbij een verbinding wordt geïnitieerd vanuit de Microsoft-Cloud naar een on-premises host. Deze verbindingen moeten meestal de firewall en andere beveiligingsinfrastructuur doorlopen waarvoor het beveiligingsbeleid van de klant voor extern van oorsprong is vereist.

Lees de sectie **zorgen voor route symmetrie** van het artikel routerings gebied van het artikel [routeren met ExpressRoute voor Office 365](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) om te bepalen welke services inkomende verkeer verzenden en zoek de kolom die is gemarkeerd met **ExpressRoute voor Office 365** in het naslagwerk voor [eindpunten van Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) .
  
Voor elke service waarvoor een uitgaande verbinding is vereist, kunt u de geplande verbindingen voor de service, waaronder netwerkroutering, proxyconfiguratie, pakket controle en bandbreedte behoeften beschrijven.
  
Voor elke service waarvoor een inkomende verbinding is vereist, moet u aanvullende informatie raadplegen. Servers in de Microsoft Cloud zorgen voor verbindingen met uw on-premises netwerk. om ervoor te zorgen dat de verbindingen correct worden uitgevoerd, moet u alle aspecten van deze verbinding beschrijven, waaronder. de openbare DNS-vermeldingen voor de services die deze binnenkomende verbindingen accepteren, de door CIDR opgemaakte IPv4-IP-adressen, welke service apparatuur bij u gaat, en hoe binnenkomende NAT-of bron-NAT wordt afgehandeld voor deze verbindingen.
  
Binnenkomende verbindingen dienen te worden beoordeeld, ongeacht of ze verbinding maken via internet of ExpressRoute om te voorkomen dat asymmetrische routering is geïntroduceerd. In sommige gevallen moeten on-premises eindpunten waarmee Office 365-Services inkomende verbindingen initiëren, ook worden geopend door andere Microsoft-en niet-Microsoft-services. Het grootste probleem is dat bij het inschakelen van ExpressRoute routeren naar deze services voor Office 365-doelen geen andere scenario's worden verbroken. In veel gevallen moeten klanten bepaalde wijzigingen doorvoeren in hun interne netwerk, zoals bron-NAT, om ervoor te zorgen dat binnenkomende stromen van Microsoft worden symmetrisch wanneer ExpressRoute is ingeschakeld.
  
Hier ziet u een voorbeeld van de hoeveelheid detail. In dit scenario wordt de hybride versie van Exchange gerouteerd naar het on-premises systeem via ExpressRoute.

|**Verbindingseigenschap**|**Value**|
|:-----|:-----|
|**Richting van netwerkverkeer** <br/> |Bound  <br/> |
|**Service** <br/> |Hybride versie van Exchange  <br/> |
|**Openbaar Office 365-eindpunt (bron)** <br/> |Exchange Online (IP-adressen)  <br/> |
|**Openbaar on-premises eindpunt (bestemming)** <br/> |5.5.5.5  <br/> |
|**Openbare DNS-vermelding (Internet)** <br/> |Autodiscover.contoso.com  <br/> |
|**Wordt dit on-premises eindpunt gebruikt door andere (niet-Office 365) Microsoft-services** <br/> |Nee  <br/> |
|**Wordt dit on-premises eindpunt gebruikt door gebruikers/systemen op Internet** <br/> |Ja  <br/> |
|**Interne systemen die zijn gepubliceerd via openbare eindpunten** <br/> |Exchange Server-functie voor clienttoegang (on-premises) 192.168.101, 192.168.102, 192.168.103  <br/> |
|**IP-aankondiging van het openbare eindpunt** <br/> |**Naar Internet**: 5.5.0.0/16  <br/> **Naar ExpressRoute**: 5.5.5.0/24  <br/> |
|**Beveiligings-en perimeter besturingselementen** <br/> |**Internet paden**: DeviceID_002  <br/> **ExpressRoute-pad**: DeviceID_003  <br/> |
|**Hoge beschikbaarheid** <br/> |Actief/actief in twee geografisch redundante  <br/> ExpressRoute-circuits, Chicago en Groningen  <br/> |
|**Pad symmetrie regeling** <br/> |**Methode**: bron-NAT  <br/> **Internet-pad**: binnenkomende bron-NAT-verbindingen met 192.168.5.5  <br/> |**ExpressRoute-pad**: bron-NAT-verbindingen naar 192.168.1.0 (Chicago) en 192.168.2.0 (Rotterdam)  <br/> |

Hier ziet u een voorbeeld van een service die alleen uitgaand is:

|**Verbindingseigenschap**|**Value**|
|:-----|:-----|
|**Richting van netwerkverkeer** <br/> |Transfer  <br/> |
|**Service** <br/> |SharePoint Online  <br/> |
|**On-premises eindpunt (bron)** <br/> |Gebruikers werkstation  <br/> |
|**Openbaar Office 365-eindpunt (bestemming)** <br/> |SharePoint Online (IP-adressen)  <br/> |
|**Openbare DNS-vermelding (Internet)** <br/> |\*. sharepoint.com (en extra FQDN)  <br/> |
|**CDN-verwijzingen** <br/> |cdn.sharepointonline.com (en extra FQDN)-IP-adressen die worden onderhouden door CDN-providers  <br/> |
|**IP-advertisement en NAT in gebruik** <br/> |**Internet-pad/bron-NAT**: 1.1.1.0/24  <br/> **ExpressRoute-pad/bron-NAT**: 1.1.2.0/24 (Chicago) en 1.1.3.0/24 (Rotterdam)  <br/> |
|**Verbindingsmethode** <br/> |**Internet**: via laag 7-proxy (PAC-bestand)  <br/> **ExpressRoute**: directe routering (geen proxy)  <br/> |
|**Beveiligings-en perimeter besturingselementen** <br/> |**Internet paden**: DeviceID_002  <br/> **ExpressRoute-pad**: DeviceID_003  <br/> |
|**Hoge beschikbaarheid** <br/> |**Internet-pad**: redundante Internet ontuitgang  <br/> **ExpressRoute-pad**: actief/actief ' hot aardappel ' routerings router voor twee geo-redundante ExpressRoute-circuits en Chicago  <br/> |
|**Pad symmetrie regeling** <br/> |**Methode**: bron-NAT voor alle verbindingen  <br/> |

### <a name="your-network-topology-design-with-regional-connectivity"></a>Uw netwerktopologie ontwerp met regionale connectiviteit
<a name="topology"> </a>

Wanneer u de services en de bijbehorende netwerk stromen begrijpt, kunt u een netwerkdiagram maken dat deze nieuwe verbindings vereisten bevat en ziet u de wijzigingen die u aanbrengt in ExpressRoute voor Office 365. Het diagram moet bestaan uit:
  
1. Alle gebruikerslocaties waarop Office 365 en andere services worden gebruikt.

2. Alle Internet-en ExpressRoute-uitgangspunten.

3. Alle apparaten voor uitgaande en inkomende verbindingen waarmee de verbindingen in en uit het netwerk worden beheerd, waaronder routers, firewalls, toepassingsproxy servers en inbraakdetectie/preventie.

4. Interne bestemmingen voor alle binnenkomende verkeer, zoals interne ADFS-servers die verbindingen accepteren van de proxyservers van de ADFS-Web toepassing.

5. Catalogus met alle IP-subnetten die worden aangekondigd

6. Identificeer elke locatie waartoe personen toegang hebben tot Office 365 en vermeld de bezorgingslocaties die worden gebruikt voor ExpressRoute.

7. Locaties en delen van uw interne netwerktopologie, waarbij Microsoft IP-voorvoegsels van ExpressRoute worden geaccepteerd, gefilterd en doorgegeven.

8. De netwerktopologie moet de geografische locatie van elk netwerksegment illustreren en de manier waarop dit verbinding maakt met het Microsoft-netwerk via ExpressRoute en/of Internet.

In het volgende diagram ziet u elke locatie waarop gebruikers Office 365 gebruiken, en de inkomende en uitgaande routerings aankondigingen naar Office 365.
  
![Land/regio voor ExpressRoute](../media/d866b36b-49bf-416b-af1b-d054e24989d2.png)
  
Voor uitgaand verkeer heeft de persoon toegang tot Office 365 op een van de volgende drie manieren:
  
1. Via een Vergader locatie in Noord-Amerika voor de personen in Californië.

2. Via een Ontmoet-me-locatie in Hongkong voor de mensen in Hongkong.

3. Via internet in Bangladesh waar zich minder personen bevinden en geen ExpressRoute-circuit inrichten.

![Uitgaande verbindingen voor regionaal diagram](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
Het binnenkomende netwerkverkeer van Office 365 retourneert op een van de volgende drie manieren:
  
1. Via een Vergader locatie in Noord-Amerika voor de personen in Californië.

2. Via een Ontmoet-me-locatie in Hongkong voor de mensen in Hongkong.

3. Via internet in Bangladesh waar zich minder personen bevinden en geen ExpressRoute-circuit inrichten.

![Binnenkomende verbindingen voor regionaal diagram](../media/d6d6160d-bf28-4de3-a787-186c7432b306.png)
  
### <a name="determine-the-appropriate-meet-me-location"></a>De juiste Ontmoet-me-locatie bepalen

De selectie van bezorgingslocaties, die de fysieke locatie zijn waar uw ExpressRoute-circuit verbinding maakt met het Microsoft-netwerk, wordt beïnvloed door de locaties waar mensen Office 365 gaan openen. Als SaaS-aanbieding gaat Office 365 niet onder het regionale model van IaaS of PaaS, op dezelfde manier als Azure wel. In plaats daarvan is Office 365 een gedistribueerde set samenwerkingsservices, waarin gebruikers mogelijk verbinding willen maken met eindpunten in meerdere datacenters en regio's, wat niet noodzakelijkerwijs mag zich op dezelfde locatie of regio bevinden waar de Tenant van de gebruiker wordt gehost.
  
Dit houdt in dat u de belangrijkste overweging moet maken bij het selecteren van een Vergader locatie voor ExpressRoute voor Office 365, waarbij de personen in uw organisatie verbinding maken. De algemene aanbeveling voor optimale werking van Office 365 wordt routering geïmplementeerd, zodat gebruikersaanvragen voor Office 365-Services in het Microsoft-netwerk via het kortste netwerkpad worden afgehandeld, ook wel ' hete aardappel ' genoemd. Als de meeste gebruikers van Office 365 zich op een of twee locaties bevinden, en het selecteren van de juiste locaties van de gebruikers in de buurt van de locatie van deze gebruikers, maakt u het optimale ontwerp. Als uw bedrijf grote gebruikers bevolking heeft in vele verschillende regio's, kunt u overwegen om meerdere ExpressRoute-circuits en locaties te ontmoeten. Voor sommige gebruikerslocaties is het kortste/meest optimale pad naar Microsoft-netwerk en Office 365 mogelijk niet via het interne WAN-en ExpressRoute-Vergader punten, maar via internet.
  
Het kan soms voorkomen dat er meerdere locaties voor het maken van een begeleidende mijzelf zijn in een regio met een relatieve nabijheid voor uw gebruikers. Vul de volgende tabel in om uw beslissingen te begeleiden.

|**Geplande ExpressRoute-me-locaties in Californië en New York**||
|:-----|:-----|
|Locatie  <br/> |Aantal personen  <br/> |Verwachte latentie bij Microsoft-netwerk via internet uitloopt  <br/> |Verwachte latentie voor Microsoft-netwerk via ExpressRoute  <br/> |
|Los Angeles  <br/> |10.000  <br/> |~ 15ms  <br/> |~ 10 MS (via Silicon dal)  <br/> |
|Washington DC  <br/> |15.000  <br/> |~ 20ms  <br/> |~ 10 MS (via New York)  <br/> |
|Noord  <br/> |5.000  <br/> |~ 15ms  <br/> |~ 40 MS (via New York)  <br/> |

Wanneer de architectuur van Office 365 wordt weergegeven in de algemene netwerkarchitectuur van de ExpressRoute netwerkservice provider, en het aantal personen per locatie is ontwikkeld en kan worden gebruikt om te bepalen of een optimalisaties kunnen worden uitgevoerd. Het kan ook zijn dat globale Maak-netwerkverbindingen worden weergegeven waarbij verkeer naar een andere locatie wordt weergegeven om de locatie van de vergaderen mij op te halen. Als een Maak op het globale netwerk wordt gedetecteerd, moet dit worden hersteld voordat u verder gaat. U kunt een andere locatie zoeken of een oplopende Internet spreek-uitgangspunten gebruiken om de maak te voorkomen.
  
Het eerste diagram geeft een voorbeeld weer van een klant met twee fysieke locaties in Noord-Amerika. U vindt de informatie over Office-locaties, de Tenant locaties van Office 365 en verschillende opties voor ExpressRoute-locaties. In dit voorbeeld heeft de klant de locatie van de vergadering op basis van twee principes geselecteerd, in volgorde:
  
1. Dichtst bij de personen in de organisatie.

2. Dichtst bij een Microsoft-datacenter waar Office 365 wordt gehost.

![ExpressRoute in de VS](../media/5ec38274-b317-4ec1-91c8-90c2a7fd32ca.png)
  
Dit concept iets verder uitvouwen, in het tweede diagram ziet u een voorbeeld met een meervoudige nationale klant, met soortgelijke informatie en besluitvorming. Deze klant heeft een klein Office in Bangladesh met slechts één klein team van tien personen die geconcentreerd zijn in de regio. Er is een Ontmoet-me-locatie in Chennai en een Microsoft-datacenter met Office 365 gehost in Chennai, zodat de locatie van een vergaderen en mijzelf duidelijk is. maar voor tien personen is de kosten van het extra circuit burdensome. Als u uw netwerk bekijkt, moet u bepalen of de latentie van het verzenden van uw netwerkverkeer via uw netwerk effectiever is dan het kapitaal voor het verkrijgen van een ander ExpressRoute circuit.
  
Daarnaast kunnen de tien medewerkers in Bangladesh betere prestaties ondervinden met hun netwerkverkeer via internet naar het Microsoft-netwerk, dan wordt de routering van het interne netwerk omgeleid naar het interne netwerk, zoals in de inleidende diagrammen en de onderstaande stappen.
  
![Uitgaande verbindingen voor regionaal diagram](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
## <a name="create-your-expressroute-for-office-365-implementation-plan"></a>Uw ExpressRoute voor Office 365-implementatie abonnement maken
<a name="implementation"> </a>

Uw implementatieplan moet bestaan uit zowel de technische gegevens van de configuratie van ExpressRoute als de details van de configuratie van alle andere infrastructuur op het netwerk, zoals hieronder beschreven.
  
- Plan welke services moeten worden gesplitst tussen ExpressRoute en Internet.

- Plan voor bandbreedte, beveiliging, hoge beschikbaarheid en failover.

- Ontwerp binnenkomende en uitgaande routering, inclusief de juiste optimalisaties van routeringspaden voor verschillende locaties

- Bepalen hoe ver ExpressRoutee routes in uw netwerk worden aangekondigd en wat het mechanisme is voor klanten om Internet-of ExpressRoute te selecteren; bijvoorbeeld directe routering of toepassingsproxy.

- Plan wijzigingen in DNS-records, waaronder Framework-beleidsregels voor [verzenders](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx) .

- Plan de NAT-strategie, inclusief uitgaande en binnenkomende bron-NAT.

### <a name="plan-your-routing-with-both-internet-and-expressroute-network-paths"></a>De routering plannen met internet-en ExpressRoute-netwerkpaden
<a name="paths"> </a>

- Voor de eerste implementatie wordt u aangeraden voor alle binnenkomende services, zoals binnenkomende e-mail of hybride connectiviteit, het Internet te gebruiken.

- De client routering van eindgebruikers plannen, zoals [een PAC/WPAD-bestand configureren](https://aka.ms/manageo365endpoints), standaardroute, proxyservers en BGP-routeadvertenties.

- Plan de perimeter routering, inclusief proxyservers, firewalls en Cloud proxy's.

### <a name="plan-your-bandwidth-security-high-availability-and-failover"></a>De bandbreedte, beveiliging, hoge beschikbaarheid en failover plannen
<a name="availability"> </a>

Maak een plan voor de bandbreedte die is vereist voor elke belangrijke Office 365-werkbelasting. U kunt de bandbreedte voor Exchange Online, SharePoint Online en Skype voor bedrijven online afzonderlijk ramen. U kunt de ramings rekenmachines voor Exchange Online en Skype voor bedrijven als uitgangspunt gebruiken. een test test met een representatieve steekproef van de gebruikersprofielen en locaties is echter vereist voor een volledig overzicht van de bandbreedte behoeften van uw organisatie.
  
Toevoegen hoe beveiliging wordt afgehandeld op elke Internet-en ExpressRoute-uitbreiieve locatie aan uw abonnement, onthoud dat alle ExpressRoute verbindingen met Office 365 gebruikmaken van openbare peering en die nog moeten worden beveiligd in overeenstemming met de beleidsregels van uw bedrijf om verbinding te maken met externe netwerken.
  
Voeg details toe aan uw plan, waarvan de werking van invloed is op het type storing en hoe deze personen hun werk op volledige capaciteit kunnen uitvoeren op de eenvoudigste manier.
  
#### <a name="plan-bandwidth-requirements-including-skype-for-business-requirements-on-jitter-latency-congestion-and-headroom"></a>De bandbreedtevereisten plannen, waaronder de vereisten voor Skype voor bedrijven op jitter, latentie, congestie en ruimte
  
Skype voor bedrijven online bevat ook specifieke extra netwerkvereisten die uitvoerig worden beschreven in het artikel [Media kwaliteit en prestaties van de netwerkverbinding in Skype voor bedrijven online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917).
  
Lees de sectie **bandbreedte planning voor Azure ExpressRoute** in [netwerk planning met ExpressRoute voor Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
Wanneer u een bandbreedte beoordeling met uw proef gebruikers uitvoert, kunt u onze richtlijnen gebruiken. [Prestatieafstemming van Office 365 met basislijnen en prestatie geschiedenis](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).
  
#### <a name="plan-for-high-availability-requirements"></a>Vereisten voor hoge beschikbaarheid plannen
  
Maak een plan voor hoge beschikbaarheid om aan uw behoeften te voldoen en neem deze op in het bijgewerkte netwerktopologie diagram. Lees de sectie **hoge beschikbaarheid en failover met Azure ExpressRoute** in [netwerk planning met ExpressRoute voor Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
#### <a name="plan-for-network-security-requirements"></a>Vereisten voor netwerkbeveiliging plannen
  
Maak een plan om te voldoen aan de vereisten voor netwerkbeveiliging en neem dit op in het bijgewerkte netwerktopologie diagram. Lees het gedeelte **Beveiligingsopties toepassen op Azure ExpressRoute voor office 365-scenario's** in [netwerk planning met ExpressRoute voor Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
### <a name="design-outbound-service-connectivity"></a>Uitgaande service verbindingen ontwerpen
<a name="outbound"> </a>

ExpressRoute voor Office 365 biedt  *uitgaande*  netwerkvereisten die mogelijk niet bekend zijn. Met name de IP-adressen die uw gebruikers en netwerken vertegenwoordigen in Office 365 en fungeren als de bron-eindpunten voor uitgaande netwerkverbindingen naar Microsoft moeten voldoen aan specifieke vereisten die hieronder worden vermeld.
  
1. De eindpunten moeten openbare IP-adressen zijn die zijn geregistreerd bij uw bedrijf of voor een provider die de ExpressRoute-connectiviteit met u levert.

2. De eindpunten moeten worden aangekondigd bij Microsoft en worden gevalideerd/geaccepteerd door ExpressRoute.

3. De eindpunten moeten niet worden aangekondigd bij Internet met dezelfde of meer geschikte routeringsmetriek.

4. De eindpunten mogen niet worden gebruikt voor verbindingen met Microsoft-services die niet zijn geconfigureerd via ExpressRoute.

Als uw netwerkontwerp niet aan deze vereisten voldoet, is er een groot risico dat uw gebruikers de connectiviteitsproblemen met Office 365 en andere Microsoft-services kunnen voordoen vanwege een Routering met zwart-Houd terwijl of asymmetrische routering. Dit gebeurt wanneer aanvragen naar Microsoft-services worden gerouteerd via ExpressRoute, maar antwoorden op internet worden gerouteerd, of vice versa, en de antwoorden worden verbroken door stateful netwerkapparaten zoals firewalls.
  
De meest voorkomende methode die u kunt gebruiken om aan de bovenstaande vereisten te voldoen, is het gebruik van bron-NAT, geïmplementeerd als onderdeel van uw netwerk of van uw ExpressRoute-provider. Met bron-NAT kunt u de details en de persoonlijke IP-adressen van uw Internet netwerk abstracten vanuit ExpressRoute en; met een goede routering van IP-routes dient een eenvoudig mechanisme te zorgen voor de symmetrie van het pad. Als u stateful netwerkapparaten gebruikt die specifiek zijn voor ExpressRoutee peering locaties, moet u afzonderlijke NAT-groepen implementeren voor elke ExpressRoute-peering om de symmetrie van het pad te waarborgen.
  
Lees meer over de [NAT-vereisten voor ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-nat/).
  
Voeg de wijzigingen voor de uitgaande verbinding toe aan het netwerktopologie diagram.
  
### <a name="design-inbound-service-connectivity"></a>Binnenkomende service verbindingen ontwerpen
<a name="inbound"> </a>

Bij de meeste Enterprise Office 365-implementaties wordt een deel van de binnenkomende verbinding van Office 365 naar on-premises Services, zoals voor hybride scenario's van Exchange, SharePoint of Skype voor bedrijven, en de Postvak migraties en verificatie via de ADFS-infrastructuur. Wanneer ExpressRoute u een extra routeringspaden inschakelt tussen uw on-premises netwerk en Microsoft voor uitgaande verbinding, worden deze binnenkomende verbindingen soms niet per ongeluk beïnvloed door asymmetrische routering, ook als u wilt dat deze stromen blijven werken via het internet. U wordt aangeraden enkele van de volgende handelingen uit te voeren om te zorgen dat er geen gevolgen zijn voor op internet gebaseerde uitgaande stromen van Office 365 naar on-premises systemen.
  
Om de Risico's van asymmetrische routering voor binnenkomende netwerkverkeer te minimaliseren, moet u alle binnenkomende verbindingen gebruiken voordat ze worden doorgestuurd naar segmenten van uw netwerk, die een routerings inzicht hebben in ExpressRoute. Als de binnenkomende verbindingen zijn toegestaan op een netwerksegment met de zichtbaarheid van routeringen in ExpressRoute zonder bron-NAT, worden aanvragen van Office 365 via internet ingevoerd, maar het antwoord gaat terug naar Office 365 om te zorgen dat de ExpressRoute voor asymmetrisch wordt doorgestuurd.
  
U kunt ook een van de volgende implementatie patronen volgen om aan deze vereiste te voldoen:
  
1. Voer bron-NAT uit voordat aanvragen worden gerouteerd naar uw interne netwerk met netwerkapparatuur zoals firewalls of load balancers op het pad van Internet naar uw on-premises systemen.

2. Zorg ervoor dat ExpressRoute-routes niet worden doorgegeven aan de netwerksegmenten waar zich binnenkomende services, zoals front-endservers of reverse-proxy-systemen, bevinden waarop Internet verbindingen worden beheerd.

Met expliciete financiële administratie van deze scenario's in uw netwerk en alle binnenkomende netwerkverkeer stromen via internet kunt u de implementatie en het operationele risico van asymmetrische routering minimaliseren.
  
Er kunnen situaties zijn waarin u ervoor kunt kiezen om bepaalde binnenkomende stromen via ExpressRoute-verbindingen te leiden. Voor deze scenario's moet u rekening houden met de volgende aanvullende overwegingen.
  
1. In Office 365 kunnen alleen on-premises eindpunten worden gebruikt die openbare IPs gebruiken. Dit betekent dat zelfs als het on-premises inkomende eindpunt alleen wordt weergegeven aan Office 365 via ExpressRoute, moeten er nog wel openbare IP-adressen zijn gekoppeld.

2. Elke DNS-naam oplossing die Office 365-Services uitvoert om on-premises eindpunten op te lossen, gebeurt met behulp van openbare DNS. Dit betekent dat u de FQDN van inkomende service-eindpunten voor IP-toewijzingen op Internet moet registreren.

3. Als u binnenkomende netwerkverbindingen wilt ontvangen via ExpressRoute, moeten de openbare IP-subnetten voor deze eindpunten worden aangekondigd bij Microsoft via ExpressRoute.

4. Evalueer deze binnenkomende netwerkverkeer vergelijkings processen om ervoor te zorgen dat de juiste beveiliging en netwerk controles hierop worden toegepast in overeenstemming met het beveiligings-en netwerkbeleid van uw bedrijf.

5. Wanneer uw on-premises inkomende eindpunten worden aangekondigd bij Microsoft via ExpressRoute, wordt ExpressRoute in feite het gewenste routerings traject voor alle Microsoft-services, waaronder Office 365. Dit betekent dat de subnetten van de eindpunten alleen mogen worden gebruikt voor communicatie met Office 365-Services en geen andere services op het Microsoft-netwerk. Anders zorgt uw ontwerp voor asymmetrische routering voor de inkomende verbindingen van andere Microsoft-services, waarbij inkomende verbindingen via ExpressRoute worden gerouteerd, terwijl het retour traject gebruikmaakt van Internet.

6. In het geval van een ExpressRoute-circuit of een beschikbare locatie is de locatie van de on-premises inkomende eindpunten beschikbaar, zodat u aanvragen kunt accepteren via een apart netwerkpad. Dit kan betekenen dat de subnetten voor deze eindpunten worden geadverteerd via meerdere ExpressRoute-circuits.

7. U wordt aangeraden bron-NAT toe te passen voor alle binnenkomende netwerkverkeer met behulp van ExpressRoute, met name wanneer deze stromen hun stateful netwerkapparaten zoals firewalls passeren.

8. Bij sommige on-premises Services, zoals ADFS-proxy of Exchange Autodiscover, worden mogelijk inkomende aanvragen ontvangen van beide Office 365-Services en-gebruikers via internet. Voor deze verzoeken gaat Office 365 dezelfde FQDN-naam als gebruikersverzoek via internet. Het toestaan van binnenkomende gebruikers verbindingen van Internet naar deze on-premises eindpunten, tijdens het afdwingen van de ExpressRoute-verbindingen van Office 365 met behulp van een hoge routerings complexiteit. Voor de meeste klanten die dergelijke ingewikkelde scenario's via ExpressRoute implementeren, wordt niet aanbevolen vanwege operationele overwegingen. Deze extra overhead omvat, het beheren van Risico's van asymmetrische routering, en het is daarom voorzichtig om routerings aankondigingen en-beleidsregels te beheren in meerdere dimensies.

### <a name="update-your-network-topology-plan-to-show-how-you-would-avoid-asymmetric-routes"></a>Werk uw netwerktopologie plan bij om aan te geven hoe u asymmetrische routes wilt vermijden
<a name="asymmetric"> </a>

U wilt asymmetrische routering voorkomen, zodat personen in uw organisatie perfect Office 365 kunnen gebruiken en andere belangrijke services op internet. Er zijn twee gemeenschappelijke configuraties waarmee klanten asymmetrische routering kunnen veroorzaken. Dit is een goed moment om de netwerkconfiguratie te controleren die u wilt gebruiken en om te controleren of een van deze asymmetrische routeringsscenario's bestaan.
  
Als u wilt beginnen, moeten we enkele verschillende situaties bekijken die zijn gekoppeld aan het volgende netwerkdiagram. In dit diagram worden alle servers waarop inkomende aanvragen worden ontvangen, zoals ADFS of on-premises hybride servers, weergegeven in het datacenter van New Jersey en worden aangekondigd op internet.
  
1. Hoewel het perimeternetwerk is beveiligd, is er geen bron-NAT beschikbaar voor binnenkomende aanvragen.

2. De servers in het datacenter van New Jersey kunnen de Internet-en ExpressRoute-routes zien.

![Overzicht van ExpressRoute-verbindingen](../media/8f074af6-ef38-44e8-bc5a-8b4d981fbb20.png)
  
We hebben ook suggesties voor het oplossen van deze problemen.
  
#### <a name="problem-1-cloud-to-on-premises-connection-over-the-internet"></a>Probleem 1: Cloud to on-premises verbinding via Internet
  
In het volgende diagram ziet u het asymmetrische netwerkpad dat wordt gebruikt wanneer uw netwerkconfiguratie geen NAT bevat voor binnenkomende aanvragen van de Microsoft-Cloud via internet.
  
1. Met de binnenkomende aanvraag van Office 365 wordt het IP-adres van het on-premises eindpunt opgehaald vanuit de openbare DNS en wordt de aanvraag verzonden naar het perimeternetwerk.

2. Bij deze fout configuratie is er geen bron-NAT geconfigureerd of beschikbaar op het perimeternetwerk waar het verkeer wordt verzonden, wat resulteert in het werkelijke IP-adres dat wordt gebruikt als de bestemming van de afzender.

  - De server in uw netwerk stuurt het retour verkeer naar Office 365 via een beschikbare ExpressRoute-netwerkverbinding.

  - Het resultaat is een asymmetrisch pad voor deze stroom naar Office 365, wat resulteert in een verbroken verbinding.

![Routerings probleem 1 met ExpressRoute Asymetric](../media/9c210c2a-e0ea-4180-8ede-1bf41746ce7a.png)
  
##### <a name="solution-1a-source-nat"></a>Oplossing 1a: bron-NAT
  
Door een bron-NAT toe te voegen aan de inkomende aanvraag, lost u dit verkeerd geconfigureerde netwerk op. In dit diagram:
  
1. De inkomende aanvraag gaat door naar het perimeternetwerk van het nieuwe Jersey-datacenter. Dit tijdstip NAT is beschikbaar.

2. Het antwoord van de server stuurt de e-mail terug naar het IP-adres dat is gekoppeld aan de bron-NAT in plaats van het oorspronkelijke IP-adres, wat resulteert in het antwoord op het desbetreffende netwerkpad.

![Routerings oplossing 1 voor ExpressRoute Asymetric](../media/0e87a155-f8de-48ed-92ac-27367b727a82.png)
  
##### <a name="solution-1b-route-scoping"></a>Oplossing 1b: route bereik
  
U kunt er ook voor kiezen om te voorkomen dat de ExpressRoute-BGP-voorvoegsels worden aangekondigd, zodat u het alternatieve netwerkpad voor de computers kunt verwijderen. In dit diagram:
  
1. De inkomende aanvraag gaat door naar het perimeternetwerk van het nieuwe Jersey-datacenter. Wanneer de voorvoegsels van Microsoft via het ExpressRoute-circuit zijn aangekondigd, zijn ze niet beschikbaar voor het nieuwe Jersey-datacenter.

2. Het antwoord van de server stuurt de e-mail terug naar het IP-adres dat is gekoppeld aan het oorspronkelijke IP-adres via de enige router die het resultaat is van de enige router.

![Routerings oplossing 2 voor ExpressRoute Asymetric](../media/9cb4b2bf-7aa6-487a-bc02-e02af8a979f6.png)
  
#### <a name="problem-2-cloud-to-on-premises-connection-over-expressroute"></a>Probleem 2: Cloud to on-premises verbinding via ExpressRoute
  
In het volgende diagram ziet u het asymmetrische netwerkpad dat wordt gebruikt wanneer uw netwerkconfiguratie geen NAT bevat voor binnenkomende aanvragen van de Microsoft-Cloud via ExpressRoute.
  
1. De inkomende aanvraag van Office 365 haalt het IP-adres op uit DNS en stuurt de aanvraag naar het perimeternetwerk.

2. Bij deze fout configuratie is er geen bron-NAT geconfigureerd of beschikbaar op het perimeternetwerk waar het verkeer wordt verzonden, wat resulteert in het werkelijke IP-adres dat wordt gebruikt als de bestemming van de afzender.

  - De computer in uw netwerk stuurt het retour verkeer naar Office 365 via een beschikbare ExpressRoute-netwerkverbinding.

  - Het resultaat is een asymmetrische verbinding met Office 365.

![Routerings probleem 2 met ExpressRoute Asymetric](../media/f6fd155b-bbb7-472a-846e-039a99f09913.png)
  
##### <a name="solution-2-source-nat"></a>Oplossing 2: bron-NAT
  
Door een bron-NAT toe te voegen aan de inkomende aanvraag, lost u dit verkeerd geconfigureerde netwerk op. In dit diagram:
  
1. De inkomende aanvraag gaat verder met het perimeternetwerk van het New York datacenter. Dit tijdstip NAT is beschikbaar.

2. Het antwoord van de server stuurt de e-mail terug naar het IP-adres dat is gekoppeld aan de bron-NAT in plaats van het oorspronkelijke IP-adres, wat resulteert in het antwoord op het desbetreffende netwerkpad.

![Routerings oplossing 3 voor ExpressRoute Asymetric](../media/a5d2b90d-a3ec-4047-afbf-6e6e99f376a7.png)
  
### <a name="paper-verify-that-the-network-design-has-path-symmetry"></a>Papier Controleer of het netwerkontwerp pad symmetrie heeft

Op dit moment moet u controleren of uw implementatieplan route symmetrie biedt voor de verschillende scenario's waarin u Office 365 gaat gebruiken. U identificeert de specifieke netwerkroute die naar verwachting wordt genomen wanneer een persoon verschillende functies van de service gebruikt. Vanuit het on-premises netwerk en WAN-routering naar de verbindingsapparaten, naar het toegangspad. ExpressRoute of Internet, en via de verbinding met het online-eindpunt.
  
U moet dit doen voor alle Office 365-netwerkservices die eerder zijn geïdentificeerd als services die uw organisatie zal aannemen.
  
Het artikel helpt u bij de loop van de routes met een tweede persoon. Leg ze uit waar elke hop van het netwerk naar verwachting van de volgende route gaat en zorg ervoor dat u bekend bent met de routeringspaden. Houd er rekening mee dat ExpressRoute altijd een meer bereik hoeft te routeren met IP-adressen van Microsoft server die de routekosten verlagen dan een standaardroute voor Internet.
  
### <a name="design-client-connectivity-configuration"></a>Client connectiviteit configureren
<a name="asymmetric"> </a>

![PAC-bestanden gebruiken met ExpressRoute](../media/7cfa6482-dbae-416a-ae6f-a45e5f4de23b.png)
  
Als u een proxyserver gebruikt voor het ontvangen van Internet-verkeer, moet u de configuratiebestanden voor de PAC of client aanpassen om ervoor te zorgen dat de clientcomputers in uw netwerk correct zijn geconfigureerd voor het verzenden van het ExpressRoute-verkeer naar Office 365 zonder dat u de proxyserver hoeft te doorsturen, en het resterende verkeer, waaronder wat Office 365-verkeer, wordt verzonden naar de desbetreffende proxy Lees onze richtlijnen voor het [beheren van Office 365-eindpunten](https://aka.ms/manageo365endpoints) voor voorbeelden van PAC-bestanden.
  
> [!NOTE]
> De eindpunten wijzigen regelmatig, net als wekelijks. U dient alleen wijzigingen aan te brengen op basis van de services en functies die uw organisatie heeft gekozen om het aantal wijzigingen die u moet aanbrengen, te beperken. Let op de **Ingangsdatum** in de RSS-feed waarbij de wijzigingen worden aangekondigd en een record wordt bewaard van alle eerdere wijzigingen, en IP-adressen die worden aangekondigd, worden mogelijk niet aangekondigd, of worden verwijderd uit de advertentie totdat de ingangsdatum is bereikt.
  
## <a name="build-your-deployment-and-testing-procedures"></a>Uw implementatie-en testprocedures maken
<a name="testing"> </a>

Voor de implementatie van uw implementatieplan moet zowel testen als een terugdraai planning bestaan. Als de implementatie niet werkt zoals verwacht, kan het plan van invloed zijn op het minste aantal personen voordat problemen worden gedetecteerd. Hier volgen enkele belangrijke principes voor uw abonnement.
  
1. Stage het netwerksegment en de Gebruikersservice onboarding om de onderbreking te beperken.

2. Plan voor het testen van routes met traceroute en TCP-verbinding vanaf een afzonderlijke host met internetverbinding.

3. Bij voorkeur wordt het testen van inkomende en uitgaande services uitgevoerd op een geïsoleerd test netwerk met een Office 365-Tenant testen.

      - U kunt ook testen uitvoeren op een productienetwerk als de klant Office 365 niet gebruikt of in de pilot fase zit.

      - Test kan ook worden uitgevoerd tijdens een productie storing die alleen is bedoeld voor testen en controleren.

      - U kunt de tests ook uitvoeren door routes te controleren voor elke service op elke laag 3 router knooppunt. Deze daling mag alleen worden gebruikt als er geen andere tests mogelijk zijn, aangezien het niet mogelijk is om Risico's te beproeven.

### <a name="build-your-deployment-procedures"></a>Uw implementatie procedures samenstellen

De implementatie procedures worden pas in fasen opgenomen in kleine groepen personen, zodat ze kunnen testen voordat ze voor de implementatie naar een grotere groep personen worden geïmplementeerd. Hier volgen enkele manieren om de implementatie van ExpressRoute te klaarzetten.
  
1. Stel ExpressRoute in met Microsoft peering en laat de routeaankondigingen doorgestuurd naar één host voor gefaseerde testdoeleinden.

2. Adverteer routes naar het ExpressRoute-netwerk in eerste instantie voor één netwerksegment en breid routeaankondigingen uit per netwerksegment of regio.

3. Als u Office 365 voor de eerste keer implementeert, gebruikt u de ExpressRoute-netwerkimplementatie als pilot voor een klein aantal personen.

4. Als u proxyservers gebruikt, kunt u ook een PAC-testbestand configureren om een klein aantal personen om te leiden naar ExpressRoute voor tests en feedback voordat u meer informatie toevoegt.

In uw implementatie abonnement moet een lijst worden opgenomen met de implementatie procedures die moeten worden gegeven of opdrachten die moeten worden gebruikt voor de implementatie van de netwerkconfiguratie. Wanneer de time-outperiode van het netwerk alle wijzigingen ontvangt, moet u afkomstig zijn van het schriftelijke implementatieplan dat vooraf werd vastgelegd en de geprojecteerde peer. Zie de technische configuratie van ExpressRoute voor meer informatie.
  
- De SPF TXT-records bijwerken als u IP-adressen hebt gewijzigd voor de on-premises servers waarop e-mail wordt verzonden.

- DNS-vermeldingen bijwerken voor on-premises servers als u IP-adressen hebt gewijzigd voor een nieuwe NAT-configuratie.

- Zorg ervoor dat u zich hebt geabonneerd op de RSS-feed voor Office 365-eindpunt meldingen om routerings-of proxyconfiguraties te onderhouden.

Nadat uw ExpressRoute-implementatie is voltooid, moeten de procedures in het testplan worden uitgevoerd. Resultaten van elke procedure moeten worden vastgelegd. U moet procedures voor het terugdraaien van de oorspronkelijke productieomgeving in het geval van de testplan resultaten aangeven dat de implementatie mislukt.
  
### <a name="build-your-test-procedures"></a>Uw testprocedures maken

Uw testprocedures dienen voor elke uitgaande en inkomende Netwerkservice voor Office 365 beide proeven te worden gebruikt die niet beschikbaar zijn voor ExpressRoute. U moet de procedures ook testen van elke unieke netwerklocatie, waaronder gebruikers die niet on-premises zijn in de bedrijfsnetwerk.
  
Hier volgen enkele voorbeelden van testactiviteiten.
  
1. Ping van uw on-premises router naar de router van de netwerkoperator.

2. Controleer of de 500 + Office 365 en CRM Online IP-adres aankondigingen zijn ontvangen op de on-premises router.

3. Validering van de binnenkomende en uitgaande NAT tussen ExpressRoute en het interne netwerk.

4. Controleer of routes naar de NAT worden aangekondigd vanaf de router.

5. Controleer of ExpressRoute de aangekondigde voorvoegsels heeft geaccepteerd.

      - Gebruik de volgende cmdlet om peering-advertenties te verifiëren:

      ```PowerShell
      Get-AzureRmExpressRouteCircuitRouteTable -DevicePath Primary -ExpressRouteCircuitName TestER -ResourceGroupName RG -PeeringType MicrosoftPeering
      ```

6. Uw openbare NAT-bereik valideren wordt niet aangekondigd bij Microsoft via een ander ExpressRoute of openbare Internet netwerkcircuit, tenzij dit een specifieke subset is van een groter bereik zoals in het vorige voorbeeld.

7. Voor ExpressRoute-circuits wordt een koppeling gemaakt, controleert u of beide BGP-sessies actief zijn.

8. Zet één host op de binnenzijde van uw NAT en gebruik ping, Tracert en tcpping om verbinding te testen via het nieuwe circuit naar de host outlook.office365.com. U kunt ook een hulpprogramma zoals wireshark of Microsoft Network Monitor 3,4 gebruiken op een gespiegelde poort naar de MSEE om te controleren of u verbinding kunt maken met het IP-adres dat is gekoppeld aan outlook.office365.com.

9. Test de functionaliteit op het toepassingsniveau voor Exchange Online.

  - Test of Outlook verbinding kan maken met Exchange Online en e-mail kan verzenden/ontvangen.

  - Test of Outlook kan worden gebruikt in de online modus.

  - Test de smartphone verbinding en de functies voor verzenden/ontvangen.

10. Functies voor toepassingsniveau testen voor SharePoint Online

  - Test de synchronisatieclient van OneDrive voor bedrijven.

  - Test de webtoegang voor SharePoint Online.

11. Test de functionaliteit op het toepassingsniveau voor oproep scenario's voor Skype voor bedrijven:

  - Deelnemen aan een telefonische vergadering als geverifieerde gebruiker [uitnodiging gestart door de eindgebruiker].

  - Gebruiker uitnodigen voor Vergader gesprek [uitnodiging verzonden via MCU].

  - Deelnemen aan een vergadering als anonieme gebruiker met de Skype voor bedrijven-webtoepassing.

  - Neem deel aan een oproep vanaf uw bekabelde PC-verbinding, IP-telefoon en mobiele apparaat.

  - Bellen naar federatieve gebruiker o oproep naar PSTN-validatie: oproep is voltooid, de gesprekskwaliteit is toegestaan, zodat de tijd van de verbinding acceptabel is.

  - Controleer of de aanwezigheidsstatus voor contactpersonen wordt bijgewerkt voor leden van de Tenant en voor federatieve gebruikers.

### <a name="common-problems"></a>Veelvoorkomende problemen

Asymmetrische routering is het meest voorkomende implementatieprobleem. Hier volgen enkele veelvoorkomende bronnen om te zoeken naar:
  
- Het gebruik van een open of platte netwerk routerings topologie zonder bron-NAT.

- Het niet gebruiken van SNAT om te routeren naar binnenkomende services via internet-en ExpressRoute-verbindingen.

- Het niet testen van binnenkomende services op ExpressRoute in een test netwerk voordat u globaal installeert.

## <a name="deploying-expressroute-connectivity-through-your-network"></a>ExpressRoute-verbindingen implementeren via uw netwerk
<a name="testing"> </a>

Faseer uw implementatie in één segment van het netwerk tegelijk en de connectiviteit met verschillende delen van het netwerk geleidelijk weer met een te herstellen plan voor elk nieuw netwerksegment. Als uw implementatie is uitgelijnd met een implementatie van Office 365, moet u eerst de proef gebruikers van Office 365 implementeren en verder verlengen.
  
Eerste voor uw test en dan voor productie:
  
- Voer de implementatie stappen uit om ExpressRoute in te schakelen.

- Test of u de verwachte netwerkroutes ziet.

- Voer tests uit op elke inkomende en uitgaande service.

- Herstel indien u problemen ontdekt.

### <a name="set-up-a-test-connection-to-expressroute-with-a-test-network-segment"></a>Een testverbinding naar ExpressRoute instellen met een test netwerksegment

Nu u het plan voor het voltooien van een papier hebt, is het tijd om te testen op een klein formaat. In deze test zet u één ExpressRoute-verbinding met Microsoft-peering op een subnet met subnetten op uw on-premises netwerk. U kunt een [proefversie van Office 365](https://go.microsoft.com/fwlink/p/?LinkID=403802) configureren met verbinding van en naar het subnet testen en alle uitgaande en binnenkomende services opnemen die u in de productie van het test subnet wilt gebruiken. DNS instellen voor het test netwerksegment en alle inkomende en uitgaande services vastleggen. Voer uw testplan uit en zorg ervoor dat u bekend bent met de routering voor elke service en de doorgestuurde route.
  
### <a name="execute-the-deployment-and-test-plans"></a>De implementatie-en testplannen uitvoeren

Wanneer u de bovenstaande items hebt uitgevoerd, schakelt u het selectievakje uit van de gebieden die u hebt voltooid en ervoor te zorgen dat u en uw team ze hebben bekeken voordat u de implementatie-en testplannen uitvoert.
  
- Lijst met uitgaande en binnenkomende services die zijn betrokken bij de netwerkwijziging.

- Wereldwijd netwerkarchitecturen diagram met zowel Internet uitvullen als ExpressRoute-locaties.

- Netwerk routerings diagram waarin de verschillende netwerkpaden worden aangegeven die worden gebruikt voor elke geïmplementeerde service.

- Een implementatieplan met stappen voor het implementeren van de wijzigingen en het terugdraaien, indien nodig.

- Een testplan voor het testen van elke Office 365-en Netwerkservice.

- Voltooide controle op papier van productieroutes voor binnenkomende en uitgaande services.

- Een voltooide test voor een test netwerksegment, inclusief het testen van de beschikbaarheid.

Kies een bewerkingsvenster dat lang genoeg moet zijn voor het hele implementatieplan en het testplan, met enige tijd voor het oplossen van problemen, indien nodig.
  
> [!CAUTION]
> Vanwege de ingewikkelde aard van het routeren via internet en ExpressRoute, wordt u aangeraden extra buffertijd toe te voegen aan dit venster voor het oplossen van ingewikkelde routering.
  
### <a name="configure-qos-for-skype-for-business-online"></a>QoS configureren voor Skype voor bedrijven online

QoS is noodzakelijk om de voordelen van spraak en vergadering te verkrijgen voor Skype voor bedrijven online. U kunt QoS configureren nadat u hebt gegarandeerd dat de netwerkverbinding van ExpressRoute geen van uw andere Office 365-service toegang blokkeert. De configuratie van QoS wordt beschreven in het artikel [ExpressRoute en QoS in Skype voor bedrijven online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) .
  
## <a name="troubleshooting-your-implementation"></a>Problemen met de implementatie oplossen
<a name="troubleshooting"> </a>

De eerste plaats waarop u wilt zoeken, is aan de hand van de stappen in deze Implementatiehandleiding gemist in uw implementatie abonnement? Ga terug en voer indien mogelijk verder klein netwerk te testen uit als dit mogelijk is om de fout te repliceren en de fout op te lossen.
  
Identificeer welke inkomende en uitgaande services niet konden worden uitgevoerd tijdens het testen. Gebruik specifiek de IP-adressen en subnetten voor elk van de services die mislukt. Ga verder met het netwerktopologie diagram en valideer de routering. U kunt met behulp van de ExpressRoute-routering voor de routering van de routering controleren of de routering is aankondigt.
  
Voer PSPing met een netwerktracering uit voor elke klanten-eindpunt en evalueer de bron-en doel-IP-adressen om te valideren dat ze correct werken. Voer Telnet uit voor een e-mail host die u vrijmaakt op poort 25 en controleer of het oorspronkelijke IP-adres van de IP-adressen wordt weergegeven als dit verwacht.
  
Houd er rekening mee dat bij het implementeren van Office 365 met een ExpressRoute-verbinding u ervoor dient te zorgen dat beide netwerkconfiguratie voor ExpressRoute optimaal is ontwikkeld en dat u ook de andere onderdelen van uw netwerk, zoals clientcomputers, hebt geoptimaliseerd. Naast het gebruik van deze planningshandleiding voor het oplossen van de stappen die u mogelijk hebt gemist, hebben we ook een [programma voor prestatieproblemen opgelost voor Office 365](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c) .
  
Met deze korte koppeling kunt u teruggaan: [https://aka.ms/implementexpressroute365](https://aka.ms/implementexpressroute365)
  
## <a name="related-topics"></a>Verwante onderwerpen

[Een beoordeling van de netwerkverbinding van Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute voor Office 365](azure-expressroute.md)
  
[ExpressRoute voor Office 365-connectiviteit beheren](managing-expressroute-for-connectivity.md)
  
[Routeren met ExpressRoute voor Office 365](routing-with-expressroute.md)
  
[Netwerk planning met ExpressRoute voor Office 365](network-planning-with-expressroute.md)
  
[Het gebruik van BGP-community's in ExpressRoute voor Office 365-scenario's](bgp-communities-in-expressroute.md)
  
[Media kwaliteit en prestaties van de netwerkverbinding in Skype voor bedrijven online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Uw netwerk optimaliseren voor Skype voor bedrijven online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute en QoS in Skype voor bedrijven online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Oproep stroom met behulp van ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Prestaties afstemmen van Office 365 met basislijnen en prestatie geschiedenis](performance-tuning-using-baselines-and-history.md)
  
[Prestatieproblemen met het plannen van Office 365](performance-troubleshooting-plan.md)
  
[URL's en IP-adresbereiken voor Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 netwerk en prestaties optimaliseren](network-planning-and-performance.md)
