---
title: Stap 2. Optimale netwerken voor uw Microsoft 365 voor enterprise-tenants
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Optimaliseer de netwerktoegang tot uw Microsoft 365-tenants.
ms.openlocfilehash: 5eac0793d2afc924a919671ffa105362ea1866d9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407190"
---
# <a name="step-2-optimal-networking-for-your-microsoft-365-for-enterprise-tenants"></a>Stap 2. Optimale netwerken voor uw Microsoft 365 voor enterprise-tenants

Microsoft 365 voor ondernemingen bevat apps voor cloudproductiviteit zoals Teams en Exchange Online, en Microsoft Intune, samen met veel identiteits- en beveiligingsservices van Microsoft Azure. Al deze cloudservices zijn afhankelijk van de beveiliging, prestaties en betrouwbaarheid van verbindingen vanaf clientapparaten op uw on-premises netwerk of een locatie op internet. 

Als u de netwerktoegang voor uw tenant wilt optimaliseren, moet u:

- Optimaliseer het pad tussen uw on-premises gebruikers en de dichtstbijzijnde locatie voor het globale netwerk van Microsoft.
- Optimaliseer de toegang tot het globale Microsoft-netwerk voor externe gebruikers die een VPN-oplossing voor externe toegang gebruiken.
- Gebruik Network Insights om de netwerkperimeter voor uw kantoorlocaties te ontwerpen.
- Optimaliseer de toegang tot specifieke assets die worden gehost op SharePoint-sites met het Office 365-CDN.
- Proxy- en netwerkrandapparaten configureren om de verwerking van vertrouwd verkeer in Microsoft 365 te omzeilen met de lijst met eindpunten en het bijwerken van de lijst te automatiseren wanneer wijzigingen worden aangebracht.

## <a name="enterprise-on-premises-workers"></a>On-premises werknemers voor ondernemingen

Voor bedrijfsnetwerken moet u de eindgebruikerservaring optimaliseren door de beste netwerktoegang in te stellen tussen clients en de dichtstbijzijnde Microsoft 365-eindpunten. De kwaliteit van de eindgebruikerservaring is rechtstreeks gerelateerd aan de prestaties en reactiesnelheid van de toepassing die de gebruiker gebruikt. Microsoft Teams is bijvoorbeeld afhankelijk van lage latentie, zodat telefoongesprekken, vergaderingen en samenwerkingen via gedeelde schermen storingenloos zijn.

Het primaire doel in het netwerkontwerp moet zijn om de latentie te minimaliseren door de retourtijd (RTT) te verkorten van clientapparaten naar het wereldwijde Netwerk van Microsoft, de openbare netwerk backbone van Microsoft die alle datacenters van Microsoft verbindt met een lage latentie, toegangspunten voor cloudtoepassing met hoge beschikbaarheid, ook wel front doorsprekjes genoemd, verspreid over de hele wereld.

Hier is een voorbeeld van een traditioneel bedrijfsnetwerk.

![Een traditioneel bedrijfsnetwerk met centrale toegang tot internet](../media/tenant-management-overview/tenant-management-networking-traditional.png)

In deze afbeelding maken filialen verbinding met een centraal kantoor via WAN-apparaten (Wide Area Network) en een WAN-backbone. Internettoegang gaat via een beveiligings- of proxyapparaat aan de netwerkrand van het centrale kantoor en via een internetprovider. Op internet heeft het wereldwijde Microsoft-netwerk een aantal front door in regio's over de hele wereld. Organisaties kunnen ook tussenliggende locaties gebruiken voor extra pakketverwerking en beveiliging voor verkeer. De Microsoft 365-tenant van een organisatie bevindt zich in het wereldwijde Microsoft-netwerk.

De problemen met deze configuratie voor Microsoft 365-cloudservices zijn:

- Voor gebruikers in filialen wordt verkeer verzonden naar niet-lokale fronten, waardoor de latentie toeneemt.
- Als u verkeer naar tussenliggende locaties stuurt, maakt u netwerk hairpins die dubbele pakketverwerking uitvoeren op vertrouwd verkeer, waardoor de latentie toeneemt.
- Netwerkrandapparaten voeren onnodige en dubbele pakketverwerking uit op vertrouwd verkeer, met grotere latentie.

Het optimaliseren van de prestaties van het Microsoft 365-netwerk hoeft niet ingewikkeld te zijn. U krijgt de best mogelijke prestaties door enkele belangrijke principes te volgen:

- Identificeer Microsoft 365-netwerkverkeer, dat vertrouwd verkeer bestemd is voor Microsoft-cloudservices.
- Sta lokaal vertakkingsverkeer van Het Microsoft 365-netwerkverkeer naar internet toe vanaf elke locatie waar gebruikers verbinding maken met Microsoft 365.
- Voorkom netwerk hairpins.
- Sta Microsoft 365-verkeer toe dat proxies en pakketcontroleapparaten worden overgeslagen.

Als u deze principes implementeert, krijgt u een bedrijfsnetwerk dat is geoptimaliseerd voor Microsoft 365.

![Een bedrijfsnetwerk geoptimaliseerd voor Microsoft 365](../media/tenant-management-overview/tenant-management-networking-optimized.png)

In deze afbeelding hebben filialen een eigen internetverbinding via een software-gedefinieerd WAN-apparaat (SDWAN), waarmee vertrouwd Microsoft 365-verkeer wordt doorverbeld naar de dichtstbijzijnde front door de regio. Bij het centrale kantoor worden met het vertrouwde Microsoft 365-verkeer de beveiliging of het proxyapparaat overgeslagen en worden tussenliggende apparaten niet meer gebruikt.

De geoptimaliseerde configuratie lost als volgende de latentieproblemen van een traditioneel bedrijfsnetwerk op:

- Vertrouwd Microsoft 365-verkeer slaat de WAN-backbone over en wordt voor alle kantoren naar lokale deuren verzonden, met afnemende latentie.
- Netwerk hairpins die dubbele pakketverwerking uitvoeren, worden overgeslagen voor vertrouwd microsoft 365-verkeer, afnemende latentie.
- Netwerkrandapparaten die onnodige en dubbele pakketverwerking uitvoeren, worden overgeslagen voor vertrouwd verkeer in Microsoft 365, met afnemende latentie.

Zie het overzicht van [de Microsoft 365-netwerkconnectiviteit voor meer informatie.](../enterprise/microsoft-365-networking-overview.md)

## <a name="remote-workers"></a>Externe werknemers

Als uw externe medewerkers een traditionele VPN-client gebruiken om extern toegang te krijgen tot uw bedrijfsnetwerk, verifieer dan dat de VPN-client split tunneling ondersteunt. Zonder split tunneling wordt al uw externe werk verzonden via de VPN-verbinding, terwijl het moet worden doorgestuurd naar de edge-apparaten van uw bedrijf, worden verwerkt en dan verzonden op internet. Hier volgt een voorbeeld.

![Netwerkverkeer van VPN-clients zonder tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

In deze afbeelding moet Microsoft 365-verkeer een indirecte route nemen via uw organisatie, die kan worden doorgestuurd naar een front door het globale netwerk van Microsoft ver weg van de fysieke locatie van de VPN-client. Met dit indirecte pad wordt een vertraging toegevoegd aan het netwerkverkeer en wordt de algehele prestatie negatief beïnvloed.  

Met split tunneling kunt u uw VPN-client zo configureren dat specifieke typen verkeer niet via de VPN-verbinding naar het bedrijfsnetwerk worden verzonden.

Configureer uw split tunneling VPN-clients zodanig dat verkeer wordt uitgesloten naar de Microsoft 365-eindpuntcategorie **Optimaliseren** over de VPN-verbinding om toegang tot Microsoft 365-cloudresources te optimaliseren. Zie office [365-eindpuntcategorieën](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) en de lijsten [van](../enterprise/microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) Categorie-eindpunten optimaliseren voor gesplitste tunneling voor meer informatie.

Hier is de resulterende verkeersstroom voor gesplitste tunneling, waarin het meeste verkeer naar Microsoft 365-cloud-apps de VPN-verbinding omzeilt.

![Netwerkverkeer van VPN-clients met tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

In deze afbeelding verstuurt en ontvangt de VPN-client essentieel Microsoft 365-cloudserviceverkeer rechtstreeks via internet en naar de dichtstbijzijnde front door naar het globale netwerk van Microsoft.

Bekijk [Office 365-connectiviteit optimaliseren voor externe gebruikers met VPN-split-tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md) voor meer informatie en richtlijnen.

## <a name="using-network-insights-preview"></a>Network Insights (preview) gebruiken

Netwerkinzichten zijn prestatiestatistieken die worden verzameld via uw Microsoft 365-tenant, zodat u de netwerkperimeters voor uw kantoorlocaties kunt ontwerpen. Elk inzicht biedt livedetails over de prestatiekenmerken voor een opgegeven probleem voor elke geografische locatie waar on-premises gebruikers toegang hebben tot uw tenant.

Er kunnen twee netwerkinzichten op tenantniveau worden weergegeven voor de tenant:

- [Voorbeeldverbindingen van Exchange die zijn beïnvloed door verbindingsproblemen](../enterprise/office-365-network-mac-perf-insights.md#exchange-sampled-connections-impacted-by-connectivity-issues)
- [Voorbeeldverbindingen in SharePoint die zijn beïnvloed door verbindingsproblemen](../enterprise/office-365-network-mac-perf-insights.md#sharepoint-sampled-connections-impacted-by-connectivity-issues)

Dit zijn de specifieke netwerkinzichten voor elke kantoorlocatie:

- [Backgressie van netwerk](../enterprise/office-365-network-mac-perf-insights.md#backhauled-network-egress)
- [Betere prestaties gedetecteerd voor klanten bij u in de buurt](../enterprise/office-365-network-mac-perf-insights.md#better-performance-detected-for-customers-near-you)
- [Gebruik van een niet-optimale voorzijde van Exchange Online-service](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-exchange-online-service-front-door)
- [Gebruik van een niet-optimale front door de SharePoint Online-service](../enterprise/office-365-network-mac-perf-insights.md#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [Lage downloadsnelheid van SharePoint-front door](../enterprise/office-365-network-mac-perf-insights.md#low-download-speed-from-sharepoint-front-door)
- [Optimaal netwerkingressie china-gebruiker](../enterprise/office-365-network-mac-perf-insights.md#china-user-optimal-network-egress)

>[!IMPORTANT]
>Netwerkinzichten, prestatieaanbevelingen en beoordelingen in het Microsoft 365-beheercentrum worden momenteel weergegeven als preview-status. Het is alleen beschikbaar voor Microsoft 365-tenants die zijn ingeschreven voor het feature preview-programma.

Zie [Microsoft 365 Network Insights](../enterprise/office-365-network-mac-perf-insights.md)voor meer informatie.

## <a name="sharepoint-performance-with-the-office-365-cdn"></a>Prestaties van SharePoint met het Office 365-CDN

Met een cdn (Content Delivery Network) in de cloud kunt u laadtijden verminderen, bandbreedte besparen en sneller reageren. Een CDN verbetert de prestaties door statische assets, zoals grafische of videobestanden, dichter bij de browsers waarin u ze aanvraagt, in de map op te slaan, om downloads te versnellen en de latentie te verminderen. U kunt het ingebouwde Office 365 Content Delivery Network (CDN), dat deel uit maakt van SharePoint in Microsoft 365 E3 en E5, gebruiken om statische assets te hosten voor betere prestaties voor uw SharePoint-pagina's.

Het Office 365-CDN bestaat uit meerdere CDN's waarmee u statische assets op meerdere locaties of _origins_ kunt hosten en deze kunt gebruiken vanuit globale netwerken met hoge snelheid. Afhankelijk van het type inhoud dat u wilt hosten in het Office  365-CDN, kunt u openbare origins,  persoonlijke origins of beide toevoegen.

Als deze zijn geïmplementeerd en geconfigureerd, worden assets van openbare en persoonlijke origins geüpload door het Office 365-CDN en worden deze beschikbaar gemaakt voor snelle toegang tot gebruikers op internet.

![Office 365 CDN geïmplementeerd voor gebruikers](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN geïmplementeerd voor gebruikers")

Zie het [Office 365-CDN gebruiken met SharePoint Online voor meer informatie.](../enterprise/use-microsoft-365-cdn-with-spo.md)

## <a name="automated-endpoint-listing"></a>Vermelding van geautomatiseerd eindpunt

Als u wilt dat de verwerking van vertrouwd Microsoft 365-verkeer wordt overgeslagen door uw on-premises clients, randapparaten en cloudgebaseerde pakketanalyseservices, moet u deze configureren met de set eindpunten (IP-adresbereiken en DNS-namen) die overeenkomen met Microsoft 365-services. Deze eindpunten kunnen handmatig worden geconfigureerd in firewalls en andere randbeveiligingsapparaten, PAC-bestanden voor clientcomputers om proxies te omzeilen of SD-WAN-apparaten in filialen. De eindpunten veranderen echter na enige tijd, waardoor op deze locaties voortdurend handmatig onderhoud van de eindpuntenlijsten moet worden vereist.

Gebruik de OFFICE [365-webservice MET IP-adres](../enterprise/microsoft-365-ip-web-service.md)en URL als u het beheer van vermeldingen en wijzigingsbeheer voor Microsoft 365-eindpunten in uw PAC-clientbestanden en -netwerkapparaten wilt automatiseren. Met deze service kunt u Microsoft 365-netwerkverkeer beter identificeren en onderscheiden, zodat u eenvoudiger de meest recente wijzigingen kunt evalueren, configureren en op de hoogte blijven.

U kunt PowerShell, Python of andere talen gebruiken om de wijzigingen in eindpunten na een periode te bepalen en uw PAC-bestanden en edge-netwerkapparaten te configureren.

De basisprocedure 2010 2016 is:

1. Gebruik de Webservice voor IP-adres en URL van Office 365 en het configuratiemechanisme van uw keuze om uw PAC-bestanden en netwerkapparaten te configureren met de huidige set Microsoft 365-eindpunten.
2. Voer een dagelijks terugkerend bericht uit om te controleren op wijzigingen in de eindpunten of gebruik een meldingsmethode.
3. Wanneer wijzigingen worden gedetecteerd, kunt u het PAC-bestand opnieuw toevoegen en opnieuw distribueren voor clientcomputers en de wijzigingen aanbrengen op uw netwerkapparaten.

Zie de Webservice voor IP-adressen en [URL's van Office 365 voor meer informatie.](../enterprise/microsoft-365-ip-web-service.md)

## <a name="results-of-step-2"></a>Resultaten van stap 2

Voor uw Microsoft 365-tenant met optimale netwerken hebt u de volgende mogelijkheden:

- Netwerkprestaties optimaliseren voor on-premises gebruikers door internetverbindingen toe te voegen aan alle filialen en netwerk hairpins te verwijderen.
- How to implement automated trusted endpoint listing for your client-based PAC files and your network devices and services, including ongoing updates (most suitable for enterprise networks).
- Ondersteuning van de toegang van externe medewerkers tot on-premises resources.
- Netwerkinzichten gebruiken
- Het Implementeren van het Office 365-CDN.

Hier is een voorbeeld van een ondernemingsorganisatie en de tenant met optimale netwerken.

![Voorbeeld van een tenant met optimale netwerken](../media/tenant-management-overview/tenant-management-tenant-build-step2.png)

[Een grotere versie van deze afbeelding bekijken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-management-overview/tenant-management-tenant-build-step2.png)

In deze afbeelding heeft de tenant voor deze organisatie het volgende:

- Lokale internetverbinding voor elke filialen met een SDWAN-apparaat dat vertrouwd Microsoft 365-verkeer doorsturen naar een lokale front door.
- Geen netwerk hairpins.
- Beveiligings- en proxyrandapparaten van Centraal kantoor die vertrouwd verkeer van Microsoft 365 doorsturen naar een lokale front door.

## <a name="ongoing-maintenance-for-optimal-networking"></a>Doorlopend onderhoud voor optimaal netwerken

Oplopende basis moet u mogelijk het volgende doen:

- Werk uw randapparaten en geïmplementeerde PAC-bestanden bij voor wijzigingen in eindpunten of controleer of het geautomatiseerde proces correct werkt.
- Beheer uw assets in het Office 365-CDN.
- Werk de configuratie van gesplitste tunneling in uw VPN-clients bij voor wijzigingen in eindpunten.

## <a name="next-step"></a>Volgende stap

[![Stap 3. Uw identiteiten synchroniseren en veilige aanmeldingen afdwingen](../media/tenant-management-overview/tenant-management-step-grid-identity.png)](tenant-management-identity.md)

Ga verder [met identiteit om](tenant-management-identity.md) uw on-premises accounts en groepen te synchroniseren en veilige aanmeldingen voor gebruikers af te dwingen.
