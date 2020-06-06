---
title: Netwerken (naar de cloud) — Het gezichtspunt van één architect
description: Beschrijving.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: c8b8416b276ce0e5335b0c0193c6cd79a81d7959
ms.sourcegitcommit: a418195dc11e6251ae37e788c102bbaa7087e44e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44581584"
---
# <a name="networking-up-to-the-cloud--one-architects-viewpoint"></a>Netwerken (naar de cloud) — Het gezichtspunt van één architect

In dit artikel beschrijft [Ed Fisher](https://www.linkedin.com/in/edfisher/), Security & Compliance Architect bij Microsoft, hoe u uw netwerk optimaliseren voor cloudconnectiviteit door de meest voorkomende valkuilen te vermijden. 

## <a name="about-the-author"></a>Over de auteur

![Ed Fisher foto](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Ik ben momenteel een principal technical specialist in de regio Zuidoost gericht op Security & Compliance. Ik heb de afgelopen tien jaar samengewerkt met klanten die naar Office 365 zijn verhuisd. Ik heb gewerkt met kleinere winkels met een handvol locaties aan overheidsinstanties en ondernemingen met miljoenen gebruikers verspreid over de hele wereld, en vele andere klanten daartussen, met de meerderheid met tienduizenden gebruikers, meerdere locaties in verschillende delen van de wereld, de noodzaak van een hogere mate van veiligheid, en een veelheid van nalevingsvereisten. Ik heb honderden bedrijven en miljoenen gebruikers geholpen veilig en veilig naar de cloud te verhuizen.

Met een achtergrond in de afgelopen 25 jaar die beveiliging, infrastructuur en netwerkengineering omvat, en twee van mijn vorige werkgevers naar Office 365 heb verplaatst voordat ik bij Microsoft kwam, heb ik vaak aan uw kant van de tafel gezeten en weet u nog hoe dat is. Hoewel geen twee klanten ooit hetzelfde zijn, hebben de meeste vergelijkbare behoeften en bij het consumeren van een gestandaardiseerde service zoals een SaaS- of PaaS-platform, zijn de beste benaderingen meestal hetzelfde.



## <a name="its-not-the-network--its-how-youre-misusing-it"></a>Het is niet het netwerk - het is hoe je (mis) gebruiken!

Hoe vaak het ook gebeurt, het verbaast me nooit hoe *creatieve* beveiligingsteams en netwerkteams proberen te krijgen hoe ze denken dat ze verbinding moeten maken met Microsoft-cloudservices. Er is altijd een beveiligingsbeleid, nalevingsstandaard of een betere manier waarop ze aandringen op het gebruik, zonder bereid te zijn om deel te nemen aan een gesprek over wat ze proberen te bereiken, of *hoe* ze beter, gemakkelijker, kosteneffectiever en performantere manieren zijn om dit te doen. 

Wanneer dit soort dingen is geëscaleerd naar mij, ik ben meestal bereid om de uitdaging aan te gaan en lopen ze door de hows en het waarom en krijgen ze naar waar ze moeten zijn. Maar als ik volledig eerlijk ben, moet ik delen dat ik ze soms gewoon wil laten doen wat ze willen, en terugkomen om te zeggen dat ik het je zo vertelde als ze eindelijk toegeven dat het niet werkt. Misschien wil ik dat soms doen, maar dat doe ik *niet.* Wat ik doe is proberen uit te leggen wat ik ga opnemen in dit bericht. Ongeacht uw rol, als uw organisatie Microsoft-cloudservices wil gebruiken, is er waarschijnlijk enige wijsheid in wat volgt dat u kan helpen.


## <a name="guiding-principles"></a>Richtsnoeren
Laten we beginnen met wat basisregels rond wat we hier doen. We bespreken hoe we veilig verbinding kunnen maken met cloudservices om de minimale complexiteit en de maximale prestaties te garanderen, met behoud van echte beveiliging. Niets van wat volgt is in strijd met een van die, zelfs als u, of uw klant, niet krijgt om uw favoriete proxy server te gebruiken voor alles.

- **Gewoon omdat je, betekent niet dat je moet** - Of om Dr Ian Malcolm parafraseren uit de Jurassic Park film. . . Ja, ja, maar je beveiligingsteam was zo bezig met de vraag of ze konden dat ze niet stoppen om na te denken of ze moesten."    
- **Beveiliging betekent niet complexiteit** - U bent niet veiliger, alleen maar omdat u meer geld uitgeeft, door meer apparaten loopt of op meer knoppen klikt.
- **Office 365 is toegankelijk via internet** - Maar dat is niet hetzelfde als Office 365 is het internet. Het is een SaaS-service die wordt beheerd door Microsoft en door u wordt beheerd. In tegenstelling tot websites die u op het internet bezoekt, u eigenlijk achter het gordijn gluren en u de controles toepassen die u nodig hebt om aan uw beleid en uw nalevingsnormen te voldoen, zolang u begrijpt dat terwijl u uw doelstellingen bereiken, u ze misschien gewoon op een andere manier moet doen.
- **Chokepoints zijn slecht, gelokaliseerde breakouts zijn goed** - Iedereen wil altijd al hun internetverkeer backhaul voor al hun gebruikers naar een centraal punt, meestal zodat ze kunnen controleren en beleid af te dwingen, maar vaak omdat het ofwel goedkoper dan het inrichten van internet toegang op al hun locaties, of het is gewoon hoe ze het doen. Maar die chokepoints zijn precies dat ... punten waar het verkeer verstikt. Er is niets mis mee om te voorkomen dat uw gebruikers naar Instagram kunnen bladeren of kattenvideo's streamen, maar behandel uw bedrijfskritieke bedrijfstoepassingsverkeer niet op dezelfde manier.
- **Als DNS niet tevreden is, is niets gelukkig** - Het best ontworpen netwerk kan worden belemmerd door slechte DNS, of dat nu is door verzoeken opnieuw te plaatsen op servers in andere gebieden van de wereld of het gebruik van de DNS-servers van uw ISP of andere openbare DNS-servers die DNS-resolutie-informatie in de cache plaatsen. 
- **Gewoon omdat dat is hoe je gebruikt om het te doen, betekent niet dat is hoe je het nu moet doen** - Technologie verandert voortdurend en Office 365 is geen uitzondering. Het toepassen van beveiligingsmaatregelen die zijn ontwikkeld en geïmplementeerd voor on-premises services of om surfen op het web te controleren, zal niet hetzelfde niveau van beveiligingsgarantie bieden en kan een aanzienlijke negatieve invloed hebben op de prestaties.
- **Office 365 is gebouwd om te worden benaderd via het internet** - Dat is het in een notendop. Het maakt niet uit wat u wilt doen tussen uw gebruikers en uw rand, het verkeer gaat nog steeds over het internet zodra het uw netwerk verlaat en voordat het op de onze komt. Zelfs als u Azure ExpressRoute gebruikt om een aantal latentiegevoelig verkeer van uw netwerk rechtstreeks naar het onze te routeren, is internetconnectiviteit absoluut vereist. Accepteer het. Denk er niet te veel over na.

## <a name="where-bad-choices-are-often-made"></a>Waar vaak slechte keuzes worden gemaakt

Hoewel er tal van plaatsen waar slechte beslissingen worden genomen in de naam van de veiligheid, dit zijn degenen die ik het vaakst tegenkomen met klanten. Veel gesprekken met klanten omvatten al deze tegelijk.

### <a name="insufficient-resources-at-the-edge"></a>Onvoldoende middelen aan de rand
Zeer weinig klanten zijn het implementeren van greenfield omgevingen, en ze hebben jarenlange ervaring met hoe hun gebruikers werken en wat hun internet uitgang is. Of klanten nu proxyservers hebben of directe toegang en gewoon NAT uitgaand verkeer toestaan, ze doen het al jaren en overwegen niet hoeveel meer ze door hun edge gaan pompen terwijl ze traditioneel interne applicaties naar de cloud verplaatsen.

Bandbreedte is altijd een punt van zorg, maar NAT-apparaten hebben mogelijk niet genoeg pk's om de verhoogde belasting aan te kunnen en kunnen voortijdig verbindingen sluiten om resources vrij te maken. Het grootste deel van de clientsoftware die verbinding maakt met Office 365 verwacht aanhoudende verbindingen en een gebruiker die Office 365 volledig gebruikt, kan 32 of meer gelijktijdige verbindingen hebben. Als het NAT-apparaat ze voortijdig laat vallen, kunnen deze apps niet meer reageren als ze proberen de verbindingen te gebruiken die er niet meer zijn. Wanneer ze opgeven en proberen om nieuwe verbindingen vast te stellen, zetten ze nog meer belasting op uw netwerk versnelling.

### <a name="localized-breakout"></a>Gelokaliseerde uitbraak
Al het andere in deze lijst komt neer op een ding - het krijgen van uw netwerk en op de onze zo snel mogelijk. Het terughalen van het verkeer van uw gebruikers naar een centraal uitgangspunt, vooral wanneer dat uitgangspunt zich in een andere regio bevindt dan uw gebruikers zich bevinden, introduceert onnodige latentie en beïnvloedt zowel de klantervaring als de downloadsnelheden. Microsoft heeft punten van aanwezigheid over de hele wereld met front-ends voor al onze diensten en peering opgericht met vrijwel elke grote ISP, dus routing verkeer van uw gebruikers *lokaal* zorgt ervoor dat het snel in ons netwerk met minimale latentie. 

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>DNS-oplossingsverkeer moet het internetpad volgen
Natuurlijk, voor een client om een eindpunt te vinden, moet het DNS gebruiken. De DNS-servers van Microsoft evalueren de bron van DNS-verzoeken om ervoor te zorgen dat we het antwoord retourneren dat in internettermen het dichtst bij de bron van het verzoek ligt. Zorg ervoor dat uw DNS is geconfigureerd, zodat aanvragen voor naamomzetting hetzelfde pad bewandelen als het verkeer van uw gebruikers, opdat u ze geen lokale uitgang geeft, maar naar een eindpunt in een andere regio. Dat betekent dat lokale DNS-servers "naar root gaan" in plaats van doorsturen naar DNS-servers in externe datacenters. En kijk uit voor publieke en private DNS-diensten, die resultaten uit een deel van de wereld kunnen cachen en ze kunnen dienen voor verzoeken uit andere delen van de wereld.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Om proxy of niet proxy, dat is de vraag
Een van de eerste dingen om te overwegen is of de verbindingen van gebruikers met Office 365 moeten worden proxy. Die is makkelijk; niet proxy. Office 365 is toegankelijk via internet, maar het is niet het internet. Het is een uitbreiding van uw kerndiensten en moet als zodanig worden behandeld. Alles wat u wilt dat een proxy te doen, zoals DLP of antimalware of inhoud inspectie, is al beschikbaar voor u in de service, en kan worden gebruikt op schaal en zonder te kraken TLS-versleutelde verbindingen. Maar als je echt wilt proxy verkeer dat je anders niet controleren, aandacht besteden aan onze begeleiding op [https://aka.ms/pnc](https://aka.ms/pnc) en de categorieën van het verkeer op [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) . We hebben drie verkeerscategorieën voor Office 365. Optimaliseren en toestaan moet echt direct gaan en omzeilen uw proxy. Standaard kan worden proxied. De details staan in die documenten. . . lees ze.

De meeste klanten die aandringen op het gebruik van een proxy, als ze daadwerkelijk kijken naar wat ze doen, komen om te beseffen dat wanneer de klant maakt een HTTP CONNECT verzoek aan de proxy, de proxy is nu gewoon een dure extra router. De protocollen in gebruik, zoals MAPI en RTC zijn niet eens protocollen die web proxy's begrijpen, dus zelfs met TLS kraken krijg je niet echt extra beveiliging. Je *are* krijgt extra latentie. Zie [https://aka.ms/pnc](https://aka.ms/pnc) voor meer informatie over dit, met inbegrip van de categorieën Optimaliseren, Toestaan en Standaard voor Microsoft 365-verkeer.

Ten slotte, rekening houden met de totale impact op de proxy en de bijbehorende reactie om te gaan met die impact. Naarmate er meer en meer verbindingen worden gemaakt via de proxy, kan het de TCP Scale Factor verlagen, zodat het niet hoeft te bufferen zo veel verkeer. Ik heb gezien dat klanten waar hun volmachten waren zo overbelast dat ze met behulp van een Scale Factor van 0. Aangezien Scale Factor een exponentiële waarde is en we graag 8 gebruiken, is elke verlaging van de waarde van de Schaalfactor een enorme negatieve impact op de doorvoer.

TLS Inspectie betekent VEILIGHEID! Maar niet echt! Veel klanten met volmachten willen ze gebruiken om al het verkeer te inspecteren, en dat betekent TLS "breken en inspecteren." Wanneer u dat doet voor een website die via HTTPS wordt benaderd (ondanks privacyproblemen) moet uw proxy dat mogelijk doen voor tien of zelfs twintig gelijktijdige streams voor een paar honderd milliseconden. Als er een grote download of misschien een video betrokken, een of meer van deze verbindingen kan veel langer duren, maar over het algemeen, de meeste van deze verbindingen vast te stellen, overdracht, en sluiten zeer snel. Doen pauze en inspecteren betekent dat de proxy moet het dubbele van het werk te doen. Voor elke verbinding van de client naar de proxy moet de proxy ook een aparte verbinding naar het eindpunt maken. Dus, een wordt twee, twee wordt vier, tweeëndertig wordt vierenzestig . . . zie je waar ik heen ga? U waarschijnlijk formaat van uw proxy-oplossing prima voor typische surfen op het web, maar als je probeert om hetzelfde te doen voor clientverbindingen met Office 365, het aantal gelijktijdige, langlevende verbindingen kan worden ordes van grootte groter dan wat je formaat voor.

### <a name="streaming-isnt-important-except-that-it-is"></a>Streaming is niet belangrijk, behalve dat *het*
De enige services in Office 365 die UDP gebruiken, zijn Skype (binnenkort met pensioen) en Microsoft Teams. Teams gebruikt UDP voor het streamen van verkeer, waaronder het delen van audio, video en presentaties. Streaming verkeer is live, zoals wanneer u een online vergadering met spraak, video, en presenteren dekken of het uitvoeren van demo's. Deze gebruiken UDP, want als pakketten worden gedropt, of aankomen buiten de orde, het is vrijwel onmerkbaar door de gebruiker en de stroom kan gewoon blijven gaan. 

Wanneer u uitgaand UDP-verkeer van clients naar de service niet toestaat, kunnen ze terugvallen op het gebruik van TCP. Maar als een TCP-pakket wordt verwijderd, *stopt alles* totdat de Timeout (Retransmission Timeout) verloopt en het ontbrekende pakket opnieuw kan worden verzonden. Als een pakket niet in orde komt, stopt alles totdat de andere pakketten aankomen en kan het in volgorde worden weer in elkaar gezet. Beide leiden tot waarneembare glitches in de audio (denk aan Max Headroom?) en video (heb je op someth klikken . . . oh, daar is het) en leiden tot slechte prestaties en een slechte gebruikerservaring. En weet je nog wat ik hierboven heb gezegd over volmachten? Wanneer u een Teams-client dwingt om een proxy te gebruiken, dwingt u deze om TCP te gebruiken. Dus nu ben je het veroorzaken van negatieve prestaties effecten twee keer.

### <a name="split-tunneling-may-seem-scary"></a>Split tunneling lijkt misschien eng
Maar dat is het niet. Alle verbindingen met Office 365 zijn meer dan TLS. We bieden TLS 1.2 al een tijdje aan en zullen binnenkort oudere versies uitschakelen omdat oudere clients ze nog steeds gebruiken en dat is een risico.

Het forceren van een TLS-verbinding, of tweeëndertig van hen, om over een VPN te gaan voordat ze dan naar de service gaan, voegt geen beveiliging toe. Het voegt latentie toe en vermindert de algehele doorvoer. In sommige VPN-oplossingen dwingt het UDP zelfs om door TCP te tunnelen, wat opnieuw een zeer negatieve invloed zal hebben op het streamingverkeer. En, tenzij u TLS inspectie doet, is er geen voordeel, alle nadeel. Een veel voorkomend thema onder klanten op dit moment, nu het grootste deel van hun personeel is afgelegen, is dat ze aanzienlijke bandbreedte en prestaties effecten van het maken van al hun gebruikers verbinding maken met behulp van een VPN te zien, in plaats van het configureren van split tunneling voor toegang tot [Optimize categorie Office 365 endpoints](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).

Het is een gemakkelijke oplossing om split tunneling te doen en het is er een die je moet doen. Controleer voor meer informatie [de Office 365-connectiviteit optimaliseren voor externe gebruikers met behulp van VPN-splittunneling.](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)


## <a name="the-sins-of-the-past"></a>De zonden van het verleden
Vaak, de reden slechte keuzes worden gemaakt komt van een combinatie van (1) niet weten hoe de service werkt, (2) proberen te houden aan het bedrijf beleid dat zijn geschreven voordat de vaststelling van de cloud, en (3) security teams die misschien niet gemakkelijk worden ervan overtuigd dat er meer dan een manier om hun doelen te bereiken. Hopelijk het bovenstaande, en de onderstaande links, zal helpen met de eerste. Uitvoerend sponsoring kan worden vereist om voorbij de tweede te komen. Het aanpakken van de doelstellingen van het beveiligingsbeleid, in plaats van hun methoden, helpt bij de derde. Van voorwaardelijke toegang tot contentmoderatie, DLP tot informatiebescherming, endpoint-validatie tot zero-day-bedreigingen - elk einddoel dat een redelijk beveiligingsbeleid kan hebben, kan worden bereikt met wat beschikbaar is in Office 365, en zonder enige afhankelijkheid van on-premises netwerkuitrusting, gedwongen VPN-tunnels en TLS-onderbreking en -inspectie. 

Andere keren kan hardware die was formaat en gekocht voordat de organisatie begon te verhuizen naar de cloud gewoon niet worden opgeschaald om de nieuwe verkeerspatronen en ladingen te verwerken. Als je echt al het verkeer moet routeren door een enkel uitgangspunt, en / of proxy, bereid zijn om netwerkapparatuur en bandbreedte dienovereenkomstig te upgraden. Controleer zorgvuldig het gebruik op beide, omdat de ervaring niet langzaam zal afnemen naarmate meer gebruikers aan boord zijn. Alles komt goed tot het kantelpunt is bereikt, dan lijdt iedereen. 

## <a name="exceptions-to-the-rules"></a>Uitzonderingen op de regels

Als uw organisatie [tenantbeperkingen](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)vereist, moet u een proxy met TLS-onderbreking gebruiken om wat verkeer via de proxy te forceren, maar u hoeft niet al het verkeer erdoorheen te forceren.  Het is niet een alles of niets propositie, dus aandacht besteden aan wat moet worden gewijzigd door de proxy. 

Als u split tunneling toestaat, maar ook een proxy gebruikt voor algemeen webverkeer, zorg er dan voor dat uw PAC-bestand definieert wat er direct moet gaan en hoe u interessant verkeer definieert voor wat er door de VPN-tunnel gaat. We bieden voorbeeld PAC-bestanden op [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) dat zal dit gemakkelijker te beheren.

## <a name="conclusion"></a>Conclusie

Tienduizenden organisaties, waaronder bijna de hele Fortune 500, gebruiken Office 365 dagelijks voor hun bedrijfskritieke functies. Dat doen ze veilig, en dat doen ze via internet.

 Het maakt niet uit welke beveiligingsdoelen je hebt in het spel, er zijn manieren om ze te bereiken die geen VPN-verbindingen, proxyservers, TLS-onderbreking en -inspectie vereisen, of gecentraliseerd internet uitgang om het verkeer van uw gebruikers uit uw netwerk en op de onze zo snel als je, die de beste prestaties biedt, of uw netwerk is het hoofdkantoor van het bedrijf, een extern kantoor , of die gebruiker die thuis werkt. Onze richtlijnen zijn gebaseerd op de manier waarop de Office 365-services zijn gebouwd en om een veilige en performante gebruikerservaring te garanderen.

## <a name="further-reading"></a>Verder lezen

[De Office 365-netwerkconnectiviteitsprincipes](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles)

[URL's en IP-adresbereiken voor Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges?redirectSourcePath=%252fen-us%252farticle%252fOffice-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Office 365-eindpunten beheren](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)

[Office 365-webservice voor IP-adres en URL](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)

[Office 365-netwerkconnectiviteit beoordelen](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity)

[Office 365-netwerk- en prestatieafstemming](https://docs.microsoft.com/office365/enterprise/network-planning-and-performance)

[Office 365-netwerkconnectiviteit beoordelen](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity)

[Office 365-prestatieafstemming met basislijnen en prestatiegeschiedenis](https://docs.microsoft.com/office365/enterprise/performance-tuning-using-baselines-and-history)

[Probleemoplossing voor prestaties voor Office 365](https://docs.microsoft.com/office365/enterprise/performance-troubleshooting-plan)

[Netwerken voor het leveren van inhoud](https://docs.microsoft.com/office365/enterprise/content-delivery-networks)

[Microsoft 365-connectiviteitstest](https://connectivity.office.com/)

[Hoe Microsoft zijn snelle en betrouwbare wereldwijde netwerk bouwt](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365-netwerkblog](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Office 365-connectiviteit voor externe gebruikers die VPN-splittunneling gebruiken](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)


