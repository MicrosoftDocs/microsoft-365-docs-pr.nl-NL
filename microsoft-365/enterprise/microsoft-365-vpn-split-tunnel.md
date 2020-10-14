---
title: 'Overzicht: gesplitste tunneling via VPN met Office 365'
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
description: Richtlijnen voor het gebruik van gesplitste VPN-tunneling met Office 365 om de connectiviteit van Office 365 voor externe gebruikers te optimaliseren.
ms.openlocfilehash: 103a5cc36c9e981ccef5717971e32330078ed721
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456385"
---
# <a name="optimize-office-365-connectivity-for-remote-users-using-vpn-split-tunneling"></a>Office 365-connectiviteit optimaliseren voor externe gebruikers met VPN-split-tunneling
<!---
>[!NOTE]
>This topic is part of a set of topics that address Office 365 optimization for remote users.
>- For VPN split tunnel implementation guidance, see [Implementing VPN split tunneling for Office 365](microsoft-365-vpn-implement-split-tunnel.md).
>- For information about optimizing Office 365 worldwide tenant performance for users in China, see [Office 365 performance optimization for China users](microsoft-365-networking-china.md).
-->

Voor klanten die hun externe werk apparaten verbinden met het bedrijfsnetwerk of de Cloud infrastructuur via VPN, raden Microsoft aan dat de belangrijkste Office 365-scenario's **Microsoft teams**, **SharePoint Online** en **Exchange Online** worden gerouteerd via een _VPN-Splits tunnel_ configuratie. Dit wordt vooral van belang als de eerste regel strategie, zodat u de productiviteit van de werknemers in grote hoeveelheden werk vergemakkelijkt tijdens grootschalige activiteiten van COVID-19-crisis.

![VPN-configuratie voor gesplitste tunnel](../media/vpn-split-tunneling/vpn-model-2.png)

_Afbeelding 1: een gesplitste VPN-oplossing met gedefinieerde Office 365-uitzonderingen die rechtstreeks naar de service zijn verzonden. Alle andere verkeer naar de VPN-tunnel, ongeacht de bestemming._

De essentie van deze methode is het opzetten van een eenvoudige methode voor ondernemingen om het risico van verzadiging van de VPN-infrastructuur te beperken en de prestaties van Office 365 aanzienlijk te verbeteren. Als VPN-clients worden geconfigureerd zodat het meest kritieke, hoge volume Office 365-verkeer om de VPN-tunnel over te slaan de volgende voordelen opleveren:

- Dit beperkt de hoofdoorzaak van een meerderheid van de door de klant gerapporteerde prestaties en problemen met de netwerkcapaciteit in Enterprise VPN-architecturen die invloed hebben op de gebruikerservaring van Office 365
  
  De aanbevolen oplossing is speciaal bedoeld voor Office 365-service-eindpunten die zijn gecategoriseerd als **geoptimaliseerd** in het onderwerp [Office 365-url's en IP-](https://aka.ms/o365ips)adresbereiken. Het verkeer naar deze eindpunten is zeer gevoelig voor latentie en bandbreedte, en zodat het niet mogelijk is om de eindgebruikers ervaring te verbeteren en de bedrijfsnetwerk te verkleinen. Office 365-verbindingen die niet het grootste deel van de bandbreedte of het footprint van gebruikerservaring vormen, kunnen nog steeds worden gerouteerd via de VPN-tunnel, samen met de rest van het Internet-netwerkverkeer. Zie [de strategieën voor gesplitste tunnels voor VPN-verbinding](#the-vpn-split-tunnel-strategy)voor meer informatie.

- Kan met klanten snel worden geconfigureerd, getest en geïmplementeerd, en zonder extra infrastructuur of toepassingsvereisten

  Afhankelijk van het VPN-platform en de netwerkarchitectuur kan implementatie slechts enkele uren duren. Zie voor meer informatie [VPN-Splits tunnel implementeren](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling).

- Behoudt de beveiligings Posture van klant VPN-implementaties door niet de manier te wijzigen waarop andere verbindingen worden gerouteerd, waaronder verkeer naar Internet.

  Met de aanbevolen configuratie wordt het **minimale bevoegdheids** beginsel gevolgd voor uitzonderingen op VPN-verkeer en kunnen klanten gesplitste tunnel VPN implementeren zonder dat ze gebruikers of infrastructuur te zien krijgen voor extra beveiligingsrisico's. Netwerkverkeer dat rechtstreeks naar Office 365-eindpunten is gerouteerd, is versleuteld, gevalideerd voor integriteit door Office-clienttoepassingen stapels en beperkt tot IP-adressen die zijn gekoppeld aan Office 365-services die worden verholpen op het niveau van de toepassing en het netwerk. Zie voor meer informatie [alternatieve manieren voor beveiliging en een nieuwe manier om te profiteren van de moderne beveiligingsfuncties in de unieke extern werk van vandaag (Microsoft Security team-blog)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

- Wordt native ondersteund door de meeste bedrijfs VPN-platforms

  Microsoft blijft samenwerken met partners die commerciële VPN-oplossingen produceren, zodat partners gerichte richtlijnen en configuratiesjablonen kunnen ontwikkelen voor hun oplossingen op basis van de bovenstaande aanbevelingen. Ga voor meer informatie naar [handleidingen voor veelgebruikte VPN-platforms](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms).

>[!TIP]
>Microsoft raadt aan om gesplitste tunnel VPN-configuraties te benoemen aan gedocumenteerde specifieke IP-bereiken voor Office 365-Services Gesplitste, gesplitste tunnel configuraties op basis van een FQDN-verbinding en mogelijk conflicterende de belangrijkste Office 365-scenario's en een conflict met IP-routeringsregels op basis van een AppID. Daarom adviseren Microsoft de FQDN van Office 365 niet te gebruiken om de gesplitste tunnel VPN te configureren. Het gebruik van FQDN-configuratie kan handig zijn in andere gerelateerde scenario's, zoals het aanpassen van het PAC-bestand of voor het implementeren van proxy bypas.

Zie voor meer informatie over de implementatie van een [VPN-gesplitste tunneling voor Office 365](microsoft-365-vpn-implement-split-tunnel.md).

## <a name="the-vpn-split-tunnel-strategy"></a>Strategie voor gesplitste VPN-tunnel

Traditionele bedrijfsnetwerken zijn vaak bedoeld om veilig te werken voor een oudere wereld waarbij de belangrijkste gegevens, services en toepassingen worden gehost en rechtstreeks verbonden zijn met het interne bedrijfsnetwerk, zoals het merendeel van de gebruikers. Daarom is de netwerkinfrastructuur rondom deze elementen op die filialen verbonden met het hoofdkantoor via _Multiprotocol Label Switching (MPLS)-_ netwerken en moeten externe gebruikers verbinding maken met het bedrijfsnetwerk via een VPN voor toegang tot de on-premises eindpunten en Internet. In dit model worden alle verkeer van externe gebruikers doorgestuurd naar het bedrijfsnetwerk en wordt de cloudservice via een gebruikelijk uitgangspunt gerouteerd.

![Geforceerde VPN-configuratie](../media/vpn-split-tunneling/vpn-model-1.png)

_Afbeelding 2: een veelvoorkomende VPN-oplossing voor externe gebruikers waarbij alle verkeer wordt afgedwongen in het bedrijfsnetwerk, ongeacht de bestemming_

Aangezien organisaties gegevens en toepassingen verplaatsen naar de Cloud, is dit model minder effectief, omdat het snel en kostbaar van invloed is op de prestaties van het netwerk en de efficiëntie van gebruikers en de mogelijkheid van de organisatie de mogelijkheid te bieden om wijzigingen aan te brengen in het wijzigen van behoeften. Diverse Microsoft-klanten hebben gerapporteerd dat een paar jaar geleden 80% van het netwerkverkeer tot een interne bestemming bevonden, maar in 2020 80% Plus van het verkeer maakt verbinding met een externe Cloud op basis van een resource.

Dit probleem is door de COVID-19 crisis verergert om direct oplossingen te bieden voor de grote meerderheid van de organisaties. Veel klanten hebben vastgesteld dat het geforceerde VPN-model niet schaalbaar is en onvoldoende presteert voor 100% Remote werk scenario's, zoals voor zover deze crisis is vereist. Snelle oplossingen zijn vereist voor deze organisatie om efficiënt te blijven werken.

Voor de Office 365-service is Microsoft de connectiviteits vereisten voor de service met dit probleem in gedachten veranderd, waarbij een gerichte, nauw beheerste en relatief vaste reeks service-eindpunten zeer eenvoudig en snel kunnen worden geoptimaliseerd, zodat gebruikers hoge prestaties kunnen bieden voor het openen van de service en de belasting van de VPN-infrastructuur kunnen reduceren, zodat deze kan worden gebruikt door verkeer waarvoor

In Office 365 worden de vereiste eindpunten voor Office 365 in drie categorieën ingedeeld: **optimaliseren**, **toestaan**en **standaard**. Eindpunten **optimaliseren** onze focus hier en heeft de volgende kenmerken:

- Microsoft bezit en beheerde eindpunten, gehost op Microsoft-infrastructuur
- Specifiek zijn voor kern werk365kosten belastingen van Office, zoals Exchange Online, SharePoint Online, Skype voor bedrijven online en Microsoft teams
- Gebiedt IPs
- Lage veranderings kosten en ze worden naar behoren genummerd (momenteel 20 IP-subnetten)
- Een hoog volume en/of een gevoelige latentie
- Kan de vereiste beveiligingselementen in de service niet gebruiken in plaats van in de regel op het netwerk.
- Account rondom 70-80% van het volume verkeer naar de Office 365-service

Deze straks ingestelde serie eindpunten kunnen in de geforceerde VPN-tunnel worden opgesplitst en veilig en rechtstreeks naar de Office 365-service verzonden via de lokale interface van de gebruiker. Dit is een zogenaamde **gesplitste tunneling**.

Beveiligingselementen zoals DLP, beveiliging tegen AV, authenticatie en toegangsbeheer kunnen allemaal veel efficiënter voor deze eindpunten op verschillende lagen binnen de service worden geleverd. Aangezien we de bulk van het verkeersvolume van de VPN-oplossing van de VPN-oplossing verder aanleidingen, dan wordt er nu de VPN-capaciteit vrijgemaakt voor kritieke activiteiten van het bedrijf, wat er nog steeds wordt gebruikgemaakt. Het is ook mogelijk om in veel gevallen de noodzaak te verwijderen om een lang en kosten upgradeprogramma te doorlopen, zodat deze nieuwe manier van werken kan worden verwerkt.

![Details van gesplitste tunnel VPN-configuratie](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_Afbeelding 3: een gesplitste VPN-oplossing met gedefinieerde Office 365-uitzonderingen die rechtstreeks naar de service zijn verzonden. Alle andere verkeer wordt in het bedrijfsnetwerk geforceerd weergeven, ongeacht de bestemming._

Vanuit een beveiligings perspectief heeft Microsoft een reeks beveiligingsfuncties die kan worden gebruikt om vergelijkbaar te zijn, of zelfs een verbeterde beveiliging te leveren dan de inline-inspectie door on-premises beveiligings stacks te bezorgen. De blogberichten van het Microsoft-beveiligingsteam [en de IT-medewerkers voor een modernere beveiligings regeling in de unieke functies voor extern bewerken van vandaag](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) is een duidelijk overzicht van de beschikbare functies en u vindt meer gedetailleerde informatie in dit artikel. U kunt ook lezen over de implementatie van de VPN-splitsing van Microsoft aan de slag [op een VPN-verbinding](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv).

In veel gevallen kan deze implementatie in enkele gevallen worden verwezenlijkt, zodat een van de meest waarschijnlijke problemen met organisaties snel op de hoogte wordt gesteld als ze snel op de volledige schaal werken. Zie voor de implementatie van een VPN-gesplitste tunnel [in Office 365](microsoft-365-vpn-implement-split-tunnel.md).

## <a name="related-topics"></a>Verwante onderwerpen

[Gesplitste VPN-tunneling implementeren voor Office 365](microsoft-365-vpn-implement-split-tunnel.md)

[Prestaties van Office 365 optimaliseren voor gebruikers van China](microsoft-365-networking-china.md)

[Andere manieren voor beveiliging en een nieuwe manier om te profiteren van de moderne beveiligingsfuncties in de unieke, externe werk scenario's van vandaag (blog van Microsoft Security team)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[VPN-prestaties verbeteren bij Microsoft: met Windows 10 VPN-profielen voor het toestaan van automatische verbindingen](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Uitvoeren op VPN: hoe Microsoft de werknemers op afstand houdt](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Beginselen voor Office 365-netwerkverbinding](microsoft-365-network-connectivity-principles.md)

[Office 365-netwerkverbinding beoordelen](assessing-network-connectivity.md)

[Microsoft 365-connectiviteitstest](https://aka.ms/netonboard)
