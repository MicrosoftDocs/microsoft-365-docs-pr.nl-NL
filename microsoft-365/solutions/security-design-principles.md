---
title: Beveiliging hindernissen u varen over - One architect's viewpoint
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
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: cdb6b557bf2f46a2338d929547167cf89a048695
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522274"
---
# <a name="security-hurdles-you-can-sail-over--one-architects-viewpoint"></a>Beveiliging hindernissen u varen over - One architect's viewpoint

In dit artikel beschrijft [Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/), Cybersecurity Architect bij Microsoft, de belangrijkste beveiligingsuitdagingen die ze tegenkomt bij bedrijfsorganisaties en beveelt ze benaderingen aan om over deze hindernissen te varen. 

## <a name="about-the-author"></a>Over de auteur

![Foto Kozeta Garrett](../media/solutions-architecture-center/kozeta-garrett-security.jpg) 

In mijn rol als Cloud Security Architect heb ik met meerdere organisaties samengewerkt om strategische en technische richtlijnen te bieden die gericht zijn op het ontwerpen en implementeren van beveiligingsarchitectuur voor klanten die migreren naar Microsoft 365 en Azure, het ontwikkelen van enterprise security-oplossingen en het helpen transformeren van beveiligingsarchitectuur en -cultuur voor bedrijfsweerbaarheid. Mijn ervaring omvat incidentdetectie en -respons, malware-analyse, penetratietests en het aanbevelen van verbeteringen aan de IT-beveiliging en defensiehouding. Ik ben zeer gepassioneerd over toonaangevende transformaties die resulteren in veiligheid als enabler voor het bedrijf, inclusief moderniseringsinspanningen.

Het is zeer bevredigend om te zien hoe organisaties die een security modernisering mentaliteit aangenomen in de afgelopen paar jaar zijn in een geweldige positie die hen in staat stelt om op afstand te blijven werken op een veilige manier, ondanks de recente COVID-19 situatie. Helaas hebben deze omstandigheden ook gediend als een wake-up call voor sommige klanten, die niet klaar waren voor deze onmiddellijke behoefte. Veel organisaties realiseren zich dat ze snel moeten moderniseren, hun geaccumuleerde IT-beveiligingsschuld moeten stoppen en hun beveiligingshouding 's nachts moeten verbeteren, zodat ze in deze uiterst ongebruikelijke omstandigheden kunnen werken.

Het goede nieuws is dat Microsoft een aantal geweldige bronnen heeft samengesteld om organisaties te helpen hun beveiligingshouding snel op te voeren. Naast deze middelen, wil ik de belangrijkste uitdagingen die ik dagelijks met klanten ben tegengekomen delen in de hoop dat u over deze hindernissen varen.

Ik woon momenteel in Noord-Virginia, dicht bij de hoofdstad van ons land, Washington DC. Ik hou van zowat elke vorm van outdoor activiteiten en lichaamsbeweging, zoals hardlopen, fietsen, wandelen en zwemmen. Om deze tegen te gaan geniet ik net zo veel koken, gastronomisch eten en reizen. 


## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Werk samen met het Security-team vanaf het begin van cloudadoptie

Om te beginnen kan ik niet genoeg benadrukken hoe belangrijk het is voor teams in uw organisatie om vanaf het begin te coördineren. Beveiligingsteams moeten worden omarmd als kritieke partners in de vroege stadia van cloudadoptie en -ontwerp. Dit betekent dat beveiligingsteams aan boord moeten worden om cloudadoptie te bevorderen, niet alleen voor de toegevoegde mogelijkheden voor het bedrijf (zoals een geweldige gebruikerservaring van veilige mobiele apparaten, volledige functionaliteitstoepassingen of het creëren van waarde op bedrijfsgegevens buiten de beperkte functionaliteitse-mail- en productiviteitstoepassingen), maar ook om gebruik te maken van de opslag-, AI- en computeranalysemogelijkheden die helpen bij het oplossen van nieuwe en oude beveiligingsuitdagingen. Beveiligingsteams moeten worden betrokken bij het beheer van alle aspecten van deze verschuiving, inclusief mensen (cultuur), processen (training) en technologie om succesvol te zijn. Het betekent ook investeren in de modernisering en continue verbetering van het Security Operations Center (SOC). Werk samen om uw beveiligingsstrategie af te stemmen op uw bedrijfsstrategie en omgevingstrends om ervoor te zorgen dat de digitale transformatie veilig wordt uitgevoerd. Wanneer dit goed gebeurt, ontwikkelen organisaties de mogelijkheid om zich sneller aan te passen aan veranderingen, waaronder wijzigingen in het bedrijf, IT en beveiliging. 

Waar ik klanten het meest over hindernissen zie struikelen is wanneer er geen echt partnerschap is tussen de activiteiten en de SOC-teams. Terwijl het operationele team onder druk wordt gezet en een opdracht krijgt met strakke deadlines om de cloud over te nemen, worden de beveiligingsteams niet altijd vroeg in het proces opgenomen om een uitgebreide beveiligingsstrategie te herzien en te plannen. Dit houdt in dat verschillende cloudcomponenten en componenten on-prem moeten worden geïntegreerd. Dit gebrek aan partnerschap sijpelt verder neer op verschillende teams die lijken te werken in silo's om controles voor hun specifieke componenten te implementeren, wat leidt tot de extra complexiteit van implementatie, probleemoplossing en integratie.

Klanten die over deze hindernissen varen, hebben goede partnerschappen tussen de Operations en Governance en de Security and Risk management teams om de beveiligingsstrategie en vereisten voor het beschermen van hybride cloudworkloads te vernieuwen. Ze richten zich op de uiteindelijke beveiligingsdoelen en -resultaten - gegevensbescherming en beschikbaarheid van systemen en services in overeenstemming met vereisten voor cybersecuritybeheer, risico's en naleving. Deze organisaties ontwikkelen vroege partnerschappen tussen hun Operations and Governance-team en SOC, wat van cruciaal belang is voor de security design-aanpak en de waarde van hun investeringen zal maximaliseren. 

## <a name="build-a-modern-identity-based-security-perimeter"></a>Bouw een moderne (identiteitsgebaseerde) beveiligingsperimeter

Neem vervolgens een Zero Trust-architectuurbenadering aan. Dit begint met het bouwen van een moderne, op identiteit gebaseerde veiligheidsperimeter. Ontwerp de beveiligingsarchitectuur waarin elke toegangspoging, of het nu on-prem of cloud is, wordt behandeld als niet-vertrouwd totdat deze is geverifieerd - 'vertrouw nooit, controleer altijd'. Deze ontwerpbenadering verhoogt niet alleen de beveiliging en productiviteit, maar stelt gebruikers ook in staat om overal met elk apparaattype te werken. De geavanceerde cloudbesturingselementen die bij Microsoft 365 zijn inbegrepen, helpen u de identiteit van gebruikers te beschermen en tegelijkertijd de toegang tot waardevolle bronnen te beheren op basis van het risiconiveau van gebruikers.

Zie [Configuraties voor identiteits- en apparaattoegang voor](../enterprise/microsoft-365-policies-configurations.md)een aanbevolen configuratie. 

## <a name="transition-security-controls-to-the-cloud"></a>Beveiligingsbesturingselementen naar de cloud overgezet

Veel beveiligingsteams gebruiken nog steeds de traditionele best practices voor beveiliging die zijn gebouwd voor een hele on-premises wereld, waaronder het onderhouden van een "netwerk perimeter security" en het proberen om de on-prem beveiligingstools en -besturingselementen te "forceren" naar cloudoplossingen. Dergelijke controles zijn niet ontworpen voor de cloud, zijn niet effectief en belemmeren de adoptie van moderne cloudmogelijkheden. Processen en tools die werken voor een netwerk perimeter security aanpak hebben bewezen inefficiënt te zijn, belemmerend voor cloud mogelijkheden, en niet mogelijk om te profiteren van moderne en geautomatiseerde beveiligingsfuncties.

U over deze hindernis varen door de defensiestrategieën te verschuiven naar cloud-managed bescherming, geautomatiseerd onderzoek en herstel, geautomatiseerde pentests, geavanceerde bedreigingsbescherming en incidentanalyse. Klanten die moderne oplossingen voor apparaatbeheer gebruiken, hebben geautomatiseerd beheer, gestandaardiseerde patching, antivirus, beleidshandhaving en toepassingsbescherming geïmplementeerd op alle apparaten (of het nu gaat om een smartphone, personal computer, laptop of tablet). Hierdoor is er geen VPN, Microsoft System Center Configuration Manager (SCCM) en active directory-groepsbeleid nodig. Dit, in combinatie met beleid voor voorwaardelijke toegang, biedt krachtige controle en zichtbaarheid, evenals gestroomlijnde toegang tot bronnen, ongeacht waar hun gebruikers vandaan komen.

## <a name="strive-for-best-together-security-tools"></a>Streven naar 'best together' beveiligingstools

Een andere hindernis die ik zie klanten struikelen over is het nemen van een 'best of breed' benadering van beveiligingstools. Voortdurend gelaagdheid 'best of breed' punt oplossingen om te voldoen aan opkomende beveiligingsbehoeften zorgt ervoor dat enterprise security uitsplitsing. Zelfs met de beste bedoelingen worden gereedschappen in de meeste omgevingen niet geïntegreerd omdat het te duur en complex wordt. Dit creëert op zijn beurt hiaten in de zichtbaarheid omdat er meer waarschuwingen zijn voor triage dan het team aankan. Het omscholen van het SecOps-team op nieuwe tools wordt ook een constante uitdaging.

De 'simple is better'-aanpak werkt ook voor de veiligheid. In plaats van achter 'best of breed' tools aan te gaan, zeil je over deze horde door een 'best together'-strategie aan te nemen met tools die standaard samenwerken. Microsoft-beveiligingsmogelijkheden beschermen uw hele organisatie met geïntegreerde bedreigingsbeveiliging die toepassingen, gebruikers en clouds omvat. Integratie stelt een organisatie in staat om veerkrachtiger te zijn en risico's te verminderen door aanvallers bij binnenkomst te bevatten en aanvallen snel te herstellen.

## <a name="balance-security-with-functionality"></a>Beveiliging in balans brengen met functionaliteit

Aangezien ik uit een lange cybersecurity achtergrond en ervaring kom, heb ik de neiging om de voorkeur te geven aan het beginnen met de meest veilige configuratie out of the box en organisaties in staat te stellen beveiligingsconfiguraties te ontspannen op basis van hun operationele en beveiligingsbehoeften. Dit kan echter komen op een forse prijs van verloren functionaliteit en een slechte gebruikerservaring. Zoals veel organisaties hebben geleerd, als beveiliging te moeilijk is voor gebruikers, zullen ze een manier vinden om om je heen te werken, inclusief het gebruik van onbeheerde cloudservices. Hoe moeilijk het ook voor mij is om te accepteren, ik ben me gaan realiseren dat de delicate functionaliteit-security balans moet worden bereikt.

Organisaties die zich realiseren dat gebruikers alles zullen doen wat nodig is om hun werk gedaan te krijgen, erkennen dat de "Shadow IT-strijd" het niet waard is om te vechten. Ze erkennen dat IT-medewerkers de grootste overtreders zijn als het gaat om Shadow IT en het gebruik van niet-goedgekeurde SaaS-toepassingen voor hun werk. Ze hebben hun strategie verschoven om het gebruik ervan aan te moedigen (in plaats van te onderdrukken) en zich te concentreren op het beperken van de risico's blootstelling die het zou kunnen creëren. De beveiligingsteams van deze organisatie dringen er niet op aan dat alles wordt geblokkeerd, geregistreerd en verzonden via een omgekeerde proxy of een VPN. Integendeel, deze beveiligingsteams verdubbelen hun inspanningen om waardevolle en gevoelige gegevens te beschermen tegen blootstelling aan de verkeerde partijen of kwaadaardige apps. Ze werken om de integriteit van de gegevens te beschermen. Ze maken volledig gebruik van meer geavanceerde mogelijkheden voor cloudinformatiebescherming, waaronder versleuteling, veilige multi-factor authenticatie, geautomatiseerde risico's en naleving, en Casb-mogelijkheden (Cloud App Security Broker) en stimuleren tegelijkertijd het beveiligde delen op meerdere platforms. Ze maken van schaduw-IT inspirerende creativiteit, productiviteit en samenwerking, waardoor hun bedrijf aan de concurrentiepositie kan blijven.


## <a name="adopt-a-methodical-approach"></a>Een methodische aanpak 

De meeste uitdagingen die ik heb ondervonden met het implementeren van cloudbeveiliging bij verschillende organisaties, ongeacht de industrie, zijn zeer vergelijkbaar. Allereerst, hoewel er veel geweldige documentatie over specifieke mogelijkheden en functies, is er een niveau van verwarring op het niveau van de organisatie over wat op hen van toepassing is, waar beveiligingsfuncties overlappen, en hoe mogelijkheden moeten worden geïntegreerd. Er is ook een mate van onzekerheid over welke beveiligingsfuncties vooraf zijn geconfigureerd uit de doos en die configuratie door de organisatie vereisen. Bovendien hebben de SOC-teams helaas niet de volledige exposure, training of de budgettoewijzing gehad die nodig is om zich voor te bereiden op de snelle cloudadoptie en digitale transformatie die hun organisaties al ondergaan.

Om u te helpen deze hindernissen te nemen, heeft Microsoft verschillende bronnen samengesteld die zijn ontworpen om u te helpen een methodische benadering van uw beveiligingsstrategie en -implementatie te volgen. 


|Resource   |Meer informatie  |
|---------|---------|
|[Belangrijkste taken voor beveiligingsteams om het thuiswerken te ondersteunen](../security/top-security-tasks-for-remote-work.md)      | Als u merkt dat u plotseling ondersteuning van een meestal werk-at-home personeel, dit artikel helpt u opvoeren beveiliging snel. Het bevat de belangrijkste aanbevolen taken op basis van uw licentieplan.    |
|[Microsoft 365 Security for Business Decisions Makers](../security/Microsoft-365-security-for-bdm.md)    | Wanneer u tijd hebt voor een uitgebreider plan, bevat dit artikel aanbevelingen die Microsoft 365 omvatten, met een prioriteit op het oppervlak van de aanval. Het wordt zelfs geleverd met een spreadsheet die u gebruiken om te sorteren op licenties en het gebied (zoals identiteit, bedreigingsbescherming en monitoring).  |
|[Aanbevelingen voor Microsoft-beveiligingsarchitectuur](https://docs.microsoft.com/security/compass/compass)    | Als u een beveiligingsarchitect bent, moet u beveiligingsaanbevelingen zien die zijn georganiseerd op discipline, waaronder identiteits-, netwerk- en beveiligingsactiviteiten.   |
|[Aanbevelingen voor Microsoft Security Operations](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|Meer informatie over Microsoft-aanbevelingen voor het instellen en uitvoeren van een Beveiligings operations center (SOC) |
|[Chief Information Security Officer (CISO) Workshop Training](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | Als je nieuw bent in cloudbeveiliging, mis dan deze reeks video's niet.        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | Technische richtlijnen van heel Microsoft voor beveiligingsstrategie en -architectuur.        |
| | |

Al deze resources zijn ontworpen om te worden gebruikt als uitgangspunt en aangepast aan de behoeften van uw organisatie. 

