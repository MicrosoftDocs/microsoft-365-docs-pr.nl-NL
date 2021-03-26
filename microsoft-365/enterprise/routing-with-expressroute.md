---
title: Routeren met ExpressRoute voor Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: e1da26c6-2d39-4379-af6f-4da213218408
description: In dit artikel leert u meer over routeringsvereisten, circuits en routeringsdomeinen voor Azure ExpressRoute voor gebruik met Office 365.
ms.openlocfilehash: 9d3c381cfb6e24c1c87ef3dcfb83a9b93f991b93
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222405"
---
# <a name="routing-with-expressroute-for-office-365"></a>Routeren met ExpressRoute voor Office 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Als u het routeringsverkeer naar Office 365 goed wilt begrijpen met Azure ExpressRoute, hebt u een goed inzicht nodig in de belangrijkste [ExpressRoute-routeringsvereisten](/azure/expressroute/expressroute-routing) en de [ExpressRoute-circuits en routeringsdomeinen.](/azure/expressroute/expressroute-circuit-peerings) Deze leggen de basisprincipes voor het gebruik van ExpressRoute voor waar Office 365-klanten op zullen vertrouwen.
  
Enkele van de belangrijkste items in de bovenstaande artikelen die u moet begrijpen, zijn:
  
- ExpressRoute-circuits worden niet in kaart gebracht aan specifieke fysieke infrastructuur, maar zijn een logische verbinding die op één peeringlocatie wordt gemaakt door Microsoft en een peeringprovider namens u.

- Er is een 1:1-toewijzing tussen een ExpressRoute-circuit en een s-key van de klant.

- Elk circuit kan twee onafhankelijke peeringrelaties ondersteunen (Azure Private peering en Microsoft peering); Office 365 vereist Microsoft-peering.

- Elk circuit heeft een vaste bandbreedte die wordt gedeeld in alle peeringrelaties.

- Openbare IPv4-adressen en openbare AS-nummers die worden gebruikt voor het ExpressRoute-circuit, moeten worden gevalideerd als eigendom van u of uitsluitend aan u toegewezen door de eigenaar van het adresbereik.

- De virtuele ExpressRoute-circuits zijn wereldwijd redundant en volgen standaard BGP-routeringspraktijken. Daarom raden we twee fysieke circuits aan die naar uw provider gaan in een actieve/actieve configuratie.

Zie de [pagina Veelgestelde vragen](/azure/expressroute/expressroute-faqs) voor meer informatie over ondersteunde services, kosten en configuratiegegevens. Zie het [artikel ExpressRoute-locaties](/azure/expressroute/expressroute-locations) voor informatie over de lijst met connectiviteitsproviders die ondersteuning bieden voor Microsoft-peering. We hebben ook een 10-delige Azure ExpressRoute voor [Office 365-trainingsreeks](https://channel9.msdn.com/series/aer) opgenomen op Kanaal 9 om de concepten beter uit te leggen.
  
## <a name="ensuring-route-symmetry"></a>Zorgen voor routesymmetrie

De front-endservers van Office 365 zijn toegankelijk op internet en ExpressRoute. Deze servers geven de voorkeur aan een route terug te leiden naar on-premises via ExpressRoute-circuits wanneer beide beschikbaar zijn. Hierdoor is er een mogelijkheid van routeasymmetrie als verkeer van uw netwerk de voorkeur geeft aan route via uw internetcircuits. Asymmetrische routes zijn een probleem omdat apparaten die stateful pakketcontrole uitvoeren, retourverkeer kunnen blokkeren dat een ander pad volgt dan de gevolgde uitgaande pakketten.
  
Ongeacht of u een verbinding met Office 365 start via internet of ExpressRoute, de bron moet een openbaar adres zijn. Omdat veel klanten rechtstreeks met Microsoft peering hebben, is het niet mogelijk om privéadressen te hebben waar duplicatie mogelijk is tussen klanten.
  
De volgende scenario's zijn waarin communicatie van Office 365 naar uw on-premises netwerk wordt gestart. Als u het netwerkontwerp wilt vereenvoudigen, raden we u aan deze te routeren via het internetpad.
  
- SMTP-services, zoals e-mail van een Exchange Online-tenant naar een on-premises host of SharePoint Online Mail die is verzonden vanuit SharePoint Online naar een on-premises host. SMTP-protocol wordt breder gebruikt binnen het microsoft-netwerk dan de route-voorvoegsels die worden gedeeld via ExpressRoute-circuits en het adverteren van on-premises SMTP-servers via ExpressRoute veroorzaakt fouten met deze andere services.

- ADFS tijdens wachtwoordvalidatie voor het aanmelden.

- [Hybride implementaties van Exchange Server](/exchange/exchange-hybrid).

- [Hybride zoeken in SharePoint federatief](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online).

- [Hybride BCS van SharePoint.](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution)

- [Skype voor Bedrijven hybride](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) en/of [Skype voor Bedrijven-federatie](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

- [Skype voor Bedrijven Cloud Connector](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Als Microsoft voor deze bi-directionele verkeersstromen terug naar uw netwerk wil, moeten de BGP-routes naar uw on-premises apparaten worden gedeeld met Microsoft. Wanneer u route-voorvoegsels aan Microsoft via ExpressRoute aanbetalt, moet u de volgende best practices volgen:

1) Maak geen reclame voor hetzelfde openbare IP-adresroute-voorvoegsel naar het openbare internet en via ExpressRoute. Het wordt aanbevolen dat de IP BGP Route Prefix-advertenties voor Microsoft via ExpressRoute afkomstig zijn van een bereik dat helemaal niet wordt aangekondigd op internet. Als dit niet mogelijk is vanwege de beschikbare IP-adresruimte, is het essentieel om ervoor te zorgen dat u reclame maakt voor een specifieker bereik via ExpressRoute dan internetcircuits.

2) Gebruik afzonderlijke NAT IP-pools per ExpressRoute-circuit en los van die van uw internetcircuits.

3) Let op: elke route die wordt aangekondigd bij Microsoft, trekt netwerkverkeer aan van elke server in het Microsoft-netwerk, niet alleen de routes waarvoor via ExpressRoute naar uw netwerk wordt aangekondigd. U kunt alleen routes adverteren naar servers waar routeringsscenario's zijn gedefinieerd en goed begrepen door uw team. Gebruik afzonderlijke IP-adresroute-voorvoegsels bij elk van meerdere ExpressRoute-circuits van uw netwerk.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>Bepalen welke toepassingen en functies worden gebruikt via ExpressRoute

Wanneer u een peeringrelatie configureert met behulp van het microsoft-peeringrouteringsdomein en wordt goedgekeurd voor de juiste toegang, kunt u alle PaaS- en SaaS-services zien die beschikbaar zijn via ExpressRoute. De Office 365-services die zijn ontworpen voor ExpressRoute, kunnen worden beheerd met [BGP-community's](./bgp-communities-in-expressroute.md) of [routefilters.](/azure/expressroute/how-to-routefilter-portal)
  
Andere toepassingen, zoals Office 365 Video, is een Office 365-toepassing. Office 365 Video bestaat echter uit drie verschillende onderdelen: de portal, de streamingservice en het netwerk voor het leveren van inhoud. De portal woont in SharePoint Online, de streamingservice woont in Azure Media Services en het netwerk voor inhoudslevering is binnen het Azure CDN. In de volgende tabel worden deze onderdelen beschreven.

|**Onderdeel**|**Onderliggende toepassing**|**Opgenomen in de BGP-community van SharePoint Online?**|**Gebruik**|
|:-----|:-----|:-----|:-----|
|Office 365 Video-portal  <br/> |SharePoint Online  <br/> |Ja  <br/> |Configuratie, uploaden  <br/> |
|Streamingservice voor Office 365 Video  <br/> |Azure Media Services  <br/> |Nee  <br/> |Streamingservice, die wordt gebruikt voor het geval de video niet beschikbaar is vanuit het CDN  <br/> |
|Office 365 Video-netwerk voor inhoudsbezorging  <br/> |Azure CDN  <br/> |Nee  <br/> |Primaire bron van video downloaden/streamen. [Meer informatie over Office 365-videonetwerken.](https://support.office.com/article/Office-365-Video-networking-Frequently-Asked-Questions-FAQ-2bed67a1-4052-49ff-a4ce-b7e6530eb98e)  <br/> |

Elk van de Office 365-functies die beschikbaar zijn met Microsoft-peering, worden weergegeven in het Office 365-eindpunten-artikel op [toepassingstype](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) en FQDN. De reden voor het gebruik van FQDN in de tabellen is dat klanten verkeer kunnen beheren met PAC-bestanden of andere proxyconfiguraties, zie onze handleiding voor het beheren van [Office 365-eindpunten,](./managing-office-365-endpoints.md) bijvoorbeeld PAC-bestanden.
  
In sommige situaties hebben we een jokertekendomein gebruikt waarbij een of meer sub-FQDN's anders worden aangekondigd dan het jokertekendomein op een hoger niveau. Dit gebeurt meestal wanneer het jokerteken een lange lijst met servers vertegenwoordigt die allemaal worden aangekondigd bij ExpressRoute en internet, terwijl een kleine subset bestemmingen alleen wordt aangekondigd op internet of omgekeerd. Raadpleeg de onderstaande tabellen om te begrijpen waar de verschillen zijn.
  
In deze tabel worden de jokerteken-FQDN's weergegeven die worden aangekondigd voor zowel internet als Azure ExpressRoute, naast de sub-FQDN's die alleen worden aangekondigd op internet.

|**Jokertekendomein dat wordt aangekondigd voor ExpressRoute- en internetcircuits**|**Sub-FQDN alleen aangekondigd voor internetcircuits**|
|:-----|:-----|
|\*.microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*.officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

Meestal zijn PAC-bestanden bedoeld om netwerkaanvragen rechtstreeks naar het circuit en alle andere netwerkaanvragen naar uw proxy te verzenden. Als u een PAC-bestand als dit configureert, stelt u het PAC-bestand in de volgende volgorde op:
  
1. Voeg de sub-FQDN's uit kolom twee in de bovenstaande tabel boven aan het PAC-bestand toe, en stuur het verkeer naar uw proxy. We hebben een voorbeeld-PAC-bestand gemaakt dat u kunt gebruiken in ons artikel over het beheren van [Office 365-eindpunten.](./managing-expressroute-for-connectivity.md)

2. Neem alle FQDN's op die zijn gemarkeerd met ExpressRoute [in](./urls-and-ip-address-ranges.md) dit artikel onder de eerste sectie, en stuur het verkeer rechtstreeks naar uw ExpressRoute-circuit.

3. Neem eventuele andere netwerk-eindpunten of -regels onder deze twee items op, die het verkeer naar uw proxy verzenden.

In deze tabel worden de jokertekendomeinen weergegeven die alleen worden aangekondigd op internetcircuits naast de sub-FQDN's die worden aangekondigd voor Azure ExpressRoute- en internetcircuits. Voor het PAC-bestand hierboven worden de FQDN's in kolom 2 in de onderstaande tabel weergegeven als wordt aangekondigd voor ExpressRoute in de koppeling waarnaar wordt verwezen, wat betekent dat ze worden opgenomen in de tweede groep items in het bestand.

|**Jokertekendomein dat alleen wordt aangekondigd voor internetcircuits**|**Sub-FQDN aangekondigd voor ExpressRoute- en internetcircuits**|
|:-----|:-----|
|\*.office.com  <br/> |\*.outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*.office.net  <br/> |agent.office.net  <br/> |
|\*.office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*.outlook.com  <br/> |\*.protection.outlook.com  <br/> \*.mail.protection.outlook.com  <br/> autodiscover- \<tenant\> .outlook.com  <br/> |
|\*.windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>Office 365-verkeer routeren via internet en ExpressRoute

Als u naar de Office 365-toepassing van uw keuze wilt gaan, moet u een aantal belangrijke factoren bepalen.
  
1. Hoeveel bandbreedte de toepassing nodig heeft. Een steekproef van bestaand gebruik is de enige betrouwbare methode om dit in uw organisatie te bepalen.

2. Welke uitgangslocatie(en) u wilt dat het netwerkverkeer uw netwerk verlaat. U moet van plan zijn om de netwerklatentie voor connectiviteit met Office 365 te minimaliseren, omdat dit van invloed is op de prestaties. Omdat Skype voor Bedrijven realtime spraak en video gebruikt, is deze met name gevoelig voor slechte netwerklatentie.

3. Als u wilt dat alle of een subset van uw netwerklocaties ExpressRoute gebruikt.

4. Van welke locaties uw gekozen netwerkprovider ExpressRoute biedt.

Wanneer u de antwoorden op deze vragen hebt bepaald, kunt u een ExpressRoute-circuit inrichten dat voldoet aan de bandbreedte en locatiebehoeften. Voor meer hulp bij netwerkplanning raadpleegt u de Office 365-netwerkafstemmingshandleiding en de case study over de manier waarop Microsoft met netwerkprestatieplanning [omgaat.](https://aka.ms/tunemsit) [](./network-planning-and-performance.md)
  
### <a name="example-1-single-geographic-location"></a>Voorbeeld 1: Enkele geografische locatie
  
Dit voorbeeld is een scenario voor een fictieve onderneming met de naam Trey Research die één geografische locatie heeft.
  
Werknemers van Trey Research mogen alleen verbinding maken met de services en websites op internet die door de beveiligingsafdeling expliciet worden toegestaan op het paar uitgaande proxies tussen het bedrijfsnetwerk en hun internetprovider.
  
Trey Research is van plan Azure ExpressRoute voor Office 365 te gebruiken en erkent dat sommige verkeer, zoals verkeer dat is bestemd voor netwerken voor inhoudsbezorging, niet kan worden omgeleid via de ExpressRoute voor Office 365-verbinding. Aangezien al het verkeer standaard al naar de proxyapparaten wordt gerouteerd, blijven deze aanvragen zoals voorheen werken. Nadat Trey Research heeft bepaald dat ze kunnen voldoen aan de routeringsvereisten voor Azure ExpressRoute, gaan ze verder met het maken van een circuit, het configureren van routering en het koppelen van het nieuwe ExpressRoute-circuit aan een virtueel netwerk. Wanneer de basisconfiguratie van Azure ExpressRoute is uitgevoerd, gebruikt Trey Research het [#2 PAC-bestand](./managing-office-365-endpoints.md)  dat we publiceren om verkeer met klantspecifieke gegevens door te sturen via de directe ExpressRoute voor Office 365-verbindingen.
  
Zoals wordt weergegeven in het volgende diagram, kan Trey Research voldoen aan de vereiste om Office 365-verkeer via internet en een subset verkeer via ExpressRoute te routeren met behulp van een combinatie van routerings- en uitgaande proxyconfiguratiewijzigingen.
  
1. Met het [#2 PAC-bestand dat we](./managing-office-365-endpoints.md) publiceren om verkeer door een afzonderlijk internet-uitgangspunt voor Azure ExpressRoute voor Office 365 te leiden.

2. Clients worden geconfigureerd met een standaardroute naar trey research's proxies.

In dit voorbeeldscenario gebruikt Trey Research een uitgaand proxyapparaat. Op dezelfde manier willen klanten die Azure ExpressRoute voor Office 365 niet gebruiken, deze techniek gebruiken om verkeer te routen op basis van de kosten voor het controleren van verkeer dat is bestemd voor bekende eindpunten met een hoog volume.
  
Het hoogste volume FQDN's voor Exchange Online, SharePoint Online en Skype voor Bedrijven Online zijn de volgende:
  
![ExpressRoute customer edge network](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com, outlook.office.com

- \<tenant-name\>.sharepoint.com, \<tenant-name\> -my.sharepoint.com, \<tenant-name\> - \<app\> .sharepoint.com

- \*. Lync.com ip-bereik voor niet-TCP-verkeer

- \*broadcast.officeapps.live.com, \* excel.officeapps.live.com, \* onenote.officeapps.live.com, \* powerpoint.officeapps.live.com, \* \* view.officeapps.live.com, visio.officeapps.live.com, \* word-edit.officeapps.live.com, \* word-view.officeapps.live.com, office.live.com

Meer informatie over het implementeren en beheren van [proxy-instellingen in](/archive/blogs/deploymentguys/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy) Windows 8 en ervoor te zorgen dat Office [365](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx)niet wordt beperkt door uw proxy.
  
Met één ExpressRoute-circuit is er geen hoge beschikbaarheid voor Trey Research. In het geval dat het redundante paar edge-apparaten van Trey dat de ExpressRoute-connectiviteit onderhoudt, mislukt, is er geen extra ExpressRoute-circuit om te mislukken. Hierdoor blijft Trey Research in een situatie waarin het niet lukt om naar internet te gaan, handmatig opnieuw configureren en in sommige gevallen nieuwe IP-adressen. Als Trey hoge beschikbaarheid wil toevoegen, is de eenvoudigste oplossing het toevoegen van extra ExpressRoute-circuits voor elke locatie en het configureren van de circuits op een actieve/actieve manier.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>ExpressRoute routeren voor Office 365 met meerdere locaties

Het laatste scenario, het routeren van Office 365-verkeer via ExpressRoute, is de basis voor nog complexere routeringsarchitectuur. Ongeacht het aantal locaties, het aantal continenten waar deze locaties aanwezig zijn, het aantal ExpressRoute-circuits, en ga zo maar door, is het nodig om verkeer naar internet te kunnen leiden en is een deel van het verkeer via ExpressRoute vereist.
  
De extra vragen die moeten worden beantwoord voor klanten met meerdere locaties in meerdere regio's zijn:
  
1. Hebt u op elke locatie een ExpressRoute-circuit nodig? Als u Skype voor Bedrijven Online gebruikt of zich zorgen maakt over latentiegevoeligheid voor SharePoint Online of Exchange Online, wordt op elke locatie een redundant paar actieve/actieve ExpressRoute-circuits aanbevolen. Zie de mediakwaliteits- en netwerkconnectiviteitshandleiding van Skype voor Bedrijven voor meer informatie.

2. Als een ExpressRoute-circuit niet beschikbaar is in een bepaalde regio, hoe moet het verkeer van Office 365 dan worden omgeleid?

3. Wat is de voorkeursmethode voor het samenvoegen van verkeer in het geval van netwerken met veel kleine locaties?

Elk van deze opties biedt een unieke uitdaging, die vereist dat u uw eigen netwerk en de beschikbare opties van Microsoft evalueert.

|**Overweging**|**Netwerkonderdelen om te evalueren**|
|:-----|:-----|
|Circuits op meer dan één locatie  <br/> |We raden u aan minimaal twee circuits te gebruiken die op een actieve/actieve manier zijn geconfigureerd.  <br/> Kosten, latentie en bandbreedtebehoeften moeten worden vergeleken.  <br/> Gebruik BGP-routekosten, PAC-bestanden en NAT om routering met meerdere circuits te beheren.  <br/> |
|Routering van locaties zonder ExpressRoute-circuit  <br/> |We raden u aan de aanvraag voor Office 365 af te ronden en de DNS-resolutie te sluiten.  <br/> DNS-doorsturen kan worden gebruikt om externe kantoren in staat te stellen het juiste eindpunt te vinden.  <br/> Clients in het externe kantoor moeten een route beschikbaar hebben die toegang biedt tot het ExpressRoute-circuit.  <br/> |
|Kleine kantoorconsolidatie  <br/> |Beschikbare bandbreedte en gegevensgebruik moeten zorgvuldig worden vergeleken.  <br/> |

> [!NOTE]
> Microsoft geeft de voorkeur aan ExpressRoute boven internet als de route beschikbaar is, ongeacht de fysieke locatie.
  
Met elk van deze overwegingen moet rekening worden gehouden voor elk uniek netwerk. Hieronder vindt u een voorbeeld.
  
### <a name="example-2-multi-geographic-locations"></a>Voorbeeld 2: Multi-geografische locaties
  
Dit voorbeeld is een scenario voor een fictieve onderneming genaamd Humongous Insurance die meerdere geografische locaties heeft.
  
Humongous Insurance is geografisch verspreid met kantoren over de hele wereld. Ze willen Azure ExpressRoute voor Office 365 implementeren om het meeste Office 365-verkeer op directe netwerkverbindingen te houden. Humongous Insurance heeft ook kantoren op twee andere continenten. De werknemers in het externe kantoor waar ExpressRoute niet haalbaar is, moeten terugleiden naar een of beide primaire faciliteiten om een ExpressRoute-verbinding te gebruiken.
  
Het uitgangspunt is om zo snel mogelijk verkeer naar een Microsoft-datacenter te krijgen dat bestemd is voor Office 365. In dit voorbeeld moet Humongous Insurance bepalen of de externe kantoren via internet moeten worden gerouteerd om zo snel mogelijk via een verbinding naar een Microsoft-datacenter te gaan of dat hun externe kantoren een route moeten maken via een intern netwerk om zo snel mogelijk via een ExpressRoute-verbinding naar een Microsoft-datacenter te gaan.
  
De datacenters, netwerken en toepassingsarchitectuur van Microsoft zijn ontworpen om de communicatie over de hele wereld op een zo efficiënt mogelijke manier te kunnen gebruiken. Dit is een van de grootste netwerken ter wereld. Aanvragen die bestemd zijn voor Office 365 die langer dan nodig in klantnetwerken blijven, kunnen niet profiteren van deze architectuur.
  
In de situatie van Humongous Insurance moeten ze doorgaan, afhankelijk van de toepassingen die ze via ExpressRoute willen gebruiken. Als ze bijvoorbeeld een skype voor Bedrijven Online-klant zijn of van plan zijn ExpressRoute-connectiviteit te gebruiken bij het maken van verbinding met externe Skype voor Bedrijven Online-vergaderingen, is het ontwerp dat wordt aanbevolen in de gids voor mediakwaliteit en netwerkconnectiviteit van Skype voor Bedrijven Online door een extra ExpressRoute-circuit in te stellen voor de derde locatie. Dit kan duurder zijn vanuit een netwerkperspectief. Routeringsaanvragen van het ene continent naar het andere voordat ze naar een Microsoft-datacenter worden gebracht, kunnen echter een slechte of onbruikbaare ervaring veroorzaken tijdens skype voor Bedrijven Online-vergaderingen en -communicatie.
  
Als Humongous Insurance Skype voor Bedrijven Online op geen enkele manier gebruikt of niet van plan is, kan het routeren van office 365 bestemd netwerkverkeer naar een continent met een ExpressRoute-verbinding haalbaar zijn, maar kan dit leiden tot onnodige latentie of TCP-congestie. In beide gevallen wordt het routeren van internetverkeer naar internet op de lokale site aanbevolen om te profiteren van de netwerken voor inhoudsbezorging waar Office 365 op vertrouwt.
  
![ExpressRoute multigeografie](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Wanneer Humongous Insurance hun strategie voor meerdere geografien plant, zijn er een aantal dingen die u moet overwegen rond de grootte van circuit, het aantal circuits, failover, en ga zo maar door.
  
Met ExpressRoute op één locatie met meerdere regio's die het circuit proberen te gebruiken, wil Humongous Insurance ervoor zorgen dat verbindingen met Office 365 vanuit het externe kantoor worden verzonden naar het dichtstbijzijnde hoofdkantoor van het Office 365-datacenter en worden ontvangen door de hoofdkantoorlocatie. Hiervoor implementeert Humongous Insurance DNS forwarding om het aantal retouren en DNS-opzoekingen te verminderen dat nodig is om de juiste verbinding tot stand te brengen met de Office 365-omgeving die zich het dichtst bij het internet-uitgangspunt van het hoofdkantoor bevindt. Hiermee voorkomt u dat de client een lokale front-endserver kan oplossen en zorgt u ervoor dat de Front-End-server die de persoon verbindt, zich in de buurt van het hoofdkantoor bevindt waar Humongous Insurance met Microsoft peert. U kunt ook leren een [voorwaardelijke doorst forwarder toe te wijzen voor een domeinnaam.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc794735(v=ws.10))
  
In dit scenario zou het verkeer van het externe kantoor de front-endinfrastructuur van Office 365 in Noord-Amerika oplossen en Office 365 gebruiken om verbinding te maken met de back-endservers volgens de architectuur van de Office 365-toepassing. Exchange Online beëindigt bijvoorbeeld de verbinding in Noord-Amerika en die front-endservers maken verbinding met de back-endpostvakserver, waar de tenant zich ook bevindt. Alle services hebben een breed verspreide front-door-service die bestaat uit unicast- en anycast-bestemmingen.
  
Als Humongous grote kantoren heeft op meerdere continenten, wordt een minimum van twee actieve/actieve circuits per regio aanbevolen om de latentie voor gevoelige toepassingen, zoals Skype voor Bedrijven Online, te verminderen. Als alle kantoren zich op één continent of niet in realtime samenwerken, is het een klantspecifieke beslissing om een geconsolideerd of gedistribueerd uitgangspunt te hebben. Wanneer er meerdere circuits beschikbaar zijn, zorgt BGP-routering ervoor dat failover wordt gebruikt als één circuit niet beschikbaar is.
  
Meer informatie over [voorbeeldrouteringsconfiguraties](/azure/expressroute/expressroute-config-samples-routing) en [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](/azure/expressroute/expressroute-config-samples-nat) .
  
## <a name="selective-routing-with-expressroute"></a>Selectieve routering met ExpressRoute

Selectieve routering met ExpressRoute kan om verschillende redenen nodig zijn, zoals het testen, het uitrollen van ExpressRoute naar een subset van gebruikers. Er zijn verschillende hulpprogramma's die klanten kunnen gebruiken om Office 365-netwerkverkeer selectief te routen via ExpressRoute:
  
1. **Routefilters/segregatie:** de BGP-routes naar Office 365 via ExpressRoute toestaan naar een subset van uw subnetten of routers. Hiermee wordt selectief gerouteerd per klantnetwerksegment of fysieke kantoorlocatie. Dit is gebruikelijk voor een duizelingwekkende implementatie van ExpressRoute voor Office 365 en is geconfigureerd op uw BGP-apparaten.

2. **PAC-bestanden/URL's:** het doorverzenderen van office 365-netwerkverkeer voor specifieke FQDN's die u op een bepaald pad wilt routeren. Hiermee wordt selectief gerouteerd op de clientcomputer, zoals aangegeven door [PAC-bestandsimplementatie.](./managing-office-365-endpoints.md)

3. **Routefiltering**  -  [Routefilters](/azure/expressroute/how-to-routefilter-portal) zijn een manier om een subset met ondersteunde services te gebruiken via Microsoft-peering.

4. **BGP-community's:** met filteren op basis van [BGP-communitylabels](./bgp-communities-in-expressroute.md) kan een klant bepalen welke Office 365-toepassingen ExpressRoute doorkruisen en welke via internet worden gebruikt.

Met deze korte koppeling kunt u teruggaan: [https://aka.ms/erorouting]()
  
## <a name="related-topics"></a>Verwante onderwerpen

[Office 365-netwerkverbinding beoordelen](assessing-network-connectivity.md)
  
[Azure ExpressRoute voor Office 365](azure-expressroute.md)
  
[ExpressRoute voor Office 365-connectiviteit beheren](managing-expressroute-for-connectivity.md)
  
[Netwerkplanning met ExpressRoute voor Office 365](network-planning-with-expressroute.md)
  
[ExpressRoute implementeren voor Office 365](implementing-expressroute.md)
  
[Mediakwaliteit en prestaties van de netwerkverbinding in Skype voor Bedrijven Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Uw netwerk instellen voor Skype voor Bedrijven Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute en QoS in Skype voor Bedrijven Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Oproepstroom met ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[BGP-community's gebruiken in ExpressRoute voor Office 365-scenario's](bgp-communities-in-expressroute.md)
  
[Office 365-prestatieafstemming met behulp van basislijnen en prestatiegeschiedenis](performance-tuning-using-baselines-and-history.md)
  
[Prestatieproblemen met Office 365 oplossen: planning](performance-troubleshooting-plan.md)
  
[URL's en IP-adresbereiken voor Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Aanpassing van Office 365-netwerk en -prestaties](network-planning-and-performance.md)