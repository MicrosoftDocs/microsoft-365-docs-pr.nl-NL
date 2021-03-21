---
title: 'Overzicht: VPN splits tunneling met Office 365'
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
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: Richtlijnen voor het gebruik van VPN-splits tunneling met Office 365 voor het optimaliseren van Office 365-connectiviteit voor externe gebruikers.
ms.openlocfilehash: 9f54d8836105896d8d00afc4a622975c007bda85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924186"
---
# <a name="optimize-office-365-connectivity-for-remote-users-using-vpn-split-tunneling"></a>Office 365-connectiviteit optimaliseren voor externe gebruikers met VPN-split-tunneling
<!---
>[!NOTE]
>This topic is part of a set of topics that address Office 365 optimization for remote users.
>- For VPN split tunnel implementation guidance, see [Implementing VPN split tunneling for Office 365](microsoft-365-vpn-implement-split-tunnel.md).
>- For information about optimizing Office 365 worldwide tenant performance for users in China, see [Office 365 performance optimization for China users](microsoft-365-networking-china.md).
-->

Voor klanten die hun externe werknemersapparaten verbinden met het bedrijfsnetwerk of de cloudinfrastructuur via VPN, raadt Microsoft aan dat de belangrijkste Office 365-scenario's **Microsoft Teams,** **SharePoint Online** en **Exchange Online** worden gerouteerd via een _VPN-splits_ tunnelconfiguratie. Dit wordt vooral belangrijk als de eerste regelstrategie om de productiviteit van werknemers te blijven verhogen tijdens grootschalige werk-van-huis-gebeurtenissen, zoals de COVID-19-crisis.

![SPLIT TUNNEL VPN-configuratie](../media/vpn-split-tunneling/vpn-model-2.png)

_Afbeelding 1: Een VPN-oplossing voor gesplitste tunnel met gedefinieerde Office 365-uitzonderingen die rechtstreeks naar de service worden verzonden. Al het andere verkeer doorkruist de VPN-tunnel, ongeacht de bestemming._

De essentie van deze benadering is het bieden van een eenvoudige methode voor ondernemingen om het risico van verzadiging van VPN-infrastructuur te beperken en de prestaties van Office 365 in de kortst mogelijke tijd drastisch te verbeteren. Het configureren van VPN-clients om het meest kritieke, hoge volume Office 365-verkeer toe te staan om de VPN-tunnel te omzeilen, biedt de volgende voordelen:

- Vermindert onmiddellijk de hoofdoorzaak van een groot deel van de door de klant gerapporteerde prestaties en netwerkcapaciteitsproblemen in VPN-architectuur voor ondernemingen die van invloed zijn op de gebruikerservaring van Office 365
  
  De aanbevolen oplossing is specifiek bedoeld voor Office 365-service-eindpunten die zijn gecategoriseerd als Optimaliseren **in** het onderwerp [Office 365-URL's en IP-adresbereiken.](./urls-and-ip-address-ranges.md) Verkeer naar deze eindpunten is zeer gevoelig voor latentie en bandbreedtebeperking. Als u de VPN-tunnel kunt omzeilen, kan dit de ervaring van de eindgebruiker aanzienlijk verbeteren en de belasting van het bedrijfsnetwerk verminderen. Office 365-verbindingen die niet de meeste bandbreedte of gebruikerservaring vormen, kunnen nog steeds worden gerouteerd via de VPN-tunnel, samen met de rest van het internetverkeer. Zie De [vpn-gesplitste tunnelstrategie](#the-vpn-split-tunnel-strategy)voor meer informatie.

- Kan snel worden geconfigureerd, getest en geïmplementeerd door klanten en zonder extra infrastructuur- of toepassingsvereisten

  Afhankelijk van het VPN-platform en de netwerkarchitectuur kan implementatie slechts enkele uren duren. Zie VPN [splits tunneling implementeren](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)voor meer informatie.

- Behoudt de beveiligingsstatus van VPN-implementaties van klanten door niet te wijzigen hoe andere verbindingen worden gerouteerd, inclusief verkeer naar internet

  De aanbevolen configuratie  volgt het minst bevoorrechte principe voor VPN-verkeers uitzonderingen en stelt klanten in staat vpn-gesplitste tunnel te implementeren zonder gebruikers of infrastructuur bloot te stellen aan extra beveiligingsrisico's. Netwerkverkeer dat rechtstreeks naar Office 365-eindpunten wordt gerouteerd, wordt versleuteld, gevalideerd voor integriteit door office-clienttoepassingsstapels en gebereikt naar IP-adressen die zijn toegewezen aan Office 365-services die zowel op toepassings- als netwerkniveau zijn gehard. Zie Alternatieve manieren voor beveiligingsprofessionals en IT voor moderne beveiligingsbesturingselementen in de unieke scenario's voor extern werk van vandaag [(Microsoft Security Team blog)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)voor meer informatie.

- Wordt inheems ondersteund door de meeste ENTERPRISE VPN-platforms

  Microsoft blijft samenwerken met branchepartners die commerciële VPN-oplossingen produceren om partners te helpen bij het ontwikkelen van gerichte richtlijnen en configuratiesjablonen voor hun oplossingen in overeenstemming met de bovenstaande aanbevelingen. Zie HOWTO-handleidingen voor [veelgebruikte VPN-platforms](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms)voor meer informatie.

>[!TIP]
>Microsoft raadt aan de VPN-configuratie voor gesplitste tunnel te richten op gedocumenteerde speciale IP-bereik voor Office 365-services. FQDN- of AppID-gebaseerde split tunnelconfiguraties, hoewel dit mogelijk is op bepaalde VPN-clientplatforms, dekken mogelijk niet volledig belangrijke Office 365-scenario's en kunnen conflicteren met VPN-routeringsregels op basis van IP. Om deze reden raadt Microsoft het niet aan office 365 FQDN's te gebruiken om vpn-gesplitste tunnel te configureren. Het gebruik van FQDN-configuratie kan handig zijn in andere gerelateerde scenario's, zoals .pac-bestandsaanpassingen of om proxy bypass te implementeren.

Zie Vpn [splits tunneling implementeren voor Office 365](microsoft-365-vpn-implement-split-tunnel.md)voor volledige implementatie.

## <a name="the-vpn-split-tunnel-strategy"></a>De VPN-strategie voor gesplitste tunnel

Traditionele bedrijfsnetwerken zijn vaak ontworpen om veilig te werken voor een pre-cloud wereld waar de belangrijkste gegevens, services, toepassingen on-premises worden gehost en rechtstreeks zijn verbonden met het interne bedrijfsnetwerk, net als de meeste gebruikers. De netwerkinfrastructuur is dus opgebouwd rond deze elementen, omdat filialen zijn verbonden met het hoofdkantoor via _MPLS-netwerken (Multiprotocol Label Switching)_ en externe gebruikers verbinding moeten maken met het bedrijfsnetwerk via een VPN om toegang te krijgen tot zowel on-premises eindpunten als internet. In dit model loopt al het verkeer van externe gebruikers door het bedrijfsnetwerk en wordt deze via een gemeenschappelijk uitgangspunt doorgeleid naar de cloudservice.

![Gedwongen VPN-configuratie](../media/vpn-split-tunneling/vpn-model-1.png)

_Afbeelding 2: Een veelgebruikte VPN-oplossing voor externe gebruikers waarbij al het verkeer terug wordt geforceerd naar het bedrijfsnetwerk, ongeacht de bestemming_

Naarmate organisaties gegevens en toepassingen naar de cloud verplaatsen, is dit model minder effectief geworden omdat het snel omslachtig, duur en oncalable wordt, waardoor de netwerkprestaties en -efficiëntie van gebruikers aanzienlijk worden beïnvloed en de organisatie niet meer in staat is zich aan te passen aan veranderende behoeften. Veel Microsoft-klanten hebben gemeld dat een paar jaar geleden 80% van het netwerkverkeer naar een interne bestemming was, maar in 2020 80% plus van het verkeer verbinding maakt met een externe cloudresource.

De COVID-19-crisis heeft dit probleem verergerd om onmiddellijke oplossingen te vereisen voor de overgrote meerderheid van de organisaties. Veel klanten hebben ontdekt dat het gedwongen VPN-model niet schaalbaar of performant genoeg is voor 100% externe werkscenario's, zoals die waarvoor deze crisis noodzakelijk is. Snelle oplossingen zijn vereist om deze organisatie efficiënt te laten blijven werken.

Voor de Office 365-service heeft Microsoft de connectiviteitsvereisten voor de service ontworpen met dit probleem in gedachten, waarbij een gerichte, strak gecontroleerde en relatief statische set service-eindpunten heel eenvoudig en snel kan worden geoptimaliseerd om hoge prestaties te leveren voor gebruikers die toegang hebben tot de service en om de belasting voor de VPN-infrastructuur te verminderen, zodat deze kan worden gebruikt door verkeer waarvoor deze nog steeds vereist is.

Office 365 categoriseert de vereiste eindpunten voor Office 365 in drie categorieën: **Optimaliseren,** Toestaan **en** **Standaard.** **Eindpunten** optimaliseren zijn onze focus hier en hebben de volgende kenmerken:

- Zijn Microsoft-eindpunten die eigendom zijn van En beheerd, gehost op Microsoft-infrastructuur
- Zijn gewijd aan de belangrijkste Office 365-werkbelastingen, zoals Exchange Online, SharePoint Online, Skype voor Bedrijven Online en Microsoft Teams
- IPs beschikbaar hebben
- Lage veranderingssnelheid en zal naar verwachting klein blijven (momenteel 20 IP-subnetten)
- Zijn hoog volume en/of latentiegevoelig
- Kunnen vereiste beveiligingselementen in de service hebben in plaats van inline op het netwerk
- Goed voor ongeveer 70-80% van het volume van het verkeer naar de Office 365-service

Deze set eindpunten met een beperkt bereik kan worden gesplitst uit de gedwongen VPN-tunnel en veilig en rechtstreeks naar de Office 365-service worden verzonden via de lokale interface van de gebruiker. Dit wordt splits **tunneling genoemd.**

Beveiligingselementen zoals DLP, AV-beveiliging, verificatie en toegangsbeheer kunnen allemaal veel efficiënter worden geleverd tegen deze eindpunten op verschillende lagen binnen de service. Aangezien we ook het grootste deel van het verkeersvolume van de VPN-oplossing afleiden, wordt de VPN-capaciteit vrij voor bedrijfskritisch verkeer dat er nog steeds van afhankelijk is. Het moet er ook voor zorgen dat er in veel gevallen geen lange en dure upgradeprogramma's meer nodig zijn om deze nieuwe manier van werken aan te kunnen.

![Split Tunnel VPN-configuratiedetails](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_Afbeelding 3: Een VPN-oplossing voor gesplitste tunnel met gedefinieerde Office 365-uitzonderingen die rechtstreeks naar de service worden verzonden. Al het andere verkeer wordt teruggeplaatst naar het bedrijfsnetwerk, ongeacht de bestemming._

Vanuit beveiligingsperspectief beschikt Microsoft over een reeks beveiligingsfuncties die kunnen worden gebruikt om vergelijkbare of zelfs verbeterde beveiliging te bieden dan die welke worden geleverd door inline-inspectie door on-premises beveiligingsstacks. Het blogbericht van het Microsoft Security-team Alternatieve manieren voor beveiligingsprofessionals en IT om moderne beveiligingsbesturingselementen te bereiken in de unieke [scenario's](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) voor extern werk van vandaag, bevat een duidelijke samenvatting van de beschikbare functies en in dit artikel vindt u meer gedetailleerde richtlijnen. U kunt ook lezen over microsofts implementatie van VPN split tunneling bij [Running on VPN:](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)How Microsoft is keeping its remote workforce connected .

In veel gevallen kan deze implementatie binnen een paar uur worden uitgevoerd, waardoor een snelle oplossing kan worden bereikt voor een van de meest urgente problemen waarmee organisaties worden geconfronteerd wanneer ze snel over schakelen naar op grote schaal werken op afstand. Zie VPN split tunneling implementeren [voor Office 365](microsoft-365-vpn-implement-split-tunnel.md)voor richtlijnen voor implementatie van VPN-gesplitste tunnel.

## <a name="related-topics"></a>Verwante onderwerpen

[Vpn-splits tunneling implementeren voor Office 365](microsoft-365-vpn-implement-split-tunnel.md)

[Office 365 performance optimization for China users](microsoft-365-networking-china.md)

[Alternatieve manieren voor beveiligingsprofessionals en IT om moderne beveiligingsbesturingselementen te bereiken in de unieke scenario's voor extern werk van vandaag (Microsoft Security Team-blog)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[De PRESTATIES van VPN bij Microsoft verbeteren: Vpn-profielen van Windows 10 gebruiken om automatische verbindingen toe te staan](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Werken met VPN: hoe Microsoft zijn externe werknemers verbonden houdt](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Beginselen voor Office 365-netwerkverbinding](microsoft-365-network-connectivity-principles.md)

[Office 365-netwerkverbinding beoordelen](assessing-network-connectivity.md)

[Microsoft 365-connectiviteitstest](https://aka.ms/netonboard)