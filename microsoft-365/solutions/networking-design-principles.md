---
title: 'Netwerken up (to the Cloud): één standpunt van een architect'
description: Leer hoe u uw netwerk voor Cloud connectiviteit optimaliseert door veelvoorkomende problemen te voorkomen.
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
ms.openlocfilehash: 175903949b639740ad00b29013d5748b99bdb2de
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771845"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Netwerken up (to the Cloud): één standpunt van een architect

In dit artikel wordt beschreven hoe u uw netwerk voor Cloud connectiviteit kunt optimaliseren door [Ed, Fisher](https://www.linkedin.com/in/edfisher/), beveiliging & compliance architect bij Microsoft te vermijden door veelvoorkomende problemen te vermijden. 

## <a name="about-the-author"></a>Info over de auteur

![Ed Fisher foto](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Ik ben momenteel een hoofd specialist van de in de Zuid-Oost-regio gefocust op de beveiliging & naleving. Ik heb met klanten gewerkt voor de afgelopen tien jaar naar Office 365. Ik heb met kleinere winkels gewerkt met een aantal locaties aan overheidsinstanties en ondernemingen met miljoenen gebruikers die wereldwijd zijn verdeeld over de hele wereld, en vele andere klanten tussen, met het grootste deel van de wereld, het behoefte aan een betere beveiliging en een groot aantal nalevingsvereisten. Ik heb honderden van ondernemingen geholpen en miljoenen gebruikers wisselen veilig en veilig naar de Cloud.

Met een achtergrond in de afgelopen 25 jaar, waaronder beveiliging, infrastructuur en netwerk engineering, en over het verplaatsen van twee van de vorige werkgevers naar Office 365 voordat u deelneemt aan Microsoft, heb ik aan de kant van de tabel veel tijd en weet ik wat ze leuk vindt. Hoewel u niet twee klanten ooit hoeft te hebben, hebben we een prima behoefte, en bij het gebruik van een gestandaardiseerde service zoals een SaaS-of PaaS-platform, zijn de beste methoden hetzelfde.

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>Dat is niet het netwerk: dit is de manier waarop u (mis) met u werkt.

Het maakt niet uit hoe vaak het duurt, maar het is niet mogelijk dat de *creatieve* beveiligings teams en de netwerk teams u vragen om te zien hoe ze verbinding kunnen maken met de Microsoft-cloudservices. Er is altijd een aantal beveiligingsbeleid, compliance Standard, of betere manier waarop ze worden gebruikt zonder dat ze een gesprek te voeren over wat ze willen doen, of *hoe* ze beter, eenvoudiger, effectiever, effectievere, effectievere, effectievere, effectievere, effectievere, effectievere, effectievere, effectievere en effectievere manieren zijn.

Als u het object wilt laten overgaan naar mij, ben ik meestal bereid de uitdaging te nemen en door te gaan met de manier waarop ze moeten zijn. Maar als ik helemaal ben, moet ik dit delen, wat ze ook willen doen, wat ze ook willen doen, en ik ga terug naar mij laten weten dat het niet werkt wanneer ze uiteindelijk uitkomen. Dit kan ik soms doen, maar ik weet het *niet*. Wat ik doe, probeer een uitleg van alles wat ik in dit bericht ga opnemen. Ongeacht uw rol, als uw organisatie Microsoft-cloudservices wil gebruiken, is er waarschijnlijk een deel van de typen in de volgende mogelijkheden.

## <a name="guiding-principles"></a>Verrichtings principes

Laten we beginnen met bepaalde grondregels rond wat we hier doen. We bespreken de manier waarop u veilig verbinding kunt maken met cloudservices om de minimale complexiteit en de maximale prestaties te garanderen met behoud van werkelijke beveiliging. Geen van de navolgende bevindt zich op een willekeurige manier, ook niet als u, of als uw klant, uw favoriete proxyserver voor alles niet gebruikt.

- **U kunt ook** het volgende doen: of u kunt het parafraseer van Dr. Ian Malcolm van de Jurassic Park-film... Ja, ja, maar uw beveiligingsteam was al eerder bezet met het feit of hij of zij niet stopt om te denken als ze dit zouden doen. "
- **Beveiliging biedt geen** betrouwbare complexiteit: u bent niet veilig, net omdat u meer geld besteedt, routeert via meer apparaten of op meer knoppen klikt.
- **Office 365 wordt geopend via internet**: dit is niet hetzelfde als Office 365 Internet. Dit is een SaaS-service die door Microsoft wordt beheerd en door u wordt beheerd. In tegenstelling tot websites die u bezoekt op internet, kunt u ook op een andere manier van het gordijn kijken en de besturingselementen toepassen die u aan uw beleidsregels en uw nalevings standaarden moet voldoen, mits u begrijpt dat u de doelstellingen kunt bereiken.
- **Chokepoints zijn slecht, gelokaliseerd breakouts zijn goed**: iedereen wil al zijn of haar Internet verkeer voor alle gebruikers naar een centraal punt laten verzorgen, meestal zodat ze dit kunnen controleren en beleid kunnen afdwingen, maar vaak omdat het een goed idee is van het inrichten van Internet toegang op al hun locaties, of alleen op de manier waarop ze dit doen. Maar deze chokepoints zijn echt... punten waar het verkeer geknepen is. Er is niets mis met het voorkomen dat uw gebruikers naar Instagram of streaming Cat-Video's browsen, maar u kunt geen bedrijfskritische bedrijfstoepassingen verkeer op dezelfde manier behandelen.
- **Als u met echie tevreden bent, echie er niets** van te maken: het best mogelijke netwerk kan worden hamstrung door slecht DNS, ongeacht of u aanvragen doet voor servers in andere delen van de wereld of met behulp van de DNS-servers van uw internetprovider of andere openbare DNS-servers die de cache van DNS-omzettingsgegevens opslaan.
- **Aangezien u dit doet, betekent dit niet dat u dit nu moet doen**: technologie verandert continu en de werking van Office 365 geen uitzondering. Het toepassen van beveiligingsmaatregelen die zijn ontwikkeld en geïmplementeerd voor on-premises Services of voor het beheren van websurfen, bieden niet dezelfde mate van beveiligings zekerheid en kunnen een significante negatieve impact op de prestaties hebben.
- **Office 365 is gebouwd voor toegang via internet**: dat is het in een kort gezegd. Ongeacht wat u wilt doen tussen uw gebruikers en uw Edge, het verkeer gaat nog steeds via Internet nadat het het netwerk heeft verlaten en voordat het op onze computer terechtkomt. Ook als u gebruikmaakt van Azure ExpressRoute om bepaalde latentie gevoelige verkeer van uw netwerk rechtstreeks naar het Internet te routeren, is het mogelijk dat u helemaal een Internet verbinding hebt vereist. Accepteren. Zorg dat het niet klopt.

## <a name="where-bad-choices-are-often-made"></a>Waar vaak bepaalde keuzes worden gemaakt

In het geval van een goede beslissing in de naam van de beveiliging zijn er nog steeds de volgende gevallen met klanten. Veel klanten gesprekken hebben allemaal één keer.

### <a name="insufficient-resources-at-the-edge"></a>Onvoldoende bronnen op de Edge

Zeer weinig klanten implementeren Greenfield-omgevingen en ze hebben veel ervaring met de werking van hun gebruikers en de manier waarop hun gebruikers uitvalt. Of klanten gebruikmaken van proxyservers of directe toegang en gewoon verkeer voor verkeer toestaan, ze het voor jaren doen en geen rekening houden met de hoeveelheid meer dat ze de pomp van de Edge willen laten overlopen wanneer ze de traditionele nationale toepassingen verplaatsen naar de Cloud.

Bandbreedte is altijd een bezorgdheid, maar het is mogelijk dat de NAT-apparaten niet voldoende zijn voor het laden van de extra belasting en om verbindingen af te sluiten om bronnen vrij te maken. De meeste clientsoftware die verbinding maakt met Office 365, verwacht permanente verbindingen en een gebruiker die Office 365 volledig gebruikt, heeft mogelijk 32 of meer gelijktijdige verbindingen. Als het NAT-apparaat voortijdig overschakelt, kunnen deze apps niet langer reageren wanneer ze probeert de verbindingen te gebruiken die niet meer beschikbaar zijn. Wanneer ze een nieuwe verbinding bieden en deze proberen te maken, bieden ze nog meer belasting op het netwerk vistuig.

### <a name="localized-breakout"></a>Gelokaliseerde spreek

Alles wat in deze lijst voorkomt, is zo snel mogelijk, zodat u ze snel kunt verlaten. Backhauling het verkeer van uw gebruikers tot een centraal uitgangspunt, met name wanneer het uitgangspunt zich in een andere regio bevindt dan de gebruikers in, worden de clientervaring en de downloadsnelheid beïnvloed. Microsoft heeft overal ter wereld overal ter wereld met front-ends voor alle services en peering die met vrijwel elke grote INTERNETPROVIDER is opgericht, zodat het verkeer van gebruikers *lokaal* verloopt, zodat het sneller in ons netwerk komt met minimale latentie.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>DNS-oplossings verkeer moet het pad voor Internet-opvolgen volgen

Wanneer een client een eindpunt wil vinden, moet ze DNS gebruiken. De DNS-servers van Microsoft evalueren de bron van DNS-aanvragen om ervoor te zorgen dat het antwoord wordt weergeven in Internet, dat het meest overeenkomt met de bron van de aanvraag. Zorg ervoor dat uw DNS is geconfigureerd, zodat aanvragen voornaam omzetting hetzelfde pad van het verkeer van uw gebruikers krijgen, Lest u ze een lokale uitstap maakt, maar ook een eindpunt in een andere regio. Dit betekent dat u de lokale DNS-servers ' naar hoofdmap ' kunt gebruiken in plaats van door te sturen naar DNS-servers in externe datacenters. En Let op de publieke en private DNS-services die de cache van een deel van de wereld kunnen cacheeren en ze kunnen gebruiken voor aanvragen van andere delen van de wereld.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Naar proxy of niet naar proxy, dat wil zeggen de vraag

Een van de eerste dingen waarmee u rekening moet houden, is of de verbindingen van een proxy voor gebruikers met Office 365. Dat is eenvoudig. geen proxy. Office 365 wordt geopend via internet, maar het is niet het internet. Het is een uitbreiding van uw kernservices en moet als dusdanig worden afgehandeld. Alles wat u wilt, bijvoorbeeld DLP of antimalware of inhouds controle, is al voor u beschikbaar in de service en kan worden gebruikt op schaal en zonder gebruik te maken van TLS-gecodeerde verbindingen. Als u zeker weet dat u niet op een andere manier kunt overkijken, moet u aandacht schenken aan onze richtlijnen [https://aka.ms/pnc](https://aka.ms/pnc) en de soorten verkeer op [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) . Er zijn drie soorten verkeer voor Office 365. Optimaliseer en zorg ervoor dat echt rechtstreeks en via de proxy hoeft te overgaan. Standaard kan via een proxy worden verzonden. De gegevens zijn in deze documenten... Lees ze.

De meeste klanten die op een proxy letten, als ze in werkelijkheid kijken wat ze doen, gaan we realiseren dat wanneer de klant een HTTP CONNECT-aanvraag maakt voor de proxy, dat de proxy nu slechts een dure extra router maakt. De protocollen die in gebruik zijn, zoals MAPI en RTC, zijn niet even protocollen die met webclients werken, dus zelfs met TLS-kraken hoeft u geen extra beveiligings zekerheid te krijgen. U *krijgt* extra latentie. Zie [https://aka.ms/pnc](https://aka.ms/pnc) voor meer informatie, waaronder de categorieën optimaliseren, toestaan en standaard voor Microsoft 365-verkeer.

Ten slotte dient u de algemene impact van de proxy en het bijbehorende antwoord te bespreken om deze gevolgen af te handelen. Als er meer en meer verbindingen via de proxy tot stand worden gebracht, kan de TCP-schaal factor kleiner worden, zodat deze niet zo veel verkeer hoeft te worden opgeslagen. Ik heb klanten gezien dat hun proxy's zo zijn overgeladen, dat ze een schaal factor van 0 gebruiken. Aangezien schaalfactor een exponentiële waarde is en we 8 gebruiken, is elke verlaging van de waarde voor schaal factor een zeer negatieve impact op de doorvoer.

TLS-inspectie betekent beveiliging! Maar niet echt. Veel klanten met proxies willen ze gebruiken voor het controleren van alle verkeer, en dat betekent dat TLS "onderbreken en inspecteren". Wanneer u een website hebt geopend via HTTPS (met uitgaand privacy), moet u mogelijk dit doen voor 10 of zelfs 20 gelijktijdige stromen gedurende honderden milliseconden. Als er sprake is van een grote download of als u een video hebt gemaakt, kan dit een of meer van deze verbindingen lang langer duren, maar voor de meeste verbindingen gaat u zeer snel verbinding maken, overdragen en sluiten. Met break en inspecteert u wat betekent dat de proxy dubbel het werk moet doen. Voor elke verbinding van de client met de proxy moet de proxy ook een afzonderlijke verbinding maken met het eindpunt. Zo wordt 1 2, 2, 2, 32 4, 3... Zie waar ik ga? U had waarschijnlijk het formaat van uw proxy-oplossing, maar als u hetzelfde voor de client verbinding probeert te doen met Office 365, kunt u het aantal gelijktijdige verbindingen voor lange tijd in een bereik maken dat groter is dan het formaat van de afbeelding.

### <a name="streaming-isnt-important-except-that-it-is"></a>Streaming is niet belangrijk, behalve *dat het*

De enige services in Office 365 die gebruikmaken van UDP, zijn Skype (binnenkort buiten gebruik gesteld) en Microsoft teams. Teams maakt gebruik van UDP voor streaming verkeer, inclusief audio, video en het delen van presentaties. Streaming verkeer is Live, bijvoorbeeld wanneer u een onlinevergadering met spraak, video en presentaties presenteert of demo's uitvoert. Met UDP omdat indien pakketten worden neergezet, of ze niet in de juiste volgorde staan, is het nagenoeg niet merkbaar van de gebruiker en kan de stream gewoon blijven.

Wanneer u uitgaande UDP-verkeer van klanten naar de service niet toestaat, kunnen ze weer gebruikmaken van TCP. Maar als een TCP-pakket wordt neergezet, *stopt alles* totdat de time-out voor herverzending (RTO) verloopt en het ontbrekende pakket kan worden herverzonden. Als een pakket niet in de juiste volgorde arriveert, stopt alles totdat de andere pakketten binnenkomen en kunnen ze opnieuw worden geassembleerd. Beide leiden tot ongemerkte storingen in de audio (maximale beruimten?) en video (geklikt om iets te onthouden... Oh, er is het) en leiden tot slechte prestaties en een onjuiste gebruikerservaring. En weet wat ik hierboven heb ingevoerd voor proxy's? Wanneer u een teams-client gedwongen maakt een proxy te gebruiken, moet u de client dwingen om TCP te gebruiken. U veroorzaakt nu de negatieve prestatie-effecten tweemaal.

### <a name="split-tunneling-may-seem-scary"></a>Gesplitste tunneling kan enge lijken

Dat is niet het geval. Alle verbindingen met Office 365 zijn via TLS. We bieden TLS 1,2 voor een goed moment en zullen oudere versies binnenkort uitschakelen omdat oudere klanten ze nog steeds gebruiken en dat is een risico.

Als u een TLS-verbinding of een 32 van de verbinding wilt verbreken, moet u een VPN-verbinding tot stand brengen voordat ze naar de service worden toegevoegd. Het voegt latentie toe en vermindert de algehele doorvoer. In sommige VPN-oplossingen moet UDP zelfs UDP met behulp van TCP, wat dan ook, een zeer negatieve impact op streaming-verkeer afdwingt. En tenzij u TLS-inspectie uitvoert, is er geen enkele nadeel. Een zeer algemeen thema onder klanten, nu het grootste deel van hun werknemers extern is, is er een groot aantal bandbreedte-en prestatie-effecten voor het maken van verbinding met een VPN, in plaats van gesplitste tunneling te configureren voor Access voor het [optimaliseren van categorie Office 365-eindpunten](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories).

Dit is een gemakkelijke oplossing om gesplitste tunneling te doen, maar het is een oplossing. Ga voor meer informatie over het [optimaliseren van Office 365-connectiviteit voor externe gebruikers met gesplitste tunneling via VPN](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel).

## <a name="the-sins-of-the-past"></a>De zonden van het verleden

De reden waarom de keuzes worden doorgevoerd, is een combinatie van (1) die niet weet hoe de service werkt, (2) het bedrijfsbeleid dat is geschreven voordat u de Cloud opneemt, en (3) beveiligings teams die zich mogelijk niet gemakkelijk kunnen verwezenlijken. Hopelijk is het bovenstaande en de onderstaande koppelingen helpen bij de eerste. Het is mogelijk dat de sponsor van de directeur van de tweede persoon moet komen. Het afwijkende van de doelstellingen van de beveiligings beleidsregels in plaats van de methoden helpt u bij de derde. Van voorwaardelijke toegang tot inhouds toezicht, DLP voor de bescherming van uw gegevens, validatie van het eindpunt van de dag van de dag, elk einddoel van een redelijk beveiligingsbeleid kan plaatsvinden met wat er beschikbaar is in Office 365, en zonder enige afhankelijkheid op on-premises netwerk tandwiel, geforceerde VPN-tunnels en TLS-onderbreking.

Ook de hardware die werd geschaald en aangeschaft voordat de organisatie is begonnen met het overstappen op de Cloud, kan niet worden aangepast om de nieuwe verkeerspatronen en de ladingen te verwerken. Als u het verkeer via één uitgangspunt werkelijk moet doorlopen en/of proxy, moet u de netwerkapparatuur en de bandbreedte voorbereiden voor de upgrade. Zorg dat het gebruik van de ervaring voor beide gebruikers zorgvuldig oploopt omdat de ervaring niet meer kan worden vertraagd als er meer gebruikers zijn. Alles gaat verder totdat het aanwijzen van de kanteling is bereikt, dan iedereen gelijdt.

## <a name="exceptions-to-the-rules"></a>Uitzonderingen op de regels

Als u voor uw organisatie [Tenant beperkingen](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)vereist, moet u een proxy met TLS-onderbreking gebruiken en controleren of het verkeer via de proxy afdwingt, maar u hoeft geen verkeer af te dwingen.  Het is geen alles of geen enkele toegevoegde, dus let op wat wel moet worden gewijzigd door de proxy.

Als u het verdelen van tunneling toestaat maar ook een proxy voor algemeen webverkeer gebruikt, moet u ervoor zorgen dat uw PAC-bestand definieert wat er direct moet zijn en wat er gebeurt bij de manier waarop u de VPN-tunnel gaat definiëren. Voorbeelden van PAC-bestanden [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) , zodat u deze eenvoudiger kunt beheren.

## <a name="conclusion"></a>Conclusie

Tientallen duizenden organisaties, waaronder bijna alle Fortune 500, gebruiken Office 365 alledaags voor hun missie kritieke functies. Ze doen veilig en doen ze via internet.

Ongeacht de beveiligingsdoelstellingen die u hebt, zijn er een aantal manieren waarop VPN-verbindingen, proxyservers, TLS-onderbrekingen en onderzoek of gecentraliseerde Internet beveiliging niet is vereist, zodat het netwerkverkeer van uw gebruikers op uw netwerk en op onze manier kan worden vertraagd, ongeacht of het netwerk de hoofdzetel, een externe Office-versie is. of de gebruiker werkt thuis. Onze richtlijnen zijn van toepassing op de werking van de Office 365-Services en om ervoor te zorgen dat deze veilig en op de gebruikerservaring van de gebruiker werken.

## <a name="further-reading"></a>Verder lezen

[De principes van Office 365-netwerkverbindingen](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[URL's en IP-adresbereiken voor Office 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Office 365-eindpunten beheren](https://docs.microsoft.com/microsoft-365/enterprise/managing-office-365-endpoints)

[IP-adres en URL-webservice van Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-ip-web-service)

[Office 365-netwerkverbinding beoordelen](https://docs.microsoft.com/microsoft-365/enterprise/assessing-network-connectivity)

[Aanpassing van Office 365-netwerk en -prestaties](https://docs.microsoft.com/microsoft-365/enterprise/network-planning-and-performance)

[Office 365-netwerkverbinding beoordelen](https://docs.microsoft.com/microsoft-365/enterprise/assessing-network-connectivity)

[Office 365-prestatieafstemming met behulp van basislijnen en prestatiegeschiedenis](https://docs.microsoft.com/microsoft-365/enterprise/performance-tuning-using-baselines-and-history)

[Prestatieproblemen met Office 365 oplossen: planning](https://docs.microsoft.com/microsoft-365/enterprise/performance-troubleshooting-plan)

[Netwerken voor contentlevering](https://docs.microsoft.com/microsoft-365/enterprise/content-delivery-networks)

[Microsoft 365-connectiviteitstest](https://connectivity.office.com/)

[Hoe Microsoft zijn snelle en betrouwbare wereldwijde netwerk opbouwt](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365-netwerkblog](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Office 365-connectiviteit voor externe gebruikers die gebruikmaken van gesplitste tunneling via VPN](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)


