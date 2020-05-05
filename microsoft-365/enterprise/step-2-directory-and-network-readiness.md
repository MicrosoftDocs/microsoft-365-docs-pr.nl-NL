---
title: 'Stap 2: gereedheid van directory en netwerk'
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Leer hoe u de gereedheid van directory en netwerken in de omgeving kunt beoordelen.
ms.openlocfilehash: b9b2ed38afd77a5dd487b7e319eeee5300a62a25
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011649"
---
# <a name="step-2-directory-and-network-readiness"></a>Stap 2: gereedheid van directory en netwerk

Zorg ervoor dat uw directory en het netwerk zijn geconfigureerd en klaar zijn om uw overstap naar Windows 10 en Microsoft 365-apps voor ondernemingen te ondersteunen. Dit vereist dat Azure Active Directory Services zijn ingesteld voor gebruikers en moet uw netwerk de capaciteit hebben om zowel het reguliere verkeer als de verplaatsing van mogelijk grote hoeveelheden gegevens af te handelen wanneer pc's worden bijgewerkt en de bestanden, instellingen en applicaties van gebruikers worden hersteld.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><strong>Stap 2: gereedheid van directory en netwerk</strong></p>
<p>Voor cloud-verbonden services in Microsoft 365-apps voor ondernemingen en nieuwe implementatie-opties zoals Windows Autopilot is Azure Active Directory vereist. Uw netwerk en connectiviteit zijn ook belangrijke zaken om te plannen bij het verplaatsen van Windows-afbeeldingen, apps, stuurprogramma's en gerelateerde bestanden naar uw pc's. Lees hoe u met nieuwe hulpprogramma's en implementatieopties netwerkverkeer vermindert en stroomlijnt.</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Directory- en netwerkgereedheid is de tweede stap in het aanbevolen implementatieproces dat zich richt op Azure Active Directory en netwerkoptimalisatie. Ga naar het [Implementatiecentrum voor desktops](https://aka.ms/HowToShift) om het volledige desktop-implementatieproces te zien.
>

Directory- en netwerkgereedheid is van fundamenteel belang voor een vlotte implementatie van besturingssystemen en desktops. Zoals bij elke geautomatiseerde implementatie is het belangrijk om ervoor te zorgen dat uw bestandsshares kunnen worden bereikt en dat uw netwerk de overdracht van zeer grote bestanden, mogelijk naar honderden of zelfs duizenden pc's tegelijk, ondersteunt.

Met de overstap naar Windows 10 en Microsoft 365-apps voor ondernemingen moet u er ook voor zorgen dat de cloudgebaseerde identiteit is ingesteld met Azure Active Directory. Dit is niet alleen bedoeld voor het activeren van Microsoft 365-apps voor ondernemingen, het stelt u ook in staat te profiteren van moderne provisioning-oplossingen zoals Windows Autopilot.

In dit artikel vindt u informatie over de tools en opties om uw directoryservices en gebruikers- en apparaatrechten voor te bereiden, gereed voor implementatie in Windows 10 en Microsoft 365-apps voor ondernemingen.

## <a name="adding-azure-active-directory"></a>Azure Active Directory toevoegen

Als uw organisatie al Office 365, Exchange Online, Microsoft Intune of andere Microsoft Online-services gebruikt, is het goede nieuws dat u al Azure Active Directory gebruikt. Als dat het geval is hoeft u er alleen maar voor te zorgen dat de gebruikers waarvoor u een desktopimplementatie wilt uitvoeren, zich in uw Azure Active Directory bevinden en dat er licenties zijn toegewezen.

Als u momenteel Azure Active Directory niet gebruikt, zijn er [talloze bronnen](https://docs.microsoft.com/azure/active-directory/) om u te helpen bij het instellen ervan. U kunt in aanmerking komen voor persoonlijke hulp via Microsoft FastTrack, als onderdeel van uw licentie. U vindt [hier](https://fasttrack.microsoft.com) meer informatie over Microsoft FastTrack.

Zodra u Azure Active Directory hebt geïnstalleerd, kunnen uw gebruikers zich aanmelden en hun apps uit Microsoft 365-apps voor ondernemingen activeren. U kunt Microsoft Intune of Windows Autopilot-implementatie gebruiken voor de geautomatiseerde implementatie van apps en beleid.

## <a name="network-readiness"></a>Netwerkgereedheid

Bij het plannen van uw implementaties moet u rekening houden met de bandbreedtevereisten. Er zijn drie hoofdonderdelen in een implementatie die van invloed zijn op uw netwerk: pc-imaging, software-updates en gebruikerspersonalisatie. Samen kan dit meer dan 20 GB per pc betekenen voor de eerste migratie, en vaak 1 GB of meer per maand per pc om up-to-date te blijven.

Laten we eerst de vereisten van elk van deze drie hoofdonderdelen verkennen:

### <a name="pc-imaging"></a>PC-imaging

Voor Windows-afbeeldingen zonder aanpassingen moet u normaal gesproken 3 GB per pc plannen, terwijl u voor aangepaste afbeeldingen met apps mogelijk 6 GB of meer moet toestaan. Het is ook mogelijk dat u stuurprogrammapakketten moet overwegen. Deze kunnen enkele honderden megabytes per pc groot zijn, soms tot 1 GB.

### <a name="software-updates"></a>Software-updates

U moet de netwerkbandbreedte voor software-updates plannen. Windows 10 en Microsoft 365-apps voor ondernemingen gebruiken een nieuw servicemodel met maandelijkse en halfjaarlijkse updates. Als u nog niet eerder met dit model hebt gewerkt, kunt u [hier](https://docs.microsoft.com/windows/deployment/update/waas-overview) meer lezen over hoe dit werkt.

Het nieuwe servicemodel omvat tweemaal per jaar functie-updates voor Windows, Office halfjaarlijkse kanaalupdates en maandelijkse kwaliteitsupdates. Functie-updates zijn doorgaans 2-4 GB groot en Office halfjaarlijkse kanaalupdates zijn 300-400 MB per update. Dan zijn er de maandelijkse kwaliteitsupdates. Deze variëren van een paar honderd megabyte tot meer dan een gigabyte. Dit komt omdat maandelijkse updates cumulatief zijn, dus deze nemen in omvang toe gedurende de levensduur van elke Windows 10-versie. Dat gezegd hebbende, er zijn hulpprogramma‘s die kunnen helpen de hoeveelheid gegevens te verminderen die over het netwerk moeten gaan om updates te implementeren. Hieronder vindt u meer informatie hierover.

### <a name="user-personalization"></a>Gebruikerspersonalisatie

Het derde onderdeel dat moet worden overwogen, is de aanpassing aan de gebruiker. Hier moet u de netwerkbandbreedte plannen om het herstel van gebruikersbestanden, hun instellingen en hun toepassingen mogelijk te maken als onderdeel van het proces voor het vernieuwen of vervangen van de pc. Samen zijn deze items vaak groter dan 20 GB per pc; voor sommige gebruikers kunnen deze meer dan 100 GB bedragen.

## <a name="limiting-bandwidth"></a>Bandbreedtebeperking

Een manier om de impact van implementatie-gerelateerd verkeer op het netwerk te beperken, is door het te beperken met behulp van de BITS-instelling (Background Intelligent Transfer Service) op clients. BITS gebruikt een adaptieve bitsnelheid (ABR) om de bandbreedte voor implementatiedoeleinden aan te passen. De service kan met Groepsbeleid worden geconfigureerd op clients.

[Informatie over BITS](https://docs.microsoft.com/windows/desktop/bits/about-bits)

Als u Microsoft Endpoint Configuration Manager (huidige tak) gebruikt, kunt u ook BITS-compatibele distributiepunten configureren of multicast inschakelen met WDS.

Het beperken van specifiek verkeer betekent dat normaal netwerkverkeer minder wordt beïnvloed door pc's die updates en applicaties downloaden. Als u een bepaald percentage van de bandbreedte voor deze taken reserveert, zorgt u ervoor dat de productiviteit niet wordt beïnvloed door de implementatie van Windows of Office en dat processen blijven draaien zoals nodig. Het kan echter de implementatie-gerelateerde downtime verergeren, waarbij gebruikers hun pc's niet kunnen gebruiken terwijl een implementatie wordt uitgevoerd.

Gelukkig zijn er nieuwe hulpmiddelen waarmee u de netwerkimpact van een grootschalige desktopimplementatie gemakkelijker kunt beheren, waaronder LEDBAT om het gebruik van de beschikbare bandbreedte te optimaliseren, en peer-to-peer (P2P) -opties om het implementatieverkeer te verplaatsen van het midden van het netwerk naar de buitenrand

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-3.png)

## <a name="scavenging-bandwidth"></a>Bandbreedte opruimen

Latency-geoptimaliseerd achtergrondtransport (LEDBAT) wordt ondersteund in Windows Server 2019 en Microsoft Endpoint Configuration Manager (huidige tak) en is ontworpen om het netwerkverkeer naar Windows-clients te optimaliseren.

[Top 10 netwerkfuncties in Windows Server 2019:\# 9 LEDBAT - Latency-geoptimaliseerd achtergrondtransport](https://blogs.technet.microsoft.com/networking/2018/07/25/ledbat/)

In tegenstelling tot de traditionele manier van netwerkverkeer beperken, kan LEDBAT alle beschikbare netwerkbandbreedte inzetten als een achtergrondtaak, wat onmiddellijk bandbreedte oplevert wanneer ander verkeer daarom vraagt. In tegenstelling tot BITS is er geen vertraging. Alles is geautomatiseerd, er is geen handmatige afstemming of planning vereist, en alles wordt aan de serverzijde ingesteld. Dit biedt mogelijk aanzienlijke prestatieverbeteringen.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-4.png)

## <a name="peer-to-peer-options"></a>Opties voor peer-to-peer

Peer-to-peer-opties worden steeds vaker gebruikt bij migraties van Windows 10, voor pc-imaging, software-updates en gebruikersaanpassingen. Ze zijn ook handig bij het vergemakkelijken van build-to-build-upgrades na uw eerste implementatie van Windows 10. Hier vindt u een aantal voorbeelden die laten zien hoe Windows 10 en Office-gerelateerd verkeer weg kan worden geleid van het midden van het netwerk, waardoor de noodzaak van klassieke beperkingsbenaderingen wordt verminderd. PC's kunnen de updatebestanden vinden bij peers in hun lokale netwerk in plaats van ze te downloaden vanaf een distributiepunt of internet.

**BranchCache** kan u helpen bij het downloaden van inhoud in gedistribueerde omgevingen zonder het netwerk te verzadigen. Er zijn twee opties: gehoste cache modus, waarmee u lokale servers kunt gebruiken om inhoud te cachen, en gedistribueerde cache modus (een modus die wordt ondersteund in Configuration Manager), waarmee klanten reeds gedownloade inhoud met elkaar kunnen delen.

**Peer Cache** clients die door Configuration Manager worden ondersteund, kunnen ook gebruikmaken van Peer Cache. Hierdoor kunnen pc's die betrouwbaar beschikbaar zijn op het netwerk de bron vormen voor de distributie van inhoud. U wilt dit niet op al uw pc's inschakelen, gebruik alleen apparaten met betrouwbare netwerkverbindingen als hosts (bijv. bureaublad, mini-tower of tower-pc's). Peer Cache kan zelfs worden gebruikt voor implementatietaken die tijdens de installatie in Windows PE-fasen worden uitgevoerd.

Opmerking: BranchCache en Peer Cache zijn complementair en kunnen in dezelfde omgeving samenwerken.

[BranchCache vs. Peer Cache](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**Delivery Optimization** Delivery Optimization is een andere peer-to-peer cachetechnologie die netwerkgebaseerde controles biedt voor implementaties. Windows 10 Delivery Optimization om ingebouwde UWP-apps bij te werken, om applicaties uit de Microsoft Store te installeren en voor software-updates die Express Updates gebruiken. Deze is beschikbaar sinds eerdere versies van Windows 10, hoewel het pas onlangs is geïntegreerd met Microsoft Endpoint Configuration Manager (huidige tak). Vanaf Windows 10 versie 1803 kunt u met nieuwe configuratie-opties onafhankelijk bandbreedtelimieten instellen voor achtergrondupdates en voorgrondtaken, zoals een app-installatie vanuit de Store. Windows Delivery Optimization ondersteunt nu ook Microsoft 365-apps voor ondernemingen tijdens clientupdates, beschikbaar in alle ondersteunde updatekanalen voor clients. Ondersteuning voor Windows Delivery Optimization tijdens de eerste installatie van de client is binnenkort beschikbaar.  

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-5.png)

**Aanvullende overwegingen voor Microsoft 365-apps voor ondernemingen**

Naast het gebruik van Delivery Optimization, zijn hier drie items die u helpen uw netwerkbelasting te verminderen als gevolg van implementaties van Microsoft 365-apps voor ondernemingen.

**Binaire Delta-compressie** Microsoft 365-apps voor ondernemingen gebruikt Binaire Delta-compressie om de bandbreedte die wordt verbruikt door software-updates te verminderen bij het bijwerken van de meest recente versie van Microsoft 365-apps voor ondernemingen naar de volgende release. Door alleen de veranderingen op binair niveau op te halen uit de vorige versie, wordt de invloed van de cumulatieve updates geminimaliseerd. Dit kan elke maand honderden megabytes aan gegevens per pc besparen. Om deze functie te kunnen gebruiken, kunt u geen releases overslaan. Als u dat doet, moet de volledige cumulatieve update worden gedownload.

[Updates voor Microsoft 365-apps downloaden](https://docs.microsoft.com/deployoffice/overview-update-process-microsoft-365-apps#download-the-updates-for-microsoft-365-apps)

**Outlook-gegevensbestanden** Outlook is vaak geconfigureerd om het hele postvak van gebruikers lokaal in de cache op te slaan voor offline gebruik. In elke Windows-implementatie, behalve een interne upgrade, moeten de Outlook-gegevensbestanden van de gebruiker na de upgrade opnieuw worden opgebouwd. Dit is een geautomatiseerd proces, maar met Outlook-postvaklimieten die doorgaans zijn ingesteld op maximaal 100 GB, betekent het opnieuw lokaal cachen van het hele postvak voor alle gebruikers veel gegevensoverdracht. Om de netwerkbelasting te verminderen, kunt u overwegen groepsbeleid te gebruiken om de instelling 'Mail offline bewaren' te verlagen. In Microsoft 365-apps voor ondernemingen of Office 2016 is de standaardwaarde voor Outlook ingesteld op 12 maanden. Om de impact op het netwerk te verminderen, kunt u overwegen om de offlinecache in te stellen tussen 1 en 6 maanden. Het wijzigen van deze instelling heeft geen invloed op de grootte van het online postvak en het hele postvak kan nog steeds online worden doorzocht via Outlook.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-6.png)

**OneDrive Files on Demand en bekende map verplaatsen** OneDrive is een geweldige manier om gebruikersbestanden te synchroniseren en weg te houden van pc's en andere apparaten in de cloud. Met Bekende mapverplaatsing kunt u bestandssynchronisatie naar OneDrive afdwingen van de gebruikersmappen Bureaublad, Documenten en Afbeeldingen, zodat die bestanden beschikbaar zijn wanneer men zich aanmeldt bij een nieuw apparaat of een opnieuw ingerichte pc. Onthoud echter dat u, vanwege de enorme omvang en het aantal bestanden op de locaties Bureaublad, Documenten en Afbeeldingen, planmatig wilt zijn met de implementatie van beleid dat OneDrive op uw pc's inschakelt en afdwingt. Een optie is om de netwerkbesturingselementen voor groepsbeleid te gebruiken om de bandbreedte die door de OneDrive-synchronisatieservice wordt gebruikt, te beperken.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-7.png)

[Bekende map verplaatsen](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/Migrate-Your-Files-to-OneDrive-Easily-with-Known-Folder-Move/ba-p/207076)

[On-Demand OneDrive-bestanden](https://www.microsoft.com/microsoft-365/blog/2017/05/11/introducing-onedrive-files-on-demand-and-additional-features-making-it-easier-to-access-and-share-files/)

Als je OneDrive nog niet hebt geïmplementeerd, is de overstap van Windows 7 naar Windows 10 een perfecte gelegenheid om OneDrive in te schakelen en naadloos Microsoft 365-apps voor ondernemingen te integreren. U kunt overwegen om deze implementatie te starten terwijl u de apps en apparaten gereed maakt. Dit geeft bestandssynchronisatie een voorsprong voordat u begint met het verplaatsen van Windows-afbeeldingen en het implementeren van apps via uw netwerk.

## <a name="next-step"></a>Volgende stap 

## <a name="step-3-office-and-lob-app-delivery"></a>[Stap 3: levering van Office- en LOB-apps](https://aka.ms/mdd3)

## <a name="previous-step"></a>Vorige stap:

## <a name="step-1-device-and-app-readiness"></a>[Stap 1: gereedheid van apparaten en apps](https://aka.ms/mdd1)

## <a name="feedback"></a>Feedback

We zijn benieuwd naar uw feedback. Kies het type site dat u wilt bieden:

Productfeedback Meld u aan om documentatiefeedback te geven

Ons nieuwe feedbacksysteem is gebouwd op GitHub Issues. Lees meer over deze wijziging in ons blogbericht.
