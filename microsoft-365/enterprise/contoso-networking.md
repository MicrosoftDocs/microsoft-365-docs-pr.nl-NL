---
title: Netwerken voor de Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Inzicht in de infrastructuur contoso-netwerken en de manier waarop het bedrijf de SD-WAN-technologie gebruikt voor optimale netwerkprestaties voor Microsoft 365 voor Enterprise Cloud-Services.
ms.openlocfilehash: ca673e6dcbf0f3db4bde33d388598e5f4ffac914
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637185"
---
# <a name="networking-for-the-contoso-corporation"></a>Netwerken voor de Contoso Corporation

Als u een infrastructuur van de Cloud gebruikt, is contoso een fundamentele dienst ontwikkeld voor de manier waarop netwerkverkeer voor cloudservices wordt verplaatst. In plaats van een intern hub-en-spoke-model dat de netwerkverbinding en het verkeer voor het volgende niveau van de Office-hiërarchie benadert, hebben ze gebruikerslocaties toegewezen aan lokale Internet uitvullen en lokale verbindingen met de dichtstbijzijnde Microsoft 365-netwerklocatie op internet.

## <a name="networking-infrastructure"></a>Netwerkinfrastructuur

Dit zijn de netwerkelementen waarmee contoso-afdelingen overal ter wereld worden gekoppeld:

- Multiprotocol-Label Switching (MPLS) WAN-netwerk

  Een MPLS WAN-netwerk verbindt de hoofdkantoren van Parijs met regionale kantoren en regionale kantoren naar satelliet kantoren via een spoke-en-hub-configuratie. Het netwerk biedt gebruikers toegang tot on-premises servers die line-of-business-toepassingen maken in de Headquarters van Parijs. Ook wordt elk algemeen internetverkeer naar het kantoor van Parijs gerouteerd, waarbij de netwerk beveiligingsapparaten de verzoeken reinigen. Binnen elke kantoor leiden routers het verkeer naar draadgebonden hosts of draadloze toegangspunten op subnetten, die gebruikmaken van de particuliere IP-adresruimte.

- Lokale directe Internet toegang voor Microsoft 365-verkeer

  Elke Office heeft een door software gedefinieerd WAN (SD)-apparaat met een of meer lokale netwerkclients met een internetverbinding via een proxyserver. Dit wordt meestal geïmplementeerd als een WAN-koppeling naar een lokale internetprovider die ook openbare IP-adressen en een lokale DNS-server biedt.

- Internetaanwezigheid

  Contoso bezit de naam van het \. openbare com-domein van contoso. De openbare website van Contoso voor het bestellen van producten is een reeks servers in een datacenter dat verbonden is met internet in de Parijs. Contoso maakt gebruik van een openbaar IP-adresbereik op internet.

Afbeelding 1 toont de infrastructuur van Contoso-netwerken en de bijbehorende verbindingen met internet.

![Het contoso netwerk](../media/contoso-networking/contoso-networking-fig1.png)
 
**Afbeelding 1: het contoso netwerk**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Gebruik van SD-WAN voor optimale netwerkconnectiviteit met Microsoft

Contoso heeft de [Beginselen voor Microsoft 365-netwerkconnectiviteit](microsoft-365-network-connectivity-principles.md) gevolgd om:

- Netwerkverkeer van Microsoft 365 te identificeren en te onderscheiden
- Lokale uitgangen van netwerkverbindingen te regelen
- Netwerk-hairpins te vermijden
- Dubbele netwerkbeveiligingsapparaten te omzeilen

Er zijn drie categorieën netwerkverkeer voor Microsoft 365: *optimaliseren*, *toestaan*en *standaard*. Verkeer optimaliseren en toestaan wordt vertrouwd netwerkverkeer dat is versleuteld en beveiligd bij de eindpunten en is bestemd voor het Microsoft 365-netwerk.

Contoso heeft besloten om:

- U kunt direct Internet uitvullen gebruiken voor het optimaliseren en toestaan van categorie verkeer en alle standaardcategorie verkeer door te sturen naar de op de basis internetverbinding van Parijs.

- Implementeer een SD-WAN-apparaat op elk Office als eenvoudige manier om deze principes te volgen en de prestaties van het netwerk te verbeteren voor Microsoft 365 cloudservices.

  De SD-WAN-apparaten hebben een LAN-poort voor het lokale kantoornetwerk en meerdere WAN-poorten. Eén WAN-poort maakt verbinding met het MPLS-netwerk. Een andere verbinding maakt met een lokaal ISP-circuit. Het SD-WAN-apparaat leidt netwerkverkeer uit de categorieën Optimaliseren en Toestaan via de ISP-koppeling.

## <a name="the-contoso-line-of-business-app-infrastructure"></a>De infrastructuur van de app contoso line-of-Business

Contoso heeft de toepassing line-van-Business en de intranet infrastructuur van de server voor het volgende:

- Satellietkantoren gebruiken lokale cacheservers voor het opslaan van veelgebruikte documenten en interne websites.
- Regionale hubs gebruiken regionale toepassingsservers voor de regionale en satellietkantoren. Deze servers worden gesynchroniseerd met servers in het hoofdkantoor in Parijs.
- De bevestigingen van Parijs van Parijs bevatten gecentraliseerde toepassingsservers die de hele organisatie dienen.

Afbeelding 2 toont het percentage netwerkverkeer dat wordt gebruikt voor het openen van servers in het intranet van contoso.

![De infrastructuur contoso voor interne toepassingen](../media/contoso-networking/contoso-networking-fig2.png)
 
**Afbeelding 2: de infrastructuur contoso voor interne toepassingen**

Voor de satelliet-of Regional hub-kantoren is 60 procent van de resources die nodig zijn voor de werknemers aan de satelliet en de regionale hub Office servers geleverd. Het extra 40 procent van de resourceaanvragen moet via de WAN-koppeling naar de Parijs van de campus gaan.

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Netwerkanalyse en-voorbereiding voor Microsoft 365 for Enterprise

Geslaagde aanneming van Microsoft 365 voor Enterprise Services door contoso gebruikers is afhankelijk van zeer beschikbare verbindingen met internet of rechtstreeks naar Microsoft-cloudservices. Contoso heeft de volgende stappen uitgevoerd voor het plannen en implementeren van geoptimaliseerde connectiviteit met Microsoft 365 voor Enterprise cloudservices:

1. Een diagram maken van een WAN-netwerk van het bedrijf voor hulp bij de planning

   Om de netwerk planning te starten, heeft Contoso een diagram gemaakt met hun Office-locaties, bestaande netwerkconnectiviteit, bestaande netwerk verbindingsapparaten en serviceklassen die worden beheerd op het netwerk. Ze hebben deze diagram gebruikt voor elke daaropvolgende stap in de planning en tijdens de implementatie van netwerkconnectiviteit.

2. Een plan maken voor Microsoft 365 voor Enterprise-netwerkconnectiviteit

   Contoso heeft de [Microsoft 365-netwerk verbindings beginselen](microsoft-365-network-connectivity-principles.md) en de voorbeelden van netwerk architecturen voor de client Architecture voor de microsoft 365-verbinding aangeduid met de desbetreffende topologie.

3. Analyseren van Internet-verbinding met MPLS en de bandbreedte van de WAN-verbinding op elk Office, en de bandbreedte naar wens verhogen

   Het huidige gebruik van Office is geanalyseerd, en de circuits zijn opgegroeid, zodat Microsoft 365 op de Cloud op basis van het voorspeld verkeer met een gemiddelde van 20 procent niet-gebruikte capaciteit werkt.

4. Prestaties optimaliseren voor Microsoft-netwerkservices

   Contoso heeft de set Office 365-, intune-en Azure-eindpunten, en de geconfigureerde firewalls, beveiligingsapparaten en andere systemen in Internet Path voor optimale prestaties vastgesteld. Eindpunten voor Office 365 optimaliseren en toestaan dat categorie verkeer is geconfigureerd in de SD-WAN-apparaten voor routering via het routerings circuit.

5. Interne DNS configureren

   DNS moet functioneel zijn en lokaal worden opgezocht voor Microsoft 365-verkeer.

6. Netwerkeindpunt en poort verbinding valideren

   Contoso heeft de testhulpprogramma's voor Microsoft netwerkverbindingen uitgevoerd om de connectiviteit voor Microsoft 365 te valideren voor Enterprise cloudservices.

7. Computers van werknemers voor netwerkconnectiviteit optimaliseren

   Afzonderlijke computers zijn gecontroleerd om er zeker van te zijn dat de nieuwste updates voor het besturingssysteem zijn geïnstalleerd en dat beveiligings bewaking van endpoint voor alle clients actief was.

## <a name="next-step"></a>Volgende stap

[Lees hier meer](contoso-identity.md) over hoe Contoso op locatie Active Directory Domain Services (AD DS) in de Cloud gebruikt voor werknemers en federatieve verificatie voor klanten en zakenpartners.

## <a name="see-also"></a>Zie ook

[Netwerkkaart voor Microsoft 365](networking-roadmap-microsoft-365.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Testlabrichtlijnen](m365-enterprise-test-lab-guides.md)
