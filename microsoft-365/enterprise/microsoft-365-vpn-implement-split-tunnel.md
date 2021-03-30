---
title: Vpn-splits tunneling implementeren voor Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: Vpn-splits tunneling implementeren voor Office 365
ms.openlocfilehash: d676c4bdcb4c3938391b044f4cb2534991278af8
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408577"
---
# <a name="implementing-vpn-split-tunneling-for-office-365"></a>Vpn-splits tunneling implementeren voor Office 365

>[!NOTE]
>Dit onderwerp maakt deel uit van een reeks onderwerpen die betrekking hebben op Office 365-optimalisatie voor externe gebruikers.
>- Zie [Overzicht: VPN split tunneling voor Office 365](microsoft-365-vpn-split-tunnel.md)voor een overzicht van het gebruik van VPN splits tunneling voor het optimaliseren van Office 365-connectiviteit voor externe gebruikers.
>- Zie Prestatieoptimalisatie van [Office 365](microsoft-365-networking-china.md)voor Gebruikers in China voor informatie over het optimaliseren van de prestaties van Office 365 worldwide tenants in China.

Al vele jaren gebruiken ondernemingen VPN's om externe ervaringen voor hun gebruikers te ondersteunen. Hoewel de kernbelasting on-premises bleef, was een VPN van de externe client die via een datacenter in het bedrijfsnetwerk werd gerouteerd, de primaire methode voor externe gebruikers om toegang te krijgen tot bedrijfsresources. Om deze verbindingen te beschermen, bouwen ondernemingen lagen met netwerkbeveiligingsoplossingen langs de VPN-paden. Deze beveiliging is gemaakt om de interne infrastructuur te beschermen en mobiel browsen van externe websites te beschermen door verkeer om te zetten in de VPN en vervolgens via de on-premises internetperimeter. VPN's, netwerkperimeters en bijbehorende beveiligingsinfrastructuur zijn vaak speciaal ontworpen en geschaald voor een gedefinieerde hoeveelheid verkeer, meestal met de meeste connectiviteit die binnen het bedrijfsnetwerk wordt gestart en het grootste deel binnen de interne netwerkgrenzen blijft.

Vpn-modellen waarbij alle verbindingen vanaf het externe gebruikersapparaat terug worden gerouteerd naar het on-premises netwerk (ook wel geforceerd **tunnelen** genoemd) waren lange tijd grotendeels houdbaar, zolang de gelijktijdige schaal van externe gebruikers bescheiden was en de verkeersvolumes voor VPN laag waren.  Sommige klanten blijven VPN-force tunneling gebruiken als status-quo, zelfs nadat hun toepassingen van binnen de bedrijfsperimeter naar openbare SaaS-clouds zijn verplaatst, met Office 365 als een goed voorbeeld.

Het gebruik van geforceerd ge tunnelde VPN's voor het maken van verbinding met gedistribueerde en prestatiegevoelige cloudtoepassingen is suboptimaal, maar het negatieve effect ervan kan door sommige ondernemingen zijn geaccepteerd om de status-status-status te behouden vanuit een beveiligingsperspectief. Hieronder ziet u een voorbeelddiagram van dit scenario:

![SPLIT TUNNEL VPN-configuratie](../media/vpn-split-tunneling/enterprise-network-traditional.png)

Dit probleem neemt al jaren toe, met veel klanten die een aanzienlijke verschuiving van netwerkverkeerspatronen melden. Verkeer dat vroeger on-premises was, maakt nu verbinding met externe cloud-eindpunten. Talloze Microsoft-klanten melden dat voorheen ongeveer 80% van het netwerkverkeer naar een interne bron was (vertegenwoordigd door de stippellijn in het bovenstaande diagram). In 2020 is dat aantal nu ongeveer 20% of lager omdat ze grote werkbelastingen naar de cloud hebben verplaatst, deze trends zijn niet ongebruikelijk in andere ondernemingen. Naarmate de cloud vordert, wordt het bovenstaande model steeds omslachtiger en onhoudbaar, waardoor een organisatie niet agile kan zijn wanneer ze naar een cloud first-wereld gaan.

De wereldwijde COVID-19-crisis heeft dit probleem geëscaleerd om onmiddellijk herstel te vereisen. De noodzaak om de veiligheid van werknemers te waarborgen, heeft een ongeëvenaarde vraag gegenereerd naar IT van ondernemingen om de productiviteit van werk van thuis uit op grote schaal te ondersteunen. Microsoft Office 365 is goed gepositioneerd om klanten te helpen aan die vraag te voldoen, maar een hoge gelijktijdigheid van gebruikers die thuis werken, genereert een groot volume Van Office 365-verkeer dat, als deze wordt gerouteerd via een geforceerd VPN-tunnelnetwerk en on-premises netwerkperimeters, snelle verzadiging veroorzaakt en VPN-infrastructuur zonder capaciteit draait. In deze nieuwe realiteit is het gebruik van VPN voor toegang tot Office 365 niet langer alleen een prestatiebeleed, maar een harde wand die niet alleen van invloed is op Office 365, maar ook op kritieke bedrijfsactiviteiten die nog steeds afhankelijk zijn van de VPN om te kunnen werken.

Microsoft werkt al jaren nauw samen met klanten en de bredere industrie om effectieve, moderne oplossingen te bieden voor deze problemen vanuit onze eigen services en om af te stemmen op de beste praktijken in de branche. [Connectiviteitsprincipes](./microsoft-365-network-connectivity-principles.md) voor de Office 365-service zijn ontworpen om efficiënt te werken voor externe gebruikers, terwijl een organisatie toch de beveiliging en controle over hun connectiviteit kan behouden. Deze oplossingen kunnen ook snel worden geïmplementeerd met beperkte hoeveelheid werk, maar hebben een aanzienlijk positief effect op de hierboven beschreven problemen.

De aanbevolen strategie van Microsoft voor het optimaliseren van de connectiviteit van externe werknemers is gericht op het snel oplossen van de problemen met de traditionele benadering en het leveren van hoge prestaties met een paar eenvoudige stappen. Met deze stappen past u de oudere VPN-benadering aan voor een paar gedefinieerde eindpunten die de bottlenecks van VPN-servers omzeilen. Een gelijkwaardig of zelfs superieur beveiligingsmodel kan op verschillende lagen worden toegepast om de noodzaak te verwijderen om al het verkeer aan het begin van het bedrijfsnetwerk te beveiligen. In de meeste gevallen kan dit effectief binnen enkele uren worden bereikt en kan het vervolgens worden schaalbaar voor andere werkbelastingen, zoals de vraag en tijd van de vereisten toestaat.

## <a name="common-vpn-scenarios"></a>Veelvoorkomende VPN-scenario's

In de onderstaande lijst ziet u de meest voorkomende VPN-scenario's in bedrijfsomgevingen. De meeste klanten werken traditioneel met model 1 (VPN Forced Tunnel). In deze sectie kunt u snel en veilig overstappen op **model 2,** dat met relatief weinig moeite kan worden bereikt en enorme voordelen heeft voor netwerkprestaties en gebruikerservaring.

| Model | Omschrijving |
| --- | --- |
| [1. VPN Geforceerd tunnel](#1-vpn-forced-tunnel) | 100% van het verkeer gaat naar de VPN-tunnel, inclusief on-premises, internet en alle O365/M365 |
| [2. VPN-geforceerd tunnel met enkele uitzonderingen](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | VPN-tunnel wordt standaard gebruikt (standaardroutepunten naar VPN), met weinig, belangrijkste vrijgestelde scenario's die rechtstreeks mogen worden gebruikt |
| [3. VPN-geforceerd tunnel met brede uitzonderingen](#3-vpn-forced-tunnel-with-broad-exceptions) | VPN-tunnel wordt standaard gebruikt (standaard routepunten naar VPN), met brede uitzonderingen die direct mogen gaan (zoals alle Office 365, Alle Salesforce, Alle zoomen) |
| [4. Vpn Selective Tunnel](#4-vpn-selective-tunnel) | VPN-tunnel wordt alleen gebruikt voor op corpnet gebaseerde services. Standaardroute (internet en alle internetservices) gaat rechtstreeks. |
| [5. Geen VPN](#5-no-vpn) | Een variatie van #2, waarbij in plaats van oudere VPN alle corpnetservices worden gepubliceerd via moderne beveiligingsmethoden (zoals Zscaler ZPA, Azure Active Directory (Azure AD) Proxy/MCAS, enz.) |

### <a name="1-vpn-forced-tunnel"></a>1. VPN Geforceerd tunnel

Dit is het meest voorkomende beginscenario voor de meeste zakelijke klanten. Er wordt een gedwongen VPN gebruikt, wat betekent dat 100% van het verkeer naar het bedrijfsnetwerk wordt doorgestuurd, ongeacht het feit dat het eindpunt zich al dan niet binnen het bedrijfsnetwerk bevindt. Extern (internet) afhankelijk verkeer, zoals Office 365 of surfen op internet, wordt vervolgens weer uit de on-premises beveiligingsapparatuur vastgemaakt, zoals proxies. In het huidige klimaat met bijna 100% van de gebruikers die op afstand werken, wordt de VPN-infrastructuur hierdoor belast door dit model en is het waarschijnlijk dat de prestaties van al het bedrijfsverkeer en dus de onderneming in tijden van crisis aanzienlijk worden gehinderd.

![VPN Geforceerd tunnelmodel 1](../media/vpn-split-tunneling/vpn-model-1.png)

### <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. VPN-geforceerd tunnel met een klein aantal vertrouwde uitzonderingen

Dit model is aanzienlijk efficiënter voor een onderneming om onder te werken, omdat het een paar gecontroleerde en gedefinieerde eindpunten toestaat die zeer hoge belasting en latentiegevoelig zijn om de VPN-tunnel te omzeilen en rechtstreeks naar de Office 365-service te gaan in dit voorbeeld. Hierdoor worden de prestaties voor de offloaded services aanzienlijk verbeterd en wordt ook de belasting van de VPN-infrastructuur verminderd, waardoor elementen waarvoor de service nog steeds moet worden gebruikt, minder worden belast voor resources. Dit model richt zich in dit artikel op het helpen bij de overgang naar, omdat eenvoudige, gedefinieerde acties snel kunnen worden ondernomen met talloze positieve resultaten.

![VPN-model voor gesplitste tunnel 2](../media/vpn-split-tunneling/vpn-model-2.png)

### <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. VPN-geforceerd tunnel met brede uitzonderingen

Het derde model verbreed het bereik van model twee als in plaats van alleen een kleine groep gedefinieerde eindpunten rechtstreeks te verzenden, maar in plaats daarvan wordt al het verkeer rechtstreeks naar vertrouwde services zoals Office 365 en SalesForce verzonden. Hierdoor wordt de belasting van de BEDRIJFS VPN-infrastructuur verder beperkt en worden de prestaties van de gedefinieerde services verbeterd. Aangezien het waarschijnlijk meer tijd zal duren om de haalbaarheid van dit model te beoordelen en uit te voeren, is het waarschijnlijk een stap die op een later tijdstip iteratief kan worden uitgevoerd nadat model twee is geïmplementeerd.

![SPLIT TUNNEL VPN-model 3](../media/vpn-split-tunneling/vpn-model-3.png)

### <a name="4-vpn-selective-tunnel"></a>4. VPN selectieve tunnel

Met dit model wordt het derde model omgekeerd, omdat alleen verkeer dat is geïdentificeerd als het hebben van een bedrijfs-IP-adres, in de VPN-tunnel wordt verzonden en het internetpad dus de standaardroute is voor al het andere. Voor dit model moet een organisatie goed op weg zijn naar [Zero Trust](https://www.microsoft.com/security/zero-trust?rtc=1) om dit model veilig te kunnen implementeren. Opgemerkt moet worden dat dit model of een bepaalde variatie daarvan waarschijnlijk de vereiste standaard wordt naarmate meer en meer services zich van het bedrijfsnetwerk naar de cloud verplaatsen. Microsoft gebruikt dit model intern. u vindt meer informatie over de implementatie van vpn-splits tunneling door Microsoft bij Lopen [op VPN:](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)Hoe Microsoft het externe personeel verbonden houdt.

![VPN-model voor gesplitste tunnel 4](../media/vpn-split-tunneling/vpn-model-4.png)

### <a name="5-no-vpn"></a>5. Geen VPN

Een meer geavanceerde versie van model nummer twee, waarbij interne services worden gepubliceerd via een moderne beveiligingsbenadering of SDWAN-oplossing, zoals Azure AD Proxy, MCAS, Zscaler ZPA, enzovoort.

![SPLIT TUNNEL VPN-model 5](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="implement-vpn-split-tunneling"></a>VPN splits tunneling implementeren

In deze sectie vindt u de eenvoudige stappen die nodig zijn om uw VPN-clientarchitectuur te migreren van een VPN-geforceerd _tunnel_ naar een VPN-geforceerd _tunnel_ met een klein aantal vertrouwde uitzonderingen [, VPN-gesplitste tunnelmodel #2](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) in veelgebruikte VPN-scenario's. [](#common-vpn-scenarios)

In het onderstaande diagram ziet u hoe de aanbevolen VPN-oplossing voor gesplitste tunnel werkt:

![Split tunnel VPN-oplossingsdetails](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

### <a name="1-identify-the-endpoints-to-optimize"></a>1. Identificeer de eindpunten die moeten worden geoptimaliseerd

In het onderwerp URL's en IP-adresbereiken van [Office 365](urls-and-ip-address-ranges.md) identificeert Microsoft duidelijk de belangrijkste eindpunten die u nodig hebt om ze te optimaliseren en te categoriseren als **Optimaliseren.** Er zijn momenteel slechts vier URL's en 20 IP-subnetten die moeten worden geoptimaliseerd. Deze kleine groep eindpunten is goed voor ongeveer 70% - 80% van het volume van het verkeer naar de Office 365-service, inclusief de latentiegevoelige eindpunten, zoals die voor Teams-media. Dit is in feite het verkeer waar we speciaal voor moeten zorgen en is ook het verkeer dat enorme druk zal uitoefenen op traditionele netwerkpaden en VPN-infrastructuur.

URL's in deze categorie hebben de volgende kenmerken:

- Zijn Microsoft-eindpunten die eigendom zijn van En beheerd, gehost op Microsoft-infrastructuur
- IPs beschikbaar hebben
- Lage veranderingssnelheid en zal naar verwachting klein blijven (momenteel 20 IP-subnetten)
- Bandbreedte en/of latentiegevoelig zijn
- Kunnen vereiste beveiligingselementen in de service hebben in plaats van inline op het netwerk
- Goed voor ongeveer 70-80% van het volume van het verkeer naar de Office 365-service

Zie het artikel Office 365-eindpunten beheren voor meer informatie over Office [365-eindpunten](managing-office-365-endpoints.md)en hoe ze worden gecategoriseerd en beheerd.

#### <a name="optimize-urls"></a>URL's optimaliseren

De huidige URL's optimaliseren vindt u in de onderstaande tabel. In de meeste gevallen hoeft u alleen URL-eindpunten te gebruiken in een [PAC-bestand](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic) in een browser waarin de eindpunten zijn geconfigureerd om rechtstreeks te worden verzonden, in plaats van naar de proxy.

| URL's optimaliseren | Poort/protocol | Doel |
| --- | --- | --- |
| <https://outlook.office365.com> | TCP 443 | Dit is een van de primaire URL's die Outlook gebruikt om verbinding te maken met de Exchange Online-server en heeft een hoog bandbreedtegebruik en een hoog aantal verbindingen. Lage netwerklatentie is vereist voor onlinefuncties, zoals: direct zoeken, andere postvakagenda's, gratis /bezet zoeken, regels en waarschuwingen beheren, Onlinearchief van Exchange, e-mailberichten die het postvak uit gaan. |
| <https://outlook.office.com> | TCP 443 | Deze URL wordt gebruikt voor Outlook Online Web Access om verbinding te maken met Exchange Online-server en is gevoelig voor netwerklatentie. Connectiviteit is met name vereist voor het uploaden en downloaden van grote bestanden met SharePoint Online. |
| https:// \<tenant\> .sharepoint.com | TCP 443 | Dit is de primaire URL voor SharePoint Online en heeft een hoge bandbreedte. |
| https:// \<tenant\> -my.sharepoint.com | TCP 443 | Dit is de primaire URL voor OneDrive voor Bedrijven en heeft een hoog bandbreedtegebruik en mogelijk een hoog aantal verbindingen van het hulpprogramma Synchronisatie van OneDrive voor Bedrijven. |
| Teams Media-IPs (geen URL) | UDP 3478, 3479, 3480 en 3481 | Toewijzing van detectie door relay en realtimeverkeer (3478), Audio (3479), Video (3480) en Videoscherm delen (3481). Dit zijn de eindpunten die worden gebruikt voor Skype voor Bedrijven en Microsoft Teams Mediaverkeer (gesprekken, vergaderingen, enzovoort). De meeste eindpunten worden geleverd wanneer de Microsoft Teams-client een oproep start (en zijn opgenomen in de vereiste IPs die voor de service worden vermeld). Gebruik van het UDP-protocol is vereist voor optimale mediakwaliteit.   |

In de bovenstaande voorbeelden moet **tenant** worden vervangen door uw Office 365-tenantnaam. U kunt **bijvoorbeeld contoso.onmicrosoft.com** gebruiken  contoso.sharepoint.com en _constoso-my.sharepoint.com._

#### <a name="optimize-ip-address-ranges"></a>IP-adresbereiken optimaliseren

Op het moment van schrijven zijn de IP-bereiken waar deze eindpunten mee corresponderen als volgt. Het **wordt** ten zeerste aangeraden een [script](https://github.com/microsoft/Office365NetworkTools/tree/master/Scripts/Display%20URL-IPs-Ports%20per%20Category) te gebruiken, zoals dit voorbeeld, de Webservice IP en URL van [Office 365](microsoft-365-ip-web-service.md) of de [URL/IP-pagina](urls-and-ip-address-ranges.md) om te controleren of er updates zijn bij het toepassen van de configuratie en om regelmatig een beleid in te stellen om dit te doen.

```
104.146.128.0/17
13.107.128.0/22
13.107.136.0/22
13.107.18.10/31
13.107.6.152/31
13.107.64.0/18
131.253.33.215/32
132.245.0.0/16
150.171.32.0/22
150.171.40.0/22
191.234.140.0/22
204.79.197.215/32
23.103.160.0/20
40.104.0.0/15
40.108.128.0/17
40.96.0.0/13
52.104.0.0/14
52.112.0.0/14
52.96.0.0/14
52.120.0.0/14
```

### <a name="2-optimize-access-to-these-endpoints-via-the-vpn"></a>2. De toegang tot deze eindpunten optimaliseren via de VPN

Nu we deze kritieke eindpunten hebben geïdentificeerd, moeten we ze afleiden van de VPN-tunnel en toestaan dat ze de lokale internetverbinding van de gebruiker gebruiken om rechtstreeks verbinding te maken met de service. De manier waarop dit wordt uitgevoerd, is afhankelijk van het gebruikte VPN-product- en machineplatform, maar met de meeste VPN-oplossingen kan deze logica eenvoudig worden toegepast. Zie HOWTO-handleidingen voor veelgebruikte [VPN-platforms](#howto-guides-for-common-vpn-platforms)voor informatie over VPN-platformspecifieke instructies voor gesplitste tunnel.

Als u de oplossing handmatig wilt testen, kunt u het volgende PowerShell-voorbeeld uitvoeren om de oplossing op het niveau van de routetabel te emuleren. In dit voorbeeld wordt een route voor elk van de IP-subnetten van Teams Media toegevoegd aan de routetabel. U kunt de mediaprestaties van Teams voor en na testen en het verschil in routes voor de opgegeven eindpunten zien.

#### <a name="example-add-teams-media-ip-subnets-into-the-route-table"></a>Voorbeeld: Teams Media IP-subnetten toevoegen aan de routetabel

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18" # Teams Media endpoints
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

In het bovenstaande script _is $intIndex_ de index van de interface die is verbonden met internet (zoeken door **get-netadapter** uit te voeren in PowerShell; de waarde van _ifIndex_ zoeken) en _$gateway_ is de standaardgateway van die interface (zoeken door **ipconfig** uit te voeren in een opdrachtprompt of **(Get-NetIPConfiguration | Foreach IPv4DefaultGateway). NextHop** in PowerShell).

Nadat u de routes hebt toegevoegd, kunt u bevestigen dat de routetabel juist is door **routeafdruk** uit te voeren in een opdrachtprompt of PowerShell. De uitvoer moet de routes bevatten die u hebt toegevoegd, met de interface-index _(22_ in dit voorbeeld) en de gateway voor die interface (_192.168.1.1_ in dit voorbeeld):

![Afdrukuitvoer route](../media/vpn-split-tunneling/vpn-route-print.png)

Als u  routes wilt toevoegen voor alle huidige IP-adresbereiken in de categorie Optimaliseren, kunt u de volgende scriptvariatie gebruiken om een query uit te voeren op de [Office 365 IP- en URL-webservice](microsoft-365-ip-web-service.md) voor de huidige set IP-subnetten optimaliseren en deze toevoegen aan de routetabel.

#### <a name="example-add-all-optimize-subnets-into-the-route-table"></a>Voorbeeld: Alle subnetten optimaliseren toevoegen aan de routetabel

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
# Query the web service for IPs in the Optimize category
$ep = Invoke-RestMethod ("https://endpoints.office.com/endpoints/worldwide?clientrequestid=" + ([GUID]::NewGuid()).Guid)
# Output only IPv4 Optimize IPs to $optimizeIps
$destPrefix = $ep | where {$_.category -eq "Optimize"} | Select-Object -ExpandProperty ips | Where-Object { $_ -like '*.*' }
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

Als u per ongeluk routes met onjuiste parameters hebt toegevoegd of alleen de wijzigingen wilt terugdraaien, kunt u de routes verwijderen die u zojuist hebt toegevoegd met de volgende opdracht:

```powershell
foreach ($prefix in $destPrefix) {Remove-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

<!--- remmed until we add more reliable interface selection logic
#### Example script to add Teams Media subnets to the route table

```powershell
$adapter = get-netadapter | ? {$_.Status -eq "Up"}
$adapterIndex = $adapter.ifIndex
$gateway = (Get-NetIPConfiguration | Foreach IPv4DefaultGateway).NextHop

$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18"
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```
-->

De VPN-client moet zo zijn geconfigureerd dat het verkeer naar de **IPs** optimaliseren op deze manier wordt gerouteerd. Hierdoor kan het verkeer gebruikmaken van lokale Microsoft-bronnen, zoals Office 365 Service Front Doors, zoals de [Azure Front Door](https://azure.microsoft.com/blog/azure-front-door-service-is-now-generally-available/) die Office 365-services en connectiviteits-eindpunten zo dicht mogelijk bij uw gebruikers levert. Hierdoor kunnen we hoge prestatieniveaus leveren aan gebruikers waar ze ook ter wereld zijn en profiteren we optimaal van het wereldwijde netwerk van [Microsoft](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)van wereldklasse, dat waarschijnlijk binnen enkele milliseconden na het directe egressie van uw gebruikers is.

## <a name="configuring-and-securing-teams-media-traffic"></a>Teams-mediaverkeer configureren en beveiligen

Sommige beheerders hebben mogelijk meer gedetailleerde informatie nodig over de werking van oproepstromen in Teams met behulp van een gesplitst tunnelingsmodel en hoe verbindingen worden beveiligd.

### <a name="configuration"></a>Configuratie

Zolang de vereiste IP-subnetten optimaliseren voor Teams-media correct zijn geplaatst in de routetabel, wordt in Teams de functie [GetBestRoute](/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute) gebeld om te bepalen welke lokale interface overeenkomt met de route die het moet gebruiken voor een bepaalde bestemming, de lokale interface wordt geretourneerd voor Microsoft-bestemmingen in de bovenstaande Microsoft IP-blokken.

Sommige VPN-clientsoftware maakt routeringsmanipulatie mogelijk op basis van URL. Er is echter geen URL voor Teams-mediaverkeer aan gekoppeld, dus de besturing van routering voor dit verkeer moet worden uitgevoerd met IP-subnetten.

In bepaalde scenario's, die vaak niet gerelateerd zijn aan de configuratie van de Teams-client, doorkruist mediaverkeer nog steeds de VPN-tunnel, zelfs met de juiste routes. Als u dit scenario tegenkomt, moet u een firewallregel gebruiken om te voorkomen dat de TEAMS IP-subnetten of poorten de VPN gebruiken.

>[!IMPORTANT]
>Als u ervoor wilt zorgen dat Teams-mediaverkeer via de gewenste methode wordt gerouteerd in alle VPN-scenario's, moet u ervoor zorgen dat gebruikers Microsoft Teams-clientversie **1.3.00.13565** of hoger uitvoeren. Deze versie bevat verbeteringen in de manier waarop de client beschikbare netwerkpaden detecteert.

Signaleringsverkeer wordt uitgevoerd via HTTPS en is niet zo latentiegevoelig als het mediaverkeer en is gemarkeerd als Toestaan **in** de URL/IP-gegevens en kan zo nodig veilig via de VPN-client worden gerouteerd.

### <a name="security"></a>Beveiliging

Een veelvoorkomende reden voor het vermijden van gesplitste tunnels is dat het minder veilig is om dit te doen, dat wil zeggen Alle verkeer dat niet door de VPN-tunnel gaat, heeft geen baat bij het versleutelingsschema dat wordt toegepast op de VPN-tunnel en is daarom minder veilig.

Het belangrijkste tegenargument hiervoor is dat mediaverkeer al is versleuteld via _Secure Real-Time Transport Protocol (SRTP),_ een profiel van Real-Time Transport Protocol (RTP) dat vertrouwelijkheid, verificatie en replay-aanvalsbeveiliging biedt voor RTP-verkeer. SRTP zelf is afhankelijk van een willekeurig gegenereerde sessiesleutel, die wordt uitgewisseld via het beveiligde TLS-signaleringskanaal. Dit wordt uitgebreid besproken [](/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online)in deze beveiligingshandleiding, maar het primaire gedeelte van belang is mediaversleuteling.

Mediaverkeer wordt versleuteld met SRTP, waarbij een sessiesleutel wordt gebruikt die wordt gegenereerd door een veilige generator voor willekeurige getallen en die wordt uitgewisseld via het TLS-kanaal voor signalering. Daarnaast worden media die in beide richtingen tussen de Mediation Server en de interne volgende hop stromen, ook versleuteld met SRTP.

Skype voor Bedrijven Online genereert gebruikersnaam/wachtwoorden voor veilige toegang tot media-relays via _Traversal Using Relays around NAT (TURN)_. Media relays exchange the username/password over a TLS-secured SIP channel. Het is vermeldenswaard dat hoewel een VPN-tunnel kan worden gebruikt om de client te verbinden met het bedrijfsnetwerk, het verkeer nog steeds moet stromen in het SRTP-formulier wanneer het het bedrijfsnetwerk verlaat om de service te bereiken.

Informatie over de manier waarop Teams veelvoorkomende beveiligingsproblemen beperkt, zoals spraak- of _Session Traversal Utilities voor NAT-amplificatieaanvallen (STUN),_ vindt u in [5.1](/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c)Beveiligingsoverwegingen voor implementers.

U kunt ook lezen over moderne beveiligingsbesturingselementen in scenario's voor extern werk op Alternatieve manieren voor beveiligingsprofessionals en IT om moderne beveiligingsbesturingselementen te bereiken in de unieke scenario's voor extern werk van vandaag [(Microsoft Security Team blog)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

## <a name="testing"></a>Testen

Zodra het beleid is aan de orde, moet u bevestigen dat het werkt zoals verwacht. Er zijn meerdere manieren om het pad correct te testen en de lokale internetverbinding te gebruiken:

- Voer de [Microsoft 365-connectiviteitstest](https://aka.ms/netonboard) uit die connectiviteitstests voor u zal uitvoeren, inclusief trace routes zoals hierboven. We voegen ook VPN-tests toe aan deze hulpprogramma's die ook extra inzichten moeten bieden.

- Een eenvoudige tracert naar een eindpunt binnen het bereik van de gesplitste tunnel moet het pad laten zien dat is genomen, bijvoorbeeld:

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  U ziet dan een pad via de lokale internetprovider naar dit eindpunt dat moet worden opgelost naar een IP in de Teams-bereiken die we hebben geconfigureerd voor gesplitste tunneling.

- Maak een netwerkopname met een hulpprogramma zoals Wireshark. Filter tijdens een gesprek op UDP en u ziet verkeer dat naar een IP loopt in het bereik Teams **optimaliseren.** Als de VPN-tunnel voor dit verkeer wordt gebruikt, is het mediaverkeer niet zichtbaar in de trace.

### <a name="additional-support-logs"></a>Aanvullende ondersteuningslogboeken

Als u meer gegevens nodig hebt om problemen op te lossen of hulp nodig hebt bij Microsoft-ondersteuning, kunt u sneller een oplossing vinden door de volgende informatie te verkrijgen. De op **TSS Windows CMD gebaseerde universele troubleShooting Script-hulpprogramma's** van Microsoft ondersteuning kunnen u helpen om de relevante logboeken op een eenvoudige manier te verzamelen. Het hulpprogramma en de instructies voor gebruik vindt u op <https://aka.ms/TssTools.>

## <a name="howto-guides-for-common-vpn-platforms"></a>HOWTO-handleidingen voor veelgebruikte VPN-platforms

In deze sectie vindt u koppelingen naar gedetailleerde handleidingen voor het implementeren van gesplitste tunneling voor Office 365-verkeer van de meest voorkomende partners in deze ruimte. We voegen extra handleidingen toe zodra deze beschikbaar zijn.

- **Windows 10 VPN-client:** Office 365-verkeer optimaliseren voor [externe werknemers met de native Windows 10 VPN-client](/windows/security/identity-protection/vpn/vpn-office-365-optimization)
- **Cisco Anyconnect**: [Anyconnect Split Tunnel optimaliseren voor Office365](https://www.cisco.com/c/en/us/support/docs/security/anyconnect-secure-mobility-client/215343-optimize-anyconnect-split-tunnel-for-off.html)
- **Palo Alto GlobalProtect:** [Office 365-verkeer](https://live.paloaltonetworks.com/t5/Prisma-Access-Articles/GlobalProtect-Optimizing-Office-365-Traffic/ta-p/319669) optimaliseren via VPN Split Tunnel Exclude Access Route
- **F5 Networks BIG-IP APM**: [Office 365-verkeer](https://devcentral.f5.com/s/articles/SSL-VPN-Split-Tunneling-and-Office-365) optimaliseren op externe toegang via VPN's bij het gebruik van BIG-IP APM
- **Citrix Gateway:** [Citrix Gateway VPN splits tunnel optimaliseren voor Office365](https://docs.citrix.com/en-us/citrix-gateway/13/optimizing-citrix-gateway-vpn-split-tunnel-for-office365.html)
- **Pulse Secure:** [VPN-tunneling: Split Tunneling configureren om Office365-toepassingen](https://kb.pulsesecure.net/articles/Pulse_Secure_Article/KB44417) uit te sluiten
- **Check Point VPN:** [Split Tunnel configureren voor Office 365 en andere SaaS-toepassingen](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk167000)

## <a name="faq"></a>Veelgestelde vragen

Het Microsoft-beveiligingsteam [](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) heeft een artikel gepubliceerd met een overzicht van belangrijke manieren voor beveiligingsprofessionals en IT kan moderne beveiligingsbesturingselementen bereiken in de unieke scenario's voor extern werk van vandaag. Daarnaast vindt u hieronder enkele veelvoorkomende vragen en antwoorden van klanten over dit onderwerp.

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>Hoe kan ik voorkomen dat gebruikers toegang krijgen tot andere tenants die ik niet vertrouw waar ze gegevens kunnen uitfiltreren?

Het antwoord is een [functie met de naam tenantbeperkingen.](/azure/active-directory/manage-apps/tenant-restrictions) Verificatieverkeer is niet hoog volume of vooral latentiegevoelig, dus kan via de VPN-oplossing worden verzonden naar de on-premises proxy waar de functie wordt toegepast. Een lijst met vertrouwde tenants wordt hier bewaard en als de client een token probeert te verkrijgen voor een tenant die niet wordt vertrouwd, wordt de aanvraag door de proxy gewoon niet toegestaan. Als de tenant wordt vertrouwd, is een token toegankelijk als de gebruiker de juiste referenties en rechten heeft.

Dus hoewel een gebruiker een TCP/UDP-verbinding kan maken met de bovenstaande gemarkeerde eindpunten optimaliseren, zonder een geldig token om toegang te krijgen tot de tenant in kwestie, kunnen ze zich niet aanmelden en geen gegevens openen of verplaatsen.

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>Biedt dit model toegang tot consumentenservices, zoals persoonlijke OneDrive-accounts?

Nee, dat doet het niet, de Office 365-eindpunten zijn niet hetzelfde als de consumentenservices (Onedrive.live.com als voorbeeld), dus in de gesplitste tunnel kan een gebruiker niet rechtstreeks toegang krijgen tot consumentenservices. Verkeer naar consumenten-eindpunten blijft gebruikmaken van de VPN-tunnel en bestaand beleid blijft van toepassing.

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>Hoe kan ik DLP toepassen en mijn gevoelige gegevens beveiligen wanneer het verkeer niet meer door mijn on-premises oplossing loopt?

Office 365 beschikt over een uitgebreide set [ingebouwde hulpprogramma's](../compliance/data-loss-prevention-policies.md)om onbedoelde openbaarmaking van gevoelige informatie te voorkomen. U kunt de ingebouwde [DLP-mogelijkheden](../compliance/data-loss-prevention-policies.md) van Teams en SharePoint gebruiken om ongepast opgeslagen of gedeelde gevoelige informatie te detecteren. Als een deel van uw strategie voor extern werk een BYOD-beleid (Bring Your Own Device) inhoudt, kunt u Voorwaardelijke toegang op basis van [apps](/azure/active-directory/conditional-access/app-based-conditional-access) gebruiken om te voorkomen dat gevoelige gegevens worden gedownload naar persoonlijke apparaten van gebruikers

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>Hoe evalueer en behoudt ik de controle over de verificatie van de gebruiker wanneer ze rechtstreeks verbinding maken?

Naast de functie tenantbeperkingen die in Q1 wordt [vermeld,](/azure/active-directory/conditional-access/overview) kunnen beleidsregels voor voorwaardelijke toegang worden toegepast om het risico van een verificatieaanvraag dynamisch te beoordelen en op de juiste manier te reageren. Microsoft raadt aan dat het [Zero Trust-model](https://www.microsoft.com/security/zero-trust?rtc=1) in de tijd wordt geïmplementeerd en we kunnen Beleid voor voorwaardelijke toegang van Azure AD gebruiken om de controle te behouden in een mobiele en cloud-first wereld. Beleid voor voorwaardelijke toegang kan worden gebruikt om in realtime te bepalen of een verificatieaanvraag succesvol is op basis van een groot aantal factoren, zoals:

- Apparaat, is het apparaat bekend/vertrouwd/Domein samengevoegd?
- IP: is de verificatieaanvraag afkomstig van een bekend IP-adres van het bedrijf? Of uit een land dat we niet vertrouwen?
- Toepassing: is de gebruiker gemachtigd om deze toepassing te gebruiken?

Vervolgens kunnen we beleid activeren, zoals goedkeuren, MFA activeren of verificatie blokkeren op basis van dit beleid.

### <a name="how-do-i-protect-against-viruses-and-malware"></a>Hoe bescherm ik me tegen virussen en malware?

Nogmaals, Office 365 biedt bescherming voor de gemarkeerde eindpunten optimaliseren in verschillende lagen in de service zelf, die [in dit document worden beschreven.](/office365/Enterprise/office-365-malware-and-ransomware-protection) Zoals vermeld, is het veel efficiënter om deze beveiligingselementen in de service zelf te leveren in plaats van te proberen dit te doen in overeenstemming met apparaten die mogelijk niet volledig inzicht hebben in de protocollen/het verkeer. Standaard worden in SharePoint Online [automatisch bestands uploads gescand](../security/office-365-security/virus-detection-in-spo.md) op bekende malware

Voor de bovenstaande Exchange-eindpunten zijn [Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) en Microsoft Defender voor Office [365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) uitstekend geschikt voor het bieden van beveiliging van het verkeer naar de service.

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>Kan ik meer verzenden dan alleen het direct verkeer optimaliseren?

Prioriteit moet worden gegeven aan de **gemarkeerde** eindpunten optimaliseren, omdat deze maximale voordelen bieden voor een laag werkniveau. Als u echter wilt, zijn de gemarkeerde eindpunten toestaan vereist om de service te laten werken en zijn IP-adressen beschikbaar voor de eindpunten die indien nodig kunnen worden gebruikt.

Er zijn ook verschillende leveranciers die cloudgebaseerde proxy-/beveiligingsoplossingen bieden, veilige _webgateways,_ die centrale beveiligings-, beheer- en bedrijfsbeleidstoepassing bieden voor algemene webnavigatie. Deze oplossingen kunnen goed werken in een eerste wereld in de cloud, als deze zeer beschikbaar, performant en ingericht zijn in de buurt van uw gebruikers, doordat beveiligde internettoegang kan worden geleverd vanaf een cloudlocatie dicht bij de gebruiker. Hierdoor is er geen haarspeld meer nodig via het VPN-/bedrijfsnetwerk voor algemeen browseverkeer, maar is er nog steeds centrale beveiligingscontrole mogelijk.

Zelfs als deze oplossingen zijn gebruikt, wordt microsoft nog steeds ten zeerste aangeraden gemarkeerd Office 365-verkeer rechtstreeks naar de service te sturen.

Zie het artikel Extern werk met [Azure VPN Gateway Point-to-site](/azure/vpn-gateway/work-remotely-support)voor informatie over het toestaan van directe toegang tot een Azure Virtual Network.

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>Waarom is poort 80 vereist? Wordt het verkeer verzonden in de fout?

Poort 80 wordt alleen gebruikt voor zaken zoals omleiden naar een poort 443-sessie, er worden geen klantgegevens verzonden of zijn toegankelijk via poort 80. [Versleuteling](../compliance/encryption.md) bevat een overzicht van versleuteling voor gegevens die onderweg en in rust worden gebruikt voor Office 365, en Type [verkeer](/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic) beschrijft hoe we SRTP gebruiken om Teams-mediaverkeer te beschermen.

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-office-365"></a>Is dit advies van toepassing op gebruikers in China die een wereldwijd exemplaar van Office 365 gebruiken?

**Nee,** dat doet het niet. De enige waarschuwing voor het bovenstaande advies is gebruikers in de Volksrepubliek China die verbinding maken met een wereldwijd exemplaar van Office 365. Als gevolg van de veelvoorkomende congestie van het grensoverschrijdende netwerk in de regio, kunnen de prestaties van direct internet-uitgang variabel zijn. De meeste klanten in de regio werken met een VPN om het verkeer naar het bedrijfsnetwerk te brengen en hun geautoriseerde MPLS-circuit te gebruiken of vergelijkbaar met het verlaten van buiten het land via een geoptimaliseerd pad. Dit wordt verder beschreven in het artikel [Office 365 performance optimization for China users](microsoft-365-networking-china.md).

### <a name="does-split-tunnel-configuration-work-for-teams-running-in-a-browser"></a>Werkt de configuratie van gesplitste tunnel voor Teams die in een browser wordt uitgevoerd?

Ja, via ondersteunde browsers, die worden weergegeven in [Get clients voor Microsoft Teams.](https://docs.microsoft.com/microsoftteams/get-clients#web-client)

## <a name="related-topics"></a>Verwante onderwerpen

[Overzicht: VPN splits tunneling voor Office 365](microsoft-365-vpn-split-tunnel.md)

[Office 365 performance optimization for China users](microsoft-365-networking-china.md)

[Alternatieve manieren voor beveiligingsprofessionals en IT om moderne beveiligingsbesturingselementen te bereiken in de unieke scenario's voor extern werk van vandaag (Microsoft Security Team-blog)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[De PRESTATIES van VPN bij Microsoft verbeteren: Vpn-profielen van Windows 10 gebruiken om automatische verbindingen toe te staan](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Werken met VPN: hoe Microsoft zijn externe werknemers verbonden houdt](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Beginselen voor Office 365-netwerkverbinding](microsoft-365-network-connectivity-principles.md)

[Office 365-netwerkverbinding beoordelen](assessing-network-connectivity.md)

[Aanpassing van Office 365-netwerk en -prestaties](network-planning-and-performance.md)
