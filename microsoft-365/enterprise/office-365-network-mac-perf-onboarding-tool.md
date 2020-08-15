---
title: Microsoft 365 Connectivity test (preview) in het Microsoft 365-Beheercentrum
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 connectiviteitstest in het M365-Beheercentrum (preview)
ms.openlocfilehash: 421df459e2a8a1c1c62680b2d3658f5bdd297b25
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689232"
---
# <a name="microsoft-365-connectivity-test-in-the-microsoft-365-admin-center-preview"></a>Microsoft 365-connectiviteitstest in het Microsoft 365-Beheercentrum (preview)

De Microsoft 365 connectiviteitstest bevindt zich op <https://connectivity.office.com> . Het is een adjunct-hulpmiddel voor de netwerk inzichten en de netwerk Score informatie die beschikbaar is in het Microsoft 365-Beheercentrum, onder de **status | Menu netwerkprestaties** .

>[!NOTE]
>Het hulpprogramma voor onboarding ondersteunt tenants in de Duitse commerciële versie en GCC matig, maar niet GCC High, DoD, Duitsland of China.

De netwerk inzichten in het Microsoft 365-Beheercentrum zijn gebaseerd op de maateenheden van het product voor uw Microsoft 365-Tenant. In vergelijking worden de netwerk inzichten van de Microsoft 365 connectiviteitstest lokaal uitgevoerd in het hulpprogramma. Tests die in het product kunnen worden uitgevoerd, zijn beperkt en door tests te voeren die voor de gebruiker toegankelijk zijn, kunnen de gegevens worden verzameld met een betere inzichten. Houd er rekening mee dat de netwerk inzichten in het Microsoft 365-Beheercentrum op een specifieke locatie van Office een netwerkprobleem voor gebruik van Microsoft 365. Met behulp van de Microsoft 365 Connectivity test kunt u de hoofdoorzaak van dit probleem achterhalen en de aanbevolen actie voor netwerk prestatieverbetering.

We raden u aan dat ze samen gebruiken waar de status van netwerkkwaliteit kan worden geëvalueerd voor elke Office-locatie in het Microsoft 365-Beheercentrum en dat specifiekere informatie kan worden gevonden na de implementatie van de test op basis van de Microsoft 365-connectiviteitstest.

>[!IMPORTANT]
>Netwerk inzichten, prestatie aanbevelingen en beoordelingen in het Microsoft 365-Beheercentrum is momenteel in de preview-versie en is alleen beschikbaar voor Microsoft 365-tenants die zijn geregistreerd in het functie voorbeeldprogramma.

## <a name="the-advanced-tests-client-application"></a>De clienttoepassing geavanceerde tests

Er zijn twee gedeelten voor de Microsoft 365-connectiviteitstest. Er is <https://connectivity.office.com> een website en er is een downloadbare Windows-clienttoepassing. De downloadbare client voert geavanceerde aansluitingen voor de netwerkverbinding uit, en de meeste van de tests vereisen dat deze worden uitgevoerd.

U kunt de geavanceerde client test uitvoeren via de website en de resultaten worden weergegeven op de webpagina wanneer deze wordt uitgevoerd.

![Voorbeeld van testresultaten van het O365-netwerk](../media/m365-mac-perf/m365-mac-perf-onboarding-tool-tests.png)

## <a name="user-office-location"></a>Locatie van gebruiker

De locatie van de gebruikers Office wordt gedetecteerd in de browser van de gebruikers. Dit wordt gebruikt voor het identificeren van de afstand van een netwerk tot bepaalde delen van de netwerkverbinding van het bedrijf.

De werklocatie van de gebruiker wordt weergegeven in de kaartweergave.

## <a name="distance-to-the-network-egress-location"></a>Afstand tot de locatie van de netwerk uitgang

We identificeren het IP-adres van het IP-adres van uw netwerk aan de serverzijde. Location-databases worden gebruikt voor het opzoeken van de geschatte locatie van de netwerk uitgang en het bepalen van de afstand tot de kantoorlocatie. Dit wordt weergegeven als een netwerk inzicht als de afstand groter is dan 500 km (800 kilometer).

De locatie van netwerk uitgang wordt weergegeven in de kaartweergave en verbonden met de kantoorlocatie van de gebruiker, die aangeeft dat de netwerk-backhaul in de Enterprise-WAN.

De locatie die is opgezocht vanuit het IP-adres van het netwerk, is mogelijk niet nauwkeurig en resulteert in een foutmelding. Als u wilt controleren of deze fout optreedt voor een specifiek IP-adres, kunt u weblocaties voor algemeen toegankelijke netwerklocaties gebruiken.

Het implementeren van lokale en rechtstreekse netwerk uitgang van gebruikers Office-locaties op Internet wordt aangeraden voor de Microsoft 365-netwerkverbinding. Verbeteringen aan lokale en direct aflossing zijn de beste manier om dit netwerk inzicht te verhelpen.

## <a name="exchange-online-service-front-door"></a>Voor deur van Exchange Online service

De Exchange Online-service voor Exchange Online wordt aangegeven op dezelfde manier als in Outlook dit doet, en de TCP-latentie van de gebruiker wordt gemeten van de werkplek in de netwerklocatie. Deze worden weergegeven en de Exchange Online-serviceas van Exchange wordt vergeleken met de lijst met aanbevolen optimale service voor de huidige locatie. Dit wordt weergegeven als een netwerk inzicht als een niet-optimale Exchange Online-service de front deur gebruikt.

Het gebruik van een niet-optimale omruil bare Exchange Online-service kan worden veroorzaakt door netwerk backhaul voordat het bedrijfsnetwerk wordt uitgevoerd, zodat het een lokale en rechtstreekse netwerk uitgang voor u aanbeveelt. Dit kan ook worden veroorzaakt door het gebruik van een externe DNS recursieve resolver-server, maar het is raadzaam de DNS recursieve resolver server uit te lijnen met het netwerk uitgang.

De TCP-latentie van de Exchange Online-service voor de front-deur wordt mogelijk verbeterd. Dit houdt in dat u de geteste netwerklatentie van de geteste gebruikerslocatie en de netwerklatentie aftrekt van de huidige locatie naar de vertrekken Exchange Online-service voor de klep. Het verschil vertegenwoordigt de potentiële verkoopkans voor verbetering.

## <a name="comparison-of-performance-of-customers-in-the-area"></a>Vergelijking van de prestaties van klanten in het gebied

De TCP-latentie van de gebruiker in de gebruikerslocatie van de Exchange Online-service wordt vergeleken met andere klanten van Microsoft 365 in hetzelfde metro gebied. Een netwerk inzicht wordt weergegeven als 10% of meer van klanten in hetzelfde metro gebied betere prestaties hebben.

Dit netwerk inzicht wordt gegenereerd op basis van de voorwaarden dat alle gebruikers in een stad toegang hebben tot dezelfde telecommunicatie infrastructuur en dezelfde dicht bij Internet circuits en van het Microsoft-netwerk.

## <a name="in-use-default-gateway"></a>Bij standaardgateway gebruiken

De standaardgateway in gebruik is de router die de test-client heeft geconfigureerd voor routerings-TCP/IP-netwerkverbindingen.

Dit wordt uitsluitend ter informatie verstrekt en geen bijdrage aan een netwerk inzicht.

## <a name="in-use-dns-servers"></a>DNS-servers gebruiken

Hier ziet u de DNS-server die is geconfigureerd op de clientcomputer waarmee de tests worden uitgevoerd. Het kan een DNS recursieve resolver server zijn, maar dit is niet gebruikelijk. Het is waarschijnlijk een DNS-doorstuurserver waarmee DNS-resultaten worden gecached en DNS-aanvragen worden doorgestuurd naar een andere DNS-server.

Dit wordt uitsluitend ter informatie verstrekt en geen bijdrage aan een netwerk inzicht.

## <a name="identified-dns-recursive-resolver-server"></a>Aangegeven DNS recursieve resolver server

De DNS recursieve resolver in gebruik wordt aangegeven door een specifieke DNS-aanvraag in te stellen en vervolgens de DNS-naam server te vragen voor het IP-adres waarvan het dezelfde aanvraag heeft ontvangen. Dit IP-adres is de recursieve resolver DNS en wordt weergegeven in databases van IP-adres locaties om de locatie te vinden. De afstand van de locatie van de werkplek van de gebruiker naar de locatie van de DNS recursieve resolver server wordt vervolgens berekend. Dit wordt weergegeven als een netwerk inzicht als de afstand groter is dan 500 km (800 kilometer).

De locatie die is opgezocht vanuit het IP-adres van het netwerk, is mogelijk niet nauwkeurig en resulteert in een foutmelding. Als u wilt controleren of deze fout optreedt voor een specifiek IP-adres, kunt u weblocaties voor algemeen toegankelijke netwerklocaties gebruiken.

Dit netwerk inzicht is specifiek van invloed op de selectie van de Exchange Online-service-voor deur. Als u dit inzicht lokaal en direct netwerk uitgang wilt verhelpen, moet u eerst een vereiste zijn en moet DNS recursieve resolver bevinden bij het afsluiten van de netwerkverbinding.

## <a name="dns-lookup-of-exchange-online-front-end-server-and-sharepoint-online-front-end-server"></a>DNS-lookup van Exchange Online front end server en SharePoint Online front end server

De DNS-record voor de front cover van de service wordt weergegeven voor deze twee workloads van Microsoft 365. Ze worden uitsluitend ter informatie verstrekt en er is geen bijbehorend netwerk inzicht.

## <a name="proxy-server-identification"></a>Proxy serveridentificatie

We identificeren welke proxyserver (s) zijn geconfigureerd op de lokale computer. We identificeren of een van deze zijn geconfigureerd in het netwerkpad voor de categorie Microsoft 365-netwerkverkeer optimaliseren. We identificeren de afstand van de werklocatie van de gebruiker naar de proxyservers. De afstand wordt eerst getest door ICMP ping en als dit niet lukt, testen met TCP ping en ten slotte als dit niet lukt, het IP-adres van de proxyserver wordt opgezocht in een database voor een IP-adreslocatie. We tonen een netwerk inzicht als de proxyserver verder is dan 500 km (800 kilometer) buiten de kantoorlocatie van de gebruiker.

## <a name="media-quality-checks"></a>Controles van media kwaliteit

Met deze toets wordt het hulpprogramma voor het uitvoeren van de Skype voor bedrijven-netwerk beoordeling geïnstalleerd en wordt de resultaten interpreteert. Het hulpmiddel is te vinden op [https://www.microsoft.com/download/details.aspx?id=53885](https://www.microsoft.com/download/details.aspx?id=53885) .

Dit zijn UDP-protocol tests die worden gebruikt door Microsoft teams-functies voor audio-en videogesprekken en vergaderingen. We testen voor UDP-pakketverlies, UDP-netwerklatentie, UDP-jitter en UDP pakket opnieuw ordenen. Een netwerk inzicht wordt weergegeven als een van deze voor het toegestane bereik valt.

## <a name="tcp-connectivity-tests"></a>TCP-connectiviteitstests

We testen for HTTP Connectivity van de gebruikerslocatie van de gebruiker op alle vereiste Microsoft 365-netwerkeindpunten. Deze worden gepubliceerd op [https://aka.ms/o365ip](https://aka.ms/o365ip) . Er wordt een netwerk inzicht weergegeven voor alle vereiste netwerkeindpunten waarop geen verbinding kan worden gemaakt.

Connectiviteits ay worden geblokkeerd door een proxyserver, firewall of een ander netwerk beveiligingsapparaat in het netwerk van het bedrijf of wordt gebruikt als Cloud proxy.

## <a name="ssl-interception-tests"></a>SSL-onderschepings tests

We testen het SSL-certificaat op elk vereist Microsoft 365-netwerk eindpunt in de categorie optimaliseren of toestaan zoals gedefinieerd [https://aka.ms/o365ip](https://aka.ms/o365ip) . Als een van de tests een Microsoft SSL-certificaat niet vindt, moet het versleutelde netwerk zijn onderschept door een tussenliggend netwerkapparaat. Een netwerk inzicht wordt weergegeven op een geintercepteerde, versleutelde netwerkeindpunten.

Wanneer er een SSL-certificaat wordt gevonden dat niet wordt geleverd door Microsoft, wordt de FQDN getoond voor de test en de eigenaar van het SSL-certificaat. Dit SSL-certificaat mag de leveranciers van een proxyserver zijn, of dit is een zelf ondertekend certificaat van een onderneming.

## <a name="network-path-diagnostics"></a>Diagnostische gegevens voor netwerk

In deze sectie ziet u de resultaten van een ICMP-traceroute naar de front-van de Exchange Online-service, de front-service van de SharePoint Online-service en de front-service van Microsoft teams. Het wordt alleen ter informatie verstrekt en er is geen netwerk inzicht.

## <a name="faq"></a>Veelgestelde vragen

Hier vindt u antwoorden op enkele van onze veelgestelde vragen.

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>Is dit hulpprogramma vrijgegeven en ondersteund door Microsoft?

Het is momenteel een proefversie van het concept en we gaan updates regelmatig leveren totdat we de algemene beschikbaarheid van de versie met ondersteuning van Microsoft bereiken. Geef feedback om ons te helpen verbeteren. Er is een overzicht van de introductiehandleiding voor Office 365 voor het netwerk als onderdeel van dit hulpprogramma dat voor de organisatie is aangepast door de testresultaten.

### <a name="what-is-microsoft-365-service-front-door"></a>Wat is de front cover van de Microsoft 365-service?

De Microsoft 365-service front deur is een toegangspunt voor het globale netwerk van Microsoft waar Office-clients en-services hun netwerkverbinding beëindigen. Voor een optimale netwerkverbinding met Microsoft 365 wordt u aangeraden uw netwerkverbinding te beëindigen met de dichtstbijzijnde Microsoft 365-voor deur in uw stad of metro.

Opmerking: de front cover van de Microsoft 365-service heeft geen directe relatie met de ' Azure-service voor de front-deur ', die beschikbaar is in azure Marketplace.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>Wat is een optimale front cover-service van Microsoft 365.

Een optimale front-service van Microsoft 365 is een service die het meest geschikt is voor uw netwerk uitgang, in het algemeen in het gebied plaats of metro. Gebruik het hulpprogramma voor prestatiehulpprogramma's van Microsoft 365 om te bepalen waar u de Microsoft 365-service voor de voor deur en de optimale service klep kunt gebruiken. Als het hulpprogramma bepaalt dat de front-in-de voorgrond van uw gebruik optimaal is, maakt u optimaal verbinding met het wereldwijde netwerk van Microsoft.

### <a name="what-is-an-internet-egress-location"></a>Wat is een locatie voor uitgaand Internet?

De locatie voor het uittreden van Internet is de locatie waar uw netwerkverkeer uw Enterprise-netwerk verlaat en verbinding maakt met internet. Dit wordt ook herkend als de locatie waar u een NAT-apparaat (Network Address Translation) hebt en meestal waarbij u verbinding maakt met een internetprovider (ISP). Als u de locatie van uw locatie en de locatie van uw internetverbinding lang ziet, kan dit een belangrijke WAN-backhaul.

## <a name="related-topics"></a>Verwante onderwerpen

[Aanbevelingen voor netwerkprestaties in het Microsoft 365-Beheercentrum (preview)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Performance Insights (preview)](office-365-network-mac-perf-insights.md)

[Microsoft 365-netwerk beoordeling (preview)](office-365-network-mac-perf-score.md)

[Locatie Services voor Microsoft 365-netwerkconnectiviteit](office-365-network-mac-location-services.md)
