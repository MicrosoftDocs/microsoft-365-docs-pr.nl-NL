---
title: Microsoft 365-netwerkverbindingen evalueren
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365 is ontworpen om klanten over de hele wereld in staat te stellen verbinding te maken met de service via een internetverbinding. Naarmate de service zich ontwikkelt, worden de beveiliging, prestaties en betrouwbaarheid van Microsoft 365 verbeterd op basis van klanten die internet gebruiken om een verbinding met de service tot stand te brengen.
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905474"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Microsoft 365-netwerkverbindingen evalueren

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft 365 is ontworpen om klanten over de hele wereld in staat te stellen verbinding te maken met de service via een internetverbinding. Naarmate de service zich ontwikkelt, worden de beveiliging, prestaties en betrouwbaarheid van Microsoft 365 verbeterd op basis van klanten die internet gebruiken om een verbinding met de service tot stand te brengen.
  
Klanten die van plan zijn Microsoft 365 hun bestaande en voorspelde internetconnectiviteitsbehoeften te beoordelen als onderdeel van het implementatieproject. Voor implementaties van ondernemingsklasse is betrouwbare en geschikte internetverbinding een essentieel onderdeel van het gebruik van Microsoft 365 functies en scenario's.
  
Netwerkevaluaties kunnen door veel verschillende personen en organisaties worden uitgevoerd, afhankelijk van uw grootte en voorkeuren. Het netwerkbereik van de evaluatie kan ook variëren, afhankelijk van waar u zich in uw implementatieproces op dat moment op dat moment op de 10000-1000-10000-40000-2019-2010 hebt 2 Om u te helpen beter te begrijpen wat er nodig is om een netwerkbeoordeling uit te voeren, hebben we een netwerkbeoordelingshandleiding gemaakt om u te helpen de beschikbare opties te begrijpen. Met deze beoordeling wordt bepaald welke stappen en resources moeten worden toegevoegd aan het implementatieproject, zodat u de implementatie Microsoft 365.
  
Een uitgebreide netwerkbeoordeling biedt mogelijke oplossingen voor netwerkontwerpuitdagingen, samen met implementatiedetails. Sommige netwerkbeoordelingen laten zien dat optimale netwerkconnectiviteit met Microsoft 365 kan worden aangepast met secundaire configuratie- of ontwerpwijzigingen in de bestaande netwerk- en internetinfrastructuur.

Sommige evaluaties geven aan dat er extra Microsoft 365 netwerkonderdelen moeten worden geïnvesteerd. Voor bedrijfsnetwerken die kantoren en meerdere geografische regio's bespannen, kunnen bijvoorbeeld investeringen in SD-WAN-oplossingen of geoptimaliseerde routeringsinfrastructuur nodig zijn om internetverbinding met Microsoft 365. Af en toe geeft een evaluatie aan dat netwerkconnectiviteit met Microsoft 365 wordt beïnvloed door regelgeving of prestatievereisten voor [scenario's zoals Skype voor Bedrijven Online mediakwaliteit.](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917) Deze aanvullende vereisten kunnen leiden tot investeringen in de infrastructuur voor internetconnectiviteit, routeringsoptimalisatie en gespecialiseerde directe connectiviteit.

Enkele bronnen die u helpen bij het beoordelen van uw netwerk:

- Zie [Microsoft 365 overzicht van netwerkconnectiviteit voor](microsoft-365-networking-overview.md) conceptuele informatie over Microsoft 365 netwerken.
- Zie [Microsoft 365 Netwerkconnectiviteitsprincipes](./microsoft-365-network-connectivity-principles.md) om de connectiviteitsprincipes te begrijpen voor het veilig beheren van Microsoft 365 en het verkrijgen van de best mogelijke prestaties.
- Meld u aan bij [Microsoft FastTrack](https://www.microsoft.com/fasttrack) voor begeleide hulp bij Microsoft 365 planning, ontwerp en implementatie. 
- Zie de [Microsoft 365 hieronder](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) om basisconnectiviteitstests uit te voeren die specifieke richtlijnen bieden voor verbeteringen in de netwerkconnectiviteit die kunnen worden aangebracht tussen een bepaalde gebruikerslocatie en Microsoft 365.

> [!NOTE]
> Microsoft-autorisatie is vereist voor het gebruik van ExpressRoute Office 365. Microsoft controleert elke klantaanvraag en machtigt ExpressRoute alleen voor Office 365 gebruik wanneer de wettelijke vereisten van een klant directe connectiviteit verplicht stellen. Als u dergelijke vereisten hebt, moet u het tekstfragment en de webkoppeling naar de verordening verstrekken die u interpreteert om te betekenen dat directe connectiviteit vereist is in het [ExpressRoute-formulier voor Office 365 Aanvraagformulier](https://aka.ms/O365ERReview) om een Microsoft-beoordeling te starten. Niet-geautoriseerde abonnementen die routefilters proberen te maken voor Office 365 ontvangen een [foutbericht.](https://support.microsoft.com/kb/3181709)
  
Belangrijke aandachtspunten bij het plannen van uw netwerkbeoordeling voor Microsoft 365:
  
- Microsoft 365 is een veilige, betrouwbare en krachtige service die via het openbare internet wordt uitgevoerd. We blijven investeren om deze aspecten van de service te verbeteren. Alle Microsoft 365 services zijn beschikbaar via internetconnectiviteit.

- We optimaliseren voortdurend de belangrijkste aspecten van Microsoft 365, zoals beschikbaarheid, wereldwijd bereik en prestaties voor op internet gebaseerde connectiviteit. Veel services Microsoft 365 bijvoorbeeld gebruikmaken van een uitdijende set randknooppunten op internet. Dit edge-netwerk biedt de beste nabijheid en prestaties voor verbindingen die via internet komen.

- Bij het overwegen Microsoft 365 te gebruiken voor een van de inbegrepen services, zoals Teams of Skype voor Bedrijven Online spraak-, video- of vergaderingsmogelijkheden, moeten klanten een einde maken aan de netwerkbeoordeling en voldoen aan de connectiviteitsvereisten met [Microsoft FastTrack.](https://www.microsoft.com/fasttrack)

Als u de Microsoft 365 evalueert en niet zeker weet waar u moet beginnen met uw netwerkbeoordeling of als u problemen met het netwerkontwerp hebt gevonden die u moet oplossen, kunt u samenwerken met uw Microsoft-accountteam.

## <a name="the-microsoft-365-connectivity-test"></a>De Microsoft 365 verbindingstest

De [Microsoft 365-connectiviteitstest](https://aka.ms/netonboard) is een hulpprogramma voor concept-evaluatie (POC) waarmee basisconnectiviteitstests worden uitgevoerd met uw Microsoft 365-tenant en specifieke aanbevelingen voor netwerkontwerpen worden gedaan voor optimale Microsoft 365 prestaties. Met het hulpprogramma worden veelgebruikte ontwerpopties voor grote bedrijfsnetwerkperimeters belicht die handig zijn voor surfen op internet, maar die van invloed zijn op de prestaties van grote SaaS-toepassingen, zoals Microsoft 365.

Het hulpprogramma Network Onboarding doet het volgende:

- Hiermee wordt uw locatie gedetecteerd of kunt u een testlocatie opgeven
- Hiermee controleert u de locatie van het netwerk
- Test het netwerkpad naar de dichtstbijzijnde Microsoft 365 van de service
- Biedt geavanceerde tests met een downloadbare Windows 10 toepassing die perimeternetwerkontwerpaanbevelingen doet met betrekking tot proxyservers, firewalls en DNS. Met het hulpprogramma worden ook prestatietests uitgevoerd voor Skype voor Bedrijven Online, Microsoft Teams, SharePoint Online en Exchange Online.

Het hulpprogramma bevat twee onderdelen: een browsergebaseerde gebruikersinterface die basisconnectiviteitsgegevens verzamelt en een downloadbare Windows 10 toepassing waarmee geavanceerde tests worden uitgevoerd en aanvullende beoordelingsgegevens worden retourneert.

In het browserprogramma worden de volgende gegevens weergegeven:

- Tabblad Resultaten en impact
  - De locatie op een kaart van de in-use service-deur
  - De locatie op een kaart van andere servicedeuren die optimale connectiviteit bieden
  - Relatieve prestaties in vergelijking met andere Microsoft 365 klanten bij u in de buurt
- Tabblad Details en oplossingen
  - Locatie van gebruiker per plaats en land
  - Netwerklocatie per plaats, provincie en land
  - Afstand tussen gebruiker en netwerk
  - Microsoft 365 Exchange Online servicelocatie voor de deur
  - Optimale Microsoft 365 Exchange Online service voor de deur(en) voor de locatie van de gebruiker
  - Klanten in uw metrogebied met betere prestaties

De downloadbare toepassing Geavanceerde tests bevat de volgende aanvullende informatie:

- Tabblad Details en oplossingen (toegevoegd)
  - Standaardgateway van gebruiker
  - Client DNS Server
  - Client DNS Recursive Resolver
  - Exchange Online DNS-server
  - SharePoint Online DNS-server
  - Proxyserveridentificatie
  - Mediaconnectiviteitscontrole
  - Mediakwaliteitspakketverlies
  - Latentie van mediakwaliteit
  - Mediakwaliteit jitter
  - Mediakwaliteitspakket opnieuw ordenen
- Connectiviteitstests voor meerdere functiespecifieke eindpunten
- Netwerkpaddiagnose met tracert- en latentiegegevens voor de Exchange Online, SharePoint Online en Teams services

U kunt meer lezen over de Microsoft 365 [connectiviteitstest](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) en feedback geven op de POC Microsoft 365-connectiviteitstest bijgewerkt met nieuwe blogberichten over netwerkontwerpaanbevelingen. Informatie over toekomstige updates voor dit hulpprogramma en andere Microsoft 365 netwerkupdates wordt op de blog Office 365 [netwerken geplaatst.](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)
  
Hier is een korte koppeling die u kunt gebruiken om terug te komen: [ https://aka.ms/o365networkconnectivity .](./microsoft-365-network-connectivity-principles.md)
  
## <a name="related-topics"></a>Verwante onderwerpen

[Overzicht van netwerkverbindingen voor Microsoft 365](microsoft-365-networking-overview.md)

[Microsoft 365 Beginselen van netwerkconnectiviteit](./microsoft-365-network-connectivity-principles.md)

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)

[URL's en IP-adresbereiken voor Office 365](urls-and-ip-address-ranges.md)

[IP-adres en URL-webservice van Office 365](microsoft-365-ip-web-service.md)

[Microsoft 365 netwerk en prestaties afstemmen](network-planning-and-performance.md)

[Microsoft 365 Enterprise overzicht](microsoft-365-overview.md)