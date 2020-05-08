---
title: Veiligheidshindernissen waar u over varen - Het gezichtspunt van één architect
description: Beschrijving.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: eb8019efb13a13b27a67d541ae69ca6f30b35ed0
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160049"
---
# <a name="security-hurdles-you-can-sail-over--one-architects-viewpoint"></a>Veiligheidshindernissen waar u over varen - Het gezichtspunt van één architect

In dit artikel beschrijft [Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/), Cybersecurity Architect bij Microsoft, de belangrijkste beveiligingsuitdagingen die ze tegenkomt bij bedrijfsorganisaties en beveelt benaderingen aan voor het varen over deze hindernissen. 

## <a name="about-the-author"></a>Over de auteur

![Foto Kozeta Garrett](../media/solutions-architecture-center/kozeta-garrett-security.jpg) 

In mijn rol als Cloud Security Architect heb ik met meerdere organisaties samengewerkt om strategische en technische richtlijnen te bieden die zich richten op het ontwerpen en implementeren van beveiligingsarchitectuur voor klanten die migreren naar Microsoft 365 en Azure, het ontwikkelen van bedrijfsbeveiligingsoplossingen en het helpen transformeren van beveiligingsarchitectuur en -cultuur voor bedrijfsveerkracht. Mijn ervaring omvat incident detectie en reactie, malware analyse, penetratie testen, en het aanbevelen van verbeteringen aan DE-beveiliging en defensie houding. Ik ben zeer gepassioneerd over het leiden van transformaties die resulteren in veiligheid als een enabler voor het bedrijf, met inbegrip van modernisering inspanningen.

Het is het meest bevredigend om te zien hoe organisaties die een security modernisering mentaliteit aangenomen in de afgelopen paar jaar zijn in een geweldige positie die hen in staat stelt om op afstand te blijven werken op een veilige manier, ondanks de recente COVID-19 situatie. Helaas hebben deze omstandigheden ook gediend als een wake-up call voor sommige klanten, die niet klaar waren voor deze onmiddellijke behoefte. Veel organisaties realiseren zich dat ze snel moeten moderniseren, hun opgebouwde IT-beveiligingsschuld moeten terugtrekken en hun beveiligingshouding moeten verbeteren, zodat ze in deze uiterst ongebruikelijke omstandigheden kunnen werken.

Het goede nieuws is Microsoft heeft samengesteld een aantal grote middelen om organisaties te helpen snel opvoeren van hun veiligheid houding. Naast deze middelen wil ik de grootste uitdagingen die ik dagelijks met klanten heb ondervonden delen in de hoop dat je over deze hindernissen varen.

Ik woon momenteel in Noord-Virginia, dicht bij de hoofdstad van ons land, Washington DC. Ik hou van zowat elke vorm van outdoor activiteiten en lichaamsbeweging, zoals hardlopen, fietsen, wandelen en zwemmen. Om deze tegen te gaan geniet ik net zoveel van koken, gastronomisch eten en reizen. 


## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Samenwerken met het securityteam vanaf het begin van cloudadoptie

Om te beginnen kan ik niet genoeg benadrukken hoe belangrijk het is voor teams in uw organisatie om vanaf het begin te coördineren. Beveiligingsteams moeten worden omarmd als kritieke partners in de vroege stadia van cloudadoptie en -ontwerp. Dit betekent dat beveiligingsteams aan boord komen om cloudadoptie te verdedigen, niet alleen voor de toegevoegde mogelijkheden voor het bedrijf (zoals een geweldige gebruikerservaring van veilige mobiele apparaten, volledige functionaliteitstoepassingen of het creëren van waarde op bedrijfsgegevens buiten de beperkte functionaliteit e-mail- en productiviteitstoepassingen), maar ook om gebruik te maken van de mogelijkheden voor opslag, AI en computeranalyse die helpen bij het oplossen van nieuwe en oude beveiligingsuitdagingen. Beveiligingsteams moeten worden betrokken bij het beheer van alle aspecten van deze verschuiving, inclusief mensen (cultuur), processen (training) en technologie om succesvol te zijn. Het betekent ook investeren in de modernisering en continue verbetering van het Security Operations Center (SOC). Werk samen om uw beveiligingsstrategie af te stemmen op uw bedrijfsstrategie en omgevingstrends om ervoor te zorgen dat de digitale transformatie veilig wordt uitgevoerd. Wanneer dit goed wordt gedaan, ontwikkelen organisaties de mogelijkheid om zich sneller aan te passen aan veranderingen, waaronder wijzigingen in het bedrijf, IT en beveiliging. 

Waar ik klanten het meest over hindernissen zie struikelen is wanneer er geen echt partnerschap is tussen de operaties en de SOC-teams. Terwijl het operationele team onder druk wordt gezet en een mandaat heeft met strakke deadlines om de cloud over te nemen, worden de beveiligingsteams niet altijd vroeg in het proces opgenomen om een uitgebreide beveiligingsstrategie te herzien en te plannen. Dit omvat de integratie van verschillende cloudcomponenten en componenten on-prem. Dit gebrek aan partnerschap sijpelt verder door naar verschillende teams die in silo's lijken te werken om besturingselementen voor hun specifieke componenten te implementeren, wat leidt tot de extra complexiteit van implementatie, probleemoplossing en integratie.

Klanten die over deze hindernissen varen, hebben goede partnerschappen tussen de teams Operations and Governance en de security- en risicomanagementteams om de beveiligingsstrategie en -vereisten voor de bescherming van hybride cloudworkloads te vernieuwen. Ze richten zich op de ultieme beveiligingsdoelstellingen en -resultaten - gegevensbescherming en beschikbaarheid van systemen en services in overeenstemming met cyberbeveiligingsgovernance, risico's en nalevingsvereisten. Deze organisaties ontwikkelen vroege partnerschappen tussen hun Operations and Governance-team en SOC, wat essentieel is voor de security design aanpak en de waarde van hun investeringen zal maximaliseren. 

## <a name="build-a-modern-identity-based-security-perimeter"></a>Bouw een moderne (identiteitsgebaseerde) beveiligingsperimeter

Kies vervolgens voor een Zero Trust-architectuurbenadering. Dit begint met het bouwen van een moderne, op identiteit gebaseerde beveiligingsperimeter. Ontwerp de beveiligingsarchitectuur waarbij elke toegangspoging, of het nu on-prem of cloud is, wordt behandeld als niet-vertrouwd totdat deze is geverifieerd - 'nooit vertrouwen, altijd verifiëren'. Deze ontwerpbenadering verhoogt niet alleen de beveiliging en productiviteit, maar stelt gebruikers ook in staat om overal met elk apparaattype te werken. De geavanceerde cloudbesturingselementen die bij Microsoft 365 zijn inbegrepen, helpen u de identiteit van gebruikers te beschermen en tegelijkertijd de toegang tot waardevolle bronnen te beheren op basis van het risiconiveau van de gebruiker.

Zie [Identiteit en apparaattoegangsconfiguraties](../enterprise/microsoft-365-policies-configurations.md)voor een aanbevolen configuratie. 

## <a name="transition-security-controls-to-the-cloud"></a>Beveiligingsbesturingselementen overschakelen naar de cloud

Veel beveiligingsteams gebruiken nog steeds de traditionele beveiligingsbestpractices die zijn gebouwd voor een on-premises wereld, waaronder het onderhouden van een "netwerkperimeterbeveiliging" en het "forceren" van de on-prem-beveiligingstools en -besturingselementen voor cloudoplossingen. Dergelijke besturingselementen zijn niet ontworpen voor de cloud, zijn niet effectief en belemmeren de acceptatie van moderne cloudmogelijkheden. Processen en tools die werken voor een netwerkperimeterbeveiligingsaanpak hebben bewezen inefficiënt te zijn, de cloudmogelijkheden belemmerend en maken het niet mogelijk om te profiteren van moderne en geautomatiseerde beveiligingsfuncties.

U over deze hindernis varen door de verdedigingsstrategieën te verschuiven naar cloudbeheerbeveiliging, geautomatiseerd onderzoek en herstel, geautomatiseerde pentests, geavanceerde bescherming van bedreigingen en incidentanalyse. Klanten die moderne oplossingen voor apparaatbeheer gebruiken, hebben geautomatiseerd beheer, gestandaardiseerde patching, antivirus, beleidshandhaving en toepassingsbescherming geïmplementeerd op alle apparaten (of het nu een smartphone, personal computer, laptop of tablet is). Hierdoor hoeven u geen VPN- of Microsoft System Center Configuration Manager (SCCM) en active directory-groepsbeleid meer te gebruiken. Dit, in combinatie met beleid voor voorwaardelijke toegang, biedt krachtige controle en zichtbaarheid, evenals gestroomlijnde toegang tot bronnen, ongeacht waar hun gebruikers vandaan opereren.

## <a name="strive-for-best-together-security-tools"></a>Streven naar 'best together' security tools

Een andere hindernis die ik zie klanten struikelen over is het nemen van een 'best of breed' benadering van security tools. Voortdurend gelaagdheid 'best of breed' punt oplossingen om opkomende beveiligingsbehoeften aan te pakken zorgt ervoor dat enterprise security tot afbraak. Zelfs met de beste bedoelingen worden gereedschappen in de meeste omgevingen niet geïntegreerd omdat het te duur en complex wordt. Dit creëert op zijn beurt hiaten in de zichtbaarheid omdat er meer waarschuwingen zijn voor triage dan het team aankan. Het omscholen van het SecOps-team op nieuwe tools wordt ook een constante uitdaging.

De 'simple is better'-aanpak werkt ook voor de veiligheid. In plaats van achter 'best of breed' tools aan te gaan, vaar je over deze hindernis door een 'best together' strategie aan te nemen met tools die standaard samenwerken. Microsoft-beveiligingsmogelijkheden beschermen uw hele organisatie met geïntegreerde bescherming tegen bedreigingen die toepassingen, gebruikers en clouds omvat. Integratie stelt een organisatie in staat om veerkrachtiger te zijn en risico's te verminderen door aanvallers bij binnenkomst en snel te herstellen aanvallen.

## <a name="balance-security-with-functionality"></a>Beveiliging in balans brengen met functionaliteit

Als ik kom uit een lange cybersecurity achtergrond en ervaring, heb ik de neiging om te beginnen met de meest veilige configuratie out of the box en waardoor organisaties om beveiligingsconfiguraties te ontspannen op basis van hun operationele en beveiligingsbehoeften. Echter, dit kan komen op een forse prijs van verloren functionaliteit en slechte gebruikerservaring. Zoals veel organisaties hebben geleerd, als beveiliging te moeilijk is voor gebruikers, zullen ze een manier vinden om om u heen te werken, inclusief het gebruik van onbeheerde cloudservices. Hoe moeilijk het ook is voor mij om te accepteren, ik ben tot het besef gekomen dat de delicate functionaliteit-security balans moet worden bereikt.

Organisaties die zich realiseren dat gebruikers zullen doen wat nodig is om hun werk gedaan te krijgen erkennen dat de "Shadow IT-strijd" is niet de moeite waard vechten. Zij erkennen dat IT-medewerkers de grootste overtreders zijn als het gaat om Shadow IT en het gebruik van niet-goedgekeurde SaaS-toepassingen voor hun werk. Ze hebben hun strategie verschoven om het gebruik ervan aan te moedigen (in plaats van te onderdrukken) en zich te concentreren op het beperken van de risico's die het zou kunnen creëren. De beveiligingsteams van deze organisatie staan er niet op dat alles wordt geblokkeerd, geregistreerd en verzonden via een omgekeerde proxy of een VPN. Integendeel, deze beveiligingsteams verdubbelen hun inspanningen om waardevolle en gevoelige gegevens te beschermen tegen blootstelling aan de verkeerde partijen of kwaadaardige apps. Ze werken aan de bescherming van de integriteit van de gegevens. Ze maken volledig gebruik van geavanceerdere mogelijkheden voor cloudinformatiebescherming, waaronder versleuteling, veilige multi-factor authenticatie, geautomatiseerde risico's en naleving, en Cloud App Security Broker (CASB) mogelijkheden, terwijl het mogelijk maken en zelfs stimuleren van het beveiligde delen op meerdere platforms. Ze maken van schaduw-IT inspirerende creativiteit, productiviteit en samenwerking, waardoor hun bedrijf op het concurrentievoordeel blijft.


## <a name="adopt-a-methodical-approach"></a>Een methodische aanpak hanteren 

De meeste uitdagingen die ik heb ervaren met het implementeren van cloudbeveiliging bij verschillende organisaties, ongeacht de industrie, zijn zeer vergelijkbaar. Allereerst, terwijl er veel geweldige documentatie over specifieke mogelijkheden en functies, is er een niveau van verwarring op het niveau van de organisatie over wat op hen van toepassing is, waar beveiligingsfuncties overlappen, en hoe mogelijkheden moeten worden geïntegreerd. Er is ook een mate van onzekerheid over welke beveiligingsfuncties uit de doos vooraf zijn geconfigureerd en die configuratie door de organisatie vereisen. Bovendien hebben de SOC-teams helaas niet de volledige blootstelling, training of de budgettoewijzing gehad die nodig is om zich voor te bereiden op de snelle cloudadoptie en digitale transformatie die hun organisaties al ondergaan.

Om u te helpen deze hindernissen te nemen, heeft Microsoft verschillende bronnen samengesteld die zijn ontworpen om u te helpen een methodische benadering van uw beveiligingsstrategie en -implementatie te volgen. 


|Resource   |Meer informatie  |
|---------|---------|
|[Belangrijkste taken voor beveiligingsteams ter ondersteuning van thuiswerken](../security/top-security-tasks-for-remote-work.md)      | Als je merkt dat je plotseling de ondersteuning van een meestal werk-at-home personeel, dit artikel helpt u opvoeren beveiliging snel. Het bevat top aanbevolen taken op basis van uw licentieplan.    |
|[Microsoft 365 Security for Business Beslissers](../security/Microsoft-365-security-for-bdm.md)    | Wanneer u tijd hebt voor een uitgebreider plan, bevat dit artikel aanbevelingen die betrekking hebben op Microsoft 365, geprioriteerd door aanvalsoppervlak. Het wordt zelfs geleverd met een spreadsheet die u gebruiken om te sorteren op licenties en gebied (zoals identiteit, bescherming van bedreigingen en monitoring).  |
|[Aanbevelingen voor Microsoft-beveiligingsarchitectuur](https://docs.microsoft.com/security/compass/compass)    | Als u een beveiligingsarchitect bent, moet u beveiligingsaanbevelingen zien die zijn georganiseerd op basis van discipline, waaronder identiteits-, netwerk- en beveiligingsbewerkingen.   |
|[Aanbevelingen voor Microsoft Security Operations](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|Microsoft-aanbevelingen voor het instellen en uitvoeren van een SOC voor beveiligingsoperaties |
|[Chief Information Security Officer (CISO) Workshop Training](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | Als je nieuw bent in cloudbeveiliging, mis dan deze serie video's niet.        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | Technische richtlijnen van heel Microsoft voor beveiligingsstrategie en -architectuur.        |
| | |

Al deze middelen zijn ontworpen om te worden gebruikt als uitgangspunt en aangepast aan de behoeften van uw organisatie. 

