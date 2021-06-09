---
title: Netwerken tot (naar de cloud)— Het gezichtspunt van een architect
description: Lees hoe u uw netwerk kunt optimaliseren voor cloudconnectiviteit door de meest voorkomende valkuilen te vermijden.
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
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 7de9aec29b0a57e85e3539fc2e99384de545c52a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904634"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Netwerken tot (naar de cloud)— Het gezichtspunt van een architect

In dit artikel beschrijft [Ed Fisher](https://www.linkedin.com/in/edfisher/), Security & Compliance Architect bij Microsoft, hoe u uw netwerk kunt optimaliseren voor cloudconnectiviteit door de meest voorkomende valkuilen te vermijden. 

## <a name="about-the-author"></a>Over de auteur

![Foto van Ed Fisher](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Ik ben momenteel een principal technical specialist in de regio Zuidoost die zich richt op & Compliance. Ik heb de afgelopen 10 jaar gewerkt met klanten die Office 365 naar een andere klant gaan. Ik heb gewerkt met kleinere winkels met een handjevol locaties voor overheidsinstanties en ondernemingen met miljoenen gebruikers verspreid over de hele wereld en vele andere klanten daartussen, met de meerderheid met tienduizenden gebruikers, meerdere locaties in verschillende delen van de wereld, de noodzaak van een hogere mate van beveiliging en een groot aantal nalevingsvereisten. Ik heb honderden ondernemingen en miljoenen gebruikers geholpen veilig naar de cloud te gaan.

Met een achtergrond in de afgelopen 25 jaar, inclusief beveiliging, infrastructuur en netwerktechniek, en nadat ik twee van mijn vorige werkgevers naar Office 365 heb verplaatst voordat ik lid werd van Microsoft, ben ik vaak aan uw kant van de tabel geweest en weet ik nog hoe dat werkt. Hoewel geen twee klanten ooit hetzelfde zijn, hebben de meeste dezelfde behoeften en wanneer u een gestandaardiseerde service gebruikt, zoals een SaaS- of PaaS-platform, zijn de beste benaderingen meestal hetzelfde.

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>Het is niet het netwerk, maar de manier waarop u het gebruikt.

Hoe vaak het ook gebeurt, het blijft  me verbazen hoe creatieve beveiligingsteams en netwerkteams proberen te leren hoe ze denken dat ze verbinding moeten maken met Microsoft-cloudservices. Er is altijd een beveiligingsbeleid, compliancestandaard of een betere manier waarop ze het gebruik ervan willen gebruiken, zonder  dat ze bereid zijn om een gesprek aan te gaan over wat ze proberen te bereiken, of hoe ze beter, eenvoudiger, voordeliger en performanter zijn.

Wanneer dit soort dingen naar mij toe escaleert, ben ik meestal bereid om de uitdaging aan te gaan en hen door de how's en de waarom's te laten lopen en ze naar de plaats te krijgen waar ze moeten zijn. Maar als ik helemaal eerlijk ben, moet ik dat soms delen. Ik wil ze gewoon laten doen wat ze willen, en terugkomen om te zeggen dat ik het u heb verteld als ze het uiteindelijk niet doen. Misschien wil ik dat soms doen, maar *dat doe ik niet.* Wat ik doe, is proberen uit te leggen wat ik allemaal ga opnemen in dit bericht. Ongeacht uw rol, als uw organisatie Microsoft-cloudservices wil gebruiken, is er waarschijnlijk enige informatie over wat u kan helpen.

## <a name="guiding-principles"></a>Richtlijnen

Laten we beginnen met enkele basisregels over wat we hier doen. We bespreken hoe u veilig verbinding kunt maken met cloudservices om de minimale complexiteit en maximale prestaties te waarborgen, met behoud van echte beveiliging. Niets van wat volgt is in strijd met dat alles, zelfs als u of uw klant niet voor alles uw favoriete proxyserver kan gebruiken.

- **Dat u dat wel kunt, betekent** niet dat u het volgende moet doen: Of om Dr. Lan Malcolm te parafraseren uit de film '... Ja, ja, maar uw beveiligingsteam was zo bezig met de vraag of ze wel of niet konden dat ze niet stopten met nadenken of ze dat wel zouden moeten doen.'
- **Beveiliging betekent niet complexiteit:** u bent niet veiliger omdat u meer geld uitgeeft, meer apparaten doorgeeft of op meer knoppen klikt.
- **Office 365 is toegankelijk via internet:** Maar dat is niet hetzelfde als Office 365 internet is. Het is een SaaS-service die door Microsoft wordt beheerd en door u wordt beheerd. In tegenstelling tot websites die u op internet bezoekt, kunt u achter het gordijn kijken en kunt u de besturingselementen toepassen die u nodig hebt om te voldoen aan uw beleid en uw nalevingsstandaarden, zolang u begrijpt dat u uw doelstellingen kunt bereiken, u ze mogelijk op een andere manier moet doen.
- Verstikkende punten zijn slecht, gelokaliseerde **breakouts** zijn goed: iedereen wil altijd al het internetverkeer voor al hun gebruikers naar een centraal punt terugplaatsen, meestal zodat ze het kunnen controleren en beleid kunnen afdwingen, maar vaak omdat het goedkoper is dan het inrichten van internettoegang op al hun locaties, of omdat ze dit alleen doen. Maar die verstikkende punten zijn precies dat... punten waar het verkeer vast komt te liggen. Er is niets mis met het voorkomen dat uw gebruikers naar Instagram bladeren of kattenvideo's streamen, maar behandel uw bedrijfskritische bedrijfstoepassingsverkeer niet op dezelfde manier.
- Als DNS niet tevreden **is,** is er niets gelukkigs: het best ontworpen netwerk kan worden beslecht door slechte DNS, of dat nu is door aanvragen te recurseren naar servers in andere gebieden van de wereld of door de DNS-servers van uw internetprovider of andere openbare DNS-servers te gebruiken die DNS-resolutiegegevens cachen.
- **Omdat u** dit vroeger deed, betekent dit niet dat u dit nu moet doen: technologie verandert voortdurend en Office 365 is geen uitzondering. Het toepassen van beveiligingsmaatregelen die zijn ontwikkeld en geïmplementeerd voor on-premises services of om websurfen te controleren, biedt niet hetzelfde beveiligingsniveau en kan een aanzienlijke negatieve invloed hebben op de prestaties.
- **Office 365 is gemaakt om toegankelijk te** zijn via internet: dat is het in een notendop. Wat u ook wilt doen tussen uw gebruikers en uw edge, het verkeer gaat nog steeds via internet zodra het uw netwerk verlaat en voordat het toegang krijgt tot het onze. Zelfs als u Azure ExpressRoute gebruikt om latentiegevoelig verkeer rechtstreeks vanuit uw netwerk naar ons te leiden, is internetverbinding absoluut vereist. Accepteer het. Denk er niet te veel over na.

## <a name="where-bad-choices-are-often-made"></a>Waar vaak slechte keuzes worden gemaakt

Hoewel er op tal van plaatsen slechte beslissingen worden genomen in de naam van de beveiliging, zijn dit de plaatsen waar ik het vaakst tegen kom met klanten. In veel klantgesprekken worden al deze gesprekken tegelijk gevoerd.

### <a name="insufficient-resources-at-the-edge"></a>Onvoldoende resources aan de rand

Er zijn maar weinig klanten die greenfield-omgevingen implementeren, en ze hebben jaren ervaring met hoe hun gebruikers werken en hoe hun internet-uittreding eruit ziet. Of klanten nu proxyservers hebben of directe toegang toestaan en gewoon NAT uitgaand verkeer, ze doen dit al jaren en denken er niet aan hoeveel meer ze door hun edge gaan bewegen terwijl ze traditioneel interne toepassingen naar de cloud verplaatsen.

Bandbreedte is altijd een probleem, maar NAT-apparaten hebben mogelijk niet genoeg pk's om de verhoogde belasting aan te kunnen en kunnen verbindingen voortijdig sluiten om bronnen vrij te maken. De meeste clientsoftware die verbinding maakt met Office 365 verwacht permanente verbindingen en een gebruiker die volledig gebruikmaakt van Office 365 kan 32 of meer gelijktijdige verbindingen hebben. Als het NAT-apparaat ze voortijdig neer laat vallen, reageren deze apps mogelijk niet meer omdat ze de verbindingen proberen te gebruiken die er niet meer zijn. Wanneer ze opgeven en proberen nieuwe verbindingen tot stand te brengen, worden uw netwerkapparatuur nog meer belast.

### <a name="localized-breakout"></a>Gelokaliseerde breakout

Al het andere in deze lijst komt neer op één ding: zo snel mogelijk van uw netwerk naar het onze gaan. Door het verkeer van uw gebruikers terug te brengen naar een centraal uitgangspunt, met name wanneer dat uitgangspunt zich in een andere regio dan uw gebruikers in, worden onnodige latentie en is dit van invloed op zowel de clientervaring als de downloadsnelheden. Microsoft heeft overal ter wereld aanwezigheidspunten met front-ends voor al onze services en peering die  zijn ingesteld bij vrijwel elke belangrijke internetprovider, dus door het verkeer van uw gebruikers lokaal te routeren, wordt het snel binnen ons netwerk gebracht met minimale latentie.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>DNS-resolutieverkeer moet het internetpad volgen

Natuurlijk moet een client DNS gebruiken om een eindpunt te vinden. De DNS-servers van Microsoft evalueren de bron van DNS-aanvragen om ervoor te zorgen dat we het antwoord retourneren dat in internettermen het dichtst bij de bron van de aanvraag staat. Zorg ervoor dat uw DNS zo is geconfigureerd dat naamresolutieaanvragen hetzelfde pad als het verkeer van uw gebruikers gaan, opdat u ze geen lokaal uitgangspunt geeft, maar naar een eindpunt in een andere regio. Dat betekent dat lokale DNS-servers 'naar root' moeten gaan in plaats van door te gaan naar DNS-servers in externe datacenters. En kijk uit voor openbare en private DNS-services, die resultaten uit een deel van de wereld in de cache kunnen cachen en deze kunnen dienen voor aanvragen uit andere delen van de wereld.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Proxy of niet proxy, dat is de vraag

Een van de eerste dingen die u moet overwegen, is of de verbindingen van gebruikers met Office 365. Die is eenvoudig. geen proxy gebruiken. Office 365 is toegankelijk via internet, maar het is niet INTERNET. Het is een uitbreiding van uw kernservices en moet als zodanig worden behandeld. Alles wat u wilt dat een proxy moet doen, zoals DLP of antimalware of inhoudscontrole, is al beschikbaar in de service en kan op schaal worden gebruikt zonder dat U TLS-versleutelde verbindingen hoeft te kraken. Maar als u echt wilt proxyverkeer dat u anders niet kunt controleren, let dan op onze richtlijnen bij en de categorieën [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) van verkeer op [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) . We hebben drie categorieën verkeer voor Office 365. Optimaliseren en Toestaan moet echt direct gaan en uw proxy omzeilen. Standaard kan worden doorbetaald. De details staan in die documenten... lees ze.

De meeste klanten die een proxy willen gebruiken, realiseren zich dat wanneer de client een HTTP CONNECT-aanvraag doet bij de proxy, de proxy nu gewoon een dure extra router is. De protocollen die worden gebruikt, zoals MAPI en RTC, zijn niet eens protocollen die webproxies begrijpen, dus zelfs met het kraken van TLS krijgt u niet echt extra beveiliging. U *krijgt* extra latentie. Zie hiervoor meer informatie, waaronder de categorieën Optimaliseren, Toestaan en Standaard voor [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) Microsoft 365 verkeer.

Houd ten slotte rekening met de algehele gevolgen voor de proxy en de bijbehorende reactie om dit effect aan te kunnen. Naarmate er steeds meer verbindingen worden gemaakt via de proxy, kan de TCP-schaalfactor worden verkleind, zodat er niet zo veel verkeer hoeft te worden gebufferd. Ik heb klanten gezien waar hun proxies zo overbelast waren dat ze een schaalfactor van 0 gebruiken. Aangezien schaalfactor een exponentiële waarde is en we graag 8 gebruiken, is elke vermindering van de waarde Schaalfactor een enorm negatief effect op de doorvoer.

TLS-inspectie betekent BEVEILIGING! Maar niet echt! Veel klanten met proxies willen ze gebruiken om al het verkeer te controleren, wat betekent dat TLS 'breken en controleren' betekent. Wanneer u dat doet voor een website die wordt gebruikt via HTTPS (privacyproblemen niettegenstaande) moet uw proxy dat mogelijk doen voor 10 of zelfs 20 gelijktijdige streams voor een paar honderd milliseconden. Als er een grote download of misschien een video bij betrokken is, kan een of meer van deze verbindingen veel langer duren, maar over het algemeen worden de meeste van deze verbindingen snel gemaakt, overdraagd en gesloten. Als u pauze en controle doet, moet de proxy het dubbele van het werk doen. Voor elke verbinding van de client met de proxy moet de proxy ook een afzonderlijke verbinding maken met het eindpunt. Dus 1 wordt 2, 2 wordt 4, 32 wordt 64...zie waar ik heen ga? U hebt waarschijnlijk de grootte van uw proxyoplossing prima voor normaal surfen op het web, maar wanneer u hetzelfde probeert te doen voor clientverbindingen met Office 365, kan het aantal gelijktijdige, langdurige verbindingen groter zijn dan het aantal gelijktijdige, langdurige verbindingen.

### <a name="streaming-isnt-important-except-that-it-is"></a>Streaming is niet belangrijk, behalve *dat* het

De enige services in Office 365 die UDP gebruiken, zijn Skype (binnenkort ingetrokken) en Microsoft Teams. Teams gebruikt UDP voor het streamen van verkeer, waaronder audio, video en het delen van presentaties. Streamingverkeer is live, bijvoorbeeld wanneer u een onlinevergadering hebt met spraak, video en het presenteren van decks of het uitvoeren van demo's. Deze maken gebruik van UDP, omdat als pakketten worden weggevallen of niet in de volgorde worden aangetroffen, dit vrijwel onmerkbaar is voor de gebruiker en de stream gewoon door kan gaan.

Als u niet toestaan dat uitgaande UDP-verkeer van clients naar de service wordt uitgevoerd, kunnen deze terugvallen op het gebruik van TCP. Maar als een TCP-pakket wordt *weggelaten,* stopt alles totdat de RTO (Retransmission Timeout) verloopt en het ontbrekende pakket kan worden doorgestuurd. Als een pakket niet in orde is, stopt alles totdat de andere pakketten binnenkomen en kunnen ze in volgorde worden opnieuw in elkaar worden geassembleerd. Beide leiden tot waarneembare problemen in de audio (onthoud Max Headroom?) en video (hebt u ergens op geklikt... oh, daar is het) en leiden tot slechte prestaties en een slechte gebruikerservaring. En weet u nog wat ik hierboven heb gezegd over proxies? Wanneer u een client Teams om een proxy te gebruiken, dwingt u deze om TCP te gebruiken. Dus nu veroorzaakt u tweemaal negatieve prestatie-effecten.

### <a name="split-tunneling-may-seem-scary"></a>Splits tunneling kan eng lijken

Maar dat is het niet. Alle verbindingen met Office 365 zijn via TLS. We bieden TLS 1.2 al een tijdje aan en zullen binnenkort oudere versies uitschakelen omdat oudere clients deze nog steeds gebruiken en dat is een risico.

Als u een TLS-verbinding, of 32 daarvan, dwingt om via een VPN te gaan voordat ze naar de service gaan, wordt er geen beveiliging meer gebruikt. Het voegt wel latentie toe en vermindert de totale doorvoer. In sommige VPN-oplossingen dwingt het UDP zelfs om door TCP te tunnelen, wat weer een zeer negatieve invloed heeft op het streamingverkeer. En, tenzij u TLS-inspectie doet, is er geen voordeel, allemaal nadeel. Een veelvoorkomende thema bij klanten, nu het grootste deel van hun personeel op afstand is, is dat ze aanzienlijke bandbreedte- en prestatieeffecten zien door al hun gebruikers verbinding te laten maken met een VPN, in plaats van gesplitste tunneling te configureren voor toegang tot Categorie [Office 365-eindpunten](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)optimaliseren.

Het is een eenvoudige oplossing om gesplitste tunneling te doen en het is een oplossing die u moet doen. Controleer voor meer informatie De verbinding optimaliseren Office 365 [externe gebruikers via VPN splits tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="the-sins-of-the-past"></a>De zonde van het verleden

Vaak komt de reden dat slechte keuzes worden gemaakt door een combinatie van (1) die niet weet hoe de service werkt, (2) die probeert te voldoen aan bedrijfsbeleid dat is geschreven voordat de cloud werd over genomen, en (3) beveiligingsteams die er mogelijk niet gemakkelijk van overtuigd zijn dat er meer dan één manier is om hun doelen te bereiken. Hopelijk helpt het bovenstaande en de onderstaande koppelingen bij de eerste. Executive sponsoring kan nodig zijn om voorbij de tweede te komen. Het aanpakken van de doelstellingen van het beveiligingsbeleid, in plaats van de methoden, helpt bij de derde. Van voorwaardelijke toegang tot inhoudsbeheer, DLP tot informatiebeveiliging, eindpuntvalidatie tot zero-day-bedreigingen: elk einddoel dat een redelijk beveiligingsbeleid kan hebben bereikt met wat beschikbaar is in Office 365 en zonder enige afhankelijkheid van on-premises netwerkapparatuur, gedwongen VPN-tunnels en TLS-onderbrekingen en -controle.

Andere keren kan hardware die is groot en gekocht voordat de organisatie naar de cloud ging, niet worden opgeschaald om de nieuwe verkeerspatronen en belastingen aan te kunnen. Als u echt al het verkeer via één uitgangspunt en/of proxy moet doorverrouteren, moet u erop voorbereid zijn om netwerkapparatuur en bandbreedte dienovereenkomstig te upgraden. Houd het gebruik van beide gebruikers zorgvuldig in de gaten, omdat de ervaring niet langzaam afneemt naarmate er meer gebruikers aan boord zijn. Alles is in orde totdat het kantelpunt is bereikt, waarna iedereen er last van heeft.

## <a name="exceptions-to-the-rules"></a>Uitzonderingen op de regels

Als uw organisatie [tenantbeperkingen](/azure/active-directory/manage-apps/tenant-restrictions)vereist, moet u een proxy met TLS-onderbreking en -controle gebruiken om verkeer via de proxy af te dwingen, maar u hoeft niet al het verkeer erdoor te dwingen.  Het is geen alles-of-nietspropositie, dus let op wat er wel moet worden gewijzigd door de proxy.

Als u splits tunneling wilt toestaan, maar ook een proxy voor algemeen webverkeer wilt gebruiken, moet u ervoor zorgen dat uw PAC-bestand definieert wat direct moet gaan en hoe u interessant verkeer definieert voor wat er door de VPN-tunnel gaat. We bieden voorbeeld-PAC-bestanden [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) aan om dit gemakkelijker te beheren.

## <a name="conclusion"></a>Conclusie

Tienduizenden organisaties, waaronder bijna alle Fortune 500, gebruiken Office 365 voor hun missiekritische functies. Ze doen dit veilig en doen dit via internet.

Ongeacht de beveiligingsdoelen die u in het spel hebt, zijn er manieren om ze te bereiken waarvoor geen VPN-verbindingen, proxyservers, TLS-onderbrekingen en -inspectie of gecentraliseerde internetuitbreeding nodig zijn om het verkeer van uw gebruikers zo snel mogelijk van uw netwerk naar het onze te krijgen, wat de beste prestaties biedt, ongeacht of uw netwerk het hoofdkantoor van het bedrijf is. , een extern kantoor of die gebruiker die thuis werkt. Onze richtlijnen zijn gebaseerd op de Office 365 services en om een veilige en performante gebruikerservaring te garanderen.

## <a name="further-reading"></a>Verder lezen

[De Office 365 Netwerkconnectiviteitsprincipes](../enterprise/microsoft-365-network-connectivity-principles.md)

[URL's en IP-adresbereiken voor Office 365](../enterprise/urls-and-ip-address-ranges.md)

[Office 365-eindpunten beheren](../enterprise/managing-office-365-endpoints.md)

[IP-adres en URL-webservice van Office 365](../enterprise/microsoft-365-ip-web-service.md)

[Office 365-netwerkverbinding beoordelen](../enterprise/assessing-network-connectivity.md)

[Aanpassing van Office 365-netwerk en -prestaties](../enterprise/network-planning-and-performance.md)

[Office 365-netwerkverbinding beoordelen](../enterprise/assessing-network-connectivity.md)

[Office 365-prestatieafstemming met behulp van basislijnen en prestatiegeschiedenis](../enterprise/performance-tuning-using-baselines-and-history.md)

[Prestatieproblemen met Office 365 oplossen: planning](../enterprise/performance-troubleshooting-plan.md)

[Netwerken voor contentlevering](../enterprise/content-delivery-networks.md)

[Microsoft 365-connectiviteitstest](https://connectivity.office.com/)

[Hoe Microsoft zijn snelle en betrouwbare wereldwijde netwerk opbouwt](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365-netwerkblog](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Office 365 verbinding voor externe gebruikers die VPN splits tunneling gebruiken](../enterprise/microsoft-365-vpn-split-tunnel.md)