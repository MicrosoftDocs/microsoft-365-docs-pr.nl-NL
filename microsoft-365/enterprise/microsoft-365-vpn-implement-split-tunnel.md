---
title: Gesplitste VPN-tunneling implementeren voor Office 365
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
description: Gesplitste tunneling voor VPN implementeren voor Office 365
ms.openlocfilehash: 4a7c2a18ae5d4f275210ddeaea90eb1bb9bc1f16
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846986"
---
# <a name="implementing-vpn-split-tunneling-for-office-365"></a>Gesplitste VPN-tunneling implementeren voor Office 365

>[!NOTE]
>Dit onderwerp maakt deel uit van een reeks onderwerpen waarmee u Office 365 optimaliseren voor externe gebruikers.
>- Voor een overzicht van het gebruik van gesplitste tunneling via VPN voor het optimaliseren van Office 365-connectiviteit voor externe gebruikers raadpleegt u [overzicht: VPN-splitsings tunneling voor Office 365](microsoft-365-vpn-split-tunnel.md).
>- Voor informatie over het optimaliseren van de prestaties van Office 365 wereldwijd voor gebruikers in China, raadpleegt u [office 365 optimaliseren voor gebruikers van China](microsoft-365-networking-china.md).

Gedurende een groot aantal jaren hebben bedrijven een VPN gebruikt voor de ondersteuning van externe ervaringen voor hun gebruikers. Hoewel kern lasten on-premises bleven, was een VPN van de externe client die via een datacenter op het bedrijfsnetwerk is gerouteerd de primaire methode voor externe gebruikers om toegang te krijgen tot de bedrijfsbronnen. Om deze verbindingen te beschermen, bouwen ondernemingen lagen van netwerkbeveiligings oplossingen langs de VPN-paden. Dit is de bescherming van de interne infrastructuur en het veilig surfen van externe websites door verkeer om te leiden naar het VPN en vervolgens via het on-premises Internet perimeter. Vpn's, netwerkverkeer en bijbehorende beveiligingsinfrastructuur waren vaak gebouwd en geschaald voor een bepaald volume van het verkeer, meestal met het merendeel van de verbinding vanaf het bedrijfsnetwerk, en het grootste deel van de verbinding binnen de interne netwerk grenzen.

Voor zeer enige tijd worden VPN-modellen waarbij alle verbindingen van het externe gebruikersapparaat worden gerouteerd naar het on-premises netwerk (bekend als **geforceerde tunneling** ), veel duurzaam, aangezien de gelijktijdig gebruikte schaal van de VPN-verbinding laag was.  Sommige klanten blijven gebruikmaken van VPN-geforceerde tunneling als status-quo, zelfs nadat hun toepassingen binnen het bedrijfsnetwerk zijn verplaatst naar openbare SaaS-wolken, Office 365 in een prime voorbeeld.

Het gebruik van geforceerde verbonden Vpn's voor het maken van een verbinding met de Distributed-en prestatie gevoelige Cloud toepassingen is zeer geschikt, maar de negatieve gevolgen van die van sommige ondernemingen zijn voor het behoud van de status quo van een beveiligings perspectief. Hieronder ziet u een voorbeeld van een diagram van dit scenario:

![VPN-configuratie voor gesplitste tunnel](../media/vpn-split-tunneling/enterprise-network-traditional.png)

Dit probleem is opgetreden gedurende een groot aantal jaren, met veel klanten die een noemenswaardige ploeg van de netwerk verkeerspatronen rapporteren. Verkeer dat wordt gebruikt om on-premises te blijven, maakt nu verbinding met externe Cloud eindpunten. Een groot aantal Microsoft-klanten rapporten is, rondom 80% van het netwerkverkeer tot een aantal interne bronnen (aangeduid met de stippellijn in het bovenstaande diagram). In 2020 is dit cijfer rondom 20% of lager, omdat ze grote belastingen op de Cloud hebben afgewerkt, dan zijn deze trends niet ongebruikelijk met andere ondernemingen. Na verloop van tijd, wanneer de Cloud reis vordert, wordt het bovenstaande model steeds lastig en onduurzaam geworden, zodat een organisatie geen Agile kan zijn omdat ze in een cloud van de eerste wereld overstappen.

De wereldwijde COVID-19 crisis heeft dit probleem al voorgedaan. U dient ervoor te zorgen dat de veiligheid van de werknemers ongeëvenaarde vragen voor Enterprise biedt om de productiviteit van de werkstroom te ondersteunen. Microsoft Office 365 is ook geschikt om klanten te helpen bij het afhandelen van die vraag, maar bij een hoge samen zetting van gebruikers die aan de gang werken, wordt een groot volume van Office 365-verkeer gegenereerd dat, wanneer routering via geforceerde tunnel VPN en on-premises netwerk perimeter verbindingen, geen ondersteuning biedt voor de VPN-infrastructuur. In deze nieuwe realiteit is het gebruik van VPN naar Office 365 niet langer slechts een betere prestaties, maar een harde muur die niet alleen van invloed is op de werking van Office 365 maar belangrijke zakelijke activiteiten die nog moeten vertrouwen op de VPN-verbinding.

Microsoft werkte nauw samen met klanten en de bredere wereld gedurende een groot aantal jaren om effectieve, moderne oplossingen te leveren aan deze problemen in de eigen services en om te stemmen met de beste gewoonte voor de branche. De mogelijkheden van de [verbinding](https://aka.ms/pnc) voor de Office 365-service zijn zodanig ontworpen dat ze efficiënt werken voor externe gebruikers, maar wel een organisatie in staat stellen om de beveiliging te behouden en door te gaan met het beheren van de verbinding. Deze oplossingen kunnen ook zeer snel worden geïmplementeerd met een beperkt werk, maar het is een belangrijke positieve impact op de hierboven beschreven problemen.

De aangeraden Microsoft-strategie voor het optimaliseren van de connectiviteit van een externe werknemer is geconcentreerd om snel de problemen met de traditionele aanpak te verhelpen en zo hoge prestaties te bieden met een paar eenvoudige stappen. Met deze stappen kunt u de verouderde VPN-aanpak voor een klein aantal gedefinieerde eindpunten aanpassen waarmee u de begeleide VPN-servers kunt overslaan. U kunt een vergelijkbaar of zelfs naliggend beveiligingsmodel toepassen op verschillende lagen om te voorkomen dat u al het verkeer van het bedrijfsnetwerk moet beveiligen. In de meeste gevallen kan dit binnen uur in de meeste gevallen ook effectief worden verwezenlijkt, en dan ook schaalbaar voor andere werkbelastingen wanneer de vereisten en de time-outwaarde.

## <a name="common-vpn-scenarios"></a>Veelgebruikte VPN-scenario's

In de onderstaande lijst ziet u de meest voorkomende VPN-scenario's die worden weergegeven in Enterprise-omgevingen. Meeste klanten werken met model 1 (VPN geforceerd tunnel). In deze sectie wordt u geholpen bij het snel en veilig overstappen naar **model 2** , wat niet voldoende is voor de prestaties en de gebruikservaring van uw netwerk.

| **Model** | **Beschrijving** |
| --- | --- |
| [1. geforceerde VPN-tunnel](#1-vpn-forced-tunnel) | 100% van het verkeer gaat in VPN-tunnel, waaronder on-premises, Internet, en alle O365-M365 |
| [2. VPN afgedwongen tunnel met een paar uitzonderingen](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | VPN-tunnel wordt standaard gebruikt (standaardroute punten voor VPN), met beperkte, belangrijkste vrijgestelde scenario's die rechtstreeks kunnen worden uitgevoerd |
| [3. VPN-geforceerde tunnel met grote uitzonderingen](#3-vpn-forced-tunnel-with-broad-exceptions) | VPN-tunnel wordt standaard gebruikt (standaardroute punten voor VPN), met grote uitzonderingen die rechtstreeks kunnen worden gebruikt (zoals alle Office 365, alles in-en uitzoomen) |
| [4. selectieve tunnel van VPN](#4-vpn-selective-tunnel) | VPN-tunnel wordt alleen gebruikt voor Corpnet-Services. Standaardroute (Internet en alle op internet gebaseerde services) worden rechtstreeks verstuurd. |
| [5. geen VPN](#5-no-vpn) | Een variatie van #2, in plaats van legacy VPN, is alle Corpnet-Services gepubliceerd via moderne beveiligingsmethoden (zoals Zscaler ZPA, Azure Active Directory (Azure AD) proxy/MCAS, enzovoort.) |

### <a name="1-vpn-forced-tunnel"></a>1. geforceerde VPN-tunnel

Dit is een veelvoorkomend begin scenario voor de meeste Enterprise-klanten. Er wordt een geforceerde VPN-verbinding gebruikt, wat inhoudt dat 100% van verkeer in het bedrijfsnetwerk omgaat, ongeacht het feit dat het eindpunt zich in het bedrijfsnetwerk bevindt. Willekeurige verkeer van extern (Internet), zoals Office 365 of Internet Browse, is dan hairpinned u weer op de on-premises beveiligingsapparatuur, zoals proxy's. In het huidige klimaat met bijna 100% van gebruikers die extern werken, zet dit model daarom zeer hoge belasting op de VPN-infrastructuur en kan de prestaties van het bedrijfs verkeer aanzienlijk beïnvloeden en zodat de onderneming efficiënt kan werken op een bepaald moment van crisis.

![VPN geforceerd tunnel model 1](../media/vpn-split-tunneling/vpn-model-1.png)

### <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. VPN-afgedwongen tunnel met een klein aantal vertrouwde uitzonderingen

Dit model is in het volgende voorbeeld zeer efficiënt voor een onderneming, zodat een klein aantal geplaatste en gedefinieerde eindpunten met zeer hoge belastingen en latentie gevoelige overeenkomsten kunnen worden gebruikt om de VPN-tunnel te omzeilen en direct naar de Office 365-service te gaan. Dit verbetert de prestaties van de verplaatste Services aanzienlijk en vermindert ook de belasting van de VPN-infrastructuur, zodat elementen die nog moeten worden uitgevoerd met minder inhoudsbronnen, kunnen worden gebruikt. Dit model wordt in dit artikel beschreven om u te helpen bij de overgang, zodat eenvoudige, gedefinieerde acties zeer snel worden uitgevoerd met talrijke positieve resultaten.

![Gesplitste tunnel VPN-model 2](../media/vpn-split-tunneling/vpn-model-2.png)

### <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. VPN-geforceerde tunnel met grote uitzonderingen

Het derde model vervalt binnen het bereik van model 2 als in plaats van een kleine groep met gedefinieerde eindpunten rechtstreeks te verzenden, en stuurt in plaats daarvan alle verkeer rechtstreeks naar vertrouwde services zoals Office 365 en SalesForce. Zo vermindert u de belasting van de VPN-infrastructuur van het bedrijfsnetwerk en verbetert u de prestaties van de gedefinieerde services. Aangezien dit model waarschijnlijk meer tijd in beslag treft om de uitvoerbaarheid van en de implementatie te beoordelen, is het waarschijnlijk een stap die op een later tijdstip na de uitvoering van het model twee uitvalt.

![Gesplitste tunnel VPN-model 3](../media/vpn-split-tunneling/vpn-model-3.png)

### <a name="4-vpn-selective-tunnel"></a>4. selectieve tunnel van VPN

Dit model verkeert het derde model waarin alleen verkeer wordt verzonden naar een zakelijk IP-adres dat wordt verstuurd naar de VPN-tunnel, en daarom is het Internet traject de standaardroute voor de rest. Voor dit model moet een organisatie het pad naar [0 vertrouwensrelaties](https://www.microsoft.com/security/zero-trust?rtc=1) goed hebben om dit model veilig te kunnen implementeren. Dit model of enige variatie ervan valt waarschijnlijk in de loop van de tijd waarschijnlijk de noodzakelijke regel te zijn omdat meer en meer services van het bedrijfsnetwerk en de cloud worden verplaatst. Microsoft gebruikt dit model intern. u vindt meer informatie over de implementatie van de VPN-splitsing van Microsoft bij het [uitvoeren van een VPN-verbinding op het moment dat Microsoft verbinding maakt met de werknemers](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv).

![Gesplitste tunnel VPN-model 4](../media/vpn-split-tunneling/vpn-model-4.png)

### <a name="5-no-vpn"></a>5. geen VPN

Een geavanceerdere versie van het modelnummer twee, waarbij interne services worden gepubliceerd via een moderne beveiligingsoplossing of een SDWAN oplossing zoals Azure AD-, MCAS, Zscaler ZPA, enzovoort.

![Gesplitste tunnel VPN-model 5](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="implement-vpn-split-tunneling"></a>Gesplitste VPN-tunneling implementeren

In deze sectie vindt u de eenvoudige stappen die nodig zijn voor het migreren van de architectuur van de VPN-client van een _geforceerde_ VPN-tunnel naar een _geforceerde VPN-tunnel met een klein aantal vertrouwde uitzonderingen_ , [#2](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) in de sectie [veelvoorkomende VPN-scenario's](#common-vpn-scenarios) .

In het onderstaande diagram ziet u hoe de aanbevolen tunnel oplossing voor VPN werkt:

![Details van gesplitste tunnel oplossingen voor VPN](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

### <a name="1-identify-the-endpoints-to-optimize"></a>1. bepalen welke eindpunten u wilt optimaliseren

In het onderwerp [Office 365-url's en IP-adresbereiken](urls-and-ip-address-ranges.md) identificeert Microsoft duidelijk de sleutel eindpunten **die u** nodig hebt om ze te optimaliseren en te categoriseren. Op dit moment zijn er slechts vier URL'S en twintig IP-subnetten die moeten worden geoptimaliseerd. Deze kleine groepen met eindpunten voor ongeveer 70%-80% van het volume van het verkeer naar de Office 365-service, waaronder de bewaarde eindpunten zoals de eindpunten voor teams-media. Dit is een zeer belangrijke hoeveelheid verkeer waarvan we u speciale aandacht moeten richten en ook het verkeer naar traditionele netwerkpaden en VPN-infrastructuur.

Url's in deze categorie hebben de volgende kenmerken:

- Microsoft bezit en beheerde eindpunten, gehost op Microsoft-infrastructuur
- Gebiedt IPs
- Lage veranderings kosten en ze worden naar behoren genummerd (momenteel 20 IP-subnetten)
- Bandbreedte en/of latentie gevoelig
- Kan de vereiste beveiligingselementen in de service niet gebruiken in plaats van in de regel op het netwerk.
- Account rondom 70-80% van het volume verkeer naar de Office 365-service

Zie het artikel [Office 365-eindpunten beheren](managing-office-365-endpoints.md)voor meer informatie over de eindpunten van Office 365 en de manier waarop ze worden gecategoriseerd en beheerd.

#### <a name="optimize-urls"></a>Url's optimaliseren

De huidige Url's voor geoptimaliseerde Url's vindt u in de onderstaande tabel. In de meeste gevallen moet u URL-eindpunten gebruiken in een browser- [PAC-bestand](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic) waarbij de eindpunten zijn geconfigureerd voor direct verzenden, in plaats van naar de proxy.

| Url's optimaliseren | Poort/Protocol | Doel |
| --- | --- | --- |
| <https://outlook.office365.com> | TCP 443 | Dit is een van de primaire Url's die in Outlook worden gebruikt om verbinding te maken met de Exchange Online-server, en er is een hoog volume bandbreedtegebruik en aantal verbindingen. Lage netwerklatentie is vereist voor online functies, waaronder direct zoeken, andere postvak agenda's, beschikbaarheidsinfo, beheerregels en waarschuwingen, Exchange Online-archief, e-mailberichten die het postvak uit. |
| <https://outlook.office.com> | TCP 443 | Deze URL wordt gebruikt voor Outlook online Web Access om verbinding te maken met Exchange Online-server en is afhankelijk van de netwerklatentie. De verbinding is vooral vereist voor grote bestanden uploaden en downloaden met SharePoint Online. |
| https:// \<tenant\> . SharePoint.com | TCP 443 | Dit is de primaire URL voor SharePoint Online en heeft een groot bandbreedtegebruik. |
| https:// \<tenant\> -My.SharePoint.com | TCP 443 | Dit is de primaire URL voor OneDrive voor bedrijven met een groot bandbreedtegebruik en mogelijk een hoge hoeveelheid verbindingen via het OneDrive voor bedrijven-synchronisatieprogramma. |
| Teams-media IPs (geen URL) | UDP 3478, 3479, 3480 en 3481 | Detectie van relay-toewijzing en real-time verkeer (3478), audio (3479), video (3480) en scherm delen van de video (3481). Dit zijn de eindpunten die worden gebruikt voor Skype voor bedrijven en Microsoft teams-media verkeer (oproepen, vergaderingen, enzovoort). De meeste eindpunten worden weergegeven wanneer de Microsoft teams-client een oproep aanlevert (en deel uitmaakt van de vereiste IP-adressen die worden vermeld voor de service). Het gebruik van het UDP-protocol is vereist voor optimale mediakwaliteit.   |

In bovenstaande voorbeelden moet **Tenant** worden vervangen door de naam van de Tenant van Office 365. Met **contoso.onmicrosoft.com** kunt u bijvoorbeeld _contoso.SharePoint.com_ en _constoso-my.SharePoint.com_.

#### <a name="optimize-ip-address-ranges"></a>IP-adresbereiken optimaliseren

U kunt als volgt de IP-bereiken waarmee deze eindpunten overeenkomen, als volgt schrijven. U wordt **ten zeerste** geadviseerd een [script, zoals dit](https://github.com/microsoft/Office365NetworkTools/tree/master/Scripts/Display%20URL-IPs-Ports%20per%20Category) voorbeeld, de [Office 365 IP-en URL-webservice](microsoft-365-ip-web-service.md) of de [URL/IP-pagina](urls-and-ip-address-ranges.md) te gebruiken om te controleren of er updates zijn wanneer u de configuratie toepast, en u kunt een beleid op regelmatige basis plaatsen.

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

### <a name="2-optimize-access-to-these-endpoints-via-the-vpn"></a>2. toegang tot deze eindpunten via VPN optimaliseren

Nu we deze kritieke eindpunten hebben geïdentificeerd, moeten ze overstappen van de VPN-tunnel zodat ze de lokale Internet verbinding van de gebruiker kunnen gebruiken om rechtstreeks verbinding te maken met de service. De manier waarop dit gebeurt, is afhankelijk van de gebruikte VPN-product-en computerplatform, maar de meeste VPN-oplossingen bieden een eenvoudige configuratie van het beleid om deze logica toe te passen. Zie [handleidingen voor veelgebruikte VPN-platforms](#howto-guides-for-common-vpn-platforms)voor informatie over de ondersteuning van de gesplitste tunnel.

Als u de oplossing handmatig wilt testen, kunt u het volgende PowerShell-voorbeeld uitvoeren om de oplossing op het tabelniveau te emuleren. In dit voorbeeld wordt een route voor elk van de subnetten media IP-subnetten in de tabel route toegevoegd. U kunt de media prestaties van teams testen vóór en na, en het verschil nakijken in routes voor de opgegeven eindpunten.

#### <a name="example-add-teams-media-ip-subnets-into-the-route-table"></a>Voorbeeld: de IP-subnetten van teams-media toevoegen aan de routetabel

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18" # Teams Media endpoints
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

In het bovenstaande script is _$intIndex_ de index van de interface die is verbonden met internet (zoeken door **Get-netadapter** in PowerShell uit **te voeren;** Zoek de waarde van _ifIndex_ ) en _$Gateway_ de standaardgateway van die interface (zoek **-NetIPConfiguration | Foreach-IPv4DefaultGateway). NextHop** in PowerShell).

Wanneer u de routes hebt toegevoegd, kunt u controleren of de routetabel juist is door **route afdrukken** in een opdrachtprompt of PowerShell uit te voeren. De uitvoer moet de aangevoegde routes bevatten, met de interface-index ( _22_ in dit voorbeeld) en de gateway voor de interface ( _192.168.1.1_ in dit voorbeeld):

![Afdrukuitvoer routeren](../media/vpn-split-tunneling/vpn-route-print.png)

Als u routes wilt toevoegen voor **alle** huidige IP-adresbereiken in de categorie optimaliseren, kunt u de volgende script variant gebruiken voor het uitvoeren van een query op de [Office 365 IP-en URL web service](microsoft-365-ip-web-service.md) voor de huidige set IP-subnetten, en voegt u ze toe aan de tabel route.

#### <a name="example-add-all-optimize-subnets-into-the-route-table"></a>Voorbeeld: alle subnetten met een tabel optimaliseren in de routetabel

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

Als u per ongeluk routes met onjuiste parameters hebt toegevoegd of als u de wijzigingen wilt herstellen, kunt u de routes die u zojuist hebt toegevoegd, verwijderen met de volgende opdracht:

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

De VPN-client moet zodanig zijn geconfigureerd dat verkeer naar de **Optimize** IPS op deze manier wordt gerouteerd. Hiermee kan het verkeer lokale Microsoft-bronnen gebruiken, zoals Office 365-service punten, [zoals de Azure-voor deur](https://azure.microsoft.com/blog/azure-front-door-service-is-now-generally-available/) , die Office 365-Services en connectiviteits eindpunten bewaart. Dit biedt ons de mogelijkheid een zeer hoge prestatieniveau te bieden aan gebruikers waar ter wereld ze zich bevinden en optimaal te profiteren van [het wereldwijde netwerk van Microsoft van Microsoft](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/), dat zeer waarschijnlijk binnen een klein aantal milliseconden van uw gebruikers leidt.

## <a name="configuring-and-securing-teams-media-traffic"></a>Teams-media verkeer configureren en beveiligen

Sommige beheerders vragen mogelijk meer informatie over de manier waarop oproep stromen in teams werken met behulp van een gesplitste tunnel model en de manier waarop verbindingen worden beveiligd.

### <a name="configuration"></a>Configuratie

Voor gesprekken en vergaderingen, mits teams de functie [GetBestRoute](https://docs.microsoft.com/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute) om te bepalen welke lokale interface overeenkomt met de route die voor een bepaalde bestemming moet worden gebruikt, wordt de lokale interface geretourneerd voor Microsoft-bestemmingen in de hierboven vermelde Microsoft-IP-blokken......

Voor sommige VPN-clientsoftware is het mogelijk maken van routering op basis van URL. Er is echter geen URL gekoppeld aan teams, dus besturingselement van routering voor dit verkeer moet worden uitgevoerd met IP-subnetten.

In bepaalde scenario's, vaak niet in verband met de configuratie van de teams-client, is er nog steeds verbinding tussen de VPN-tunnel, zelfs met de juiste routes ter plaatse. Als u dit scenario tegenkomt, moet u een firewallregel gebruiken om te voorkomen dat de IPSec IP-subnetten of-poorten van het gebruik van het VPN, voldoende zijn.

>[!IMPORTANT]
>Zorg ervoor dat gebruikers Microsoft teams-clientversie **1.3.00.13565** of hoger uitvoeren om ervoor te zorgen dat teams-media verkeer via de gewenste methode in alle VPN-scenario's wordt gerouteerd. Deze versie bevat verbeteringen voor het detecteren van beschikbare netwerkpaden in de client.

Signalering van verkeer wordt doorgevoerd via HTTPS en is niet de latentie gevoelig als het media verkeer en wordt gemarkeerd als **toegestaan** in de URL/IP-gegevens en kan zo nodig veilig worden gerouteerd via de VPN-client.

### <a name="security"></a>Beveiliging

Eén gemeenschappelijk argument voor het vermijden van gesplitste tunnels is dat het minder veilig is, d.w.z. verkeer dat niet via de VPN-tunnel gaat, is niet van toepassing op de VPN-tunnel, en is daarom minder veilig.

Het belangrijkste argument van Counter is dat media verkeer al versleuteld is via _Secure Real-Time Transport Protocol (srtp)_ , een profiel van Real-Time Transport Protocol (RTP) waarmee vertrouwelijkheid, verificatie en beveiliging van aanvallen op RTP-verkeer wordt geboden. SRTP zichzelf vertoont een willekeurig gegenereerde sessiesleutel, die wordt uitgewisseld via het TLS-kanaal voor beveiligde signalering. Dit wordt in [deze beveiligingshandleiding](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online)uitvoerig besproken, maar de belangrijkste belangrijke sectie is media versleuteling.

Media verkeer wordt versleuteld met SRTP, dat gebruikmaakt van een sessiesleutel die wordt gegenereerd door een Secure Random Number Generator en Exchange via het TLS-kanaal signalering. Daarnaast kunt u ook mediastromen in beide richtingen tussen de bemiddelings server en de interne volgende hop versleutelen met behulp van SRTP.

In Skype voor bedrijven online worden gebruikersnamen en wachtwoorden voor veilige toegang tot media relays via het _traversal via NETWERKADRESOMZETTING weer_ gegeven. Media relay Exchange de gebruikersnaam/het wachtwoord uitwisselen via een TLS-kanaal met SIP-beveiliging. Het is ook mogelijk dat ook hoewel een VPN-tunnel kan worden gebruikt om de client te verbinden met het bedrijfsnetwerk, het verkeer nog steeds moet debiet in het SRTP-formulier wanneer het het bedrijfsnetwerk van de dienst verlaat.

[In dit artikel](https://docs.microsoft.com/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c)vindt u informatie over de manier waarop teams veelvoorkomende beveiligingskwesties zoals spraak _-of sessie traversal Utilities voor NAT (stun)_ verhogen.

U kunt ook informatie weer bieden over moderne beveiligings besturingen in externe werk scenario's op een [afwijkende manier voor beveiligings professionals en een nieuwe manier om te profiteren van de meest unieke externe werk scenario's van vandaag (Microsoft Security team-blog)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

## <a name="testing"></a>Testen

Als het beleid is ingevuld, dient u te controleren of het naar verwachting werkt. U kunt op verschillende manieren testen of het pad juist is ingesteld op het gebruik van de lokale Internet verbinding:

- Voer de [Microsoft 365-connectiviteitstest](https://aka.ms/netonboard) uit waarop verbindings tests worden uitgevoerd, waaronder tracerings routes. In dit hulpprogramma voegt u ook extra inzichten toe aan een VPN-test.

- Bij een eenvoudige tracering naar een eindpunt binnen de scope van de gesplitste tunnel moet het gebruikte pad worden weergegeven, bijvoorbeeld:

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  U dient vervolgens een pad te zien via de lokale provider van dit eindpunt dat moet worden omgezet in een IP-adres in de teams-bereiken die door de gesplitste tunneling zijn geconfigureerd.

- Maak een netwerk opname met behulp van een hulpprogramma zoals wireshark. U kunt tijdens een gesprek filteren op UDP en u moet verkeer doorlopen naar een IP-adres in het bereik voor **optimaliseren** van teams. Als de VPN-tunnel wordt gebruikt voor dit verkeer, is het media verkeer niet zichtbaar in de tracering.

### <a name="additional-support-logs"></a>Aanvullende ondersteunings logboeken

Als u meer informatie nodig hebt over het oplossen van problemen of als u hulp nodig hebt bij de ondersteuning van Microsoft, kunt u snel een oplossing vinden door de volgende informatie te vinden. Microsoft-ondersteuning **TSS Windows CMD-based Universal troubleshoote,** kan u helpen bij het verzamelen van de relevante logboeken op een eenvoudige manier. U vindt meer informatie over de tool en de gebruiksaanwijzing op <https://aka.ms/TssTools.>

## <a name="howto-guides-for-common-vpn-platforms"></a>Handleidingen voor veelgebruikte VPN-platforms

Dit gedeelte bevat koppelingen naar gedetailleerde gidsen voor het implementeren van gesplitste tunneling voor Office 365-verkeer van de meest voorkomende partners in deze ruimte. We toevoegen extra hulplijnen wanneer deze beschikbaar komen.

- **Windows 10 VPN-client** : [Office 365-verkeer voor externe werknemers optimaliseren met de native Windows 10 VPN-client](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-office-365-optimization)
- **Cisco AnyConnect** : [AnyConnect Split-tunnel voor Office365 optimaliseren](https://www.cisco.com/c/en/us/support/docs/security/anyconnect-secure-mobility-client/215343-optimize-anyconnect-split-tunnel-for-off.html)
- **Palo Alto GlobalProtect** : [Office 365-verkeer optimaliseren via de gesplitste tunnel van een VPN-verbinding uitsluiten](https://live.paloaltonetworks.com/t5/Prisma-Access-Articles/GlobalProtect-Optimizing-Office-365-Traffic/ta-p/319669)
- **F5 netwerken Big-IP apm** : [Office 365-verkeer optimaliseren voor externe toegang via vpn's wanneer u gebruikmaakt van grote IP-apm](https://devcentral.f5.com/s/articles/SSL-VPN-Split-Tunneling-and-Office-365)
- **Citrix gateway** : het [optimaliseren van een gesplitste tunnel voor VPN-gateway voor Office365](https://docs.citrix.com/en-us/citrix-gateway/13/optimizing-citrix-gateway-vpn-split-tunnel-for-office365.html)
- **Pulse veilig** : [VPN-tunneling: gesplitste tunneling configureren om Office365-toepassingen uit te sluiten](https://kb.pulsesecure.net/articles/Pulse_Secure_Article/KB44417)
- **Kijk punt VPN** : de [gesplitste Tunnel voor Office 365 en andere SaaS-toepassingen configureren](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk167000)

## <a name="faq"></a>Veelgestelde vragen

Het Microsoft-beveiligings team heeft [een artikel](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) gepubliceerd met een overzicht van de belangrijkste manieren van beveiligings professionals en kan in de unieke scenario's voor extern werken van vandaag de moderne beveiligings regeling bereiken. Daarnaast volgen hieronder enkele veelvoorkomende vragen en antwoorden van klanten voor dit onderwerp.

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>Hoe kan ik voorkomen dat gebruikers toegang hebben tot andere tenants die ik niet vertrouwt, waar ze gegevens kunnen exfiltrateen?

Het antwoord is een [functie met de naam Tenant beperkingen](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions). Verificatieverkeer is niet hoog volume en met name latentie gevoelig, zodat het via de VPN-oplossing kan worden verzonden naar de on-premises proxy waarop de functie wordt toegepast. Hier wordt een lijst met vertrouwde tenants weergeven en wordt de client geprobeerd een token te verkrijgen aan een Tenant die niet wordt vertrouwd, dan heeft de proxy de aanvraag gewoon geweigerd. Als de Tenant wordt vertrouwd, is een token toegankelijk als de gebruiker over de juiste referenties en rechten beschikt.

Zelfs hoewel een gebruiker een TCP/UDP-verbinding kan maken met de hierboven gemarkeerde eindpunten, zonder een geldig token om toegang te krijgen tot de Tenant, kan hij of zij simpelweg geen gegevens meer raadplegen en verplaatsen.

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>Is in dit model toegang tot consumenten services zoals persoonlijke OneDrive-accounts toegestaan?

Nee, de eindpunten van Office 365 zijn niet hetzelfde als de consumenten Services (Onedrive.live.com als voorbeeld) zodat de gesplitste tunnel geen directe toegang heeft tot consumenten Services. Het verkeer naar eindpunten van de consument blijft gebruikmaken van de VPN-tunnel, en het bestaande beleid blijft van toepassing.

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>Hoe kan ik DLP toepassen en mijn gevoelige gegevens beschermen wanneer het verkeer niet meer via mijn on-premises oplossing loopt?

Om te voorkomen dat vertrouwelijke informatie door onbedoeld wordt vrijgegeven, biedt Office 365 een uitgebreide set [ingebouwde hulpmiddelen](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies). U kunt de ingebouwde [DLP-functies](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) van teams en SharePoint gebruiken om niet-opgeslagen of gedeelde gevoelige informatie te vinden. Als een onderdeel van uw strategie voor extern werken een bedrijf (BYOD) omvat, kunt u [voorwaardelijke toegang op basis van apps](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) gebruiken om te voorkomen dat vertrouwelijke gegevens worden gedownload naar persoonlijke apparaten van gebruikers

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>Hoe kan ik de authenticatie van gebruikers evalueren en beheren wanneer ze rechtstreeks verbinding maken?

Naast de functie voor Tenant beperkingen die wordt vermeld in W1, kunnen [regels voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) worden toegepast om het risico van een authenticatieaanvraag dynamisch te beoordelen en de juiste manier te reageren. Microsoft adviseert het [vertrouwensmodel nul](https://www.microsoft.com/security/zero-trust?rtc=1) in de loop van de tijd en we kunnen Azure AD Conditional Access-beleidsregels gebruiken voor het beheren van de besturing in een mobiele en de eerste wereld in de Cloud. U kunt regels voor voorwaardelijke toegang gebruiken voor het maken van een realtime-beslissing voor het maken van een verificatieaanvraag op basis van een groot aantal factoren zoals:

- Apparaat is het apparaat bekend/vertrouwd/domein geworden?
- IP – de authenticatieaanvraag komt van een bekend zakelijk IP-adres? Of van een land dat we niet vertrouwen?
- Application: de gebruiker die is geautoriseerd voor het gebruik van deze toepassing?

We kunnen vervolgens het beleid activeren, zoals goedkeuren, een MFA activeren of verificatie blokkeren op basis van deze beleidsregels.

### <a name="how-do-i-protect-against-viruses-and-malware"></a>Hoe kan ik de beveiliging tegen virussen en malware beschermen?

Ook weer, Office 365 biedt bescherming voor de gemarkeerde eindpunten in verschillende lagen in de service zelf, [zoals beschreven in dit document](https://docs.microsoft.com/office365/Enterprise/office-365-malware-and-ransomware-protection). Zoals u ziet, is het zeer efficiënt om deze beveiligingselementen aan te bieden in de service zelf, in plaats van het te proberen en te doen in overeenstemming met apparaten die de protocollen/verkeer mogelijk niet volledig begrijpen. In SharePoint Online wordt het uploaden van bestanden op basis van bekende malware standaard [automatisch gecontroleerd](https://docs.microsoft.com/microsoft-365/security/office-365-security/virus-detection-in-spo) .

Voor de bovenstaande Exchange-eindpunten, [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) en [Microsoft Defender voor Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) , beschikt u over een uitstekende functie voor het verschaffen van de beveiliging van het verkeer naar de service.

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>Kan ik meer dan alleen het verkeer voor direct optimaliseren verzenden?

U **moet de prioriteit** geven aan de gemarkeerde eindpunten, aangezien deze de maximale voordelen bieden voor een laag werk niveau. Als u wilt, kunt u echter de gemarkeerde eindpunten voor de service gebruiken en de Ip's opgeven voor de eindpunten die u indien nodig kunt gebruiken.

Er zijn ook verschillende leveranciers die Cloud/beveiligingsoplossingen met de Cloud en de zogeheten veilig webgateways bieden die de toepassing centrale beveiliging, besturing en bedrijfsbeleid bieden voor algemeen browsen op het web. Deze oplossingen kunnen goed werken in de eerste wereld van de Cloud, indien een hoge beschikbare, bedrijfsgebruikte en ingerichte nauwer zijn voor uw gebruikers, zodat ze veilige Internet toegang kunnen afleveren vanuit een locatie in de cloud die voor de gebruiker is gesloten. Hiermee verwijdert u een Maak via het VPN/Corporate Network voor algemeen Browse verkeer, terwijl u nog steeds de centrale beveiligings besturing toestaat.

Ook als deze oplossingen ook op hun plaats staan, wordt Microsoft nog steeds sterk aangeraden om het gemarkeerde Office 365-verkeer rechtstreeks naar de service te sturen.

Zie het artikel [Extern werken via Azure VPN gateway Point-to-site](https://docs.microsoft.com/azure/vpn-gateway/work-remotely-support)voor meer informatie over het toestaan van directe toegang tot een Azure virtueel netwerk.

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>Waarom is poort 80 nodig? Verzendt het verkeer naar de heldere invoeg?

Poort 80 wordt alleen gebruikt voor zaken zoals omleiding naar een poort 443-sessie, geen klantgegevens worden verzonden of zijn toegankelijk via Port 80. [Dit artikel](https://docs.microsoft.com/microsoft-365/compliance/encryption) bevat een overzicht van de versleuteling voor gegevens in de transit en de rest van Office 365, en in [dit artikel](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic) wordt uitgelegd hoe u srtp gebruikt om te beschermen tegen het media verkeer van teams.

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-office-365"></a>Is dit advies van toepassing op gebruikers in China met een wereldwijde instantie van Office 365?

**Nee** , dat is niet het geval. Het voorbeeld van het bovenstaande advies is gebruikers in de Volksrepubliek China die verbinding maken met een wereldwijde instantie van Office 365. De prestaties van de netwerkcongestie van de gemeenschappelijke grenzen in de regio zijn direct van een variabele. De meeste klanten in de regio werken via een VPN om het verkeer in het bedrijfsnetwerk te brengen en gebruikmaken van hun geautoriseerde MPLS-circuit of vergelijkbaar met het opzeggen van het land via een geoptimaliseerd pad. Dit wordt verder beschreven in het artikel [Office 365 prestaties optimaliseren voor gebruikers van China](microsoft-365-networking-china.md).

### <a name="does-split-tunnel-configuration-work-for-teams-running-in-a-browser"></a>Werkt de gesplitste tunnelconfiguratie voor teams met een browser?

**Nee** , dat is niet het geval. Dit werkt alleen op Microsoft teams-clientversie 1.3.00.13565 of hoger. Deze versie bevat verbeteringen voor het detecteren van beschikbare netwerkpaden in de client.

## <a name="related-topics"></a>Verwante onderwerpen

[Overzicht: gedeelde tunneling voor VPN voor Office 365](microsoft-365-vpn-split-tunnel.md)

[Prestaties van Office 365 optimaliseren voor gebruikers van China](microsoft-365-networking-china.md)

[Andere manieren voor beveiliging en een nieuwe manier om te profiteren van de moderne beveiligingsfuncties in de unieke, externe werk scenario's van vandaag (blog van Microsoft Security team)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[VPN-prestaties verbeteren bij Microsoft: met Windows 10 VPN-profielen voor het toestaan van automatische verbindingen](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Uitvoeren op VPN: hoe Microsoft de werknemers op afstand houdt](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Beginselen voor Office 365-netwerkverbinding](microsoft-365-network-connectivity-principles.md)

[Office 365-netwerkverbinding beoordelen](assessing-network-connectivity.md)

[Aanpassing van Office 365-netwerk en -prestaties](network-planning-and-performance.md)
