---
title: Microsoft 365 Enterprise resourceplanning - Architectuur voor cyberbeveiliging
description: Meer informatie over het oplossen van beveiligingsuitdagingen in de Microsoft Enterprise-architectuur van Kozeta Garrett, Cyberbeveiligingsarchitect bij Microsoft.
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
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: 7cd9098766024093a0b9fa2d6e95131bf13d09df
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052480"
---
# <a name="security-hurdles-you-can-sail-overone-architects-viewpoint"></a>Obstakels voor beveiliging die u kunt overvaren: het gezichtspunt van een architect

In dit artikel beschrijft [Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/), Cyberbeveiligingsarchitect bij Microsoft, de belangrijkste beveiligingsuitdagingen die ze ondervindt bij ondernemingsorganisaties en worden benaderingen aanbevolen voor het overlopen van deze obstakels.

## <a name="about-the-author"></a>Over de auteur

![Foto Kozeta Garrett](../media/solutions-architecture-center/kozeta-garrett-security.jpg)

In mijn rol als cloudbeveiligingsarchitect heb ik samen met meerdere organisaties strategische en technische richtlijnen voor het ontwerpen en implementeren van beveiligingsarchitectuur voor klanten die migreren naar Microsoft 365 en Azure, het ontwikkelen van beveiligingsoplossingen voor ondernemingen en het helpen transformeren van beveiligingsarchitectuur en -cultuur voor bedrijfsweerbaarheid. Mijn ervaring omvat incidentdetectie en -reactie, malwareanalyse, penetratietests en het aanbevelen van verbeteringen in de IT-beveiliging en verdedigingshouding. Ik ben erg enthousiast over het leiden van transformaties die resulteren in beveiliging als een enabler voor het bedrijf, inclusief de inspanningen voor de modernisatie.

Het was het meest bevredigend om te zien hoe organisaties die de afgelopen jaren een beveiligingsmoderisatie hebben toegepast, zich in een geweldige positie kunnen plaatsen waardoor ze op een veilige manier op afstand kunnen blijven werken, ondanks de recente COVID-19-situatie. Helaas zijn deze omstandigheden ook een wake-up call voor sommige klanten, die niet klaar waren voor deze onmiddellijke behoefte. Veel organisaties realiseren zich dat ze snel moeten moderniseren, hun geaccumuleerde IT-beveiligingsschuld moeten ingetrokken en hun beveiligingspositie 's nachts moeten verbeteren, zodat ze in deze zeer ongebruikelijke omstandigheden kunnen werken.

Het goede nieuws is dat Microsoft een aantal geweldige bronnen heeft samengesteld om organisaties te helpen hun beveiligingsbeleid snel te verbeteren. Naast deze bronnen wil ik graag de belangrijkste uitdagingen delen die ik dagelijks met klanten heb ondervonden in de hoop dat u deze obstakels kunt overvaren.

Ik woon momenteel in Noord-Virginia, vlakbij de hoofdstad van ons land, Washington DC. Ik houd van bijna elke vorm van buitenactiviteiten en -oefeningen, zoals hardlopen, fietsen, wandelen en zwemmen. Om deze tegen te gaan, geniet ik van net zo veel eten, lekker eten en reizen.

## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Partner met het beveiligingsteam vanaf het begin van de acceptatie van de cloud

Om te beginnen kan ik niet genoeg benadrukken hoe belangrijk het is dat teams in uw organisatie vanaf het begin coördineren. Beveiligingsteams moeten worden omarmd als kritieke partners in de beginfase van de acceptatie en het ontwerp van de cloud. Dit betekent dat beveiligingsteams aan boord moeten worden gestuurd om de acceptatie van de cloud te ondersteunen, niet alleen voor de toegevoegde mogelijkheden voor het bedrijf (zoals een geweldige gebruikerservaring van veilige mobiele apparaten, toepassingen met volledige functionaliteit of het creëren van waarde voor bedrijfsgegevens buiten de beperkte functionaliteit voor e-mail- en productiviteitstoepassingen), maar ook om gebruik te maken van de mogelijkheden voor opslag, AI en computeranalyse waarmee nieuwe en oude beveiligingsuitdagingen kunnen worden opgelost. Beveiligingsteams moeten worden opgenomen in het beheren van alle aspecten van deze dienst, inclusief personen (cultuur), processen (training) en technologie om succesvol te zijn. Dit betekent ook dat u moet investeren in de modernisering en continue verbetering van het Security Operations Center (SOC). Werk samen om uw beveiligingsstrategie af te stemmen op uw bedrijfsstrategie en omgevingstrends om ervoor te zorgen dat de digitale transformatie veilig wordt uitgevoerd. Wanneer dit goed wordt gedaan, ontwikkelen organisaties de mogelijkheid om zich sneller aan te passen aan wijzigingen, waaronder wijzigingen in het bedrijf, IT en beveiliging.

Waar ik klanten het meest over obstakels zie struikel, is wanneer er geen echte samenwerking is tussen de activiteiten en de SOC-teams. Hoewel het operationele team onder druk wordt gezet en met strakke deadlines wordt verplicht om de cloud te gebruiken, worden de beveiligingsteams niet altijd vroeg in het proces opgenomen om een uitgebreide beveiligingsstrategie te herzien en te plannen. Hierbij worden verschillende cloudonderdelen en onderdelen on-prem geïntegreerd. Dit gebrek aan partnerschap leidt verder tot verschillende teams die in silo's lijken te werken om besturingselementen voor hun specifieke onderdelen te implementeren, wat leidt tot de extra complexiteit van implementatie, probleemoplossing en integratie.

Klanten die deze obstakels doorzeilen, hebben goede samenwerkingen tussen de teams Operations en Governance en beveiligings- en risicobeheer om de beveiligingsstrategie en vereisten voor het beschermen van hybride cloudbelastingen te vernieuwen. Ze richten zich op de uiteindelijke beveiligingsdoelen en -resultaten: gegevensbescherming en beschikbaarheid van systemen en services in overeenstemming met de vereisten voor beheer, risico's en naleving van cyberbeveiliging. Deze organisaties ontwikkelen samenwerkingen in een vroeg stadium tussen hun Operations and Governance-team en SOC, wat essentieel is voor de beveiligingsontwerpbenadering en de waarde van hun investeringen zal maximaliseren.

## <a name="build-a-modern-identity-based-security-perimeter"></a>Een moderne beveiligingsperimeter (op identiteit gebaseerde) bouwen

Gebruik vervolgens een Zero Trust-architectuurbenadering. Dit begint met het bouwen van een moderne, op identiteit gebaseerde beveiligingsperimeter. Ontwerp de beveiligingsarchitectuur waarin elke toegangspoging, ongeacht of deze on-prem of cloud is, wordt beschouwd als niet-vertrouwd totdat deze is geverifieerd, 'nooit vertrouwen, altijd verifiëren'. Deze ontwerpbenadering verhoogt niet alleen de beveiliging en productiviteit, maar stelt gebruikers ook in staat om overal met elk apparaattype te werken. De geavanceerde cloudbesturingselementen die Microsoft 365 helpen u de identiteit van gebruikers te beschermen en tegelijkertijd de toegang tot waardevolle resources te beheren op basis van het risiconiveau van de gebruiker.

Zie Identiteits- en [apparaattoegangsconfiguraties](../security/defender-365-security/microsoft-365-policies-configurations.md)voor een aanbevolen configuratie.

## <a name="transition-security-controls-to-the-cloud"></a>Beveiligingsbesturingselementen overstappen naar de cloud

Veel beveiligingsteams gebruiken nog steeds de traditionele beveiligings best practices die zijn ontwikkeld voor een on-premises wereld, waaronder het onderhouden van een 'netwerkperimeterbeveiliging' en het proberen om de on-prem-beveiligingshulpmiddelen en -besturingselementen te 'dwingen' tot cloudoplossingen. Dergelijke besturingselementen zijn niet ontworpen voor de cloud, zijn niet effectief en belemmeren de acceptatie van moderne cloudmogelijkheden. Processen en hulpprogramma's die werken voor een netwerkperimeterbeveiligingsbenadering, zijn inefficiënt, belemmerend voor cloudfuncties en maken het niet mogelijk om te profiteren van moderne en geautomatiseerde beveiligingsfuncties.

U kunt deze drempel overlopen door de defensiestrategieën te verplaatsen naar door de cloud beheerde beveiliging, geautomatiseerd onderzoek en herstel, geautomatiseerde pentests, Defender voor Office 365 en incidentanalyse. Klanten die moderne oplossingen voor apparaatbeheer gebruiken, hebben geautomatiseerd beheer, gestandaardiseerde patching, antivirus, beleidshandhaving en toepassingsbeveiliging geïmplementeerd op alle apparaten (of het nu om een smartphone, pc, laptop of tablet gaat). Hierdoor hoeft u geen VPN-, Microsoft-System Center Configuration Manager (SCCM) en Active Directory-groepsbeleid te gebruiken. Dit, gecombineerd met beleid voor voorwaardelijke toegang, biedt krachtige controle en zichtbaarheid, evenals gestroomlijnde toegang tot resources, ongeacht waar hun gebruikers vandaan werken.

## <a name="strive-for-best-together-security-tools"></a>Streven naar 'best together' beveiligingshulpmiddelen

Een andere obstakel waar ik klanten over zie struikelen, is het kiezen van een 'best of breed' benadering van beveiligingshulpmiddelen. Door voortdurend 'best of breed' point-oplossingen te lagen om te voldoen aan nieuwe beveiligingsbehoeften, wordt de beveiliging van het bedrijf afbreekt. Zelfs met de beste bedoelingen worden hulpmiddelen in de meeste omgevingen niet geïntegreerd omdat deze te duur en complex worden. Dit zorgt op zijn beurt voor hiaten in de zichtbaarheid, omdat er meer waarschuwingen voor triage zijn dan het team kan verwerken. Het secops-team opnieuw trainen op nieuwe hulpprogramma's wordt ook een constante uitdaging.

De 'eenvoudige is betere' benadering werkt ook voor beveiliging. In plaats van achter 'best of breed'-hulpmiddelen aan te gaan, gaat u over deze drempel door een 'best together'-strategie te volgen met hulpmiddelen die standaard samenwerken. Microsoft-beveiligingsfuncties beschermen uw hele organisatie met geïntegreerde bedreigingsbeveiliging die zich over toepassingen, gebruikers en clouds bespant. Integratie stelt een organisatie in staat om veerkrachtiger te zijn en het risico te beperken door aanvallers bij de invoer te bevatten en snel aanvallen te herstellen.

## <a name="balance-security-with-functionality"></a>Beveiliging in balans brengen met functionaliteit

Aangezien ik afkomstig ben van een lange achtergrond en ervaring op het gebied van cyberbeveiliging, heb ik de neiging om te beginnen met de meest veilige configuratie en organisaties in staat te stellen beveiligingsconfiguraties te ontspannen op basis van hun operationele en beveiligingsbehoeften. Dit kan echter een forse prijs zijn voor verloren functionaliteit en slechte gebruikerservaring. Veel organisaties hebben geleerd dat als beveiliging te moeilijk is voor gebruikers, ze een manier vinden om om u heen te werken, inclusief het gebruik van niet-verantwoordelijke cloudservices. Hoe moeilijk het voor mij ook is om te accepteren, ik ben me gaan realiseren dat het delicate evenwicht tussen functionaliteit en beveiliging moet worden bereikt.

Organisaties die zich realiseren dat gebruikers alles doen wat nodig is om hun werk te doen, erkennen dat de 'Shadow IT-strijd' niet de moeite waard is om te vechten. Ze erkennen dat IT-werknemers de grootste overtreders zijn als het gaat om Schaduw-IT en het gebruik van niet-goedgekeurde SaaS-toepassingen voor hun werk. Ze hebben hun strategie verschoven om het gebruik ervan aan te moedigen (in plaats van te onderdrukken) en zich te richten op het beperken van de risico's die het kan maken. De beveiligingsteams van deze organisatie willen niet dat alles wordt geblokkeerd, geregistreerd en verzonden via een reverse proxy of een VPN. In plaats daarvan verdubbelen deze beveiligingsteams hun inspanningen om te beschermen dat waardevolle en gevoelige gegevens niet worden blootgesteld aan de verkeerde partijen of schadelijke apps. Ze werken om de integriteit van de gegevens te beschermen. Ze maken volledig gebruik van de geavanceerdere mogelijkheden voor beveiliging van cloudgegevens, zoals versleuteling, veilige meervoudige verificatie, geautomatiseerde risico's en naleving, en Cloud App Security De mogelijkheden van Makelaar (CASB) terwijl ze het beveiligde delen op meerdere platforms toestaan en zelfs aanmoedigen. Ze veranderen schaduw-IT in inspirerende creativiteit, productiviteit en samenwerking, waardoor hun bedrijf op de concurrentiepositie kan blijven.

## <a name="adopt-a-methodical-approach"></a>Een methodische benadering gebruiken

De meeste uitdagingen die ik heb ondervonden met het implementeren van cloudbeveiliging bij verschillende organisaties, ongeacht de industrie, lijken sterk op elkaar. In de eerste plaats is er voldoende documentatie over specifieke mogelijkheden en functies, maar er bestaat verwarring op organisatieniveau over wat er op hen van toepassing is, waar beveiligingsfuncties elkaar overlappen en hoe mogelijkheden moeten worden geïntegreerd. Er is ook een mate van onzekerheid over welke beveiligingsfuncties vooraf zijn geconfigureerd en waarvoor configuratie door de organisatie is vereist. Daarnaast hebben de SOC-teams helaas niet de volledige blootstelling, training of de budgettoewijzing gehad die nodig is om zich voor te bereiden op de snelle acceptatie van de cloud en de digitale transformatie die hun organisaties al ondergaan.

Om u te helpen deze obstakels op te helderen, heeft Microsoft verschillende resources samengesteld die zijn ontworpen om u te helpen een methodische benadering van uw beveiligingsstrategie en implementatie te volgen.

|Resource   |Meer informatie  |
|---------|---------|
|[Belangrijkste taken voor beveiligingsteams om het thuiswerken te ondersteunen](../security/top-security-tasks-for-remote-work.md)      | Als u plotseling een voornamelijk thuiswerker ondersteunt, kunt u in dit artikel de beveiliging snel verbeteren. Het bevat de aanbevolen taken op basis van uw licentieplan.    |
|[Microsoft 365 Makers van beveiligingsbeslissingen voor bedrijven](../security/Microsoft-365-security-for-bdm.md)    | Wanneer u tijd hebt voor een uitgebreider plan, bevat dit artikel aanbevelingen die Microsoft 365, die zijn geprioriteerd door het oppervlak van de aanval. Het wordt zelfs geleverd met een spreadsheet die u kunt gebruiken om te sorteren op licenties en gebied (zoals identiteit, bedreigingsbeveiliging en monitoring).  |
|[Aanbevelingen voor microsoft-beveiligingsarchitectuur](/security/compass/compass)    | Als u een beveiligingsarchitect bent, moet u beveiligingsaanbevelingen zien die zijn georganiseerd op discipline, zoals identiteit, netwerken en beveiligingsbewerkingen.   |
|[Aanbevelingen voor Microsoft Security Operations](/security/compass/security-operations-videos-and-decks)|Microsoft-aanbevelingen voor het instellen en uitvoeren van een soc (Security Operations Center) |
|[Workshoptraining voor Ciso (Chief Information Security Officer)](/security/ciso-workshop/ciso-workshop)   | Als cloudbeveiliging nieuw voor u is, hoeft u deze reeks video's niet te missen.        |
|[docs.security.com/security](/security/)    | Technische richtlijnen van microsoft voor beveiligingsstrategie en -architectuur.        |
| | |

Al deze resources zijn ontworpen om te worden gebruikt als uitgangspunt en aangepast aan de behoeften van uw organisatie.