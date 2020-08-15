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
description: In dit artikel vindt u meer informatie over de routerings vereisten, circuits en Routeringsdomeinen van Azure ExpressRoute voor gebruik met Office 365.
ms.openlocfilehash: 7201c23777cbf4ca5285736db5a947955a443c51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689010"
---
# <a name="routing-with-expressroute-for-office-365"></a>Routeren met ExpressRoute voor Office 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Voor een goed overzicht van routerings verkeer naar Office 365 met behulp van Azure ExpressRoute, hebt u een firma begrijpt nodig van de kern [ExpressRoute routerings vereisten](https://azure.microsoft.com/documentation/articles/expressroute-routing/) en de [Routeringsdomeinen en de Routeringsdomeinen](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/). Dit zijn de grondbeginselen voor het gebruik van ExpressRoute waartoe Office 365-klanten vertrouwen.
  
Voor enkele van de belangrijkste artikelen in de artikelen die u nodig hebt, dient u het volgende te weten:
  
- ExpressRoute-circuits worden niet toegewezen aan een specifieke fysieke infrastructuur, maar zijn een logische verbinding gemaakt op één peering-locatie door Microsoft en een peering provider namens u.

- Er is een 1:1-toewijzing tussen een ExpressRoute-circuit en de s-key van een klant.

- Elk circuit biedt ondersteuning voor 2 onafhankelijke peering relaties (Azure private peering en Microsoft peering). Voor Office 365 is Microsoft peering vereist.

- Elk circuit heeft een vaste bandbreedte die wordt gedeeld via alle peers relaties.

- Geldige IPv4-adressen en openbare IPv4-adressen die worden gebruikt voor het ExpressRoute-circuit, moeten zijn gevalideerd of u de eigenaar bent van het adresbereik.

- De virtuele ExpressRoute-circuits zijn wereldwijd redundant en zullen de standaard BGP-routeringsmethoden volgen. U wordt aangeraden twee fysieke circuits per uitgang van de provider uit te voeren in een actieve/actieve configuratie.

Zie de [pagina met veelgestelde vragen](https://azure.microsoft.com/documentation/articles/expressroute-faqs/) voor meer informatie over ondersteunde services, kosten en configuratiedetails. Zie het [artikel ExpressRoute locations](https://azure.microsoft.com/documentation/articles/expressroute-locations/) voor informatie over de lijst met verbindings providers die ondersteuning bieden voor Microsoft peering. We hebben ook een 10-Part [Azure ExpressRoute voor Office 365-trainings serie voor Office-training](https://channel9.msdn.com/series/aer) opgenomen in kanaal 9, zodat u de concepten uitgebreider kunt uitleggen.
  
## <a name="ensuring-route-symmetry"></a>Zorgen voor route symmetrie

De front-end servers van Office 365 zijn toegankelijk op internet en ExpressRoute. Deze servers routeren liever terug naar on-premises ExpressRoute-circuits wanneer beide beschikbaar zijn. Daarom is er sprake van route-asymmetrie als het verkeer van uw netwerk de routerende voorkeur heeft voor het routeren van Internet circuits. Asymmetrische routes zijn een probleem omdat apparaten die stateful pakket inspectie uitvoeren, het retour verkeer kunnen blokkeren die op een ander pad volgen dan de uitgaande pakketten.
  
Ongeacht of u een verbinding tot stand brengt met Office 365 via internet of ExpressRoute, moet de bron een openbaar routeerbaar adres zijn. Met een groot aantal klanten die rechtstreeks met Microsoft worden afpeeren, met persoonlijke adressen waar de mogelijkheid bestaat dat de klant niet haalbaar is.
  
Hier volgen een scenario waarin communicatie van Office 365 naar uw on-premises netwerk wordt gestart. Om het ontwerp van uw netwerk te vereenvoudigen, is het raadzaam deze via het Internet pad te routeren.
  
- SMTP-services zoals e-mail van een Exchange Online-Tenant naar een on-premises host of SharePoint Online-E-mail verzonden vanaf SharePoint Online naar een on-premises host. Het SMTP-protocol wordt globaal uitgebreid weergegeven in het Microsoft-netwerk dan de route prefixen die worden gedeeld via ExpressRoute-circuits en on-premises SMTP-servers via ExpressRoute veroorzaken een storing met deze andere services.

- ADFS tijdens wachtwoordvalidatie voor aanmelden.

- [Hybride implementaties van Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx).

- [Hybride zoeken in SharePoint](https://technet.microsoft.com/library/dn197174.aspx)

- [Hybride versie van SharePoint](https://technet.microsoft.com/library/dn197239.aspx ).

- [Skype voor bedrijven](https://technet.microsoft.com/library/jj205403.aspx) -Federatie voor hybride en/of [Skype voor bedrijven](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx).

- [Skype voor bedrijven cloud connector](https://technet.microsoft.com/library/mt605227.aspx ).

Als u wilt dat Microsoft terugkeert naar uw netwerk voor deze bidirectionele verkeersstromen, moet u de BGP-routes naar uw on-premises apparaten delen met Microsoft. Wanneer u route prefixen adverteert voor Microsoft via ExpressRoute, moet u de volgende aanbevolen procedures volgen:

1) Adverteer niet op hetzelfde openbare IP-adres voorvoegsel voor het openbare Internet en via ExpressRoute. Het wordt ten zeerste aanbevolen dat de IP BGP-route voorvoegsel advertenties naar Microsoft via ExpressRoute, afkomstig zijn van een bereik dat u helemaal niet adverteert naar het internet. Als dit niet mogelijk is vanwege de beschikbare IP-adresruimte, moet u ervoor zorgen dat u een specifiek bereik voor ExpressRoute adverteert dan alle Internet circuits.

2) Gebruik afzonderlijke NAT IP-Pools per ExpressRoute-circuit en scheid deze van uw Internet circuits.

3) Wanneer een door u geadverteerde route naar Microsoft het netwerkverkeer van een server in het netwerk van Microsoft trekt, wordt het netwerkverkeer van een server met het Microsoft-netwerk aantrekken, niet alleen voor degenen met wie de routes worden aangekondigd via ExpressRoute. U kunt alleen routes adverteren naar servers waar routeringsscenario's zijn gedefinieerd en duidelijk zijn voor uw team. Neem aparte route-prefixen voor IP-adressen op bij elk van de verschillende ExpressRoute-circuits van uw netwerk.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>Bepalen welke toepassingen en functies u wilt routeren via ExpressRoute

Wanneer u een peering-relatie configureert met behulp van het Microsoft peering-routeringsdomein en wordt goedgekeurd voor de juiste toegang, ziet u alle PaaS-en SaaS-services die via ExpressRoute beschikbaar zijn. De Office 365-services die zijn ontworpen voor ExpressRoute, kunnen worden beheerd met [BGP-community's](https://aka.ms/bgpexpressroute365) of [routefilters](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal).
  
Andere toepassingen zoals Office 365 video, is een Office 365-toepassing. de video van Office 365 bestaat echter uit drie verschillende onderdelen, de portal, de streaming-service en het netwerk voor content levering. De portal valt binnen SharePoint Online, de streaming-service binnen Azure Media Services en het netwerk voor content levering binnen het Azure CDN. De volgende tabel bevat een overzicht van deze onderdelen.

|**Invoert**|**Onderliggende toepassing**|**Inbegrepen in de SharePoint Online-BGP-Community?**|**Gebruik**|
|:-----|:-----|:-----|:-----|
|Video portal van Office 365  <br/> |SharePoint Online  <br/> |Ja  <br/> |Configuratie, uploaden  <br/> |
|Service Office 365 video streaming  <br/> |Azure Media Services  <br/> |Nee  <br/> |Streaming-service, die wordt gebruikt in het geval dat de video niet beschikbaar is in het CDN  <br/> |
|Office 365 video-leverings netwerk  <br/> |Azure CDN  <br/> |Nee  <br/> |Primaire bron van video downloaden/streaming. Meer [informatie over Office 365 video-netwerken](https://support.office.com/article/Office-365-Video-networking-Frequently-Asked-Questions-FAQ-2bed67a1-4052-49ff-a4ce-b7e6530eb98e).  <br/> |

Alle Office 365-functies die beschikbaar zijn via Microsoft peering, worden weergegeven in het [artikel Office 365-eindpunten](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) van toepassingstype en FQDN. De reden voor het gebruik van de FQDN in de tabellen is de mogelijkheid te bieden klanten verkeer te laten beheren met behulp van PAC-bestanden of andere proxyconfiguraties, Lees onze handleiding voor het [beheren van Office 365-eindpunten](https://aka.ms/manageo365endpoints) voor voorbeelden van PAC-bestanden.
  
In sommige situaties hebben we een Joker domein gebruikt waarbij een of meer subtotalen anders worden geadverteerd dan het domein met jokertekens voor hoger niveau. Dit gebeurt meestal wanneer het jokerteken een lange lijst vertegenwoordigt met servers die worden geadverteerd naar ExpressRoute en Internet, terwijl een kleine subreeks bestemmingen alleen wordt aangekondigd op internet, of omgekeerd. Zie de onderstaande tabellen om te begrijpen waar de verschillen zijn.
  
In deze tabel ziet u de jokertekens die worden aangekondigd op internet en bij Azure ExpressRoute naast de subfqdns die alleen worden aangekondigd op internet.

|**Jokers domein aangekondigd bij ExpressRoute en Internet circuits**|**Subdomein-FQDN die alleen wordt aangekondigd op Internet circuits**|
|:-----|:-----|
|\*. microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*. officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

Meestal PAC-bestanden zijn bedoeld om netwerkaanvragen te verzenden naar ExpressRoute aangekondigde eindpunten rechtstreeks naar het circuit en alle andere netwerkverzoeken van uw proxy. Als u een PAC-bestand zoals dit configureert, moet u een PAC-bestand opstellen in de volgende volgorde:
  
1. Neem de sub-FQDN-namen op uit de kolom twee in de bovenstaande tabel bovenaan het PAC-bestand en verzend het verkeer naar uw proxy. Er is een voorbeeld van een PAC-bestand gemaakt dat u in ons artikel kunt gebruiken voor het [beheren van Office 365-eindpunten](https://aka.ms/manageexpressroute365).

2. Neem alle FQDN-namen op die zijn gemarkeerd in het ExpressRoute in [dit artikel](https://aka.ms/o365endpoints) , onder de eerste sectie, het verkeer rechtstreeks naar uw ExpressRoute-circuit verzenden.

3. Neem eventuele andere netwerkeindpunten of-regels op onder deze twee vermeldingen om het verkeer naar uw proxy te sturen.

In deze tabel ziet u de jokertekens die worden aangekondigd op Internet circuits, naast de onderliggende FQDN-namen die worden aangekondigd in azure ExpressRoute en Internet circuits. Voor het bovenstaande PAC-bestand worden de FQDN-namen in kolom twee in de bovenstaande tabel weergegeven als aangekondigd in ExpressRoute in de koppeling waarnaar wordt verwezen, wat betekent dat ze in de tweede groep met gegevens in het bestand worden opgenomen.

|**Domein met jokertekens wordt alleen aangekondigd naar Internet circuits**|**Subfqdn die wordt aangekondigd bij ExpressRoute en Internet circuits**|
|:-----|:-----|
|\*. office.com  <br/> |\*. outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*. office.net  <br/> |agent.office.net  <br/> |
|\*. office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*. outlook.com  <br/> |\*. protection.outlook.com  <br/> \*. mail.protection.outlook.com  <br/> automatisch opsporen: \<tenant\> . Outlook.com  <br/> |
|\*. windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>Office 365-verkeer routeren via internet en ExpressRoute

U moet een aantal belangrijke factoren bepalen om te routeren naar de Office 365-toepassing van uw keuze.
  
1. De hoeveelheid bandbreedte die voor de toepassing is vereist. Een steekproef van een bestaand gebruik is de enige betrouwbare methode om dit in uw organisatie te bepalen.

2. Welke locatie (s) u wilt dat het netwerkverkeer van uw netwerk vervalt. U moet de netwerklatentie voor connectiviteit met Office 365 minimaliseren omdat dit gevolgen heeft voor de prestaties. Omdat Skype voor bedrijven gebruikmaakt van realtime spraak en video, is dit met name kwetsbaar voor slechte netwerklatentie.

3. Als u wilt dat alle of een subset van uw netwerklocaties gebruikmaakt van ExpressRoute.

4. Op welke locaties uw netwerkprovider ExpressRoute biedt.

Wanneer u de antwoorden op deze vragen hebt vastgesteld, kunt u een ExpressRoute-circuit inrichten die voldoet aan de bandbreedte en de behoeften van de locatie. Als u meer hulp nodig hebt bij de netwerk planning, raadpleegt u de [Office 365 Network Tuning Guide](https://aka.ms/tune) en de casestudy [voor de planning van de netwerkprestaties van Microsoft](https://aka.ms/tunemsit).
  
### <a name="example-1-single-geographic-location"></a>Voorbeeld 1: één geografische locatie
  
Dit voorbeeld is een scenario voor een fictief bedrijf genaamd Trey Research met één geografische locatie.
  
Medewerkers van Trey Research zijn alleen toegestaan verbinding te maken met de services en websites op internet, zodat de beveiligingsafdeling expliciet toestaat welke uitgaande proxy's tussen het bedrijfsnetwerk en de INTERNETPROVIDER valt.
  
Trey Research-abonnementen voor het gebruik van Azure ExpressRoute voor Office 365 en erkent dat sommige verkeer, zoals verkeer, bestemd voor netwerken voor content levering, niet kunnen worden gerouteerd via de ExpressRoute voor Office 365-verbinding. Aangezien al het verkeer naar de proxy apparatuur wordt doorgestuurd, blijven deze verzoeken werken zoals u dat wilt. Nadat Trey Research heeft bepaald dat ze kunnen voldoen aan de vereisten voor de Azure ExpressRoute-routering, gaan ze een circuit maken, routeren configureren en de nieuwe ExpressRoute-circuit koppelen aan een virtueel netwerk. Nadat de basisconfiguratie van Azure ExpressRoute is ingesteld, gebruikt Trey Research het [#2 PAC-bestand](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) om verkeer te routeren met klantspecifieke gegevens via de directe ExpressRoute voor Office 365-verbindingen.
  
Zoals u kunt zien in het volgende diagram, kan Trey Research voldoen aan de vereisten voor het routeren van Office 365-verkeer via internet en een subset van verkeer via ExpressRoute, met een combinatie van routerings-en uitgaande proxyconfiguratie wijzigingen.
  
1. Met behulp van het [#2 PAC-bestand publiceren](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) wordt het routeren van verkeer via een afzonderlijk Internet-uitgangspunt voor Azure ExpressRoute voor Office 365.

2. Klanten zijn geconfigureerd met een standaardroute naar de proxy's van Trey Research.

In dit voorbeeld is Trey Research een apparaat met uitgaande proxy's. Evenzo willen klanten die Azure ExpressRoute voor Office 365 niet gebruiken, deze methode gebruiken om verkeer te routeren op basis van de kosten van het controleren van verkeer dat is bestemd voor bekend hoog volume eindpunten.
  
De grootste volume FQDN voor Exchange Online, SharePoint Online en Skype voor bedrijven online zijn de volgende:
  
![ExpressRoute Customer Edge Network](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com, outlook.office.com

- \<tenant-name\>. SharePoint.com, \<tenant-name\> -My.SharePoint.com, \<tenant-name\> - \<app\> . SharePoint.com

- \*. Lync.com samen met de IP-bereiken voor niet-TCP-verkeer

- \*broadcast.officeapps.live.com, \* Excel.officeapps.live.com, \* onenote.officeapps.live.com, \* PowerPoint.officeapps.live.com, \* view.officeapps.live.com, \* Visio.officeapps.live.com, \* Word-Edit.officeapps.live.com, \* Word-View.officeapps.live.com, Office.live.com

Meer informatie over het [implementeren en beheren van proxy-instellingen in Windows 8](https://blogs.technet.com/b/deploymentguys/archive/2013/05/08/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy.aspx) en [ervoor zorgen dat Office 365 niet wordt vertraagd door uw proxy](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx).
  
Met één ExpressRoute-circuit vormt dit geen hoge beschikbaarheid van Trey Research. In het overbodige paar van de edge-apparaten van de evenementen van Trey die de ExpressRoute-verbinding hebben mislukt, is er geen extra ExpressRoute-circuit voor failover naar. Als het niet lukt om op internet een predicament te doen, is het niet mogelijk om met Trey Research te zorgen voor een handmatige configuratie en voor enkele zaken nieuwe IP-adressen. Als Trey hoge beschikbaarheid wil toevoegen, is de eenvoudigste oplossing om extra ExpressRoute-circuits toe te voegen voor elke locatie en de circuits op een actieve/actieve manier te configureren.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>Routeren van ExpressRoute voor Office 365 met meerdere locaties

Het laatste scenario, routering van Office 365-verkeer via ExpressRoute is de basis voor een nog complexe routerings architectuur. Ongeacht het aantal locaties, het aantal continenten waar die locaties bestaan, het aantal ExpressRoute-circuits, enzovoort, voor het doorsturen van wat verkeer naar het internet en het verkeer via ExpressRoute is vereist.
  
De extra vragen die moeten worden beantwoord voor klanten met meerdere locaties in meerdere regio's zijn onder andere:
  
1. Is er een ExpressRoute-circuit voor elke locatie nodig? Als u Skype voor bedrijven online gebruikt of als u gebruikmaakt van vertraging voor de latentie voor SharePoint Online of Exchange Online, wordt op elke locatie het redundante paar actieve ExpressRoute-circuits aangeraden. Zie de mediakwaliteit en de netwerkverbinding van Skype voor bedrijven voor meer informatie.

2. Als een ExpressRoute-circuit niet beschikbaar is in een bepaald gebied, hoe moet Office 365-verkeer worden gerouteerd?

3. Wat is de beste methode voor het samenvoegen van verkeer in het geval van netwerken met veel kleine locaties?

Elk van deze biedt een unieke uitdaging waarbij u uw eigen netwerk en de beschikbare opties van Microsoft moet evalueren.

|**Aanmerking**|**Te evalueren netwerkonderdelen**|
|:-----|:-----|
|Circuits in meerdere locaties  <br/> |We raden u aan een minimum aan te gaan van twee circuits die zijn geconfigureerd op een actieve/actieve manier.  <br/> De behoeften voor kosten, latentie en bandbreedte moeten worden vergeleken.  <br/> Gebruik BGP route cost, PAC-bestanden en NAT om Routering met meerdere circuits te beheren.  <br/> |
|Routeren van locaties zonder een ExpressRoute-circuit  <br/> |We raden u aan een aflossing van de DNS-oplossing en een DNS-oplossing als dicht bij de persoon die de aanvraag voor Office 365 start.  <br/> DNS forwarding kan worden gebruikt om externe kantoren het juiste eindpunt te ontdekken.  <br/> De clients in het externe kantoor moeten een route beschikbaar hebben die toegang biedt tot het ExpressRoute-circuit.  <br/> |
|Kleine Office-consolidatie  <br/> |De beschikbare bandbreedte en het gegevens gebruik moeten zorgvuldig worden vergeleken.  <br/> |

> [!NOTE]
> Microsoft zal de voorkeur ExpressRoute over Internet als de route beschikbaar is, ongeacht de fysieke locatie.
  
Elk van deze overwegingen moet in rekening worden gebracht voor elk uniek netwerk. Hieronder ziet u een voorbeeld.
  
### <a name="example-2-multi-geographic-locations"></a>Voorbeeld 2: meerdere geografische locaties
  
Dit voorbeeld is een scenario voor een fictief bedrijf met de naam Giga Insurance en meerdere geografische locaties.
  
Giga Insurance is geografisch verspreid met kantoren overal ter wereld. De persoon wil Azure ExpressRoute voor Office 365 implementeren, zodat de meeste Office 365-verkeer op directe netwerkverbindingen wordt bewaard. Giga Insurance heeft ook kantoren van twee extra continenten. De werknemers in het externe Office waarbij ExpressRoute niet haalbaar is, moeten teruggaan naar een of beide primaire faciliteiten om een ExpressRoute-verbinding te kunnen gebruiken.
  
Het verzorgings principe is het snel mogelijk Office 365 met behulp van verkeer naar een Microsoft-datacenter. In dit voorbeeld moet Giga verzekeringen bepalen of hun externe kant-en-Bel via internet kan worden doorgestuurd naar een Microsoft-datacenter via een willekeurige verbinding, of als hun externe kantoren moet worden gerouteerd via een intern netwerk om een Microsoft-datacenter via een ExpressRoute-verbinding te verkrijgen.
  
De datacenters, netwerken en toepassingsarchitectuur van Microsoft zijn zodanig ontworpen dat ze overal en op de efficiëntste manier kunnen worden gecommuniceerd. Dit is een van de grootste netwerken ter wereld. Aanvragen die zijn bestemd voor Office 365 en die op klanten van de klant langer blijven dan nodig, kunnen niet gebruikmaken van deze architectuur.
  
In de situatie van Giga Insurance moet de persoon verdergaan, afhankelijk van de toepassingen die ze willen gebruiken voor ExpressRoute. Als u bijvoorbeeld een klant van Skype voor bedrijven online bent, of als u van ExpressRoute verbinding wilt maken bij het maken van verbinding met externe vergaderingen met Skype voor bedrijven online, kunt u het ontwerp dat wordt aanbevolen in de Skype voor bedrijven online-mediakwaliteit en de netwerk verbindings handleiding een extra ExpressRoute-circuit inrichten voor de derde locatie. Dit kan duurder zijn bij een netwerk perspectief; routeraanvragen van een continent naar een andere continent voordat ze overleveren naar een Microsoft-datacenter, kan tijdens de Skype voor bedrijven online-vergaderingen slecht of onbruikbaar werken.
  
Als Giga Insurance niet wordt gebruikt of als het niet is gepland om Skype voor bedrijven online te gebruiken, routert Office 365 met netwerkverkeer terug naar een continent met een ExpressRoute-verbinding kan mogelijk worden vertraagd, ook als er sprake is van onnodige latentie of TCP congestie. In beide gevallen wordt het bezorgen dat internetverkeer naar het Internet van de lokale site wordt gebruikgemaakt van de netwerken voor content levering waarop Office 365 zich bevindt.
  
![ExpressRoute meervoudige Geografie](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Wanneer Giga Insurance een strategie voor meervoudige meerdere regio's plant, moet u rekening houden met de grootte van het circuit, het aantal circuits, de failover, enzovoort.
  
Met ExpressRoute op een enkele locatie waarbij meerdere regio's gebruikmaken van het circuit, wil Giga Insurance ervoor zorgen dat de verbindingen met Office 365 van de externe Office naar het Office 365-datacenter van Office en worden verzonden via de Headquarters-locatie. Om dit te doen, implementeert Giga Insurance DNS forwarding om het aantal ronde reizen en DNS-lookups te verminderen die nodig zijn om de juiste verbinding tot stand te brengen met de Office 365-omgeving die het meest overeenkomt met het hoofdpunt van de Headquarters Internet. Hiermee voorkomt u dat de klant een lokale front-endserver kan omzetten en ervoor zorgt dat de front-endserver verbinding maakt met Microsoft. U kunt ook leren hoe u [een voorwaardelijke doorstuurserver kunt toewijzen voor een domeinnaam](https://technet.microsoft.com/library/Cc794735%28v=WS.10%29.aspx).
  
In dit scenario verloopt verkeer van de externe Office-infrastructuur Office 365 front-enddatabase in de Verenigde Staten en helpt Office 365 om verbinding te maken met de backend-servers overeenkomstig de architectuur van de Office 365-toepassing. Met Exchange Online werd bijvoorbeeld de verbinding in Noord-Amerika beëindigd en kunnen deze servers verbinding maken met de backend-postvakserver, waar de Tenant zich ook bevindt. Alle services hebben een algemeen verspreide front deur-dienst, met unicast-en anycast-bestemmingen.
  
Als Giga belangrijke kantoren heeft in meerdere continenten, wordt u aangeraden om de latentie voor gevoelige toepassingen zoals Skype voor bedrijven online te verminderen. Als alle kantoren zich in één continent bevinden of niet samenwerken in realtime en geen realtime samenwerking hebben, is het een klantspecifieke of Distributed uitgangspunt een klantspecifieke beslissing. Wanneer meerdere circuits beschikbaar zijn, controleert BGP-routering of een willekeurig circuit geen enkel circuit meer beschikbaar is.
  
Meer informatie over voorbeelden van [routeringsconfiguraties](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-routing/) en [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/) .
  
## <a name="selective-routing-with-expressroute"></a>Selectief routeren met ExpressRoute

Selectief routeren met ExpressRoute kan verschillende oorzaken hebben, zoals het testen van ExpressRoute op een subset van gebruikers. Gebruikers kunnen diverse hulpmiddelen gebruiken om Office 365-netwerkverkeer selectief te routeren via ExpressRoute:
  
1. **Route filters/scheiding** : de BGP-routes naar Office 365 via ExpressRoute naar een subset van uw subnetten of routers. Dit selectief Voorst te doen op het netwerksegment van de klant of de fysieke kantoorlocatie. Dit is gebruikelijk voor het verspringen van een traject van ExpressRoute voor Office 365 en is geconfigureerd op de BGP-apparaten.

2. **PAC-bestanden/url's** voor het doorsturen van Office 365 naar netwerkverkeer voor specifieke FQDN-gegevens voor routering voor een specifiek pad. Dit selectief voor de clientcomputer wordt door [Pac-bestandsimplementatie](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies)aangegeven.

3. **Routeren filteren**  -  Met behulp van [route filters](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) kunt u een subset van ondersteunde services met behulp van Microsoft peering gebruiken.

4. **BGP-community's** : door te filteren op basis van [BGP-labels](https://aka.ms/bgpexpressroute365) kan een klant bepalen welke Office 365-toepassingen worden gebruikt in de ExpressRoute en welke ze door Internet worden verzonden.

Met deze korte koppeling kunt u teruggaan: [https://aka.ms/erorouting](https://aka.ms/erorouting)
  
## <a name="related-topics"></a>Verwante onderwerpen

[Een beoordeling van de netwerkverbinding van Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute voor Office 365](azure-expressroute.md)
  
[ExpressRoute voor Office 365-connectiviteit beheren](managing-expressroute-for-connectivity.md)
  
[Netwerk planning met ExpressRoute voor Office 365](network-planning-with-expressroute.md)
  
[ExpressRoute voor Office 365 implementeren](implementing-expressroute.md)
  
[Media kwaliteit en prestaties van de netwerkverbinding in Skype voor bedrijven online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Uw netwerk optimaliseren voor Skype voor bedrijven online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute en QoS in Skype voor bedrijven online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Oproep stroom met behulp van ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Het gebruik van BGP-community's in ExpressRoute voor Office 365-scenario's](bgp-communities-in-expressroute.md)
  
[Prestaties afstemmen van Office 365 met basislijnen en prestatie geschiedenis](performance-tuning-using-baselines-and-history.md)
  
[Prestatieproblemen met het plannen van Office 365](performance-troubleshooting-plan.md)
  
[URL's en IP-adresbereiken voor Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 netwerk en prestaties optimaliseren](network-planning-and-performance.md)
