---
title: Office 365-eindpunten beheren
ms.author: kvice
author: kelleyvice-msft
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
description: Meer informatie over het beheren van Office 365-eindpunten, zodat deze werken met de netwerkarchitectuur van uw ondernemingsorganisatie.
ms.openlocfilehash: ea89c263b1d2c89ff49ec7263269afc6030292e8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905114"
---
# <a name="managing-office-365-endpoints"></a>Office 365-eindpunten beheren

De meeste ondernemingsorganisaties met meerdere kantoorlocaties en een verbindings-WAN hebben configuratie nodig voor office 365-netwerkconnectiviteit. U kunt uw netwerk optimaliseren door alle vertrouwde Office 365-netwerkaanvragen rechtstreeks via uw firewall te verzenden en alle aanvullende inspectie of verwerking op pakketniveau te omzeilen. Dit vermindert de latentie en de capaciteitsvereisten voor de perimeter. Het identificeren van Office 365-netwerkverkeer is de eerste stap in het bieden van optimale prestaties voor uw gebruikers. Zie Office [365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md)voor meer informatie.

Microsoft raadt u aan toegang te krijgen tot de Office 365-netwerk-eindpunten en lopende wijzigingen in deze eindpunten met behulp van de [Office 365 IP-adres- en URL-webservice.](microsoft-365-ip-web-service.md)

Ongeacht hoe u het essentiële Office 365-netwerkverkeer beheert, office 365 vereist internetverbinding. Andere netwerk-eindpunten waar verbinding is vereist, worden vermeld bij Aanvullende eindpunten die niet zijn opgenomen in de [Office 365 IP-adres- en URL-webservice.](additional-office365-ip-addresses-and-urls.md)

Hoe u de Office 365-netwerk-eindpunten gebruikt, is afhankelijk van de netwerkarchitectuur van uw ondernemingsorganisatie. In dit artikel worden verschillende manieren beschreven waarop bedrijfsnetwerkarchitectuur kan worden geïntegreerd met IP-adressen en URL's van Office 365. De eenvoudigste manier om te kiezen welke netwerkaanvragen u wilt vertrouwen, is door SD-WAN-apparaten te gebruiken die geautomatiseerde Office 365-configuratie ondersteunen op elk van uw kantoorlocaties.

## <a name="sd-wan-for-local-branch-egress-of-vital-office-365-network-traffic"></a>SD-WAN voor lokale tak van essentieel Office 365-netwerkverkeer

Op elke vestigingslocatie kunt u een SD-WAN-apparaat leveren dat is geconfigureerd voor het routeverkeer voor Office 365 Categorie eindpunten optimaliseren of Categorieën optimaliseren en toestaan rechtstreeks naar het microsoft-netwerk. Ander netwerkverkeer, waaronder on-premises datacenterverkeer, algemeen internetwebsitesverkeer en verkeer naar Office 365 Standaardcategorie-eindpunten, wordt verzonden naar een andere locatie waar u een aanzienlijker netwerkperimeter hebt.

Microsoft werkt samen met SD-WAN-providers om geautomatiseerde configuratie in te stellen. Zie Office [365 Networking Partner Program](microsoft-365-networking-partner-program.md)voor meer informatie.

<a name="pacfiles"> </a>
## <a name="use-a-pac-file-for-direct-routing-of-vital-office-365-traffic"></a>Een PAC-bestand gebruiken voor directe routering van belangrijk Office 365-verkeer

Gebruik PAC- of WPAD-bestanden om netwerkaanvragen te beheren die zijn gekoppeld aan Office 365, maar geen IP-adres hebben. Normale netwerkaanvragen die via een proxy of perimeterapparaat worden verzonden, verhogen de latentie. Hoewel met SSL Break and Inspect de grootste latentie wordt gemaakt, kunnen andere services, zoals proxyverificatie en reputatiezoekactie, slechte prestaties en een slechte gebruikerservaring veroorzaken. Bovendien hebben deze perimeternetwerkapparaten voldoende capaciteit nodig om alle netwerkverbindingsaanvragen te verwerken. Het is raadzaam om uw proxy- of controleapparaten te omzeilen voor directe Office 365-netwerkaanvragen.
  
[PowerShell Gallery Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) is een PowerShell-script dat de meest recente netwerk-eindpunten leest van de Office 365 IP-adres- en URL-webservice en een voorbeeld-PAC-bestand maakt. U kunt het script zo wijzigen dat het wordt geïntegreerd met uw bestaande PAC-bestandsbeheer.

![Verbinding maken met Office 365 via firewalls en proxies.](../media/34d402f3-f502-42a0-8156-24a7c4273fa5.png)

**Afbeelding 1 - Eenvoudige bedrijfsnetwerkperimeter**

Het PAC-bestand wordt geïmplementeerd in webbrowsers op punt 1 in afbeelding 1. Wanneer u een PAC-bestand gebruikt voor direct uittreding van essentieel Office 365-netwerkverkeer, moet u ook connectiviteit toestaan met de IP-adressen achter deze URL's op de firewall van de netwerkperimeter. Dit wordt gedaan door de IP-adressen op te halen voor dezelfde Office 365-eindpuntcategorieën als is opgegeven in het PAC-bestand en firewall-ACL's te maken op basis van deze adressen. De firewall is punt 3 in afbeelding 1.

Afzonderlijk als u ervoor kiest om alleen directe routering te doen voor de categorie-eindpunten optimaliseren, moeten alle vereiste categorie-eindpunten toestaan die u naar de proxyserver verzendt, worden vermeld in de proxyserver om verdere verwerking te omzeilen. SSL-eind- en verificatie van verificatie via proxy's zijn bijvoorbeeld niet compatibel met de eindpunten van de categorie Optimaliseren en Toestaan. De proxyserver is punt 2 in afbeelding 1.

De algemene configuratie is om toe te staan zonder al het uitgaande verkeer van de proxyserver te verwerken voor de doel-IP-adressen voor Office 365-netwerkverkeer dat de proxyserver raakt. Zie Netwerkapparaten of oplossingen van derden gebruiken voor [Office 365-verkeer](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365)voor informatie over problemen met SSL Break and Inspect.

Er zijn twee typen PAC-bestanden die door het Get-PacFile worden gegenereerd.

| Type | Beschrijving |
|:-----|:-----|
|**1** <br/> |Verzend Het endpoint-verkeer rechtstreeks optimaliseren en al het andere naar de proxyserver. <br/> |
|**2** <br/> |Send Optimize and Allow endpoint traffic direct and everything else to the proxy server. Dit type kan ook worden gebruikt om alle ondersteunde ExpressRoute voor Office 365-verkeer naar ExpressRoute-netwerksegmenten en al het andere naar de proxyserver te verzenden. <br/> |

Hier is een eenvoudig voorbeeld van het aanroepen van het PowerShell-script:

```powershell
Get-PacFile -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

Er zijn veel parameters die u aan het script kunt doorgeven:

| Parameter | Beschrijving |
|:-----|:-----|
|**ClientRequestId** <br/> |Dit is vereist en is een GUID die is doorgegeven aan de webservice die de clientmachine vertegenwoordigt die de oproep doet. <br/> |
|**Exemplaar** <br/> |Het Office 365-service-exemplaar, dat standaard is ingesteld op Worldwide. Dit wordt ook doorgegeven aan de webservice. <br/> |
|**TenantName** <br/> |De naam van uw Office 365-tenant. Doorgegeven aan de webservice en gebruikt als vervangbare parameter in sommige OFFICE 365-URL's. <br/> |
|**Type** <br/> |Het type proxy PAC-bestand dat u wilt genereren. <br/> |

Hier is nog een voorbeeld van het aanroepen van het PowerShell-script met extra parameters:

```powershell
Get-PacFile -Type 2 -Instance Worldwide -TenantName Contoso -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

## <a name="proxy-server-bypass-processing-of-office-365-network-traffic"></a>Proxyserver omzeilt verwerking van Office 365-netwerkverkeer

Als PAC-bestanden niet worden gebruikt voor direct uitgaand verkeer, wilt u de verwerking op de netwerkperimeter omzeilen door de proxyserver te configureren. Sommige leveranciers van proxyservers hebben de geautomatiseerde configuratie van deze configuratie ingeschakeld, zoals beschreven in het [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md).

Als u dit handmatig doet, moet u de categoriegegevens voor eindpunten optimaliseren en toestaan van de Office 365 IP-adres- en URL-webservice downloaden en de proxyserver configureren om de verwerking hiervoor te omzeilen. Het is belangrijk om SSL-einden en verificatie van verificatie via verificatie van proxy's voor de categorie-eindpunten optimaliseren en toestaan te voorkomen.
  
<a name="bkmk_changes"> </a>
## <a name="change-management-for-office-365-ip-addresses-and-urls"></a>Wijzigingsbeheer voor IP-adressen en URL's van Office 365

Naast het selecteren van de juiste configuratie voor de netwerkperimeter, is het essentieel dat u een wijzigingsbeheerproces voor Office 365-eindpunten goedkeurt. Deze eindpunten worden regelmatig gewijzigd en als u de wijzigingen niet beheert, kunt u gebruikers blokkeren of slecht presteren nadat een nieuw IP-adres of URL is toegevoegd.

Wijzigingen in de IP-adressen en URL's van Office 365 worden meestal gepubliceerd op de laatste dag van elke maand. Soms wordt een wijziging buiten die planning gepubliceerd vanwege operationele, ondersteunings- of beveiligingsvereisten.

Wanneer een wijziging wordt gepubliceerd waarin u moet handelen omdat er een IP-adres of URL is toegevoegd, moet u verwachten dat u 30 dagen van de melding ontvangt vanaf het moment dat we de wijziging publiceren totdat er een Office 365-service op dat eindpunt staat. Hoewel we streven naar deze meldingsperiode, is dit mogelijk niet altijd mogelijk vanwege operationele, ondersteunings- of beveiligingsvereisten. Wijzigingen waarvoor geen onmiddellijke actie nodig is om de verbinding te behouden, zoals verwijderde IP-adressen of URL's of minder belangrijke wijzigingen, omvatten geen melding vooraf. Ongeacht de melding die wordt verstrekt, wordt de verwachte actieve servicedatum voor elke wijziging vermeld.

### <a name="change-notification-using-the-web-service"></a>Melding wijzigen met de webservice

U kunt de Office 365 IP-adres- en URL-webservice gebruiken om een wijzigingsmelding te ontvangen. U wordt aangeraden de **webmethode /versie** eenmaal per uur te bellen om de versie van de eindpunten te controleren die u gebruikt om verbinding te maken met Office 365. Als deze versie verandert ten opzichte van de versie die u gebruikt, moet u de meest recente eindpuntgegevens van de **webmethode /eindpunten** krijgen en desgewenst de verschillen krijgen van de **webmethode /changes.** Het is niet nodig om de **webmethoden /eindpunten** of **/wijzigingen** te bellen als er geen wijziging is aangebracht in de versie die u hebt gevonden.

Zie IP-adres en URL-webservice [van Office 365](microsoft-365-ip-web-service.md)voor meer informatie.

### <a name="change-notification-using-rss-feeds"></a>Melding wijzigen met RSS-feeds

De Office 365 IP-adres- en URL-webservice biedt een RSS-feed waarop u zich kunt abonneren in Outlook. Er zijn koppelingen naar de RSS-URL's op elk van de office 365-service-exemplaarspecifieke pagina's voor de IP-adressen en URL's. Zie IP-adres en URL-webservice [van Office 365](microsoft-365-ip-web-service.md)voor meer informatie.

### <a name="change-notification-and-approval-review-using-microsoft-flow"></a>Meldings- en goedkeuringsbeoordeling wijzigen met Microsoft Flow

We begrijpen dat u mogelijk nog steeds handmatige verwerking nodig hebt voor netwerk-eindpuntwijzigingen die elke maand worden doorgevoerd. U kunt Microsoft Flow gebruiken om een stroom te maken die u per e-mail op de hoogte stelt en desgewenst een goedkeuringsproces voor wijzigingen voert wanneer office 365-netwerk-eindpunten wijzigingen hebben. Nadat de controle is voltooid, kunt u de stroom automatisch een e-mail sturen naar de wijzigingen in uw firewall- en proxyserverbeheerteam.

Zie Microsoft Flow gebruiken om een e-mail te ontvangen voor wijzigingen in IP-adressen en URL's van [Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/td-p/240651)voor informatie over een voorbeeld en sjabloon van Microsoft Flow.
  
<a name="FAQ"> </a>
## <a name="office-365-network-endpoints-faq"></a>Veelgestelde vragen over office 365-netwerk-eindpunten

Bekijk deze veelgestelde vragen over office 365-netwerkconnectiviteit.
  
### <a name="how-do-i-submit-a-question"></a>Hoe kan ik een vraag indienen?

Klik op de koppeling onderaan om aan te geven of het artikel nuttig was of niet en stuur aanvullende vragen in. We controleren de feedback en werken de vragen hier bij met de meestgestelde vragen.
  
### <a name="how-do-i-determine-the-location-of-my-tenant"></a>Hoe bepaal ik de locatie van mijn tenant?

 **Tenantlocatie** wordt het best bepaald met behulp van onze [datacenterkaart.](./o365-data-locations.md)
  
### <a name="am-i-peering-appropriately-with-microsoft"></a>Peering ik op de juiste manier met Microsoft?

 **Peeringlocaties** worden in meer detail beschreven in [peering met Microsoft.](https://www.microsoft.com/peering)
  
Met meer dan 2500 peeringrelaties van internetproviders wereldwijd en 70 aanwezigheidspunten, moet het naadloos zijn om van uw netwerk naar het onze te gaan. Het kan geen kwaad om een paar minuten te besteden om ervoor te zorgen dat de peeringrelatie van uw isp het meest optimaal [is.](/archive/blogs/onthewire/__guidance) Hier zijn enkele voorbeelden van goede en minder goede peering hand-offs voor ons netwerk.
  
<a name="bkmk_MissingIP"> </a>
### <a name="i-see-network-requests-to-ip-addresses-not-on-the-published-list-do-i-need-to-provide-access-to-them"></a>Ik zie netwerkaanvragen voor IP-adressen die niet in de gepubliceerde lijst staan, moet ik daar toegang toe geven?

We bieden alleen IP-adressen voor de Office 365-servers waar u rechtstreeks naar moet door routen. Dit is geen uitgebreide lijst met alle IP-adressen waar u netwerkaanvragen voor ziet. U ziet netwerkaanvragen voor Microsoft en niet-gepubliceerde IP-adressen van derden. Deze IP-adressen worden dynamisch gegenereerd of beheerd op een manier die tijdige kennisgeving voorkomt wanneer deze worden gewijzigd. Als uw firewall geen toegang kan toestaan op basis van de FQDN's voor deze netwerkaanvragen, gebruikt u een PAC- of WPAD-bestand om de aanvragen te beheren.
  
Ziet u een IP-adres dat is gekoppeld aan Office 365 waar u meer informatie over wilt?
  
1. Controleer of het IP-adres is opgenomen in een groter gepubliceerd bereik met behulp van een CIDR-rekenmachine, zoals deze voor [IPv4](https://www.ipaddressguide.com/cidr) of [IPv6.](https://www.ipaddressguide.com/ipv6-cidr) 40.96.0.0/13 bevat bijvoorbeeld het IP-adres 40.103.0.1, ondanks dat 40,96 niet overeenkomt met 40.103.
2. Kijk of een partner eigenaar is van het IP-adres met een [whois-query.](https://dnsquery.org/) Als microsoft eigenaar is, kan het een interne partner zijn. Veel partnernetwerk-eindpunten worden vermeld als behorend tot de _standaardcategorie,_ waarvoor IP-adressen niet worden gepubliceerd.
3. Het IP-adres maakt mogelijk geen deel uit van Office 365 of een afhankelijkheid. De publicatie van office 365-netwerk eindpunten bevat niet alle microsoft-netwerk-eindpunten.
4. Controleer het certificaat. Maak met een browser verbinding *\<IP_ADDRESS\>* met het IP-adres met HTTPS:// en controleer de domeinen in het certificaat om te begrijpen welke domeinen aan het IP-adres zijn gekoppeld. Als het een IP-adres van Microsoft is en niet in de lijst met IP-adressen van Office 365 staat, is het IP-adres waarschijnlijk gekoppeld aan een Microsoft CDN, zoals  *MSOCDN.NET of*  een ander Microsoft-domein zonder gepubliceerde IP-gegevens. Als u vindt dat het domein op het certificaat een domein is waarin we beweren dat het IP-adres wordt vermeld, laat het ons dan weten.

<a name="bkmk_cname"> </a>
### <a name="some-office-365-urls-point-to-cname-records-instead-of-a-records-in-the-dns-what-do-i-have-to-do-with-the-cname-records"></a>Sommige OFFICE 365-URL's wijzen naar CNAME-records in plaats van A-records in de DNS. Wat heb ik te maken met de CNAME-records?

Clientcomputers hebben een DNS A- of AAAA-record t)hat nodig, inclusief een of meer IP-adres(es) om verbinding te maken met een cloudservice. Sommige URL's in Office 365 tonen CNAME-records in plaats van A- of AAAA-records. Deze CNAME-records zijn tussenpersoon en er kunnen meerdere in een keten zijn. Ze worden uiteindelijk altijd opgelost in een A- of AAAA-record voor een IP-adres. Denk bijvoorbeeld aan de volgende reeks DNS-records, die uiteindelijk worden opgelost in het _IP-IP_1:_

```console
serviceA.office.com -> CNAME: serviceA.domainA.com -> CNAME: serviceA.domainB.com -> A: IP_1
```

Deze CNAME-omleidingen zijn een normaal onderdeel van de DNS en zijn transparant voor de clientcomputer en transparant voor proxyservers. Ze worden gebruikt voor taakverdeling, netwerken voor inhoudsbezorging, hoge beschikbaarheid en beperking van service-incidenten. Microsoft publiceert de tussenliggende CNAME-records niet, ze kunnen op elk moment worden gewijzigd en u hoeft ze niet te configureren zoals toegestaan op uw proxyserver.

Een proxyserver valideert de oorspronkelijke URL, die in het bovenstaande voorbeeld serviceA.office.com, en deze URL zou worden opgenomen in office 365-publicatie. De proxyserver vraagt om DNS-resolutie van die URL naar een IP-adres en ontvangt deze IP_1. De tussenliggende CNAME-omleidingsrecords worden niet gevalideerd.

Hard gecodeerde configuraties of whitelisting op basis van indirecte Office 365 FQDN's worden niet aanbevolen, worden niet ondersteund door Microsoft en zijn bekend dat ze problemen met de klantverbinding veroorzaken. DNS-oplossingen die de omleiding van CNAME blokkeren of die anders de DNS-items van Office 365 onjuist oplossen, kunnen worden opgelost via DNS-doorst forwarders waarbij DNS-recursie is ingeschakeld of door DNS-hoofdhints te gebruiken. Veel externe netwerkperimeterproducten integreren inheems aanbevolen whitelisting van Office 365-eindpunten in hun configuratie met behulp van de [Office 365 IP-adres- en URL-webservice.](microsoft-365-ip-web-service.md)

<a name="bkmk_akamai"> </a>
### <a name="why-do-i-see-names-such-as-nsatcnet-or-akadnsnet-in-the-microsoft-domain-names"></a>Waarom zie ik namen zoals nsatc.net of akadns.net in de Microsoft-domeinnamen?

Office 365 en andere Microsoft-services gebruiken verschillende services van derden, zoals Akamai en MarkMonitor, om uw Office 365-ervaring te verbeteren. Om u de best mogelijke ervaring te blijven bieden, kunnen we deze services in de toekomst wijzigen. Domeinen van derden kunnen inhoud hosten, zoals een CDN, of ze kunnen een service hosten, zoals een geografische verkeersbeheerservice. Enkele services die momenteel worden gebruikt, zijn:
  
[MarkMonitor](https://www.markmonitor.com/) wordt gebruikt wanneer u aanvragen ziet met *\* .nsatc.net.* Deze service biedt domeinnaambeveiliging en -monitoring om te beschermen tegen schadelijk gedrag.
  
[ExactTarget](https://www.marketingcloud.com/) wordt gebruikt wanneer u aanvragen voor *\* .exacttarget.com.* Deze service biedt beheer van e-mailkoppelingen en monitoring tegen schadelijk gedrag.
  
[Akamai](https://www.akamai.com/) wordt gebruikt wanneer u aanvragen ziet met een van de volgende FQDN's. Deze service biedt netwerkservices voor geo-DNS en inhoudslevering.
  
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
### <a name="i-have-to-have-the-minimum-connectivity-possible-for-office-365"></a>Ik moet de minimale connectiviteit hebben die mogelijk is voor Office 365

Aangezien Office 365 een suite met services is die is gebouwd voor gebruik via internet, zijn de beloften voor betrouwbaarheid en beschikbaarheid gebaseerd op veel standaardinternetservices die beschikbaar zijn. Standaardinternetservices zoals DNS, CRL en CDN's moeten bijvoorbeeld bereikbaar zijn om Office 365 te kunnen gebruiken, net zoals ze bereikbaar moeten zijn om de meeste moderne internetservices te kunnen gebruiken.

De Office 365-suite is onderverdeeld in belangrijke servicegebieden. Deze kunnen selectief worden ingeschakeld voor connectiviteit en er is een gemeenschappelijk gebied, dat een afhankelijkheid voor iedereen is en altijd vereist is.

| Servicegebied | Beschrijving |
|:-----|:-----|
|**Exchange** <br/> |Exchange Online en Exchange Online Protection <br/> |
|**SharePoint** <br/> |SharePoint Online en OneDrive voor Bedrijven <br/> |
|**Skype voor Bedrijven Online en Microsoft Teams** <br/> |Skype voor Bedrijven en Microsoft Teams <br/> |
|**Veelvoorkomende** <br/> |Office 365 Pro Plus, Office in een browser, Azure AD en andere veelgebruikte netwerk-eindpunten <br/> |

Naast basisinternetservices zijn er services van derden die alleen worden gebruikt om functionaliteit te integreren. Hoewel deze nodig zijn voor integratie, worden ze gemarkeerd als optioneel in het Office 365-eindpunten-artikel, wat betekent dat de kernfunctionaliteit van de service blijft functioneren als het eindpunt niet toegankelijk is. Elk netwerk-eindpunt dat vereist is, heeft het vereiste kenmerk ingesteld op waar. Elk netwerk-eindpunt dat optioneel is, heeft het vereiste kenmerk ingesteld op onwaar en het notitiekenmerk bevat de ontbrekende functionaliteit die u mag verwachten als de verbinding wordt geblokkeerd.
  
Als u Office 365 probeert te gebruiken en vindt dat services van derden niet toegankelijk zijn, wilt u ervoor zorgen dat alle [FQDN's](urls-and-ip-address-ranges.md)die zijn gemarkeerd als vereist of optioneel in dit artikel zijn toegestaan via de proxy en firewall.
  
<a name="bkmk_consumer"> </a>
### <a name="how-do-i-block-access-to-microsofts-consumer-services"></a>Hoe blokkeer ik de toegang tot de consumentenservices van Microsoft?

Het beperken van de toegang tot onze consumentenservices moet op eigen risico worden uitgevoerd. De enige betrouwbare manier om consumentenservices te blokkeren, is door de toegang tot de  *login.live.com*  FQDN te beperken. Deze FQDN wordt gebruikt door een breed scala aan services, waaronder niet-consumentenservices zoals MSDN, TechNet en andere. Deze FQDN wordt ook gebruikt door het Secure File Exchange-programma van Microsoft Support en is nodig om bestanden over te zetten om het oplossen van problemen voor Microsoft-producten te vergemakkelijken.  Als u de toegang tot deze FQDN beperkt, kan het nodig zijn om ook uitzonderingen op de regel op te nemen voor netwerkaanvragen die aan deze services zijn gekoppeld.
  
Houd er rekening mee dat het blokkeren van de toegang tot de Microsoft-consumentenservices alleen niet verhindert dat iemand in uw netwerk gegevens kan exfiltreren met een Office 365-tenant of een andere service.

<a name="bkmk_IPOnlyFirewall"> </a>
### <a name="my-firewall-requires-ip-addresses-and-cannot-process-urls-how-do-i-configure-it-for-office-365"></a>Voor mijn firewall zijn IP-adressen vereist en kunnen URL's niet worden verwerkt. Hoe configureer ik deze voor Office 365?

Office 365 biedt geen IP-adressen van alle vereiste netwerk-eindpunten. Sommige zijn alleen beschikbaar als URL's en worden als standaard gecategoriseerd. URL's in de standaardcategorie die vereist zijn, moeten worden toegestaan via een proxyserver. Als u geen proxyserver hebt, bekijkt u hoe u webaanvragen hebt geconfigureerd voor URL's die gebruikers in de adresbalk van een webbrowser typen. de gebruiker geeft ook geen IP-adres op. De STANDAARDCATEGORIE-URL's van Office 365 die geen IP-adressen bieden, moeten op dezelfde manier worden geconfigureerd.

## <a name="related-topics"></a>Verwante onderwerpen

[IP-adres en URL-webservice van Office 365](microsoft-365-ip-web-service.md)

[IP-bereiken van Microsoft Azure Datacenter](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Microsoft Public IP Space](https://www.microsoft.com/download/details.aspx?id=53602)
  
[Netwerkinfrastructuurvereisten voor Microsoft Intune](/intune/get-started/network-infrastructure-requirements-for-microsoft-intune)
  
[ExpressRoute en Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-power-bi-expressroute/)
  
[URL's en IP-adresbereiken voor Office 365](urls-and-ip-address-ranges.md)
  
[ExpressRoute voor Office 365-connectiviteit beheren](managing-expressroute-for-connectivity.md)
  
[Beginselen voor Office 365-netwerkverbinding](microsoft-365-network-connectivity-principles.md)