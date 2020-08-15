---
title: Microsoft 365-netwerkconnectiviteit beoordelen
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
description: Microsoft 365 is ontworpen om klanten overal ter wereld toegang te bieden tot de service met een internetverbinding. Naarmate de service wordt ontwikkeld, zijn de beveiliging, de prestaties en de betrouwbaarheid van Microsoft 365 verbeterd op basis van klanten die Internet gebruiken om verbinding te maken met de service.
ms.openlocfilehash: c0bca2f354d71aa2f4f0c2b6fd05cb4786368b43
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689344"
---
# <a name="assessing-microsoft-365-network-connectivity"></a>Microsoft 365-netwerkconnectiviteit beoordelen

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft 365 is ontworpen om klanten overal ter wereld toegang te bieden tot de service met een internetverbinding. Naarmate de service wordt ontwikkeld, zijn de beveiliging, de prestaties en de betrouwbaarheid van Microsoft 365 verbeterd op basis van klanten die Internet gebruiken om verbinding te maken met de service.
  
Klanten die Microsoft 365 gebruiken, moeten hun bestaande en Voorspellings behoefte voor de internetverbinding beoordelen als onderdeel van het implementatieproject. Voor implementaties van bedrijfs klassen betrouwbare en geëigende, grote internetverbinding is een belangrijk onderdeel van de functies en scenario's van Microsoft 365.
  
Netwerk evaluaties kunnen door veel verschillende personen en organisaties worden uitgevoerd, afhankelijk van uw grootte en voorkeuren. Het netwerkbereik van de beoordeling kan ook variëren, afhankelijk van waar u zich bevindt in uw implementatieproces. Om u te helpen beter inzicht te krijgen in de manier waarop u een netwerkanalyse uitvoert, hebben we een netwerkassessment-handleiding gemaakt waarmee u inzicht krijgt in de beschikbare opties. Met deze beoordeling wordt bepaald welke stappen en bronnen moeten worden toegevoegd aan het implementatieproject, zodat u Microsoft 365 kunt aannemen.
  
Een uitgebreide beoordeling van het netwerk levert mogelijke oplossingen voor de communicatie van netwerken, en de details van de implementatie. Sommige netwerk beoordelingen tonen aan dat de optimale netwerkverbinding met Microsoft 365 kan worden afgevangen met beperkte configuratie-of ontwerpwijzigingen in het bestaande netwerk en de infrastructuur van de uitgang van Internet.

Voor sommige beoordelingen wordt aangegeven dat de netwerkverbinding met Microsoft 365 extra investeringen met de netwerkonderdelen vereist. Enterprise-netwerken die filialen (filialen en meerdere geografische regio's) hebben, hebben mogelijk investeringen nodig in de SD-WAN-oplossingen of een geoptimaliseerde routeringsinfrastructuur voor ondersteuning van internetconnectiviteit met Microsoft 365. Af en toe geeft een beoordeling aan dat netwerkconnectiviteit met Microsoft 365 is beïnvloed door de regelgeving of de prestatievoorschriften voor scenario's, zoals de [mediakwaliteit van Skype voor bedrijven online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917). Deze aanvullende vereisten kunnen leiden tot investeringen in de internetconnectiviteit-infrastructuur, omleiding van Routering en gespecialiseerde directe connectiviteit.

Sommige bronnen om u te helpen bij het bepalen van uw netwerk:

- Zie [Microsoft 365 Network Connectivity-overzicht](microsoft-365-networking-overview.md) voor conceptuele informatie over microsoft 365-netwerken.
- Zie [Microsoft 365-beginselen](https://aka.ms/o365networkingprinciples) voor de connectiviteit om inzicht te krijgen in de verbindings principes voor het veilig beheren van microsoft 365-verkeer en de best mogelijke prestaties te verkrijgen.
- Registreer u voor [Microsoft FastTrack](https://www.microsoft.com/fasttrack) voor hulp bij microsoft 365 voor hulp bij het plannen, ontwerpen en implementeren van microsoft. 
- Zie het gedeelte [Microsoft 365 Connectivity test](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) hieronder voor basis verbindingen, waaronder richtlijnen voor de verbeteringen van de netwerkverbinding die kunnen worden gemaakt tussen een bepaalde gebruikerslocatie en microsoft 365.

> [!NOTE]
> Microsoft Authorization is vereist voor het gebruik van ExpressRoute voor Office 365. Microsoft beoordeelt elke klantaanvraag en gemachtigdet ExpressRoute voor Office 365 gebruik wanneer de wettelijke vereisten van de klant directe verbinding vereisen. Als u dergelijke vereisten hebt, dient u het tekstfragment en de webkoppeling naar de verordening te geven die u vertolkt om te betekenen dat directe verbinding is vereist in het [ExpressRoute voor Office 365 aanvraagformulier](https://aka.ms/O365ERReview) om een beoordeling van Microsoft te starten. Niet-geautoriseerde abonnementen bij het maken van routefilters voor Office 365 wordt een [foutbericht](https://support.microsoft.com/kb/3181709)weergegeven.
  
Belangrijkste punten waarmee u rekening moet houden bij het plannen van de evaluatie van uw netwerk voor Microsoft 365:
  
- Microsoft 365 is een veilige, betrouwbare en krachtige service die wordt uitgevoerd via het openbare Internet. We blijven investeren om deze aspecten van de service te verbeteren. Alle 365-services van Microsoft zijn beschikbaar via internetverbindingen.

- We optimaliseren de kern aspecten van Microsoft 365, zoals beschikbaarheid, algemeen bereik en prestaties voor op internet gebaseerde verbindingen. Een groot aantal Microsoft 365-Services maakt bijvoorbeeld gebruik van een uitvouwbare set Internet Facing Edge-knooppunten. Dit Edge-netwerk biedt de beste proximity en prestaties voor verbindingen via internet.

- Wanneer u Microsoft 365 voor een van de opgenomen Services gebruikt, zoals teams of de functies voor spraak, Video's en vergaderingen van Skype voor bedrijven online, moet klanten een end netwerk beoordeling voltooien en voldoen aan de connectiviteits vereisten met behulp van [Microsoft FastTrack](https://www.microsoft.com/fasttrack).

Neem contact op met uw Microsoft-accountteam als u Microsoft 365 evalueert en niet zeker weet waar u met uw netwerk beoordeling moet beginnen of als er een nieuwe netwerk ervaring voor u is gevonden.

## <a name="the-microsoft-365-connectivity-test"></a>De Microsoft 365 connectiviteitstest

De [connectiviteitstest voor Microsoft 365](https://aka.ms/netonboard) is een haalbaarheidstest (haalbaarheidstest) met een proefversie van het netwerk voor de implementatie van basis verbindingen tegen uw microsoft 365-Tenant en aanbevelingen te doen voor optimale prestaties van microsoft 365. Met het hulpprogramma worden veelvoorkomende keuzes van grote Enterprise-netwerkverbindingen beschreven die nuttig zijn voor Internet browsen, maar die de prestaties beïnvloeden van grote SaaS-toepassingen, zoals Microsoft 365.

Het hulpprogramma voor onboarding van netwerken doet het volgende:

- Detecteert uw locatie, of u kunt een te testen locatie opgeven
- Controleert de locatie van uw netwerk uitgang
- Hiermee wordt het netwerkpad getest op de dichtstbijzijnde Microsoft 365-service-klep
- Biedt geavanceerde tests met behulp van een downloadbare Windows 10-toepassing die aanbevelingen maakt voor de aanbevelingen van het perimeternetwerk met betrekking tot proxyservers, firewalls en DNS. Met dit hulpprogramma voert u ook prestatietests uit voor Skype voor bedrijven online, Microsoft teams, SharePoint Online en Exchange Online.

Het hulpmiddel bestaat uit twee onderdelen: een browserinterface met een browser waarmee basisinformatie wordt verzameld en een downloadbare Windows 10-toepassing waarmee geavanceerde tests worden uitgevoerd en extra beoordelings gegevens worden weergegeven.

Met het hulpprogramma voor browsers worden de volgende gegevens weergegeven:

- Tabblad resultaten en impact
  - De locatie op een kaart van de service voor gebruik
  - De locatie op een kaart met andere service-en front-deuren die een optimale connectiviteit oplevert
  - Relatieve prestaties vergeleken met andere Microsoft 365-klanten in de buurt
- Het tabblad Details en oplossingen
  - Gebruikerslocatie per plaats en land
  - Netwerklocatie voor uitgaand verkeer per plaats, provincie en land
  - Gebruikers van de afstands verbinding voor netwerken
  - Locatie van Microsoft 365 Exchange Online-service voor deur
  - Optimale Microsoft 365 Exchange Online-service-voor deur (en) voor gebruikerslocatie
  - Klanten in uw metro gebied met betere prestaties

De downloadbare toepassing geavanceerde testen biedt de volgende aanvullende informatie:

- Tabblad Details en oplossingen (toegevoegd)
  - Standaardgateway van de gebruiker
  - Client-DNS-server
  - Client DNS recursieve resolver
  - DNS-server voor Exchange Online
  - SharePoint Online-DNS-server
  - Proxy serveridentificatie
  - Controle van media connectiviteit
  - Pakketverlies Media kwaliteit
  - Latentie van media kwaliteit
  - Media kwaliteit-jitter
  - Volgorde van pakket voor media kwaliteit
- Connectiviteitstests voor meerdere functies, specifieke eindpunten
- Diagnostische gegevens van netwerkpad met tracering en latentie gegevens voor de services Exchange Online, SharePoint Online en teams

U vindt meer informatie over de Microsoft 365-connectiviteitstest en u krijgt feedback over de [bijgewerkte Microsoft 365-connectiviteitstest voor de nieuwe versie van het blogbericht nieuwe netwerkontwerp](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) . Informatie over toekomstige updates van dit hulpprogramma en andere updates voor Microsoft 365-netwerken worden gepubliceerd naar het netwerk blog van [Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) .
  
Met deze korte koppeling kunt u teruggaan [ https://aka.ms/o365networkconnectivity :](https://aka.ms/o365networkconnectivity)
  
## <a name="related-topics"></a>Verwante onderwerpen

[Overzicht van Microsoft 365 netwerkverbinding](microsoft-365-networking-overview.md)

[Principes voor Microsoft 365-netwerkverbindingen](https://aka.ms/o365networkingprinciples)

[Office 365-eindpunten beheren](managing-office-365-endpoints.md)

[URL's en IP-adresbereiken voor Office 365](urls-and-ip-address-ranges.md)

[Office 365 IP Address en URL web service](microsoft-365-ip-web-service.md)

[Microsoft 365-netwerk en prestaties optimaliseren](network-planning-and-performance.md)

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)
