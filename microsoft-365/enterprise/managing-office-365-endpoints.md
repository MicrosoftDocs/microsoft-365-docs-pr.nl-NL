---
title: Office 365-eindpunten beheren
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 99cab9d4-ef59-4207-9f2b-3728eb46bf9a
description: Meer informatie over het beheren van Office 365-eindpunten, zodat deze werken met de netwerkarchitectuur van uw organisatie.
ms.openlocfilehash: dcacb10492f4377dbcdf6e74c848a404f1b64c6f
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780482"
---
# <a name="managing-office-365-endpoints"></a>Office 365-eindpunten beheren

Voor de meeste ondernemingen met meerdere Office-locaties en een verbinding met een WAN-verbinding is de configuratie voor Office 365-netwerkconnectiviteit nodig. U kunt uw netwerk optimaliseren door alle vertrouwde Office 365-netwerkaanvragen rechtstreeks via uw firewall te verzenden, zodat alle extra inspectie of verwerking van pakketniveau wordt genegeerd. Dit vermindert de latentie en de vereisten voor de capaciteit van de verbinding. Het identificeren van het netwerkverkeer van Office 365 is de eerste stap bij het leveren van optimale prestaties voor uw gebruikers. Zie voor meer informatie de [beginselen voor de netwerkverbindingen van Office 365](microsoft-365-network-connectivity-principles.md).

Microsoft raadt u aan toegang te krijgen tot de netwerkeindpunten van Office 365 en de voortdurende wijzigingen door te voeren met behulp van de [IP-adressen en URL-webservice van office 365](microsoft-365-ip-web-service.md).

Ongeacht de manier waarop u belangrijk netwerkverkeer van Office 365 beheert, is voor Office 365 een Internet verbinding vereist. Andere netwerkeindpunten waarbij de verbinding is vereist, worden weergegeven op [extra eindpunten die niet zijn opgenomen in het Office 365 IP Address en URL web service](additional-office365-ip-addresses-and-urls.md).

Hoe u de netwerkeindpunten van Office 365 gebruikt, is afhankelijk van de netwerkarchitectuur van uw organisatie. Dit artikel bevat een overzicht van de manieren waarop netwerk architecturen van het bedrijf kunnen worden geïntegreerd met Office 365 IP-adressen en Url's. De eenvoudigste manier om te bepalen welke netwerkaanvragen u wilt vertrouwen, is door gebruik te kunnen maakt van een SD-WAN-apparaat dat op elk van uw Office-locaties ondersteuning biedt voor automatische configuratie van Office 365.

## <a name="sd-wan-for-local-branch-egress-of-vital-office-365-network-traffic"></a>SD-WAN voor lokale branch-uitgebrachte cruciale Office 365-netwerkverkeer

U kunt op elke filiaallocatie een SD-WAN-apparaat maken dat is geconfigureerd voor het routeren van gegevens van Office 365, de categorie eindpunten optimaliseren of categorieën optimaliseren en toestaan rechtstreeks naar het netwerk van Microsoft. Het andere netwerkverkeer, waaronder on-premises datacenter verkeer, algemeen verkeer van Internet sites en verkeer naar Office 365 Standaardeindpunten voor de eindpunten van de netwerkverbinding.

Microsoft werkt met SD-WAN-providers om geautomatiseerde configuratie mogelijk te maken. Zie voor meer informatie [Office 365 Networking partner programma](microsoft-365-networking-partner-program.md).

<a name="pacfiles"> </a>
## <a name="use-a-pac-file-for-direct-routing-of-vital-office-365-traffic"></a>Een PAC-bestand gebruiken voor de directe routering van cruciale Office 365-verkeer

Gebruik PAC-of WPAD-bestanden om netwerkaanvragen te beheren die zijn gekoppeld aan Office 365, maar geen IP-adres. Typische netwerkaanvragen die worden verzonden via een proxy of een verbindingsapparaat zorgen voor een langere latentie. Met SSL-onderbreking en-inspectie wordt de grootste latentie gemaakt, andere services, zoals proxyverificatie en reputatie zoeken, kunnen leiden tot verminderde prestaties en een onjuiste gebruikerservaring. Daarnaast zijn deze perimeternetwerk apparaten voldoende capaciteit om alle netwerk verbindingsaanvragen te kunnen verwerken. U wordt aangeraden uw proxy of controleapparatuur te negeren voor direct Office 365-netwerkaanvragen.
  
[PowerShell Gallery Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) is een PowerShell-script dat de laatste netwerkeindpunten leest van de IP-adressen en URL-webservice van Office 365 en een voorbeeld van een PAC-bestand maken. U kunt het script zodanig wijzigen dat het wordt geïntegreerd met uw bestaande PAC-bestandsbeheer.

![Verbinding maken met Office 365 via firewalls en proxy's.](../media/34d402f3-f502-42a0-8156-24a7c4273fa5.png)

**Afbeelding 1: eenvoudige netwerkverbinding met bedrijfsnetwerk**

Het PAC-bestand wordt geïmplementeerd op webbrowsers, punt 1, in afbeelding 1. Wanneer u een PAC-bestand gebruikt voor de directe uituitgang van belangrijk netwerkverkeer van Office 365, moet u ook connectiviteit met IP-adressen achter deze Url's toestaan op de firewall van uw netwerk perimeternetwerk. Dit doet u door de IP-adressen voor dezelfde Office 365-eindpunten op te halen, zoals beschreven in het PAC-bestand en het maken van Firewall-Acl's op basis van deze adressen. De firewall is punt 3 in afbeelding 1.

Als u ervoor kiest om directe routering voor de eindpunten van de categorie te optimaliseren, moet u toestaan dat categorie eindpunten die u naar de proxyserver verzendt, worden weergegeven in de proxyserver om verdere verwerking te negeren. De SSL-onderbreking en-verificatie en verificatie van proxy zijn incompatibel met de eindpunten voor de categorie optimaliseren en toestaan. De proxyserver is punt 2 in afbeelding 1.

De gemeenschappelijke configuratie is toegestaan zonder te verwerken al het uitgaande verkeer van de proxyserver voor de IP-adressen van Office 365 die de proxyserver betrefferen. Zie [netwerkapparaten of oplossingen van derden gebruiken voor Office 365-verkeer](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365)voor informatie over problemen met de SSL-onderbreking en de inspectie.

Er zijn twee typen PAC-bestanden die door het Get-PacFile script worden gegenereerd.

| Type | Beschrijving |
|:-----|:-----|
|**1** <br/> |Verstuur verkeer direct naar het eindpunt en alles naar de proxyserver. <br/> |
|**3** <br/> |Verstuur het verkeer naar het eind en alles wat naar de proxyserver gaat en alles. Dit type kan ook worden gebruikt voor het verzenden van alle ondersteunde ExpressRoute voor Office 365-verkeer naar ExpressRoute-netwerksegmenten en alles wat ook is voor de proxyserver. <br/> |

Hier volgt een eenvoudig voorbeeld van het bellen van het PowerShell-script:

```powershell
Get-PacFile -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

U kunt een groot aantal parameters aan het script doorgeven:

| Tabelwaardeparameter | Beschrijving |
|:-----|:-----|
|**ClientRequestId** <br/> |Dit is vereist en is een GUID die wordt doorgegeven aan de webservice waarmee de clientcomputer wordt gebeld. <br/> |
|**Versie** <br/> |Het service-exemplaar van Office 365, dat standaard wordt gebruikt voor wereldwijd. Dit wordt ook doorgegeven aan de webservice. <br/> |
|**Tenantname vervangt** <br/> |De naam van de Tenant van Office 365. Wordt doorgegeven aan de webservice en gebruikt als een vervangbare parameter in sommige Office 365-Url's. <br/> |
|**Type** <br/> |Het type proxy PAC-bestand dat u wilt genereren. <br/> |

Hier is nog een voorbeeld van het aanroepen van het PowerShell-script met aanvullende parameters:

```powershell
Get-PacFile -Type 2 -Instance Worldwide -TenantName Contoso -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

## <a name="proxy-server-bypass-processing-of-office-365-network-traffic"></a>De verwerking van de proxy server omzeilen van Office 365 netwerkverkeer

Wanneer PAC-bestanden niet worden gebruikt voor direct uitgaand verkeer, moet u de verwerking van uw netwerk netwerk omzeilen door de proxyserver te configureren. Sommige proxyserver leveranciers hebben een geautomatiseerde configuratie ingeschakeld, zoals beschreven in het [Office 365-programma voor de netwerk partner](microsoft-365-networking-partner-program.md).

Als u dit handmatig doet, moet u de gegevens van de eindpunten voor de einddatum en-URL van het Office 365 IP-adres en de webservice van de client configureren en de proxyserver configureren om de verwerking voor deze services te omzeilen. Het is belangrijk dat u de SSL-onderbreking vermijdt en inspecteert en proxy verificatie voor de eindpunten van de categorie optimaliseert en toestaat.
  
<a name="bkmk_changes"> </a>
## <a name="change-management-for-office-365-ip-addresses-and-urls"></a>Wijzigingsbeheer voor Office 365 IP-adressen en Url's

Naast het selecteren van de juiste configuratie voor uw netwerk netwerk, is het essentieel dat u een proces voor het wijzigen van het wijzigingsbeheer voor Office 365-eindpunten aanneemt. Deze eindpunten worden regelmatig gewijzigd en als u de wijzigingen niet beheert, kunt u beëindigen met geblokkeerde gebruikers of met slechte prestaties nadat een nieuw IP-adres of een nieuwe URL is toegevoegd.

Wijzigingen in de IP-adressen en Url's van Office 365 worden meestal bij de laatste dag van elke maand gepubliceerd. Soms wordt een wijziging buiten dat schema gepubliceerd vanwege operationele, ondersteunings-en beveiligingsvereisten.

Wanneer een wijziging wordt gepubliceerd waarbij u moet reageren omdat een IP-adres of URL is toegevoegd, kunt u het beste 30 dagen van de wijziging ontvangen, vanaf de tijd dat de wijziging wordt gepubliceerd totdat er een Office 365-service op dit eindpunt wordt weergegeven. Hoewel we voor deze meldings periode streven, is het mogelijk dat het niet altijd mogelijk is om te voldoen aan de operationele, ondersteunings-en beveiligingsvereisten. Wijzigingen waarvoor geen directe actie moet worden ondernomen om de connectiviteit te behouden, zoals verwijderde IP-adressen of Url's of minder significante wijzigingen, bevatten geen meldingen voor voorafgaande meldingen. Ongeacht welke melding wordt gegeven, vermelden we de verwachte service actieve datum voor elke wijziging.

### <a name="change-notification-using-the-web-service"></a>Bericht wijzigen met de webservice

U kunt de Office 365 IP Address en URL-webservice gebruiken om meldingen te ontvangen. U wordt aangeraden de **/Version** -webmethode eenmaal per uur te bellen om de versie van de eindpunten te controleren die u gebruikt om verbinding te maken met Office 365. Als deze versie wordt gewijzigd als deze wordt vergeleken met de versie die u gebruikt, moet u de meest recente gegevens van het eindpunt krijgen van de webmethode **/endpoints** en eventueel de verschillen van de **/Changes** -webmethode achterhalen. U hoeft de **/endpoints** -of **/Changes** -webmethode niet te bellen als de versie die u hebt gevonden, niet is gewijzigd.

Zie voor meer informatie [Office 365 IP Address en URL web service](microsoft-365-ip-web-service.md).

### <a name="change-notification-using-rss-feeds"></a>Kennisgeving wijzigen via RSS-feeds

Het IP-adres en de URL van Office 365 bieden een RSS-feed waarop u zich kunt abonneren in Outlook. Er zijn koppelingen naar de RSS-Url's op elk van de Office 365-service-specifieke pagina's voor de IP-adressen en Url's. Zie voor meer informatie [Office 365 IP Address en URL web service](microsoft-365-ip-web-service.md).

### <a name="change-notification-and-approval-review-using-microsoft-flow"></a>Wijziging van meldingen en goedkeuren in Microsoft flow

We begrijpen dat u mogelijk nog steeds handmatige verwerking nodig hebt voor wijzigingen van netwerkeindpunten die per maand worden verzonden. U kunt Microsoft flow gebruiken om een stroom te creëren waarmee u per e-mail op de hoogte wordt gesteld van een goedkeuringsproces voor wijzigingen wanneer Office 365-netwerkeindpunten worden gewijzigd. Wanneer de beoordeling is voltooid, kunt u de stroom automatisch een e-mailbericht sturen met de wijzigingen in uw firewall-en proxyserver management-team.

Zie [Microsoft flow gebruiken voor het ontvangen van een e-mailbericht voor wijzigingen in Office 365 IP-adressen en url's](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/td-p/240651)voor informatie over de Microsoft-stroom voorbeelden en-sjablonen.
  
<a name="FAQ"> </a>
## <a name="office-365-network-endpoints-faq"></a>Office 365 netwerkeindpunten Veelgestelde vragen

Zie de volgende veelgestelde vragen over de netwerkverbinding van Office 365.
  
### <a name="how-do-i-submit-a-question"></a>Hoe kan ik een vraag stellen?

Klik op de koppeling onder aan het scherm om aan te geven of het artikel handig of niet is en dien eventuele aanvullende vragen in. We volgen de feedback en werken de vragen hier bij, met het meest Veelgestelde vragen.
  
### <a name="how-do-i-determine-the-location-of-my-tenant"></a>Hoe bepaal ik de locatie van mijn Tenant?

 **Tenant locatie** kan het beste worden bepaald via onze [datacenter kaart](https://aka.ms/datamaps).
  
### <a name="am-i-peering-appropriately-with-microsoft"></a>Is de peering geschikt voor Microsoft?

 **Peering-locaties** worden uitvoerig beschreven in de [peering met Microsoft](https://www.microsoft.com/peering).
  
Met een relatie tussen de peer-en 70-locaties van meer dan 2500, is het belangrijk dat u van uw netwerk naar uw familie beschikt. U kunt er niet zeker van zijn dat u een paar minuten besteedt dat de peering-relatie van uw INTERNETPROVIDER het meest optimaal is, maar [hier volgen enkele voorbeelden](https://blogs.technet.microsoft.com/onthewire/2017/03/22/__guidance/) van goed en geen goede peering met ons netwerk.
  
<a name="bkmk_MissingIP"> </a>
### <a name="i-see-network-requests-to-ip-addresses-not-on-the-published-list-do-i-need-to-provide-access-to-them"></a>Ik zie netwerkaanvragen voor IP-adressen die niet voorkomen in de gepubliceerde lijst, moet ik er toegang toe bieden?

We bieden alleen IP-adressen voor de Office 365-servers waarnaar u rechtstreeks moet routeren. Dit is geen uitgebreide lijst met alle IP-adressen waarop u netwerkaanvragen ziet. U ziet netwerkaanvragen voor Microsoft en van derden met de eigenaar, niet gepubliceerd, IP-adressen. Deze IP-adressen worden dynamisch gegenereerd of worden beheerd op basis van een manier die een tijdige kennisgeving voorkomt wanneer ze worden gewijzigd. Als uw firewall geen toegang mag hebben op basis van de FQDN-namen voor deze netwerkaanvragen, gebruikt u een PAC-of WPAD-bestand om de verzoeken te beheren.
  
Zie een IP-adres dat is gekoppeld aan Office 365 waarover u meer informatie wilt?
  
1. Controleer of het IP-adres deel uitmaakt van een groter gepubliceerd bereik met behulp van een CIDR-rekenmachine, zoals deze voor [IPv4](https://www.ipaddressguide.com/cidr) of [IPv6](https://www.ipaddressguide.com/ipv6-cidr). 40.96.0.0/13 bevat bijvoorbeeld het IP-adres 40.103.0.1, ondanks 40,96 niet-overeenkomend 40,103.
2. Kijk of een partner de eigenaar is van het IP-adres met een [WHOIS-query](https://dnsquery.org/). Als dit Microsoft de eigenaar is, is dit een interne partner. Veel netwerkeindpunten voor partners worden weergegeven als de _standaard_ categorie, waarvan de IP-adressen niet worden gepubliceerd.
3. Het IP-adres mag geen deel uitmaken van Office 365 of een afhankelijkheid. De publicatie van Office 365 Network endpoint biedt geen gehele Microsoft-netwerkeindpunten.
4. Controleer het certificaat. Met een browser maakt u verbinding met het IP-adres met behulp van *https:// \<IP_ADDRESS\>* en schakelt u het selectievakje in van de domeinen die zijn gekoppeld aan het IP-adres. Als dit een Microsoft-to-IP-adres is en niet in de lijst met IP-adressen van Office 365, is het waarschijnlijk dat het IP-adres is gekoppeld aan een Microsoft CDN, zoals  *MSOCDN.net*  of een ander Microsoft-domein zonder dat er een IP-informatie is gepubliceerd. Als u het domein voor het certificaat vindt, kunt u het op de hoogte stellen van de naam van het IP-adres.

<a name="bkmk_cname"> </a>
### <a name="some-office-365-urls-point-to-cname-records-instead-of-a-records-in-the-dns-what-do-i-have-to-do-with-the-cname-records"></a>Sommige Office 365-Url's verwijzen naar CNAME-records in plaats van in een record in de DNS. Wat moet ik doen met de CNAME-records?

Client computers moeten een of meer IP-adressen hebben om verbinding te kunnen maken met een cloudservice. Voor sommige Url's in Office 365 worden CNAME-records weergegeven in plaats van een of AAAA-record. Deze CNAME-records zijn in tussen beide gevallen en er kunnen meerdere in een keten staan. Ze worden altijd omgezet in een A-of AAAA-record voor een IP-adres. Kijk bijvoorbeeld naar de volgende reeks DNS-records die uiteindelijk worden omgezet in het IP-adres _IP_1_:

```console
serviceA.office.com -> CNAME: serviceA.domainA.com -> CNAME: serviceA.domainB.com -> A: IP_1
```

Deze CNAME-omleiding is een normaal onderdeel van de DNS en transparant voor de clientcomputer en transparant voor proxyservers. Ze worden gebruikt voor werklast distributie, netwerken voor content levering, hoge beschikbaarheid en risicobeperking voor een service-incident. De intermediaire CNAME-records worden niet gepubliceerd, ze kunnen op elk moment worden gewijzigd en u hoeft ze niet te configureren zoals toegestaan in uw proxyserver.

Een proxyserver valideert de oorspronkelijke URL, die in het bovenstaande voorbeeld is serviceA.office.com, en deze URL werd opgenomen in de publicatie van Office 365. De proxyserver vraagt een DNS-omzetting van die URL naar een IP-adres en ontvangt weer IP_1. De tussenliggende CNAME-omleidings records worden niet gevalideerd.

Configuraties met vaste code of het verkeer op basis van indirecte Office 365 FQDN wordt niet aanbevolen, niet ondersteund door Microsoft, en bekend is dat er problemen met de verbinding met de klant zijn. DNS-oplossingen die op CNAME-omleiding of op andere wijze de DNS-vermeldingen van Office 365 op een andere manier op te lossen, kunnen worden verholpen via DNS Conditional forwarding (scoped to direct used Office 365 FQDN) met DNS-herhalingen ingeschakeld. Tal van producten van derden die door Microsoft worden gebruikt, worden door de configuratie van de [IP-adressen en URL van office 365](microsoft-365-ip-web-service.md)365 aanbevolen.

<a name="bkmk_akamai"> </a>
### <a name="why-do-i-see-names-such-as-nsatcnet-or-akadnsnet-in-the-microsoft-domain-names"></a>Waarom zie ik namen zoals nsatc.net of akadns.net in de Microsoft-domeinnamen?

Office 365 en andere Microsoft-services gebruikmaken van diverse services van derden, zoals Akamai en MarkMonitor, om uw Office 365-ervaring te verbeteren. Om de beste ervaring mogelijk te houden, kunnen we deze services in de toekomst wijzigen. Domeinen van derden kunnen host zijn voor inhoud, zoals een CDN, of ze kunnen host zijn voor een service, zoals een service voor het beheer van de geografische gegevens. Enkele van de services die momenteel worden gebruikt, zijn:
  
[MarkMonitor](https://www.markmonitor.com/) wordt gebruikt wanneer u aanvragen met de operator *\* . nsatc.net* ziet. Deze service biedt bescherming van domeinnamen en beveiliging tegen schadelijk gedrag.
  
[ExactTarget](https://www.marketingcloud.com/) wordt gebruikt wanneer u verzoeken om *\* . ExactTarget.com* ziet. Met deze service kunt u het beheer van e-mail koppelingen tegen kwaadaardige gedrag controleren.
  
[Akamai](https://www.akamai.com/) wordt gebruikt wanneer u aanvragen met een of meer van de volgende FQDN-namen ziet. Deze service biedt geo-DNS en netwerkservices voor content levering.
  
```console
*.akadns.net
*.akam.net
*.akamai.com
*.akamai.net
*.akamaiedge.net
*.akamaihd.net
*.akamaized.net
*.edgekey.net
*.edgesuite.net
```

<a name="bkmk_thirdparty"> </a>
### <a name="i-have-to-have-the-minimum-connectivity-possible-for-office-365"></a>Ik moet de minimaal mogelijke verbindingen voor Office 365

Aangezien Office 365 een groep services is die op hun computer is gebouwd via internet, zijn de belofte betrouwbaarheid en beschikbaarheid gebaseerd op een groot aantal standaard Internet Services. Voorbeeld van een standaard Internet service zoals DNS, CRL en Cdn's moet bereikbaar zijn voor het gebruik van Office 365, net zoals ze moet bereikbaar zijn voor het gebruik van de moderne Internet Services.

De Office 365-Suite is opgesplitst in grote serviceregio's. Dit kan selectief worden ingeschakeld voor verbindingen en er is een gemeenschappelijk gebied, wat een afhankelijkheid is en altijd vereist.

| Service gebied | Beschrijving |
|:-----|:-----|
|**Exchange** <br/> |Exchange Online en Exchange Online Protection <br/> |
|**SharePoint** <br/> |SharePoint Online en OneDrive voor Bedrijven <br/> |
|**Skype voor Bedrijven Online en Microsoft Teams** <br/> |Skype voor bedrijven en Microsoft teams <br/> |
|**Eigenschapnamen** <br/> |Office 365 Pro Plus, Office in een browser, Azure AD en andere veelgebruikte netwerkeindpunten <br/> |

Naast basis Internet Services zijn er ook andere services van derden die uitsluitend voor de integratie van functies gelden. Hoewel deze gegevens nodig zijn voor integratie, worden deze als optioneel gemarkeerd in het artikel Office 365-eindpunten, wat betekent dat de kernfunctionaliteit van de service blijft werken als het eindpunt niet toegankelijk is. Het vereiste kenmerk van een eindpunt voor een netwerk moet zijn ingesteld op waar. Voor elk netwerkeindpunt dat optioneel is, moet het vereiste kenmerk zijn ingesteld op ONWAAR en wordt in het notitie kenmerk de ontbrekende functionaliteit weergegeven, zodat u kunt verwachten dat de verbinding wordt geblokkeerd.
  
Als u Office 365 probeert te gebruiken en de services van derden niet toegankelijk zijn, moet u [ervoor zorgen dat alle FQDN-records die zijn gemarkeerd met vereist of optioneel in dit artikel, worden toegestaan via de proxy en firewall](urls-and-ip-address-ranges.md).
  
<a name="bkmk_consumer"> </a>
### <a name="how-do-i-block-access-to-microsofts-consumer-services"></a>Hoe blokkeer ik de toegang tot consumenten services van Microsoft?

Het beperken van de toegang tot onze consumenten Services moet op eigen risico geschieden. De enige betrouwbare manier om de consumenten service te blokkeren is de toegang tot de  *login.live.com*  -FQDN te beperken. Deze FQDN wordt gebruikt door een uitgebreide set services, waaronder niet-consumenten services zoals MSDN, TechNet en andere. Deze FQDN wordt ook gebruikt door het Secure File Exchange-programma van de Microsoft-ondersteuning en is vereist voor het overbrengen van bestanden om het oplossen van problemen met Microsoft-producten te vereenvoudigen.  Wanneer u de toegang tot deze FQDN beperkt, kan dit ertoe leiden dat ook uitzonderingen moeten worden opgenomen in de regel voor netwerkaanvragen die aan deze services zijn gekoppeld.
  
Houd er rekening mee dat het blokkeren van toegang tot de Microsoft consumenten Services niet voorkomt dat iemand in uw netwerk informatie kan exfiltrate met behulp van een Office 365-Tenant of een andere service.

<a name="bkmk_IPOnlyFirewall"> </a>
### <a name="my-firewall-requires-ip-addresses-and-cannot-process-urls-how-do-i-configure-it-for-office-365"></a>Voor de firewall is een IP-adres vereist en de Url's kunnen niet worden verwerkt. Hoe configureer ik Office voor Office 365?

Office 365 biedt geen IP-adressen van alle vereiste netwerkeindpunten. Sommige worden alleen verstrekt als Url's en zijn gecategoriseerd als standaard. Url's in de standaardcategorie die nodig zijn, moeten worden toegestaan via een proxyserver. Als u geen proxyserver hebt, bekijkt u hoe u webaanvragen hebt geconfigureerd voor Url's die gebruikerstypen in de adresbalk van een webbrowser. de gebruiker biedt geen IP-adres. De standaard Url's van de categorie Office 365 waarbij geen IP-adressen worden opgegeven, worden op dezelfde manier geconfigureerd.

## <a name="related-topics"></a>Verwante onderwerpen

[IP-adres en URL-webservice van Office 365](microsoft-365-ip-web-service.md)

[IP-bereiken van Microsoft Azure Datacenter](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Microsoft Public IP Space](https://www.microsoft.com/download/details.aspx?id=53602)
  
[Vereisten voor de netwerkinfrastructuur voor Microsoft intune](https://docs.microsoft.com/intune/get-started/network-infrastructure-requirements-for-microsoft-intune)
  
[ExpressRoute en Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-power-bi-expressroute/)
  
[URL's en IP-adresbereiken voor Office 365](urls-and-ip-address-ranges.md)
  
[ExpressRoute voor Office 365-connectiviteit beheren](managing-expressroute-for-connectivity.md)
  
[Beginselen voor Office 365-netwerkverbinding](microsoft-365-network-connectivity-principles.md)
