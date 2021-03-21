---
title: Testprogramma voor microsoft 365-netwerkconnectiviteit (preview)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Testprogramma voor microsoft 365-netwerkconnectiviteit (preview)
ms.openlocfilehash: 3597996a74cccc3a178f7a5a637c956e0393641b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926116"
---
# <a name="microsoft-365-network-connectivity-test-tool-preview"></a>Testprogramma voor microsoft 365-netwerkconnectiviteit (preview)

Het testprogramma voor microsoft 365-netwerkconnectiviteit bevindt zich op <https://connectivity.office.com> . Het is een extra hulpmiddel voor de netwerkbeoordeling en netwerkinzichten die beschikbaar zijn in het Microsoft 365-beheercentrum onder de **| Verbindingsmenu.**

> [!IMPORTANT]
> Het is belangrijk om u aan te melden bij uw Microsoft 365-tenant, aangezien alle testrapporten worden gedeeld met uw beheerder en worden geüpload naar de tenant terwijl u bent aangemeld.

![Connectiviteitstesthulpmiddel](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>Het testprogramma voor netwerkconnectiviteit ondersteunt tenants in WW Commercial en Duitsland, maar niet GCC Moderate, GCC High, DoD of China.

De netwerkinzichten in het Microsoft 365-beheercentrum zijn gebaseerd op regelmatige in-product metingen voor uw Microsoft 365-tenant die elke dag worden samengevoegd. Ter vergelijking: de netwerkinzichten van de Microsoft 365-netwerkconnectiviteitstest worden lokaal en één keer uitgevoerd in het hulpprogramma. Testen die in een product kunnen worden uitgevoerd, zijn beperkt en door tests lokaal uit te voeren voor de gebruiker, kunnen meer gegevens worden verzameld, wat resulteert in diepere inzichten. Houd er dan rekening mee dat de netwerkinzichten in het Microsoft 365-beheercentrum laten zien dat er een netwerkprobleem is voor gebruik van Microsoft 365 op een specifieke kantoorlocatie. De Microsoft 365-connectiviteitstest kan helpen bij het identificeren van de hoofdoorzaak van dat probleem, wat leidt tot een aanbevolen actie voor het verbeteren van de netwerkprestaties.

We raden u aan deze samen te gebruiken, waar de netwerkkwaliteitsstatus kan worden beoordeeld voor elke kantoorlocatie in het Microsoft 365-beheercentrum en meer specifieke informatie kan worden gevonden na de implementatie van tests op basis van de Microsoft 365-connectiviteitstest.

>[!IMPORTANT]
>Netwerkinzichten, prestatieaanbevelingen en evaluaties in het Microsoft 365-beheercentrum hebben momenteel de preview-status en zijn alleen beschikbaar voor Microsoft 365-tenants die zijn geregistreerd voor het functievoorbeeldprogramma.

## <a name="what-happens-at-each-test-step"></a>Wat gebeurt er bij elke teststap

### <a name="office-location-identification"></a>Locatie-identificatie van Office

Wanneer u op de knop Uitvoeren test klikt, wordt de testpagina weergegeven en wordt de locatie van het kantoor gevonden. U kunt uw locatie typen op plaats, provincie en land of u kunt de locatie laten detecteren vanuit de webbrowser. Als u deze detecteert, vragen we de breedte- en lengtegraad van de webbrowser aan en beperken we de nauwkeurigheid tot 300m bij 300 meter vóór gebruik. We doen dit omdat het niet nodig is om de locatie nauwkeuriger te identificeren dan het gebouw voor netwerkprestaties. 

### <a name="javascript-tests"></a>JavaScript-tests

Na de identificatie van office-locatie voeren we een TCP-latentietest uit in JavaScript en vragen we gegevens van de service over in-gebruik en aanbevolen Office 365-serviceservers. Wanneer deze zijn voltooid, worden ze weergegeven op de kaart en op het detailtabblad waar ze vóór de volgende stap kunnen worden bekeken.

### <a name="download-the-advanced-tests-client-application"></a>De clienttoepassing voor geavanceerde tests downloaden

Vervolgens starten we de download van de clienttoepassing voor geavanceerde tests. We zijn afhankelijk van de gebruiker om de clienttoepassing te starten en ze moeten ook .NET Core hebben geïnstalleerd.

De microsoft 365-netwerkconnectiviteitstest bestaat uit twee onderdelen. de website en <https://connectivity.office.com> een downloadbare Windows-clienttoepassing met geavanceerde netwerkconnectiviteitstests. Voor de meeste tests moet de toepassing worden uitgevoerd. De resultaten worden weer op de webpagina ingevuld terwijl deze wordt uitgevoerd.

U wordt gevraagd de geavanceerde clienttesttoepassing van de website te downloaden nadat de webbrowsertests zijn voltooid. Open het bestand en voer het uit wanneer u daarom wordt gevraagd.

![Clienttoepassing voor geavanceerde tests](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>De clienttoepassing voor geavanceerde tests starten

Zodra de clienttoepassing is gestart, wordt de webpagina bijgewerkt om deze weer te geven en worden testgegevens ontvangen op de webpagina. Deze wordt bijgewerkt telkens wanneer er nieuwe gegevens worden ontvangen en u kunt de gegevens bekijken wanneer deze binnenkomen.

### <a name="advanced-tests-completed-and-test-report-upload"></a>Geavanceerde tests voltooid en rapport uploaden testen

Wanneer de tests zijn voltooid, worden de webpagina en de client voor geavanceerde tests beide aangegeven en als de gebruiker is aangemeld in het testrapport, wordt deze geüpload naar de tenant van de klant.

## <a name="sharing-your-test-report"></a>Uw testrapport delen

Voor het testrapport moet u zich aanmelden bij uw Office 365-account. De beheerder selecteert hoe u uw testrapport kunt delen.

### <a name="sharing-your-report-with-your-administrator"></a>Uw rapport delen met uw beheerder

Alle testrapporten terwijl u bent aangemeld, worden gedeeld met uw beheerder.

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Delen met uw Microsoft-accountteam, ondersteuning of ander personeel

Testrapporten, exclusief persoonlijke identificatie, worden gedeeld met Microsoft-werknemers. Dit is standaard ingeschakeld en kan worden uitgeschakeld door uw beheerder in de **| Pagina Netwerkconnectiviteit** in het Microsoft 365-beheercentrum.

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a>Delen met andere gebruikers die zich aanmelden bij dezelfde Office 365-tenant

U kunt gebruikers kiezen om uw rapport mee te delen en dit is standaard ingeschakeld. Het kan ook worden uitgeschakeld door uw beheerder.

![Een koppeling naar uw testresultaten delen met een gebruiker](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>Delen met iedereen die een reportid-koppeling gebruikt

U kunt uw testrapport met iedereen delen door toegang te geven tot een ReportID-koppeling. Hiermee wordt een URL gegenereerd die u naar iemand kunt verzenden, zodat deze persoon het testrapport kan openen zonder zich aan te melden. Dit is standaard uitgeschakeld en moet zijn ingeschakeld door uw beheerder.

![Een koppeling naar uw testresultaten delen](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>Testresultaten voor netwerkconnectiviteit

De resultaten worden weergegeven op de **tabbladen Overzicht** **en** Details. Op het overzichtstabblad ziet u een kaart van de gedetecteerde netwerkperimeter en een vergelijking van de netwerkbeoordeling met andere Office 365-klanten in de buurt. Het is ook mogelijk om het testrapport te delen. De overzichtsresultatenweergave ziet er als volgt uit.

![Samenvattingsresultaten van testprogramma voor netwerkconnectiviteit](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

Hier ziet u een voorbeeld van de uitvoer van het tabblad Details die door het hulpprogramma wordt weergegeven. Op het tabblad Details wordt een groene cirkel weergegeven als het resultaat gunstig is vergeleken met een drempelwaarde. We geven een rood driehoeksuitroepteken weer als het resultaat een drempelwaarde overschrijdt die een netwerkinzicht aangeeft. In de volgende secties worden de rijen met de resultaten van elk detailtabblad beschreven en worden de drempelwaarden voor netwerkinzichten beschreven.

![Voorbeeld van testresultaten van testprogramma voor netwerkconnectiviteit](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>Uw locatiegegevens

In deze sectie ziet u testresultaten die betrekking hebben op uw locatie.

#### <a name="your-location"></a>Uw locatie

De locatie van de gebruiker wordt gedetecteerd vanuit de webbrowser van gebruikers of kan worden getypt bij de gebruikerskeuze. Het wordt gebruikt om netwerkafstanden tot specifieke delen van de bedrijfsnetwerkperimeter te identificeren. Alleen de plaats van deze locatiedetectie en de afstand tot andere netwerkpunten worden opgeslagen in het rapport.

De locatie van het gebruikerskantoor wordt weergegeven in de kaartweergave.

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>Netwerklocatie (de locatie waar uw netwerk verbinding maakt met uw isp)

We identificeren het IP-adres van het netwerk aan de serverzijde. Locatiedatabases worden gebruikt om de locatie van het netwerk bij benadering op te zoeken. Deze databases hebben meestal een nauwkeurigheid van ongeveer 90% van de IP-adressen. Als de locatie die is op gezocht vanuit het IP-adres van het netwerk niet juist is, zou dit leiden tot een onwaar resultaat van deze test. Als u wilt controleren of deze fout optreedt voor een specifiek IP-adres, kunt u openbare IP-adressites van het netwerk gebruiken om te vergelijken met uw werkelijke locatie.

#### <a name="your-distance-from-the-network-egress-location"></a>Uw afstand tot de netwerklocatie

We bepalen de afstand van die locatie tot de kantoorlocatie. Dit wordt weergegeven als een netwerkinzicht als de afstand groter is dan **800** kilometer, omdat de TCP-latentie hierdoor waarschijnlijk met meer dan 25 ms wordt vergroot en de gebruikerservaring kan worden beïnvloed.

De netwerklocatie wordt weergegeven in de kaartweergave en is verbonden met de kantoorlocatie van de gebruiker die aangeeft dat de netwerkbackhaul binnen de WAN van het bedrijf is.

Voor microsoft 365-netwerkconnectiviteit wordt aanbevolen om lokale en directe netwerkverdrading van gebruikers office-locaties naar internet te implementeren. Verbeteringen in lokale en directe uittreding zijn de beste manier om dit netwerkinzicht aan te pakken.

#### <a name="proxy-server-information"></a>Proxyservergegevens

We identificeren proxyservers die zijn geconfigureerd op de lokale computer. We identificeren of een van deze zijn geconfigureerd in het netwerkpad voor het optimaliseren van categorie Microsoft 365-netwerkverkeer. We identificeren de afstand van de locatie van het gebruikerskantoor tot de proxyservers. De afstand wordt eerst getest door ICMP-ping en als dat mislukt, testen we met TCP-ping en als dat mislukt, zoeken we het IP-adres van de proxyserver op in een IP-adreslocatiedatabase. We geven een netwerkinzicht weer als de proxyserver zich verder dan **800** kilometer van de locatie van het gebruikerskantoor bevindt.

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>Vpn (Virtual Private Network) dat u gebruikt om verbinding te maken met uw organisatie

Hiermee wordt gedetecteerd of u een VPN gebruikt om verbinding te maken met Office 365. Een passerend resultaat laat zien of u geen VPN hebt of als u een VPN hebt met de aanbevolen configuratie van een gesplitste tunnel voor Office 365.

#### <a name="vpn-split-tunnel"></a>VPN Split Tunnel

Elke categorieroute optimaliseren voor Exchange Online, SharePoint Online en Microsoft Teams wordt getest om te zien of deze al dan niet wordt ge tunneld op de VPN. Een gesplitste werkbelasting voorkomt dat de VPN volledig wordt gebruikt. Een ge tunnelde werkbelasting wordt allemaal via de VPN verzonden. Een selectief ge tunnelde werkbelasting heeft een aantal routes die via de VPN zijn verzonden en sommige zijn gesplitst. Een passerend resultaat laat zien of alle werkbelastingen zijn gesplitst of selectief zijn ge tunneld.

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>Klanten in uw grootstedelijke regio met betere prestaties

De TCP-latentie van het netwerk van de kantoorlocatie van de gebruiker naar de voordeur van de Exchange Online-service wordt vergeleken met andere Microsoft 365-klanten in hetzelfde metrogebied. Een netwerkinzicht wordt weergegeven als 10% of meer klanten in hetzelfde metrogebied betere prestaties hebben. Dit betekent dat hun gebruikers betere prestaties hebben in de gebruikersinterface van Microsoft 365.

Dit netwerkinzicht wordt gegenereerd op basis van het feit dat alle gebruikers in een stad toegang hebben tot dezelfde telecommunicatie-infrastructuur en dezelfde nabijheid van internetcircuits en het netwerk van Microsoft.

#### <a name="time-to-make-a-dns-request-on-your-network"></a>Tijd om een DNS-aanvraag in uw netwerk te doen

Hier ziet u de DNS-server die is geconfigureerd op de clientmachine die de tests heeft uitgevoerd. Het kan een DNS Recursive Resolver-server zijn, maar dit is ongebruikelijk. Het is waarschijnlijker dat het een DNS-doorstoverserver is die DNS-resultaten cachet en eventuele niet-cached DNS-aanvragen doorstovert naar een andere DNS-server.

Dit wordt alleen ter informatie verstrekt en draagt niet bij aan enig netwerkinzicht.

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>Uw afstand tot en/of tijd om verbinding te maken met een DNS-recursieve resolver

De in-use DNS Recursive Resolver wordt geïdentificeerd door een specifieke DNS-aanvraag te doen en vervolgens de DNS-naamserver te vragen om het IP-adres waar het dezelfde aanvraag van heeft ontvangen. Dit IP-adres is de DNS Recursive Resolver en wordt opgeslagen in IP-adreslocatiedatabases om de locatie te vinden. De afstand van de locatie van het gebruikerskantoor tot de dns-recursieve resolver-serverlocatie wordt vervolgens berekend. Dit wordt weergegeven als een netwerkinzicht als de afstand groter is dan **800** kilometer.

De locatie die is op gezocht vanuit het IP-adres van het netwerk, is mogelijk niet nauwkeurig en dit zou leiden tot een onwaar resultaat van deze test. Als u wilt valideren of deze fout optreedt voor een specifiek IP-adres, kunt u openbare IP-adreslocatiesites van het netwerk gebruiken.

Dit netwerkinzicht is specifiek van invloed op de selectie van de Exchange Online-servicedeuren. Om dit inzicht aan te pakken moet een lokaal en direct netwerkverdediging een vereiste zijn en moet DNS Recursive Resolver zich dicht bij dat netwerk-uitgang bevinden.

### <a name="exchange-online"></a>Exchange Online

In deze sectie ziet u testresultaten met betrekking tot Exchange Online.

#### <a name="exchange-service-front-door-location"></a>Locatie van de Exchange-service voor de deur

De in-use Exchange-servicedeuren worden op dezelfde manier geïdentificeerd als outlook en we meten de TCP-latentie van het netwerk van de gebruikerslocatie naar de service. De TCP-latentie wordt weergegeven en de in gebruik genomen Exchange-servicedeuren worden vergeleken met de lijst met beste servicedeuren voor de huidige locatie. Dit wordt weergegeven als een netwerkinzicht als een van de beste Exchange-service-front-door(s) niet wordt gebruikt.

Het niet gebruiken van een van de beste exchange-servicedeuren kan worden veroorzaakt door netwerkbackhaul voordat het bedrijfsnetwerk uitkomt. In dat geval raden we lokale en directe netwerkuittreding aan. Dit kan ook worden veroorzaakt door het gebruik van een externe DNS-recursieve resolverserver, in welk geval het raadzaam is om de DNS-recursieve resolverserver uit te lijnen met het netwerkuitstroom.

We berekenen een mogelijke verbetering van de TCP-latentie (ms) naar de exchange-servicedeuren. Dit wordt gedaan door te kijken naar de geteste latentie van het office-netwerk van gebruikers en de netwerklatentie af te trekken van de huidige locatie naar de kasten van de Exchange-servicedeuren. Het verschil vertegenwoordigt de potentiële kans voor verbetering.

#### <a name="best-exchange-service-front-doors-for-your-location"></a>Beste Exchange-service voor deur(en) voor uw locatie

Hier vindt u de beste locaties voor de Exchange-service voor de deur per plaats voor uw locatie.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Servicedeuren die zijn opgenomen in de DNS-client

Hier ziet u de DNS-naam en HET IP-adres van de Server voor de Exchange-service waar u naar bent doorgestuurd. De informatie wordt alleen verstrekt voor informatie en er is geen netwerkinzicht.

### <a name="sharepoint-online"></a>SharePoint Online

In deze sectie ziet u testresultaten met betrekking tot SharePoint Online en OneDrive.

#### <a name="the-service-front-door-location"></a>De locatie van de service voor de deur

De in-use SharePoint-servicedeuren worden op dezelfde manier geïdentificeerd als de OneDrive-client en we meten de TCP-latentie van het netwerk vanaf de locatie van het gebruikerskantoor naar de client.

#### <a name="download-speed"></a>Downloadsnelheid

We meten de downloadsnelheid voor een bestand van 15 Mb van de SharePoint-servicedeuren. Het resultaat wordt weergegeven in megabytes per seconde om aan te geven welke bestandsgrootte in megabytes in één seconde kan worden gedownload vanuit SharePoint **of** OneDrive. Het getal moet vergelijkbaar zijn met een tiende van de minimale circuitbandbreedte in megabits per seconde. Als u bijvoorbeeld een internetverbinding van 100 mbps hebt, kunt u 10 megabyte per seconde (10 MBps) verwachten.

#### <a name="buffer-bloat"></a>Bufferzwelling

Tijdens de download van 15 Mb meten we de TCP-latentie naar de SharePoint-servicedeuren. Dit is de latentie onder belasting en wordt vergeleken met de latentie wanneer deze niet wordt geladen. De toename van de latentie bij belasting is vaak toe te schrijven aan buffers voor consumentennetwerkapparaat die worden geladen (of een opgeblazen gevoel). Een netwerkinzicht wordt weergegeven voor elke 1.000 of meer.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Servicedeuren die zijn opgenomen in de DNS-client

Hier ziet u de DNS-naam en HET IP-adres van de SharePoint-serviceserver waar u naar bent doorgestuurd. De informatie wordt alleen verstrekt voor informatie en er is geen netwerkinzicht.

### <a name="microsoft-teams"></a>Microsoft Teams

In deze sectie ziet u testresultaten met betrekking tot Microsoft Teams.

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>Mediaconnectiviteit (audio, video en het delen van toepassingen)

Hiermee wordt getest op UDP-connectiviteit met de microsoft Teams-servicedeuren. Als dit wordt geblokkeerd, werkt Microsoft Teams mogelijk nog steeds met TCP, maar wordt audio en video beperkt. Lees meer over deze UDP-netwerkmetingen die ook van toepassing zijn op Microsoft Teams bij [Media Quality and Network Connectivity Performance in Skype voor Bedrijven Online](/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)

#### <a name="packet-loss"></a>Pakketverlies

Toont het UDP-pakketverlies gemeten in een 10 seconden testaudiogesprek van de client naar de microsoft Teams-servicedeuren. Dit moet lager zijn dan **1,00%** voor een pas.

#### <a name="latency"></a>Latentie

Geeft de gemeten UDP-latentie weer, die lager moet zijn dan **100 ms.**

#### <a name="jitter"></a>Jitter

Toont de gemeten UDP-jitter, die lager moet zijn dan **30 ms.**

#### <a name="connectivity"></a>Connectiviteit

We testen op HTTP-connectiviteit vanaf de kantoorlocatie van de gebruiker naar alle vereiste Microsoft 365-netwerk-eindpunten. Deze worden gepubliceerd op [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md) . Er wordt een netwerkinzicht weergegeven voor alle vereiste netwerk-eindpunten die niet kunnen worden verbonden.

Connectiviteit kan worden geblokkeerd door een proxyserver, een firewall of een ander netwerkbeveiligingsapparaat op de perimeter van het bedrijfsnetwerk. Connectiviteit met TCP-poort 80 wordt getest met een HTTP-aanvraag en de verbinding met TCP-poort 443 wordt getest met een HTTPS-aanvraag. Als er geen antwoord is, is de FQDN gemarkeerd als een fout. Als er een HTTP-antwoordcode 407 is, is de FQDN gemarkeerd als een fout. Als er een HTTP-antwoordcode 403 is, controleren we het serverkenmerk van het antwoord en als het een proxyserver lijkt te zijn, markeren we dit als een fout. U kunt de tests simuleren die we uitvoeren met het windows-opdrachtregelprogramma curl.exe.

We testen het SSL-certificaat bij elk vereist Microsoft 365-netwerk-eindpunt dat zich in de categorie optimaliseren of toestaan, zoals gedefinieerd op [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md) . Als bij tests geen Microsoft SSL-certificaat wordt gevonden, moet het versleutelde netwerk dat is verbonden, zijn onderschept door een tussenliggende netwerkapparaat. Een netwerkinzicht wordt weergegeven op onderschepte versleutelde netwerk-eindpunten.

Als er een SSL-certificaat wordt gevonden dat niet door Microsoft is geleverd, worden de FQDN voor de test en de in gebruik genomen SSL-certificaateigenaar. Deze eigenaar van het SSL-certificaat kan een leverancier van een proxyserver zijn of een zelfgesigneerd bedrijfscertificaat.

#### <a name="network-path"></a>Netwerkpad

In deze sectie ziet u de resultaten van een ICMP-traceroute naar de Exchange Online-servicedeuren, de SharePoint Online-servicedeuren en de microsoft Teams-servicedeuren. De informatie wordt alleen verstrekt voor informatie en er is geen netwerkinzicht. Er zijn drie traceroutes beschikbaar. Een traceroute naar _outlook.office365.com,_ een traceroute naar de klanten SharePoint front end _of naar microsoft.sharepoint.com_ als er geen traceroute is opgegeven en een traceroute naar _world.tr.teams.microsoft.com_.

## <a name="connectivity-reports"></a>Connectiviteitsrapporten

Wanneer u bent aangemeld, kunt u eerdere rapporten bekijken die u hebt uitgevoerd. U kunt ze ook delen of verwijderen uit de lijst.

![Rapporten](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>Status van netwerkstatus

Hier ziet u belangrijke gezondheidsproblemen met het globale netwerk van Microsoft die van invloed kunnen zijn op Microsoft 365-klanten.

![Status van netwerkstatus](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a>Veelgestelde vragen

Hier vindt u antwoorden op enkele veelgestelde vragen.

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>Wordt dit hulpprogramma uitgebracht en ondersteund door Microsoft?

Het is momenteel een voorbeeld en we zijn van plan regelmatig updates te verstrekken totdat we de releasestatus voor algemene beschikbaarheid bereiken met ondersteuning van Microsoft. Geef feedback om ons te helpen ons te verbeteren. We zijn van plan om een gedetailleerdere Office 365 Network Onboarding-handleiding te publiceren als onderdeel van dit hulpprogramma dat door de testresultaten voor de organisatie is aangepast.

### <a name="what-is-required-to-run-the-advanced-test-client"></a>Wat is er nodig om de geavanceerde testclient uit te voeren?

Voor de geavanceerde testclient is .NET Core 3.1 Desktop Runtime vereist. Als u de geavanceerde testclient gebruikt zonder dat deze is geïnstalleerd, wordt u doorgestuurd naar de [installatiepagina .NET Core 3.1.](https://dotnet.microsoft.com/download/dotnet-core/3.1) Installeer de Desktop Runtime en niet de SDK of de ASP.NET Core Runtime die hoger op de pagina staan. Beheerdersmachtigingen op de computer zijn vereist om .NET Core te installeren.

### <a name="what-is-microsoft-365-service-front-door"></a>Wat is microsoft 365 service voor de deur?

De microsoft 365-servicedeuren zijn een toegangspunt op het globale netwerk van Microsoft, waar Office-clients en -services hun netwerkverbinding beëindigen. Voor een optimale netwerkverbinding met Microsoft 365 wordt aangeraden uw netwerkverbinding te beëindigen in de dichtstbijzijnde Microsoft 365-voordeur in uw stad of metro.

Opmerking: De microsoft 365-servicedeuren hebben geen directe relatie met het **Azure Front Door Service-product** dat beschikbaar is in de Azure Marketplace.

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>Wat is de beste microsoft 365-servicedeuren?

Een beste Microsoft 365-servicedeuren (voorheen bekend als een optimale servicedeuren) is er een die het dichtst bij uw netwerk komt, meestal in uw stad of metrogebied. Gebruik het hulpprogramma voor de prestaties van het Microsoft 365-netwerk om de locatie te bepalen van uw in-use Microsoft 365-servicedeuren en de beste servicedeuren. Als het hulpprogramma bepaalt dat uw ingebruikte voordeur een van de beste is, kunt u een goede verbinding met het globale netwerk van Microsoft verwachten.

### <a name="what-is-an-internet-egress-location"></a>Wat is een internetlocatie?

De internetlocatie is de locatie waar uw netwerkverkeer uw bedrijfsnetwerk verlaat en verbinding maakt met internet. Dit wordt ook geïdentificeerd als de locatie waar u een NAT-apparaat (Network Address Translation) hebt en meestal waar u verbinding maakt met een internetprovider . Als u een lange afstand ziet tussen uw locatie en uw internetlocatie, kan hierdoor een significante WAN-backhaul worden gevonden.

## <a name="related-topics"></a>Verwante onderwerpen

[Netwerkconnectiviteit in het Microsoft 365-beheercentrum (preview)](office-365-network-mac-perf-overview.md)

[Inzichten in de prestaties van het Microsoft 365-netwerk (preview)](office-365-network-mac-perf-insights.md)

[Microsoft 365-netwerkbeoordeling (preview)](office-365-network-mac-perf-score.md)

[Microsoft 365 Network Connectivity Location Services (preview)](office-365-network-mac-location-services.md)